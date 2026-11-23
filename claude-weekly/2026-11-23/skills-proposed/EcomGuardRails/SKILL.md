# Skill: EcomGuardRails

**Source** : Lydia Hallie – Rethinking Claude Code Best Practices (Anthropic, Nov 11 2026)  
**Vidéo** : https://www.youtube.com/watch?v=vlfCjWuv4es  
**Statut** : Proposé — À valider par Ivan avant déploiement

## Description
Génère automatiquement un fichier `settings.json` avec des règles `deny` adaptées à un projet Shopify/dropship. Protège contre les opérations dangereuses : git reset --hard, accès .env, modifications directes de thèmes sans backup, appels non autorisés aux API de paiement.

## Cas d'usage pour Ivan
- TempleTwins : empêcher Claude de modifier des fichiers de thème critiques sans confirmation
- PURESOLE : bloquer l'accès aux clés API dropship / fournisseurs
- Usage général : sandbox auto sur sessions cloud

## Pattern core
```json
{
  "permissions": {
    "deny": [
      "Bash(git reset --hard *)",
      "Read(./.env)",
      "Bash(rm -rf *)",
      "Write(config/secrets*)"
    ]
  },
  "sandbox": { "enabled": true }
}
```

## Instructions skill (ébauche)
1. Scanner le projet pour identifier les fichiers/dossiers sensibles
2. Générer les règles deny adaptées au type de projet (Shopify theme / dropship / Node.js)
3. Proposer la config settings.json à valider
4. Optionnel : activer le sandboxing pour les sessions cloud
