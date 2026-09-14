# Skill : ecommerce-mcp-connector
**Source :** Analyse vidéo dbb1v7QKYBU (Claude Code MCP Full Tutorial)
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Objectif
Guide interactif pour connecter les APIs e-commerce populaires à Claude via MCP. Spécialement conçu pour non-développeurs et solo founders.

## Ce que fait le skill
1. Demande à Ivan quel outil connecter (Shopify / Klaviyo / GA4 / Meta Ads / autre)
2. Guide la récupération des credentials (liens directs vers les pages API du service)
3. Génère automatiquement la commande `claude mcp add` correcte
4. Lance la configuration et vérifie avec `/mcp` que le serveur est actif
5. Teste la connexion avec une requête simple

## Outils supportés
- **Shopify** : orders, products, customers, inventory
- **Klaviyo** : campaigns, flows, segments, metrics
- **Google Analytics 4** : sessions, events, conversions
- **Meta Ads** : campaigns, ad sets, spend, ROAS

## Usage
```
/ecommerce-mcp-connector
/ecommerce-mcp-connector shopify  # Direct pour Shopify
/ecommerce-mcp-connector --list   # Voir connecteurs configurés
```

## Valeur pour Ivan
Simplifie l'onboarding MCP à < 5 minutes par outil. Plus besoin de lire la documentation technique de chaque service.

## Notes implémentation
- Nécessite accès internet pour vérification URLs MCP
- Sauvegarde config dans `.claude/mcp-config.json` (git-ignored)
- Compatible Claude Code CLI et application desktop
