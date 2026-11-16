# Skill : n8n-shopify-lifecycle
**Source :** Analyse Gemini vidéo WzZyRsYZeDQ (NEW n8n Skill for Claude Code!)  
**Proposé le :** 2026-11-16  
**Statut :** Proposition — review Ivan requis avant déploiement

## Objectif
Permettre à Claude Code de créer et gérer le cycle de vie complet des automatisations Shopify dans n8n par langage naturel : commandes, produits, clients, marketing, stock.

## Usage type pour Ivan (TempleTwins + PURESOLE)
- "Crée un workflow de suivi d'expédition Shopify → email client avec tracking"
- "Automatise la synchronisation stock fournisseur toutes les 4h"
- "Workflow marketing : clients >500€ → liste VIP Klaviyo"

## Implémentation suggérée
Extension du n8n skills officiel (`/plugin install n8n-skills@n8n-io`) avec des patterns Shopify-specifiques. Inclure les nœuds Shopify courants (orders, products, customers, inventory), les webhooks Shopify, et les mappings de données Shopify↔n8n.

## Installation (base officielle disponible)
```bash
/plugin marketplace add n8n-io/skills
/plugin install n8n-skills@n8n-io
claude mcp add --transport http <N8N_INSTANCE>/mcp-server/http \
  --header "Authorization: Bearer <TOKEN>"
```

## Prérequis
- n8n avec Instance-level MCP activé
- Claude Code 2.1.319+ (MCP tasks background)
- Connexion Shopify configurée dans n8n
