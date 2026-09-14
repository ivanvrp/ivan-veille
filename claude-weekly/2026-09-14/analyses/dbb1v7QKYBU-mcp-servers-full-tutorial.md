# Claude Code MCP | How to Add MCP Servers (2026) Full Tutorial
**URL:** https://www.youtube.com/watch?v=dbb1v7QKYBU
**Date:** ~Aug 2026 (1 mois)
**Score Ivan:** 9/10

## Résumé exécutif
Tutoriel pratique montrant comment ajouter des serveurs MCP à Claude via l'application desktop (GUI) ou via Claude Code CLI. Couvre les deux méthodes avec authentification OAuth. Directement applicable pour connecter Claude aux APIs Shopify, Klaviyo, Google Analytics.

## Concepts clés avec timestamps
- [00:08] Deux méthodes d'intégration : application desktop Claude (GUI) vs Claude Code (CLI)
- [00:23] GUI : bouton '+' → Connectors → Add custom connector
- [00:35] Champs requis : Name + Remote MCP server URL (OAuth Client ID/Secret optionnels)
- [01:46] Authentification : "Connect" depuis Manage connectors → page navigateur OAuth (ex: Google)
- [02:17] CLI : commande prête à l'emploi fournie par le service MCP
- [02:48] Vérifier serveurs MCP configurés : `/mcp` dans terminal Claude Code
- [02:55] Auth CLI : sélectionner serveur dans `/mcp` → Authenticate → page navigateur

## Code/prompts/commandes verbatim
```bash
# Ajouter serveur MCP via CLI (exemple nexlev)
claude mcp add -s user --transport http nexlev https://prod.dashboard.nexlev.io/api/claude-mcp

# Lister les serveurs MCP configurés dans Claude Code
/mcp
```

## Patterns réutilisables pour Ivan
- Connecter Claude à l'API Shopify pour récupération temps réel commandes/stocks/clients
- Intégrer Klaviyo (email marketing) pour analyser performances campagnes depuis Claude
- Connecter Google Analytics / Facebook Ads pour rapports marketing automatisés
- Tout outil avec API REST peut devenir un connecteur MCP personnalisé

## Skill_potential
**`/ecommerce-mcp-connector`** : Skill qui guide Ivan étape par étape pour connecter les APIs e-commerce populaires (Shopify, Klaviyo, GA4) — demande clés API et URLs, génère automatiquement la commande `claude mcp add` correcte. Simplifie l'onboarding MCP pour non-développeurs.

## Score utilité 0-10 pour Ivan
**9/10** — Compétence fondamentale pour transformer Claude d'assistant conversationnel en hub d'opérations interconnecté pour TempleTwins et PURESOLE. Méthode CLI particulièrement utile.
