# Skill : contextual-data-filter
**Source :** Analyse Gemini vidéo wSYqwfd5mV0 (Claude Code MCP Code Mode)  
**Proposé le :** 2026-11-16  
**Statut :** Proposition — review Ivan requis avant déploiement

## Objectif
Filtrer les données renvoyées par des appels d'outils (MCP, API) avant leur injection dans le contexte LLM de Claude Code. Évite le gonflement du contexte qui rend Claude "plus bête" et coûteux.

## Usage type pour Ivan
Interroger l'API Shopify ou un fournisseur dropshipping, puis ne conserver que les champs pertinents (prix, stock, SKU) avant que Claude traite la réponse.

## Exemple d'activation
```
/contextual-data-filter --keep "price,sku,inventory_quantity" --filter "inventory_quantity > 0"
```

## Implémentation suggérée
Se déclenche avec `CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1`. Claude génère un script JS qui appelle l'outil MCP, transforme les données avec les règles de filtrage spécifiées, et retourne uniquement les champs demandés.

## Économies estimées
-50% à -75% de tokens de messages sur les tâches API-intensive (selon les benchmarks de la vidéo).

## Prérequis
- Claude Code v2.1.323+
- `CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1`
- Node.js 22.13+ (si plugin MCP tiers)
