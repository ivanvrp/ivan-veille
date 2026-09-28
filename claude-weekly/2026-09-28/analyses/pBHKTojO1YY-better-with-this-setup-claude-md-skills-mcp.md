# Better With This Setup (CLAUDE.md + Skills + MCPs)
**URL:** https://www.youtube.com/watch?v=pBHKTojO1YY
**Source:** Créateur Claude Code | **Date:** post-14 septembre 2026 | **Score Gemini Ivan:** 9/10

## Résumé exécutif
Transformer Claude Code d'une "feuille blanche" en station de travail complète. CLAUDE.md global+projet, skills officiels Anthropic, 6 MCPs starter, Agent Teams expérimental.

## Concepts clés avec timestamps
- [00:46] PRD vs CLAUDE.md : PRD = quoi/pourquoi, CLAUDE.md = comment construire (règles persistantes)
- [01:06] Sans CLAUDE.md : Claude oublie le projet, code inconsistant, risques sécurité
- [01:18] Types CLAUDE.md : Global (`~/.claude/CLAUDE.md`) + Projet (`./CLAUDE.md`)
- [01:43] Hiérarchie : Global → Projet → `.claude/settings.json` → Conversation
- [02:44] Règles sécurité : JAMAIS clés API dans code, toujours `.env` + `.gitignore`
- [11:19] Skills = expertise IA portable, ~100 tokens pour scanner
- [16:15] Types Skills : Personnels, Projet (dans git), Plugins (marketplace)
- [16:45] 3 méthodes : A) `/plugin` officiel, B) `npx skills add` communauté, C) Build Your Own
- [35:23] MCPs = "ports USB pour l'IA"
- [37:45] 6 MCPs starter : GitHub, Filesystem, Context7, Sequential Thinking, Playwright, Brave Search
- [43:40] Agent Teams (expérimental) : équipes agents spécialisés en parallèle

## Code/prompts/commandes verbatim
```bash
npx skills add https://github.com/vercel-labs/skills --skill find-skills
claude mcp add github
claude mcp add filesystem --scope project
claude mcp add context7 --scope user
claude mcp add sequential-thinking --scope user
claude mcp add playwright --scope user
claude mcp add brave-search --scope user --api_key $BRAVE_API_KEY
```
```
Add the agent teams experimental flag to my project settings. Add CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS set to 1 in the env section of ./claude/settings.json.
```

## Patterns réutilisables pour Ivan
- CLAUDE.md global avec profil e-commerce Ivan (TempleTwins + PURESOLE, stack Shopify, ton de voix)
- Installer skills officiels : `document-skills`, `frontend-design`
- MCP Brave Search pour tendances streetwear/dropship
- Créer skill copywriting custom basé sur son propre contenu
- Activer Agent Teams pour audit code boutiques

## Skill_potential
**E-commerce Launchpad** : Génère CLAUDE.md pré-remplis, PRD, structure fichiers, frameworks copywriting, commandes MCP pour projets e-commerce.

**Audit SEO E-commerce** : Via MCP Brave Search, audite SEO d'une page produit et génère rapport avec recommandations.

## Score utilité 0-10 pour Ivan
**9/10** — Mine d'or pour solo founder e-commerce. Skills directement applicables.

---
*Analyse Gemini 2.5 Flash — 2026-09-28*
