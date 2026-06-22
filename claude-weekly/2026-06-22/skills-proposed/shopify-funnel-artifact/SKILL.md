---
name: shopify-funnel-artifact
version: 0.1.0
status: PROPOSED — review manuel Ivan requis avant déploiement
source_video: https://www.youtube.com/watch?v=m7TJqx8CYG8
source_date: 2026-06-18
proposed_by: veille-claude-weekly
proposed_date: 2026-06-22
---

# Skill : shopify-funnel-artifact

## Description
Analyse le tunnel de conversion d'un store Shopify et génère un artifact HTML interactif partageable avec visualisations, diagnostics et propositions d'A/B tests.

## Problème résolu pour Ivan
Ivan veut identifier rapidement où les visiteurs décrochent sur TempleTwins et PURESOLE (product page → add-to-cart → checkout → payment) sans passer par des outils analytics externes complexes. Le résultat doit être partageable avec des prestataires ou agences via un simple lien.

## Pattern inspiré de
La démo "Artifacts in Claude Code" (Anthropic, 18 juin 2026) qui montre :
1. Claude analyse des données de cohortes sur 90 jours
2. Identifie le point de friction principal (68% d'échec sur une étape)
3. Génère un rapport HTML interactif avec maquettes avant/après
4. Produit un lien `claude.ai/code/artifact/` partageable sans compte

## Workflow proposé

```markdown
# SKILL: shopify-funnel-artifact
# Analyse le funnel de conversion Shopify et génère un artifact partageable

## Usage
/shopify-funnel-artifact [store: templeTwins|puresole] [period: 7d|30d|90d]

## Steps

### 1. Collecte données
- Utiliser MCP Shopify (mcp__Shopify__run-analytics-query) pour extraire :
  - Sessions par page (product, cart, checkout, payment)
  - Taux d'abandon par étape
  - Comparaison par source de trafic (organic, paid, direct)

### 2. Analyse
Demander à Claude d'identifier :
- L'étape avec le plus fort taux de décrochage
- Les patterns par device (mobile vs desktop)
- Les produits/collections avec le meilleur/pire taux de conversion

### 3. Génération artifact
Claude génère un fichier HTML interactif contenant :
- Funnel visuel étape par étape
- Heatmap des dropoffs
- Top 3 hypothèses de cause
- Propositions d'A/B tests avec métriques cibles
- Maquettes avant/après pour les changements UI

### 4. Partage
L'artifact est accessible via claude.ai/code/artifact/ pour partage avec prestataires
```

## Commandes clés
```bash
# Extraire données analytics Shopify
mcp__Shopify__run-analytics-query --query "funnel_conversion" --period 30d

# Générer l'artifact
> Génère un rapport HTML interactif de conversion pour [store]. 
  Inclus : funnel par étape, comparaison mobile/desktop, top 3 hypothèses, 
  maquettes A/B. Format partageable via artifact Claude Code.
```

## Dépendances
- MCP Shopify (déjà configuré dans la session)
- Claude Code v2.1.178+ (pour la feature Artifacts)
- Accès analytics Shopify Admin API

## Notes
- NE PAS déployer automatiquement. Ivan doit valider les propositions A/B avant tout changement en prod.
- Adapter les queries ShopifyQL selon la structure exacte des stores.
