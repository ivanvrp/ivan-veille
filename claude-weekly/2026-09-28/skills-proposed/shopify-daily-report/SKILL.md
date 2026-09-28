---
name: shopify-daily-report
description: Génère un check-in quotidien concis des performances boutiques Shopify (TempleTwins + PURESOLE) — ventes, best/worst sellers, alertes stock, tendances. Utilisable comme briefing matinal sans ouvrir le dashboard Shopify.
---

# Shopify Daily Report

## Contexte
Ivan gère deux boutiques Shopify. Il a besoin d'un check-in quotidien rapide (< 2 min de lecture) sans plonger dans les dashboards.

## Instructions

### Déclenchement
Ce skill s'active quand Ivan dit :
- "check-in", "rapport du jour", "comment vont les boutiques", "daily report"
- Ou lance le skill explicitement : `/shopify-daily-report`

### Format du rapport
```
## 📊 [Nom boutique] — [Date]

**Ventes J-1**
- Chiffre d'affaires : [montant]
- Commandes : [nb] (AOV : [montant])
- vs hier : [+/- %]

**Top 3 Produits**
1. [Produit] — [nb ventes] — [CA]
2. [Produit] — [nb ventes] — [CA]
3. [Produit] — [nb ventes] — [CA]

**Alertes Stock** ⚠️
- [Produit] : [nb unités restantes] (seuil bas)

**Insight**
[1 observation actionnable : pattern de vente, opportunité, anomalie]
```

### Alertes automatiques
Signale si :
- Un produit passe sous 5 unités en stock
- Une baisse > 30% du CA par rapport à la moyenne des 7 derniers jours
- Une commande en attente depuis > 48h
