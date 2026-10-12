# Skill: production-safety-policy

> **STATUS: PROPOSÉ — Review manuel Ivan requis avant déploiement**
> Source: Analyse Gemini vidéo IkaPHiMDazM (Hooks in Claude Code)
> Date proposition: 2026-10-12

## Description

Configure des hooks Claude Code pour protéger l'environnement de production : bloque les commandes destructives, protège les fichiers critiques, empêche les push forcés sur main.

## Use case Ivan

- Eviter de push --force sur la branche main de TempleTwins en production
- Bloquer `rm -rf` et `DROP TABLE` accidentels
- Protéger les fichiers `.env`, `config/secrets.yml`, tokens Shopify
- Log automatique de toutes les actions sensibles

## Déclenchement

```
/production-safety-policy --setup
```

Configure les hooks dans `.claude/settings.json` du projet actuel.

## Instructions

Tu es un expert Claude Code hooks. Quand invoqué avec `--setup` :

### 1. Analyse le projet
- Détecte le type (Shopify Liquid, Node.js, Python, etc.)
- Identifie les fichiers/dossiers sensibles (.env, config/, secrets/)
- Identifie les branches protégées (main, production, master)

### 2. Configure les hooks dans `.claude/settings.json`

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [{
          "type": "command",
          "command": "bash /home/user/.claude/hooks/check-dangerous-commands.sh",
          "onFailure": "block"
        }]
      }
    ],
    "PostToolUse": [
      {
        "matcher": "Edit|Write|MultiEdit",
        "hooks": [{
          "type": "command",
          "command": "bash /home/user/.claude/hooks/log-file-changes.sh"
        }]
      }
    ]
  }
}
```

### 3. Crée les scripts hooks

**check-dangerous-commands.sh** — bloque :
- `rm -rf /` ou `rm -rf *` hors /tmp
- `git push --force origin main`
- `DROP TABLE` ou `DELETE FROM` sans WHERE
- `git reset --hard` sans confirmation
- Toute commande ciblant `.env` ou `secrets/`

**log-file-changes.sh** — log dans `.claude/audit.log` :
- Date/heure, fichier modifié, taille avant/après

### 4. Rapport setup

```
HOOKS CONFIGURÉS: PreToolUse(Bash), PostToolUse(Edit|Write)
COMMANDES BLOQUÉES: 8
FICHIERS PROTÉGÉS: .env, config/secrets*, *.pem, *.key
BRANCHES PROTÉGÉES: main, production
LOG: .claude/audit.log
```

## Note importante

Ce skill modifie `.claude/settings.json`. Toujours vérifier avec `git diff` avant commit.
Le skill ne déploie JAMAIS les hooks automatiquement sans confirmation d'Ivan.
