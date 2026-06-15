# Veille Claude — Semaine du 2026-06-15

> **Run** : complet (nocturne autonome) · **Sources scannées** : 9 · **Candidats analysés** : ~24 · **Tokens (estim.)** : ~14k

> ⚠️ Reddit r/ClaudeAI injoignable cette session (fetch bloqué) — collecte basée sur YouTube + WebSearch + Anthropic. Doublons exclus vs digest 08/06 (Routines, Shopify AI Toolkit, Dynamic Workflows, `/reload-skills`) et veille-360 du 15/06.

---

## 🔥 Must-watch (max 5)

### 1. [Anthropic Skill Creator — créer ses skills interactivement](https://www.kdnuggets.com/anthropics-complete-guide-to-claude-skills-building)
- 📺 **Anthropic (officiel) via KDnuggets/Composio** · 📅 récent
- 🎯 **Thème** : Claude Skills
- 💡 **TL;DR** : Anthropic a lancé le **Skill Creator**, le moyen le plus simple de construire un skill Claude Code en mode interactif (il génère le SKILL.md + structure à ta place).
- ⭐ **Pourquoi pour toi** : tu maintiens 41+ skills à la main (TT/veravie/Tora) — le Skill Creator standardise la création et réduit les erreurs de structure.

### 2. [Agent Teams — orchestration multi-sessions](https://www.developersdigest.tech/blog/claude-code-agent-teams-subagents-2026)
- 📺 **Developers Digest / claudefa.st** · 📅 2026
- 🎯 **Thème** : Claude Code / agents
- 💡 **TL;DR** : une session = "team lead" qui coordonne via une task list partagée ; les "teammates" tournent chacun dans leur contexte et **communiquent entre eux** (≠ subagents qui ne reportent qu'au main). Expérimental.
- ⭐ **Pourquoi pour toi** : pour les gros chantiers (refonte homepage veravie, audit 360 TT) — dépasse la limite d'un seul contexte, là où tes subagents actuels ne se parlent pas.

### 3. [Top 5 Claude Code Skills that 10x productivity (2026)](https://www.youtube.com/watch?v=Xs942zwWfdY)
- 📺 **YouTube** · ⏱ court · 📅 2026
- 🎯 **Thème** : Claude Skills
- 💡 **TL;DR** : 5 skills Anthropic concrets pour accélérer le code/ops. *(analysé par Gemini → voir analyses/)*
- ⭐ **Pourquoi pour toi** : piocher des skills réutilisables prêts à adapter à ton workflow Shopify.

### 4. [The Ultimate Claude Code Guide — MCP, Skills & More](https://www.youtube.com/watch?v=uogzSxOw4LU)
- 📺 **YouTube** · 📅 2026
- 🎯 **Thème** : Claude Code (primitives)
- 💡 **TL;DR** : guide complet des primitives (CLAUDE.md, skills, subagents, slash commands, hooks, MCP). *(analysé par Gemini → voir analyses/)*
- ⭐ **Pourquoi pour toi** : consolidation — vérifier que tu exploites bien les 6 primitives sur tes projets.

### 5. [7 Rules for an Effective Claude Code Skill](https://uxplanet.org/7-rules-for-creating-an-effective-claude-code-skill-2d81f61fc7cd)
- 📺 **UX Planet — Nick Babich** · 📅 2026
- 🎯 **Thème** : Claude Skills (best practices)
- 💡 **TL;DR** : description = règle de routage ; code déterministe pour le déterministe (scripts > "fais attention") ; SKILL.md lean + companion files chargés à la demande ; **un seul job par skill** ; exemples concrets > règles abstraites ; **pas de mega-skills** (accuracy + composabilité en chute).
- ⭐ **Pourquoi pour toi** : audit direct — certains de tes skills sont des mega-skills (ex. token-optimize 2-en-1, boutique-360 orchestrateur) → candidats au découpage.

---

## ✅ Nice to watch

### [Hooks in Claude Code — Full Theory + Practical Use](https://www.youtube.com/watch?v=oo1oADOiVmM) — CampusX · 2026
Hooks = contrôle déterministe sur les events lifecycle (auto-format, blocage d'op dangereuses) → *renforcer tes garde-fous deploy*.

### [Top 10 Must-have Claude Skills 2026](https://composio.dev/content/top-claude-skills) — Composio
Directory de skills populaires (doc processing, marketing, sandbox E2B) → *inspiration catalogue*.

### [Claude Agent SDK en 2026](https://www.totalum.app/blog/claude-agent-sdk-totalum-2026) — Totalum
Quand passer du CLI au SDK pour shipper un agent → *si un jour tu industrialises une automation TT*.

### [Multi-agent orchestration for Claude Code](https://shipyard.build/blog/claude-code-multi-agent/) — Shipyard
Patterns d'orchestration multi-agents → *complément à Agent Teams*.

---

## ⏭ Skip (mention rapide)

- Claude Routines / Cowork (YouTube) — déjà couvert digest 08/06
- Shopify AI Toolkit (avril) — déjà couvert digest 08/06
- Claude Skills Tutorial O_z9vDLgvoY — déjà vu (seen-urls)
- "Claude Code 2026 Best Practices" (guSs80sefNo) — langue russe (hors fr/en)
- "My Claude Code Workflow 2026" (sy65ARFI9Bg) — daté janvier, generic

---

## 💡 Insights extraits (synthèse cross-sources)

- **Convergence best-practices skills** : un job/skill · description = routing rule · code déterministe · companion files · exemples > règles · anti-mega-skill. → audit de ton catalogue recommandé.
- **Agent Teams = nouvelle couche au-dessus des subagents** : orchestration multi-sessions qui se parlent, vs subagents isolés. Pertinent pour tes chantiers multi-étapes.
- **Skill Creator officiel** : Anthropic industrialise la création de skills → moins de SKILL.md écrits à la main.

---

## 📚 À capitaliser dans Obsidian

- [ ] **7 règles d'un skill efficace** → note `10-Concepts/claude-skill-rules.md`
- [ ] **Agent Teams vs subagents vs workflows** → note `20-Workflows/claude-orchestration-layers.md`

> Lancer `/obsidian-knowledge-base` pour capturer.

---

## 🚀 Pipeline complet exécuté

*(Phase 6 Gemini + Phase 7 skill-distiller lancées en parallèle — voir `claude-weekly/2026-06-15/analyses/` et `skills-proposed/`. Statut consolidé dans `_AU-REVEIL.md`.)*

---

## 🔁 Suite ?

A) Voir le transcript d'une vidéo Must-watch → me dire le numéro
B) Capitaliser dans Obsidian → `/obsidian-knowledge-base`
C) Auditer mes skills vs les 7 règles → me dire "audit skills"
