---
name: solo-founder-ideation
description: >
  Version e-com du pattern `grill-me` de Matt Pocock : interviewe Ivan sans
  relâche pour transformer une idée floue de feature Shopify/dropship en
  spec + tickets exploitables, sans écrire une ligne de code. Trigger : Ivan
  décrit une idée, une refonte, un nouveau parcours produit, ou lance
  `/solo-founder-ideation "…"`.
source: inspiration Matt Pocock — Claude Skills Beat Superpowers Now (YouTube 8D8ewFBJfFM)
status: DRAFT — review Ivan avant merge dans ~/.claude/skills/
---

# solo-founder-ideation — DRAFT

## But
Faire passer une idée floue ("je veux un customiseur de t-shirts", "je veux
un flow abandoned cart plus agressif") à :
- un `SPEC.md` sans code (QUOI, jamais COMMENT)
- une liste de tickets découpés **par feature** (pas par couche)
- un plan de délégation possible à un freelance

## 5 règles (héritées de `grill-me`)
1. **RELENTLESSLY** — pose des questions jusqu'à consensus.
2. **DECISION TREE** — attaque UNE branche à la fois, en commençant par les dépendances.
3. **ONE AT A TIME** — attends la réponse avant la question suivante.
4. **RECOMMEND ONE** — jamais de question ouverte sans option par défaut proposée.
5. **DO NOT ACT** — n'écris rien tant qu'Ivan n'a pas dit "OK spec".

## Focus e-com (à ajouter au brief de base de grill-me)
- Type de produit (physique / on-demand / dropship / bundle) ?
- Marché cible (FR / EU / US ; B2C / grossiste) ?
- Impact checkout / payment ? (breaking?)
- Impact SEO on-page / structured data ?
- Impact stock (physique vs synced fournisseur) ?
- KPIs de succès (AOV, taux de conversion, marge, LTV) ?
- Freelance-able ou solo-only ?

## Livrables
- `SPEC.md` (sans code, mots-guides autorisés : "slice-by-feature", "TDD", "idempotent", "GDPR-safe")
- `TICKETS.md` (1 ticket = 1 feature complète UI+API+DB)
- `RISKS.md` (regressions checkout / SEO / stock)

## Anti-pattern
NE JAMAIS produire du code pendant `solo-founder-ideation`. Si Ivan demande
du code, dis : "Passe à `/implement` ou `/to-tickets` — j'écris uniquement
du spec ici."
