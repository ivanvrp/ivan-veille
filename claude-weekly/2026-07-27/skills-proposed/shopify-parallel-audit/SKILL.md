---
name: shopify-parallel-audit
description: Lance N agents en parallèle pour auditer différentes sections d'un thème ou app Shopify (products, checkout, collections, performance, sécurité). Consolide les findings en rapport actionnable.
source: Analyse Gemini — Claude Code Subagents are Absolutely Insane (2026-07-27)
status: proposed — review manuelle Ivan requise
---

## Contexte
Utilise la fonctionnalité de sub-agents Claude Code (v2.1.219+) pour lancer plusieurs agents simultanément sur différentes sections du thème/app Shopify, sans polluer la fenêtre de contexte principale.

## Usage
```
/shopify-parallel-audit [scope] [type]
```

Exemples :
```
/shopify-parallel-audit thème sécurité
/shopify-parallel-audit checkout performance
/shopify-parallel-audit produits SEO
```

## Scopes disponibles
- `thème` : fichiers Liquid, CSS, JS du thème
- `checkout` : pages panier, checkout, confirmation
- `produits` : templates produit, collections, recherche
- `app` : app custom ou intégration tierce
- `complet` : audit full store

## Types d'audit
- `sécurité` : vulnérabilités OWASP, injections, XSS
- `performance` : temps de chargement, assets lourds, lazy loading
- `SEO` : balises manquantes, contenu dupliqué, structure
- `accessibilité` : WCAG 2.1, contraste, alt texts

## Workflow interne

### Phase 1 — Discovery (Haiku, x5 agents)
```
Lancer 5 agents File-Finder-Haiku pour cartographier :
- Agent 1 : fichiers templates produit
- Agent 2 : fichiers checkout/panier
- Agent 3 : assets JS/CSS
- Agent 4 : fichiers config/settings
- Agent 5 : intégrations tierces
```

### Phase 2 — Analyse (Opus, x3 agents)
```
Sur chaque section identifiée, lancer agents Opus :
- Agent A : analyse [type] section [X]
- Agent B : analyse [type] section [Y]
- Agent C : analyse [type] section [Z]
```

### Phase 3 — Rapport consolidé
Agréger tous les findings en :
- 🔴 Critique (action immédiate)
- 🟡 Important (semaine prochaine)
- 🟢 Nice-to-have (backlog)

## Output
```markdown
# Audit Shopify — [date] — [scope] — [type]

## Résumé exécutif
[3 lignes max]

## 🔴 Critique (N issues)
| File | Issue | Fix suggéré |
...

## 🟡 Important (N issues)
...

## 🟢 Backlog (N issues)
...

## Temps estimé correction : Xh
```

## Prérequis
- Claude Code v2.1.219+ (sub-agents nesting depth 3)
- Accès au répertoire du thème Shopify
- Pour audit sécurité : lister les apps tierces installées
