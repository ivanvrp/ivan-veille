# Analyse Gemini — "Top 5 Claude Code Skills That Will 10x Your Productivity (2026)"
**URL:** https://www.youtube.com/watch?v=Xs942zwWfdY
**Score scoring:** 8/10 (skills officiels Anthropic, concret, applicable e-com)

## Résumé exécutif
Présente les 5 skills officiels Anthropic sur le dépôt GitHub anthropic/agent-skills. Couvre skill-creator (méta-skill pour créer ses propres skills), frontend-design (générer UI à partir de texte), mcp-builder, claude-api quickstart, et webapp-testing (Playwright automatisé). 17 skills disponibles au total sur le repo.

## Concepts clés avec timestamps
- [0:47] Skills = fichier .md dans ~/.claude/skills/, activé après restart Claude Code
- [2:11] Installation : git clone + copie, ou `/plugin marketplace add` + `/plugin install`
- [3:45] /skill-creator : méta-skill pour construire de nouvelles compétences avec l'IA, ex: notes de version depuis historique Git
- [7:57] /frontend-design : générer UI complète (HTML/CSS/JS) depuis description textuelle (ex: page pricing SaaS)
- [11:13] /mcp-builder : construire serveurs MCP en 4 phases (recherche, implémentation, test, évaluation)
- [12:04] /claude-api : quickstart multilingue, détecte stack, fournit streaming + gestion erreurs
- [12:51] /webapp-testing : tests UI automatisés Playwright, Claude écrit et exécute les scripts

## Code/prompts/commandes verbatim
```bash
# Installation manuelle
git clone https://github.com/anthropics/agent-skills
cp -r agent-skills/frontend-design ~/.claude/skills/

# Via marketplace
/plugin marketplace add anthropic/agent-skills
/plugin install frontend-design
```

## Patterns réutilisables pour Ivan
- `/skill-creator` pour créer des skills TempleTwins (descriptions produits, réponses CRM, génération contenus)
- `/frontend-design` pour créer/modifier pages de landing sans designer — gain énorme pour solo founder
- `/webapp-testing` pour tester flux de commande, checkout Shopify, réactivité mobile sans équipe QA
- 17 skills officiels disponibles sur anthropic/agent-skills à explorer

## Skill_potential
**Skill proposé : `shopify-product-description`**
Un skill basé sur /skill-creator qui génère descriptions produits streetwear optimisées SEO pour Shopify : ton brand TempleTwins, mots-clés fashion, variants couleur/taille, en fr + en.

**Skill proposé : `shopify-checkout-tester`**
Skill /webapp-testing adapté e-commerce : teste automatiquement le flux add-to-cart → checkout → confirmation sur Shopify, flags les régressions.

## Score utilité 0-10 pour Ivan
**8/10** — frontend-design + webapp-testing + skill-creator = triple combo solo founder e-com
