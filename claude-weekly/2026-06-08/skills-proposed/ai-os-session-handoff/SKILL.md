---
name: ai-os-session-handoff
trigger: /session-handoff
source_video: 0WDkwMxj13s (Nate Herk — Claude Opus 4.8 AI OS)
score_ivan: 8/10
status: PROPOSED — à reviewer manuellement avant déploiement
---

# Skill : Session Handoff

## Objectif

Génère un résumé structuré de la session Claude Code en cours (décisions prises, fichiers créés/modifiés, prochaines étapes, contexte clé). Utile pour continuer le lendemain ou handoff entre appareils.

## Usage

```
/session-handoff
```

Optionnel : `/session-handoff [projet: TempleTwins|PURESOLE|veille]`

## Output généré

```markdown
# Session Handoff — [DATE] [HEURE]

## Projet actif
[nom du projet]

## Ce qui a été fait
- [action 1]
- [action 2]

## Fichiers créés / modifiés
- path/to/file.md — [description 1 ligne]

## Décisions prises
- [décision importante avec rationale]

## Prochaines étapes
1. [next step 1] — priorité HAUTE
2. [next step 2]

## Contexte à retenir
[snippet ou info clé que Claude devra avoir au prochain /resume]

## Commande pour reprendre
`claude /resume [session-id si dispo]`
```

## Patterns clés (tiré de l'analyse Nate Herk)

- **"Default Shift"** : ouvrir AI OS en premier, pas le navigateur
- **Cadence** : le handoff crée une routine de fin de session → discipline d'AI OS
- Installer globalement (`~/.claude/skills/`) pour disponibilité cross-projet

## Variante : Auto-handoff via hook

```json
// .claude/settings.json
{
  "hooks": {
    "Stop": [
      {"command": "claude --print '/session-handoff' >> session-logs/$(date +%Y-%m-%d).md"}
    ]
  }
}
```

## À faire avant déploiement

- [ ] Tester sur une vraie session TempleTwins
- [ ] Ajuster le format output selon préférence Ivan
- [ ] Considérer auto-hook Stop si Claude Code 2.1.160+ (acceptEdits mode)
