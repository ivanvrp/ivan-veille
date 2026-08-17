---
name: shopify-pipeline
description: Coordonne un pipeline multi-agent pour workflows e-commerce (research → content → ops → report). Utilise la messagerie cross-session Claude Code v2.1.232.
triggers:
  - /shopify-pipeline
requires:
  - cross-session messaging (Claude Code v2.1.232+)
---

# Skill : shopify-pipeline

Skill de coordination multi-agent exploitant la feature SendMessage/ListAgents de Claude Code v2.1.232.

## Prérequis

- Claude Code v2.1.232 minimum
- Plusieurs sessions actives avec des noms dédiés

## Noms de sessions standards

Pour TempleTwins :
- `tt-research` : veille produit, tendances streetwear, concurrents
- `tt-content` : rédaction descriptions, emails, posts
- `tt-ops` : actions Shopify (inventaire, prix, fiches produits)
- `tt-report` : génération rapports de session

Pour PURESOLE :
- `ps-sourcing` : recherche fournisseurs, nouveaux produits dropship
- `ps-listing` : création fiches produits, descriptions
- `ps-pricing` : calcul marges, optimisation prix
- `ps-report` : rapports session

## Workflow standard

```
/shopify-pipeline [store] [mode]

Modes:
- product-launch : pipeline complet pour lancement produit
- seo-update : research mots-clés → content → update SEO
- weekly-ops : ops hebdomadaires automatisées
```

### Exemple product-launch TempleTwins :
1. Session `tt-research` : analyse 5 concurrents, identifie angle différenciant
2. `SendMessage tt-content` : "Rédige 3 descriptions produit pour [item] avec angle [X]"
3. `SendMessage tt-ops` : "Mets à jour Shopify avec la meilleure description, prix suggéré [Y]"
4. `SendMessage tt-report` : "Génère rapport lancement dans sessions/YYYY-MM-DD.md"

## Format résumé inter-agents

Les sessions envoient des résumés structurés (pas l'historique complet) :

```markdown
## Résumé Session [nom] — [date]
**Action effectuée :** [1 ligne]
**Résultats clés :** [2-3 bullets]
**Prochaine étape attendue :** [instruction claire]
**Fichiers modifiés :** [liste]
```

## Source

Issu de l'analyse de : https://www.youtube.com/watch?v=6L6qG_safRY
Feature source : Claude Code v2.1.232 changelog
Semaine : 2026-08-17
