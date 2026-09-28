# Claude Code Skills just Built me an AI Agent Team (2026 Guide)
**URL:** https://www.youtube.com/watch?v=OdtGN27LchE
**Source:** Créateur Claude Code | **Date:** ~2026 | **Score Gemini Ivan:** 9/10

## Résumé exécutif
Claude Code = agent de codage ET agent généraliste. Skills = fichiers SKILL.md qui transforment Claude Code en agent personnalisable. Démo : création d'apps locales + skill "Twitter X Post" connecté à API Typefully pour automatiser les tweets.

## Concepts clés avec timestamps
- [00:18] Claude Skills : SKILL.md = SOPs que Claude apprend et applique de manière autonome
- [02:45] Exécution locale : fichiers créés directement sur la machine, sans cloud tiers
- [05:36] Obsidian comme espace de travail structuré pour l'agent
- [07:40] "do what's in my queue" : exécuter liste de tâches Markdown
- [11:57] Structure : `.claude/skills/{skill-name}/SKILL.md` + scripts/ + references/ + assets/
- [12:44] Format SKILL.md : Name, Description (crucial), Instructions, Examples
- [13:57] Skill "Twitter X Post" : entraîné sur style personnel via images annotées
- [20:30] Intégration API Typefully : planifier brouillons tweets via API

## Code/prompts/commandes verbatim
```bash
claude
```
```
do what's in my queue
```
```
I want you to replace this @.claude/skills/summarize/ skill with a "Twitter X Post Skill" [...] use the images that are in the @newskillhere/ folder as a reference
```
```
I want you to add to our x-post skill. I'm using Typefully [...] schedule these as a draft. https://typefully.com/docs/api here are the docs [...] api key it is in a text file @key.txt
```

## Patterns réutilisables pour Ivan
- Obsidian comme cerveau structuré pour contexte agent (objectifs, ton, docs API, exemples)
- Skills pour chaque processus récurrent : e-mails, posts LinkedIn, analyses
- Intégrer APIs tierces dans les skills (Shopify, Klaviyo, Meta Ads) avec la doc
- Skill "brand voice" basé sur exemples TempleTwins/PURESOLE
- Pattern "do what's in my queue" : liste de tâches Markdown → exécution agent

## Skill_potential
**Shopify Product Listing** : SKILL.md + scripts pour créer/MAJ fiches via API Shopify avec refs doc et exemples.

**E-commerce Ad Copy Generator** : SKILL.md pour copy publicitaire Facebook/Google adapté TempleTwins/PURESOLE.

**Customer Support Email Responder** : SKILL.md réponses types FAQ (retours, livraisons, paiement) + intégration ticketing.

## Score utilité 0-10 pour Ivan
**9/10** — Automation marketing très élevée. Skills custom = avantage compétitif pour solo founder.

---
*Analyse Gemini 2.5 Flash — 2026-09-28*
