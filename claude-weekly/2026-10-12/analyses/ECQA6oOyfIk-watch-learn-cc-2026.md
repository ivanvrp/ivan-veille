# Analyse Gemini — ECQA6oOyfIk
URL: https://www.youtube.com/watch?v=ECQA6oOyfIk

## Résumé exécutif
Claude Code + ScaleKit pour construire des agents IA avec auth multi-tenant. Montre comment un solo founder peut déployer des agents qui agissent directement sur ses systèmes (Shopify, CRM) avec permissions déléguées et sécurisées. Architecture multi-agents sur worktrees isolés pour tests A/B simultanés.

## Concepts clés
- Agent Teams (expérimental) : plusieurs Claude Code collaborent via tmux
- ScaleKit : couche auth pour connecter 100+ apps SaaS aux agents
- Worktree Isolation : tester variations UI/UX en parallèle
- Loop : automatisation continue type cron job intelligent
- Monitor : surveillance des logs et détection anomalies
- Advisor : consulter Opus pour décisions complexes depuis Haiku/Sonnet
- Goal : tâche longue avec condition d'achèvement
- /security-review, /simplify, /code-review, /ultrareview

## Score utilité 0-10 pour Ivan
**9.5/10** — Extrêmement pertinent pour automatisation workflows Shopify + dropship.

## Skill_potential
1. `shopify-connector-auth` (Plugin ScaleKit) : auth déléguée pour APIs Shopify
2. `ecom-ab-test-stylist` (Worktrees) : variantes UI/UX en parallèle
3. `product-data-ingest-monitor` (Loop + ChromaDB) : base de connaissances produits auto
4. `dropship-supplier-api-health-check` (Loop + Monitor) : surveillance APIs fournisseurs
