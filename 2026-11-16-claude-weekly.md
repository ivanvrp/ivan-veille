# Claude Weekly — 2026-11-16
> Deep-dive hebdomadaire Claude / Claude Code / Skills / MCP  
> Période couverte : 2 au 16 novembre 2026

---

## 🔥 MUST-WATCH (2 vidéos — score ≥ 7)

### 1. Claude Code Finally Got MCP Code Mode (Setup + Test)
**URL :** https://www.youtube.com/watch?v=wSYqwfd5mV0  
**Score :** 8/10 | **Date :** ~11-12 nov 2026 (couvre v2.1.323) | **Durée :** ~7 min  
**Analyse Gemini :** `claude-weekly/2026-11-16/analyses/wSYqwfd5mV0-claude-code-mode-mcp.md`

**TL;DR :** Le Code Mode (v2.1.323) permet à Claude d'écrire du JS pour appeler ses outils, réduisant le contexte de 50 à 75%. Activation : `CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1 claude`

**Key insights Ivan :**
- -75% tokens sur les requêtes OpenRouter/API → économies directes sur les coûts Claude
- Idéal pour interroger APIs Shopify/fournisseurs dropshipping avec filtrage JS avant injection dans contexte
- Expérimental, terminal uniquement, ne fonctionne pas avec Agent Teams

**Skills proposés :** ContextualDataFilter, APIOrchestratorJS

---

### 2. NEW n8n Skill for Claude Code!
**URL :** https://www.youtube.com/watch?v=WzZyRsYZeDQ  
**Score :** 7/10 | **Date :** ~15 nov 2026 | **Durée :** ~6 min  
**Analyse Gemini :** `claude-weekly/2026-11-16/analyses/WzZyRsYZeDQ-n8n-skill-claude-code.md`

**TL;DR :** Les skills n8n officiels permettent à Claude Code de créer et modifier des workflows n8n par langage naturel, avec auto-correction et validation avant publication.

**Key insights Ivan :**
- Créer des automations Shopify en disant juste "crée un workflow suivi expédition → email client"
- Skills `n8n-agents` + `n8n-workflow-lifecycle` = Claude sait comment configurer chaque nœud n8n
- Connexion via `claude mcp add --transport http <n8n-url>/mcp-server/http`

**Skills proposés :** n8n-shopify-lifecycle, n8n-supplier-integration

---

## 👍 NICE-TO-WATCH (5 items — score 4-6)

| # | Titre | URL | Raison |
|---|-------|-----|--------|
| 1 | Add Your First MCP Server to Claude Code in 2 Minutes | https://www.youtube.com/watch?v=BPPQ2_rCfR4 | Bon onboarding MCP, rapide |
| 2 | Claude MCP Tutorial: Give Claude Superpowers in 30 Seconds | https://www.youtube.com/watch?v=Lxznc91wlTk | MCP primer, léger hype |
| 3 | How to Build AI Agents with CLAUDE SKILLS in n8n | https://recapio.com/digest/how-to-build-ai-agents-with-claude-skills-in-n8n-by-mark-kashef | Skills + n8n, bon complément |
| 4 | Claude Code 2.1.323 Adds Code Mode (DEV article) | https://dev.to/raxxostudios/claude-code-21323-adds-code-mode-for-javascript-tool-calls-3ibk | Synthèse technique Code Mode |
| 5 | Shopify Skills for Claude Code (get-ryze.ai) | https://www.get-ryze.ai/blog/claude-shopify-skills | Skills Shopify officiels, références |

---

## ⏭️ SKIP (mentions)

- `jZOes6Tbm1w` — "Claude Code, Advanced: MCP, Hooks, Skills, Subagents, Headless" — >14j (7 semaines)
- `tuY2ChJIx48` — "Beyond the basics with Claude Code" — >14j (7 semaines)
- `hVRjUvjDQwE` — "Claude Code & Claude AI Full Course 2026" — >14j (octobre)
- `2g8A53SIv3w` — "What's New in Claude Code" — >14j (mai 2026)
- `diTuQaSJ3nI` — "Claude Code Is an MCP Now?...3 CRAZY Things" — clickbait (-3)
- `0hdFJA-ho3c` — "Claude Code is all you need in 2026" — générique, date incertaine

---

## 📰 ANNONCES ANTHROPIC (semaine du 6-16 nov 2026)

### 🚀 Claude Fable 5.2 + Mythos 5.2 (9 nov 2026)
- **ID modèles :** `claude-fable-5-2` (public) et `claude-mythos-5-2` (access restreint)
- **Prix :** $8/M input, $40/M output | Cache : $0.20/M
- **Performances :** +30% vitesse vs 5.1 | FrontierCode 2.0 : 49.1% (record)
- **Contexte :** 1M tokens | Fast mode disponible
- **Source :** https://www.anthropic.com/claude-fable-and-mythos-5-2

### 🛠️ Claude Code v2.1.323 (12 nov 2026) — highlights
- **Code Mode (expérimental)** : `CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1` — Claude écrit du JS pour appeler ses outils
- **engines["claude-code"]** dans plugin.json pour versionner les plugins
- Heartbeat 30s pendant les hooks longs (SDK)
- Fenêtre contexte inconnue → 1M par défaut (au lieu de 200K)

### 🛠️ Claude Code v2.1.325 (13 nov 2026) — highlights
- Suggestions prompts dans VS Code (Tab pour accepter)
- Connexion Console sans clé API
- **Skills doivent confirmation** avant exécution si déclarent `allowed-tools` ou hooks
- Correctif sécurité zstd

### 🛠️ Claude Code v2.1.319 (6 nov 2026)
- **MCP tasks background** : tâches longues en arrière-plan, Claude notifié à la fin
- `permissions.denyInsteadOfPrompting` : refus silencieux au lieu de prompt
- `/claude-api latency-optimize`

### 🔒 MCP Servers v2.4.0 (11 nov 2026)
- Release majeure avec correctifs sécurité critiques : filesystem (GHSA-p9cv-8g75-4xcg), git (GHSA-6hqx-gqrx-c5r2), fetch (GHSA-3rxj-6jhw-qfv7)
- **Action requise** : mettre à jour tous les serveurs MCP filesystem/git/fetch ASAP
- Nouvelles versions Python CalVer (2026.11.11)
- Filesystem : accès en lecture seule par répertoire via `--read-only-dir`

---

## 🏪 E-COMMERCE / SHOPIFY CLAUDE (focus Ivan)

### Shopify AI Toolkit — état des lieux
- Installation : `claude plugin install shopify-ai-toolkit@claude-plugins-official`
- Skills officiels couvrant : GraphQL Admin API, Functions, Polaris, Liquid, Hydrogen, CLI Shopify
- Dev MCP Shopify : `claude mcp add --transport stdio shopify-dev-mcp -- npx -y @shopify/dev-mcp@latest`
- **Composio Shopify MCP** via Rube (rube.app/mcp) : produits, commandes, clients, inventaire par prompt naturel

### K-Dense-AI claude-skills-mcp
- Serveur MCP qui charge 160+ skills officiels Anthropic via vector search
- GitHub : https://github.com/K-Dense-AI/claude-skills-mcp
- Activation : `uvx ...`

---

## 🧠 SKILLS PROPOSÉS (2 — review Ivan requis)

### 1. contextual-data-filter
**Dossier :** `claude-weekly/2026-11-16/skills-proposed/contextual-data-filter/SKILL.md`  
**Résumé :** Filtre les données d'outils MCP avant injection dans le contexte LLM. -50 à -75% de tokens sur tâches API-intensive.  
**Usage :** `CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1` + règles de filtrage JSON  
**Prérequis :** Claude Code v2.1.323+

### 2. n8n-shopify-lifecycle
**Dossier :** `claude-weekly/2026-11-16/skills-proposed/n8n-shopify-lifecycle/SKILL.md`  
**Résumé :** Cycle de vie complet des automations Shopify dans n8n par langage naturel. Commandes, produits, clients, marketing, stock.  
**Usage :** Extension du n8n skills officiel avec patterns Shopify spécifiques  
**Prérequis :** n8n MCP Instance-level + Claude Code 2.1.319+

---

## 📊 RÉSUMÉ EXÉCUTIF

**Semaine explosive sur Claude Code :**
- Fable 5.2 (1M contexte, -30% latence) est maintenant le modèle Fable par défaut dans Claude Code
- Code Mode (expérimental) change le paradigme : Claude code en JS pour ses propres outils → moins de tokens, moins de coûts
- n8n + skills officiels = automations e-commerce par langage naturel opérationnelles
- Alerte sécurité MCP v2.4.0 : mettre à jour filesystem/git/fetch servers sans attendre

**Pattern cross-semaine :**
> L'axe Skills + MCP converge vers un seul paradigme : Claude comme orchestrateur qui écrit et exécute son propre code d'orchestration, réduisant radicalement le bruit contextuel. Pour Ivan, l'implication concrète est une réduction significative des coûts API sur les tâches e-commerce intensives en données.

---

## 🔗 Sources principales

- Anthropic News : https://www.anthropic.com/news
- Claude Code Changelog : https://code.claude.com/docs/en/changelog
- MCP Servers Commits : https://github.com/modelcontextprotocol/servers/commits/main
- DEV Community Code Mode : https://dev.to/raxxostudios/claude-code-21323-adds-code-mode-for-javascript-tool-calls-3ibk
- Shopify AI Toolkit : https://www.get-ryze.ai/blog/claude-shopify-skills

---

*Généré automatiquement par veille-claude-weekly · 2026-11-16 · Analyses Gemini 2.5 Flash*
