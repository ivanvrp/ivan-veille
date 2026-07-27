---
name: claude-effort-optimizer
description: Sélectionne automatiquement le bon niveau de raisonnement Claude (low/medium/high/xhigh/max) selon le type de tâche pour maximiser qualité/coût. Évite les sur-coûts d'effort "max" inutile.
source: Analyse Gemini — We Tested Claude Opus 5. It's Frustrating with Flashes of Brilliance. (2026-07-27)
status: proposed — review manuelle Ivan requise
---

## Contexte
Avec Claude Opus 5, les niveaux d'effort ont un impact majeur sur qualité ET coût. Utiliser "max" par défaut est souvent contre-productif (modèle "s'arrête", sur-raisonne, coûts inutiles). Ce skill guide vers l'effort optimal.

## Grille de sélection effort

| Type de tâche | Effort recommandé | Justification |
|---|---|---|
| Réponse rapide, FAQ | `low` | Pas besoin de raisonnement profond |
| Description produit SEO | `medium` | Créativité + structure, pas de logique complexe |
| Analyse de tendances marché | `medium` | Synthèse, pas de calcul |
| Débogage code simple | `medium` | Pattern matching |
| Agent autonome multi-étapes | `high` (défaut) | Standard pour la plupart des agents |
| Architecture système complexe | `xhigh` | Raisonnement profond sur décisions structurelles |
| Tâche critique (sécurité, juridique) | `max` | Justifié seulement si conséquences majeures |

## Usage
Invoquer avant une session de travail intensive :
```
/claude-effort-optimizer [description tâche]
```

Claude retourne :
1. Niveau effort recommandé
2. Justification en 1 ligne
3. Coût estimatif relatif (1x / 3x / 10x)

## Règles Ivan spécifiques
- **TempleTwins** descriptions : `medium` — le style streetwear n'a pas besoin d'effort max
- **PURESOLE** sourcing analysis : `high` — trade-offs fournisseurs méritent réflexion
- **Bug Shopify** urgent : `high` — pas max, sauf crash production
- **Stratégie pricing** : `xhigh` — décision avec impact direct revenus
- **Email client mécontant** : `medium` — empathie + clarté, pas logique formelle

## Note sur Opus 5
Avec Opus 5 spécifiquement : le modèle "s'arrête prématurément" en mode max sur les skills complexes. Commencer par `high` et remonter seulement si résultats insuffisants.

## Économies estimées
Passer de "max systématique" à "effort adaptatif" peut réduire les coûts Claude de 40-60% sur les tâches quotidiennes, sans perte de qualité perceptible.
