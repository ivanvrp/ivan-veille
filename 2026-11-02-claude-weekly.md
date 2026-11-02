# Claude Weekly — 2 novembre 2026
> Routine veille-claude weekly | Deep-dive Claude / Claude Code / Skills / MCP

---

## 📊 Résumé de la semaine

| Métrique | Valeur |
|---|---|
| Must-watch | 3 |
| Nice-watch | 6 |
| Skip | 4 |
| Analyses Gemini | 3/3 |
| Skills proposés | 4 |
| Date digest | 2026-11-02 |

---

## 🔥 MUST-WATCH

### 1. Better With This Setup (CLAUDE.md + Skills + MCPs)
- **URL :** https://www.youtube.com/watch?v=pBHKTojO1YY
- **Score Gemini :** 10/10 pour Ivan
- **Durée :** ~15-20 min (sweet spot)
- **Thème :** CLAUDE.md global/projet + Skills marketplace + MCP servers + Agent Teams
- **Pourquoi must-watch :** Feuille de route complète pour passer de Claude Code basique à un assistant IA personnalisé et persistant. Couvre le setup idéal pour un solo founder.
- **TL;DR :** Configure ton CLAUDE.md global (préférences Ivan), installe les skills via `/plugin marketplace anthropic/agent-skills`, connecte GitHub/Brave/Playwright via MCPs, active CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1 pour revue parallèle.
- **⚡ Action :** Créer ~/.claude/CLAUDE.md avec ta stack TempleTwins + PURESOLE ce weekend.
- **Analyse complète :** `claude-weekly/2026-11-02/analyses/pBHKTojO1YY-better-setup-claude-md-skills-mcps.md`

---

### 2. Top 5 Claude Code Skills That Will 10x Your Productivity (2026)
- **URL :** https://www.youtube.com/watch?v=Xs942zwWfdY
- **Score Gemini :** 8/10 pour Ivan
- **Thème :** 5 skills officiels Anthropic (skill-creator, frontend-design, mcp-builder, claude-api, webapp-testing)
- **Pourquoi must-watch :** Présente les 17 skills officiels Anthropic sur GitHub, avec démo de chacun. Le skill `/frontend-design` est un game-changer pour générer des landing pages sans designer.
- **TL;DR :** Les 5 skills clés : `/skill-creator` (créer ses propres skills), `/frontend-design` (UI depuis texte), `/mcp-builder` (4 phases), `/claude-api` (quickstart 8 langages), `/webapp-testing` (Playwright auto).
- **⚡ Action :** Installer `/skill-creator` + `/frontend-design` depuis anthropic/agent-skills via `/plugin marketplace`.
- **Analyse complète :** `claude-weekly/2026-11-02/analyses/Xs942zwWfdY-top5-skills-productivity.md`

---

### 3. How Complete Beginners Master Claude Code MCP in 19 minutes
- **URL :** https://www.youtube.com/watch?v=dhsyihMpqZQ
- **Upload :** 22 octobre 2026 (< 14 jours)
- **Score Gemini :** 9/10 pour Ivan
- **Durée :** 19 min (sweet spot)
- **Thème :** MCP pour débutants — filesystem local + Notion hébergé + workflow fan-out
- **Pourquoi must-watch :** Récent, très pratique, montre exactement comment combiner 2 MCPs dans 1 prompt (fan-out). Pattern immédiatement applicable pour review hebdo Shopify → rapport local + Notion.
- **TL;DR :** 2 types MCP (local JSON config vs connecteurs OAuth). Fan-out = 1 prompt → Claude écrit en local ET crée page Notion simultanément. 4 erreurs courantes documentées avec diagnostic.
- **⚡ Action :** Configurer MCP filesystem sur ton dossier dropship PURESOLE + connecter Notion.
- **Analyse complète :** `claude-weekly/2026-11-02/analyses/dhsyihMpqZQ-mcp-19min-beginners.md`

---

## 👍 NICE-WATCH

| # | Titre | URL | Pourquoi |
|---|---|---|---|
| 1 | How to Add GitHub MCP to Claude Code (2026 Guide) | https://www.youtube.com/watch?v=IFhveUVzNB4 | ~13 jours, GitHub MCP setup step-by-step |
| 2 | How To Use MCPs With Claude Code | https://www.youtube.com/watch?v=Tt0EiNam9T4 | Guide pratique MCPs généraliste |
| 3 | Better Claude Code Tutorial for Beginners (2026) | https://www.youtube.com/watch?v=sX-FmJL7Wd0 | Beginner-friendly 1h, bonne base |
| 4 | Claude Code is all you need in 2026 | https://www.youtube.com/watch?v=0hdFJA-ho3c | Vue d'ensemble, opinion/positioning |
| 5 | Watch This If You're Just Learning Claude Code 2026 | https://www.youtube.com/watch?v=ECQA6oOyfIk | Good entry point, format court |
| 6 | Cómo Usar MCP en Claude Code (2026) | https://www.youtube.com/watch?v=vfrCM-hFfm0 | Espagnol — skip si non-hispano |

---

## ⏭️ SKIP

| Titre | Raison |
|---|---|
| Claude Code Full Course 2026 (No Coding Needed) | 5 heures — trop long |
| 【2026最新】Claude Code 徹底解説 | Japonais |
| 14分钟掌握Claude Code | Chinois |
| Comment utiliser Claude AI en 2026 | Trop généraliste, pas deep-dive |

---

## 🚀 SKILLS PROPOSÉS (4 — review manuel requis)

> ⚠️ Ces skills sont DES PROPOSITIONS. Ivan doit les valider manuellement avant déploiement.

### 1. `shopify-copywriting-style`
**Source :** Vidéo pBHKTojO1YY (pattern: skill copywriting personnalisé)
**Usage :** Générer descriptions produits, emails Klaviyo, landing pages dans le style Ivan/TempleTwins (streetwear, conversion-first, fr+en)
**Fichier :** `claude-weekly/2026-11-02/skills-proposed/shopify-copywriting-style/SKILL.md`

### 2. `claude-md-generator`
**Source :** Vidéo pBHKTojO1YY (pattern: générer CLAUDE.md depuis description)
**Usage :** Générer automatiquement un CLAUDE.md de projet complet depuis une description rapide
**Fichier :** `claude-weekly/2026-11-02/skills-proposed/claude-md-generator/SKILL.md`

### 3. `shopify-product-description`
**Source :** Vidéo Xs942zwWfdY (pattern: skill-creator pour e-com)
**Usage :** Fiches produits streetwear optimisées SEO pour Shopify TempleTwins, avec titre/meta/description HTML/tags
**Fichier :** `claude-weekly/2026-11-02/skills-proposed/shopify-product-description/SKILL.md`

### 4. `notion-shopify-sync`
**Source :** Vidéo dhsyihMpqZQ (pattern: fan-out multi-MCP)
**Usage :** Workflow fan-out Shopify → rapport local + page Notion pour review hebdo solo founder
**Fichier :** `claude-weekly/2026-11-02/skills-proposed/notion-shopify-sync/SKILL.md`

---

## 📰 ANNONCES ANTHROPIC (semaine du 19-29 oct. 2026)

### 🏛️ Agent Skills → Agentic AI Foundation (22 oct.)
**URL :** https://www.anthropic.com/news/donating-agent-skills-to-the-agentic-ai-foundation
**Impact pour Ivan :** Anthropic confie le standard ouvert Agent Skills à la Agentic AI Foundation. 70+ plateformes déjà intégrées depuis décembre 2025. Cela signifie que les skills que tu crées pour Claude fonctionneront sur d'autres plateformes compatibles (Cursor, Codex, Gemini CLI). Investissement skills = investissement cross-platform.

### 🏛️ Claude Code releases (oct. 19-31)
Versions publiées : 2.1.304 → 2.1.316

Highlights pour Ivan :
- **v2.1.316 (31 oct.)** : Nouvelle variable `CLAUDE_CODE_DISABLE_ULTRATHINK`, budgets groupés partagés, tableau de bord sévérité Code Review
- **v2.1.314 (30 oct.)** : `permissions.blockWritesOutsideWorkingDirectories` (sécurité++), compaction en veille VS Code
- **v2.1.312 (27 oct.)** : Sélecteur d'effort pour les routines cloud ← utile pour la routine veille
- **v2.1.311 (26 oct.)** : `ultrathink` passe en effort xhigh sur modèles 5.x, tableau des skills dans analytics Claude Tag
- **v2.1.304 (19 oct.)** : `/auto-mode-setup`, niveaux de revue Quick/Standard/Deep pour Code Review

Dépréciation à noter : **Opus 4.8 fast mode → suppression le 30 novembre 2026**. Migrer vers Opus 5.5.

### 🔌 MCP officiel (commits 27-28 oct.)
Repo modelcontextprotocol/servers actif : corrections filesystem (cross-device, symlinks, timestamps). Upgrade certifi vers 2026.10.23.

### 🛒 Claude Commerce (context)
Anthropic a lancé en septembre 2026 un blueprint Commerce avec shopper + merchant agents open-source. Shopify a shipper sa propre implémentation le même jour. Le Shopify AI Toolkit (open-sourced avril 2026) donne accès aux GraphQL schemas + CLI Shopify directement depuis Claude Code. Plugin disponible dans le marketplace Claude.

---

## 💡 Insight cross-vidéos

**Pattern récurrent de la semaine :** Les 3 must-watch convergent tous vers la même architecture gagnante pour le solo founder — **CLAUDE.md + Skills + MCPs comme stack de base**, avec le fan-out multi-MCP comme superpower pour automatiser les workflows cross-plateformes. L'ordre d'installation optimal : (1) CLAUDE.md global → (2) 2-3 skills officiels Anthropic → (3) 1-2 MCPs essentiels (filesystem + Notion ou Shopify).

---

## 🔗 Ressources clés

- Repo skills officiels Anthropic : https://github.com/anthropics/agent-skills (17 skills)
- MCP servers officiels : https://github.com/modelcontextprotocol/servers
- Claude Code changelog : https://code.claude.com/docs/en/changelog
- Shopify AI Toolkit : https://github.com/Shopify/shopify-ai-toolkit
- Anthropic news : https://www.anthropic.com/news

---

*Généré par routine veille-claude weekly — 2026-11-02 07:17 UTC*
*Analyses Gemini : 3/3 réussies | Skills proposés : 4 | Review manuel requis avant déploiement*
