# suivi-perf-ecom

> Skill proposé le 2026-10-26 — à valider manuellement par Ivan avant déploiement.
> Source: analyse Gemini vidéo "Anthropic Just Released Claude DUET (Full Breakdown)" — youtube.com/watch?v=c3WW9bR4ejM

## Description

Génère un briefing quotidien/hebdomadaire des métriques clés des boutiques e-commerce (Shopify + PURESOLE). Consolide ventes, stock critique, cash flow et signale les anomalies.

## Usage

```
/perf-report [daily|weekly]
```

Nécessite : accès MCP Shopify configuré.

## Ce que ça fait

1. Récupère les ventes du jour / de la semaine via MCP Shopify
2. Identifie les produits en stock bas (seuil configurable)
3. Calcule le chiffre d'affaires vs objectif
4. Signale les anomalies (baisse >20% vs semaine précédente)
5. Retourne un rapport condensé en Markdown + 3 actions prioritaires

## Exemple de sortie

```
📊 PURESOLE — Semaine du 20-26 oct
Revenus : 3 240 € (+12% vs S-1)
Stock critique : Air Force 1 Noir (2 restants)
⚠️ Sneakers femme : -35% vs S-1 → vérifier pub Meta
Actions :
1. Réapprovisionner Air Force 1 Noir
2. Revoir l'audience pub sneakers femme
3. Lancer promo weekend sur les tops-sellers
```

## Pertinence Ivan

Fort — remplace un suivi manuel quotidien fastidieux, permet à Ivan de commencer sa journée avec les 3 priorités opérationnelles sans ouvrir 4 dashboards.
