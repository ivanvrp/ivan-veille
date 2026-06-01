# Skill: shopify-ultracode-ops

## Description
Utilise Ultracode (effort xhigh + auto-orchestration Dynamic Workflows) combiné au Shopify MCP pour exécuter des opérations e-commerce à grande échelle sur TempleTwins et PURESOLE.

## Trigger
Quand Ivan mentionne une tâche Shopify répétitive, volumineuse, ou complexe : mise à jour catalogue, audit SKUs, refactor themes Liquid, synchronisation inventaire, bulk content generation.

## Prérequis
```bash
# Installer le Shopify MCP
claude mcp add --transport stdio shopify-dev-mcp -- npx -y @shopify/dev-mcp@latest
```

## Usage type
```
/effort xhigh
"[Tâche Shopify] : [description détaillée du besoin]"
```

## Exemples concrets
- "Met à jour toutes les descriptions produits PURESOLE avec les nouvelles guidelines SEO v2"
- "Audite les 300 SKUs TempleTwins et identifie ceux sans variant image"
- "Génère 50 titles et meta-descriptions pour les nouvelles collections streetwear"
- "Refactore le theme Liquid pour ajouter le composant loyalty points sur toutes les pages produit"

## Notes
- Dynamic Workflows disponible sur Max/Team (on par défaut) ou Pro (activer via /config)
- 16 agents concurrent max, 1000 total par run
- Source: Claude Code v2.1.154, mai 2026
- Proposé le 2026-06-01 | NON déployé, review Ivan requis
