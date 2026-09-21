---
name: shopify-cro-analyzer
description: Analyse les performances des pages Shopify (CVR, sessions, rebond) et génère des recommandations CRO concrètes
trigger: "analyse mes pages shopify" OR "quelles pages convertissent" OR "CRO shopify"
requires: shopify-ai-toolkit plugin
---

# Shopify CRO Page Analyzer

## Ce que fait ce skill

Connecte-toi au Shopify AI Toolkit pour analyser les pages de ta boutique sur 30 jours, identifie les star performers et les underperformers, et génère un rapport d'action priorisé.

## Workflow

1. Interroge les données de conversion par page (sessions × CVR)
2. Classe les pages en 3 buckets : Star (CVR > moyenne), Normal, Faible
3. Pour les pages Faibles avec trafic élevé : propose 3 pistes d'amélioration concrètes
4. Génère un rapport markdown prêt à partager

## Prompt de déclenchement

```
Je veux analyser le taux de conversion de mes pages Shopify sur les 30 derniers jours.
Classe les pages par (sessions × CVR), identifie les 3 meilleures et les 3 moins bonnes.
Pour chaque underperformer à fort trafic, propose 3 actions concrètes (CTA, copy, images, UX).
Format: tableau markdown + liste d'actions priorisée.
```

## Use-case Ivan

- TempleTwins : identifier les fiches produit streetwear qui ont du trafic mais ne convertissent pas
- PURESOLE : comparer les pages de collection dropship pour prioriser les optimisations

## Source

Extrait de l'analyse Gemini du 2026-09-21 — vidéo EpPuU9k6Ahg "Claude Can Now Do EVERYTHING on Shopify"

## ⚠️ À valider par Ivan avant déploiement
