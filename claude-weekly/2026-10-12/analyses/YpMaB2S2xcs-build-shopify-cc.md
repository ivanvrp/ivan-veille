# Analyse Gemini — YpMaB2S2xcs
URL: https://www.youtube.com/watch?v=YpMaB2S2xcs

## Résumé exécutif
Démontre comment utiliser Claude Code avec Shopify pour automatiser les tâches e-commerce — création produits (CSV → Shopify), gestion remises automatiques, création de landing pages listicles, analyse des ventes avec charts. Met en lumière l'importance d'un "Master Prompt" stocké dans CLAUDE.md.

## Master Prompt (extrait)
```
I want to use Claude Code to build and manage a Shopify store.
Core objectives: Launch product, Setup bundle discount, Launch listicle LP, Analyze sales, Audit SEO
Process Rules: Always plan first. Never edit Live theme. Draft Mode for products.
Memory: Create CLAUDE.md with conventions. Maintain PROGRESS.md as audit log.
```

## Commandes
```bash
shopify auth login
/plugin marketplace add Shopify/shopify-ai-toolkit
/plugin install shopify-plugin:shopify-ai-toolkit
```

## Score utilité 0-10 pour Ivan
**9/10** — Méthodologie complète pour gérer boutique Shopify sans coder.

## Skill_potential
- Agent de lancement de produit Shopify (CSV → DRAFT) → **IMPLÉMENTÉ comme shopify-product-launcher**
- Agent de gestion des remises Shopify
- Agent de création de Landing Page Listicle
- Agent d'analyse des ventes et des conversions
- Agent d'audit et d'optimisation SEO Shopify
