---
name: ecom-routine-manager
trigger: /ecom-routine [tache]
source_video: GMIWm5y90xA (Code with Claude SF 2026 — Routines + Managed Agents)
score_ivan: 7/10
status: PROPOSED — à reviewer manuellement avant déploiement
---

# Skill : Ecom Routine Manager

## Objectif

Orchestrateur de tâches e-commerce récurrentes via des Routines Claude Code. Lance des subagents pour les tâches répétitives sans intervention manuelle d'Ivan.

## Usage

```
/ecom-routine check-stock         # Vérifier le stock PURESOLE
/ecom-routine daily-brief         # Brief quotidien ventes + tasks
/ecom-routine supplier-update     # Email fournisseurs dropship
/ecom-routine product-launch [id] # Workflow lancement produit complet
```

## Sous-workflows inclus

### `check-stock`
- Interroge l'API Shopify (lecture seule) pour les variantes < seuil stock
- Génère un rapport markdown avec alertes
- Optionnel : draft email fournisseur auto

### `daily-brief`
- Pull métriques Shopify hier (commandes, CA, taux de retour)
- Pull top 3 tâches ClickUp/Notion en retard
- Génère brief 10 lignes dans `/tmp/daily-brief-[date].md`

### `supplier-update`
- Template communication fournisseur dropship (FR/EN)
- Merge avec données commandes en attente
- Génère draft email — **NE PAS envoyer automatiquement** (permission écriture non accordée)

### `product-launch [id]`
Workflow multi-étapes (Dynamic Workflow) :
1. Génère description Shopify → appelle `shopify-content-optimizer`
2. Crée draft post Instagram + TikTok
3. Génère meta tags SEO
4. Checklist de lancement (stock confirmé, prix OK, images uploadées)

## Architecture (Dynamic Workflows pattern — v2.1.154+)

```
/ecom-routine product-launch SKU-PP-007
→ Claude écrit un script workflow
→ Lance subagents en parallèle :
   ├── Agent 1 : content generation
   ├── Agent 2 : SEO analysis
   └── Agent 3 : social media drafts
→ Agrège résultats → rapport final
```

## Prérequis

- Claude Code v2.1.154+ (Dynamic Workflows)
- MCP Shopify connecté (lecture seule suffisant pour check-stock/daily-brief)
- Permissions : JAMAIS donner accès écriture Shopify sans "bike method" graduelle

## À faire avant déploiement

- [ ] Configurer MCP Shopify en read-only
- [ ] Tester `daily-brief` en premier (le plus safe)
- [ ] Définir seuils stock alertes PURESOLE
- [ ] Valider format email fournisseur avant d'activer
