# Analyse Gemini — "Better With This Setup (CLAUDE.md + Skills + MCPs)"
**URL:** https://www.youtube.com/watch?v=pBHKTojO1YY
**Score scoring:** 7/10 (topic ++, use-case solo founder, durée sweet spot estimée)

## Résumé exécutif
Guide complet pour transformer Claude Code d'une feuille blanche en environnement IA intelligent. Couvre CLAUDE.md global/projet, installation/création de Skills, connexion MCP Servers (GitHub, Brave Search), et Agent Teams pour revue parallèle. Token-efficient par conception.

## Concepts clés avec timestamps
- [0:45] PRD (Product Requirements Document) : Plan directeur du projet pour les features et l'architecture
- [0:55] CLAUD.md : Instructions persistantes en Markdown pour comportement Claude Code (règles, stack, préférences)
- [1:19] Types de CLAUD.md : ~/.claude/CLAUD.md (global, tous projets) vs ./CLAUD.md (spécifique projet)
- [1:43] Hiérarchie config : global → projet → settings.json → conversation temps réel
- [1:56] Skills marketplace : /plugin → "Marketplaces" → anthropic/agent-skills
- [2:55] Skills communauté : `npx skills add` depuis GitHub (vercel-labs, supabase, etc.)
- [3:29] Skills personnalisées : demander à Claude Code de créer un SKILL.md sur description
- [3:42] MCP : "ports USB pour l'IA" — GitHub, bases de données, Playwright, Brave Search
- [4:50] Agent Teams : flag expérimental CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1, agents spécialisés parallèles

## Code/prompts/commandes verbatim
```bash
# Installation skill via npx
npx skills add https://github.com/vercel-labs/skills --skill find-skills
npx skills add https://github.com/supabase/agent-skills --skill supabase-postgres-best-practices

# MCPs
claude mcp add github
claude mcp add brave-search
claude mcp add filesystem
claude mcp add context7
claude mcp add playwright

# Activer Agent Teams
# Dans settings.json env: { "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1" }
```

Prompt création skill copywriting :
> "I want to create a skill that is a copywriting skill that will help me write emails, front-end landing pages, websites based on my copywriting style..."

Prompt lancer agent team :
> "Create an agent team to review my codebase. Have one focus on security, one on code quality, and one on documentation."

## Patterns réutilisables pour Ivan
- CLAUDE.md global avec stack TempleTwins (Shopify, Liquid, Metafields) + préférences Ivan
- CLAUDE.md par projet spécifique PURESOLE dropship (supplier APIs, pricing rules)
- Skill copywriting "Ivan Style" pour textes produits, emails CRM, landing pages en français/anglais
- MCP Brave Search pour veille concurrents streetwear + MCP Shopify pour automatisation catalog
- Agent Teams pour audit SEO + revue code Shopify theme en parallèle

## Skill_potential
**Skill proposé : `shopify-copywriting-style`**
Un skill CLAUDE.md qui encode le voice guide Ivan/TempleTwins (ton streetwear, storytelling produit, appels à l'action conversion-first) pour générer descriptions produits, emails Klaviyo, et landing page copy cohérents avec la marque.

**Skill proposé : `claude-md-generator`**
Skill qui génère automatiquement un CLAUD.md de projet depuis une description rapide : stack détectée, commandes fréquentes, conventions équipe/solo.

## Score utilité 0-10 pour Ivan
**10/10** — Feuille de route complète CLAUDE.md + Skills + MCP directement applicable à TempleTwins et PURESOLE.
