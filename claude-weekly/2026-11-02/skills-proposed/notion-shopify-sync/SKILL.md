---
name: notion-shopify-sync
description: Workflow fan-out Shopify → rapport local + page Notion pour review hebdo solo founder
triggers:
  - bilan hebdo
  - rapport ventes
  - sync notion
  - revue semaine
---

# Notion-Shopify Sync — Weekly Review

## Prérequis
- MCP filesystem connecté (dossier reports/)
- MCP Notion connecté (page "Weekly Reviews" dans workspace Ivan)

## Workflow
1. Lire les données fournies (ventes, commandes, best-sellers, stock)
2. Analyser : top produits, tendances, alertes stock
3. Sauvegarder rapport Markdown en local : reports/weekly-{date}.md
4. Créer page Notion "Weekly Review {date}" avec résumé structuré

## Format rapport
```markdown
# Weekly Review {date}
## 📊 Ventes
- Total : {amount}
- Top produit : {product}
## 🚨 Alertes
- Stock faible : {products}
## 💡 Action items
- {item 1}
```

## Notes
- Utilisable avec les données collées directement ou via MCP Shopify si connecté
- Fan-out : les 2 destinations se remplissent en 1 prompt
