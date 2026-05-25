# Veille Claude Weekly — 2026-05-25

> Vidéos analysées : 4 · Skills proposés : 3 · Tokens Gemini : ~12k

---

## 🔥 Must-watch (4)

### 1. [Stop Using Claude's /goal Feature | Here's What Works](https://www.youtube.com/watch?v=XzlSn1M6WKw) — Eric Tech · ~12 min · 18 mai 2026

- 💡 **TL;DR** : `/goal` souffre du "context rot" sur les longues tâches — quand le contexte grossit, la précision chute. La solution : un pattern Orchestrateur → instances Claude headless (`claude -p`) éphémères, chacune avec un contexte propre, gérant leur état dans GitHub Projects.
- ⭐ **Pourquoi Ivan** : Directement applicable pour automatiser les audits qualité de TempleTwins/PURESOLE sans perdre en précision après 30+ actions. Le pattern headless est la clé pour les workflows longs (SEO batch, QA e-commerce, scraping produits).
- 🎯 **Top concept** : [0:47] Pattern Orchestrator → Claude Headless — chaque `claude -p "tâche"` s'exécute et se termine proprement, "True Zero-Rot State".
- 📦 **Skill proposé** : `ecom-qa-manager`
- 🔗 [Analyse Gemini complète](claude-weekly/2026-05-25/analyses/XzlSn1M6WKw-stop-using-goal.md)

---

### 2. [Claude Goal Command Explained](https://www.youtube.com/watch?v=2qlZsi8eh3s) — inconnu · ~4 min · 21 mai 2026

- 💡 **TL;DR** : Guide pratique pour utiliser `/goal` correctement : activer Auto-Approve, formuler une "ligne d'arrivée vérifiable" mesurable, et toujours ajouter un hard cap (`stop after 20 turns or 30 minutes`) pour ne pas brûler ses tokens.
- ⭐ **Pourquoi Ivan** : Les templates verbatim sont directement réutilisables pour automatiser le classement des factures PURESOLE, la standardisation des fiches produits TT, et le tracking des commandes dropship.
- 🎯 **Top concept** : [02:18] Règle "ligne d'arrivée vérifiable" — le Boss agent ne peut valider que ce qui est observable (fichier CSV créé, dossier vide, count de lignes > N).
- 📦 **Skill proposé** : `ecom-finance-reconciler`
- 🔗 [Analyse Gemini complète](claude-weekly/2026-05-25/analyses/2qlZsi8eh3s-goal-command-explained.md)

---

### 3. [Claude Code Agent View IS INSANE! Huge New Update Introduces /goal, sessions, & More!](https://www.youtube.com/watch?v=-jINRoST0mk) — inconnu · ~15 min · 11-12 mai 2026

- 💡 **TL;DR** : Tour complet des nouveautés Claude Code 2.1.139 : Agent View (`claude agents`) pour superviser toutes les sessions en parallèle, background sessions (`claude --bg`), `/goal` en prod, et compaction silencieuse des prompts. Claude Code devient un vrai OS d'agents.
- ⭐ **Pourquoi Ivan** : En tant que solo founder, l'Agent View change tout : lancer 3 agents en parallèle (descriptions produits + SEO + debug) et surveiller depuis un écran. Commande clé : `gh issue view 3 | claude -p "fix this" --allowedTools "Read,Write"`.
- 🎯 **Top concept** : [04:46] Background anything — `claude --bg "tâche"` pour déporter n'importe quelle tâche et y revenir plus tard avec `/resume`.
- 🔗 [Analyse Gemini complète](claude-weekly/2026-05-25/analyses/jINRoST0mk-agent-view-insane.md)

---

### 4. [I Mapped Every Claude Code Concept So You Don't Have To (Full 2026 Roadmap)](https://www.youtube.com/watch?v=9JoIpWgAsZ8) — inconnu · ~20 min · 18 mai 2026

- 💡 **TL;DR** : Cartographie exhaustive de l'écosystème Claude Code 2026 : Skills, Agents, MCP, Hooks, Plugins — quand utiliser quoi, comment les combiner. Présente aussi des agents "revenus passifs" (content faceless, lead gen, repurposing) directement applicables à l'e-commerce.
- ⭐ **Pourquoi Ivan** : Le pattern "Content Repurposing Agent" est parfait pour TT/PURESOLE : transformer un article de blog en 10 posts Instagram + 3 TikToks + 1 thread X sans manipulation manuelle.
- 🎯 **Top concept** : [11:48] Agents pour revenus passifs — automatiser création contenu, lead gen, repurposing, intégrations. Blueprint concret pour solo founder.
- 📦 **Skill proposé** : `ecom-content-autopilot`
- 🔗 [Analyse Gemini complète](claude-weekly/2026-05-25/analyses/9JoIpWgAsZ8-claude-concept-roadmap.md)

---

## ✅ Nice to watch (4)

- **[Build your first AI agent (Claude Code)](https://www.youtube.com/watch?v=o1u_mEELKOQ)** — ~2 semaines · Fondamentaux construction agent Claude Code from scratch. Bien pour comprendre l'architecture sous-jacente.

- **[Claude Code Just Got an Agent Dashboard](https://www.youtube.com/watch?v=ZAaxx3qyT8g)** — ~2 semaines · Focus spécifique sur l'interface `claude agents`. Complément visuel du must-watch #3.

- **[9 Claude Code Plugins to Build 10x Faster](https://www.youtube.com/watch?v=sBF3UumkL4Y)** — date incertaine · Couvre des plugins méconnus : Caveman (réponses concises), Morph (opérations coûteuses), Code Burn (analyse usage tokens). Utile pour optimiser la conso tokens.

- **[Claude Goal Command Explained in 45 Seconds](https://www.youtube.com/shorts/slf3MIYADy4)** — 4 jours · Version ultra-courte du must-watch #2. Parfait pour mémoriser la formule hard cap.

---

## ⏭ Skip

- **How to Install Claude Code AI Desktop on Windows 10/11** (wkOLu5AYVrM) — guide installation de base, pas pertinent
- **Full Claude Code Tutorial for Non-Technical Beginners** (bqJzIWAEn40) — 4 semaines, contenu introductif
- **Top 5 Claude Code Skills That Will 10x Your Productivity** (Xs942zwWfdY) — mars 2026, trop vieux
- **Better With This Setup (CLAUDE.md + Skills + MCPs)** (pBHKTojO1YY) — mars 2026, trop vieux
- **Claude Code Full Course 12 Hours** (05aY2LRIC3s) — format trop long, pas de nouveauté

---

## 🚀 Skills proposés (à valider manuellement)

### `ecom-qa-manager` — [détail](claude-weekly/2026-05-25/skills-proposed/ecom-qa-manager/SKILL.md)
Orchestre un QA automatisé de boutique Shopify via BFS + instances Claude headless éphémères. Résout le context rot pour les audits longs. Utile après chaque déploiement TT/PURESOLE.

### `ecom-finance-reconciler` — [détail](claude-weekly/2026-05-25/skills-proposed/ecom-finance-reconciler/SKILL.md)
Classement/renommage automatisé de factures fournisseurs, rapports de vente et tracking commandes dropshipping via `/goal` avec hard cap. Économise 2-3h/semaine d'admin pour PURESOLE.

### `ecom-content-autopilot` — [détail](claude-weekly/2026-05-25/skills-proposed/ecom-content-autopilot/SKILL.md)
Analyse tendances sociales + génère planning contenu complet (textes + prompts visuels) pour Instagram/TikTok/YouTube Shorts, adapté au ton TempleTwins (streetwear) ou PURESOLE (dropship).

---

## 💡 Insights cross-vidéos

- **Le /goal command domine la semaine** (3 vidéos sur 4) — c'est la feature du moment, mais la nuance critique est que `/goal` seul souffre de context rot sur les tâches longues → le vrai pattern pro est Orchestrateur + instances headless `claude -p` éphémères.
- **Claude Code = OS d'agents solo founder** — avec Agent View + background sessions + /resume + /goal + plugin marketplace, Anthropic a construit une infra complète pour gérer plusieurs workflows en parallèle sans équipe. C'est le stack solo founder de 2026.
- **Hard cap = best practice universelle** — toutes les vidéos sur /goal convergent : `Stop after N turns or X minutes` dans CHAQUE prompt autonome, sans exception.
- **Changelog semaine (v2.1.139→2.1.150)** : `/code-review` avec niveaux d'effort + `--comment` pour PR GitHub (remplace `/simplify`), `/usage` per-category, background pinned sessions, `claude agents --json` pour scripting.

---

## 📋 Annexe Changelog

Highlights Claude Code v2.1.139→2.1.150 (11-23 mai 2026) :

| Version | Date | Feature clé |
|---------|------|-------------|
| 2.1.139 | 11 mai | **Agent View** (`claude agents`) + **`/goal` command** |
| 2.1.142 | 14 mai | Fast mode → Opus 4.7 · Root SKILL.md dans plugin = skill auto-surfacé |
| 2.1.144 | 19 mai | `/resume` background sessions · `/model` par session |
| 2.1.145 | 19 mai | `claude agents --json` pour scripting · `/plugin` browse amélioré |
| 2.1.147 | 21 mai | **`/code-review`** (niveaux effort + `--comment` GitHub PR) |
| 2.1.149 | 22 mai | `/usage` per-category · `/diff` scrollable · GFM checkboxes |
