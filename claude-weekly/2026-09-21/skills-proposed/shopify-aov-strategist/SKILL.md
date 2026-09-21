---
name: shopify-aov-strategist
description: Analyse les patterns d'achat Shopify pour identifier les meilleures opportunités de bundling, upsell et cross-sell
trigger: "augmenter panier moyen" OR "AOV shopify" OR "bundle produits" OR "cross-sell"
requires: shopify-ai-toolkit plugin
---

# Shopify AOV Growth Strategist

## Ce que fait ce skill

Analyse les données d'achat réelles de ta boutique pour découvrir quels produits sont achetés ensemble, en quelle quantité, et propose des stratégies concrètes pour augmenter la valeur moyenne des commandes.

## Workflow

1. Interroge les données de co-occurrence d'achat (produits achetés ensemble)
2. Identifie les produits souvent achetés en quantité > 1
3. Propose 3-5 packs ou bundles à tester immédiatement
4. Génère les descriptions produit pour les bundles suggérés

## Prompt de déclenchement

```
Analyse mes données d'achat Shopify des 90 derniers jours.
Identifie : 
1. Les produits souvent achetés en quantité > 1 (opportunités de volume discount)
2. Les paires de produits fréquemment achetées ensemble (opportunités de bundle)
3. Les produits complémentaires (cross-sell naturel)
Pour chaque opportunité : calcule l'impact potentiel sur l'AOV et propose un titre + prix de bundle.
```

## Use-case Ivan

- TempleTwins : streetwear → packs capsule (tshirt + hoodie même coloris), volume discount (2 tshirts = -15%)
- PURESOLE : dropship → bundles produits complémentaires, upsell sur accessoires

## Source

Extrait de l'analyse Gemini du 2026-09-21 — vidéo EpPuU9k6Ahg "Claude Can Now Do EVERYTHING on Shopify"

## ⚠️ À valider par Ivan avant déploiement
