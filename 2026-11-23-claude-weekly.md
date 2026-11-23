# Claude Weekly — 2026-11-23

> Deep-dive hebdomadaire Claude / Claude Code / Skills / MCP  
> Routine : veille-claude-weekly | Focus : solo founder e-commerce

---

## Résumé exécutif

Semaine intense côté Anthropic : IPO clôturée le 20 novembre, lancement de Claude Fable 5.2 + Mythos 5.2 le 9 novembre, et une vague de releases Claude Code (v2.1.326→2.1.330). Le Code Mode expérimental est **la** feature à tester immédiatement. MCP v2.5.0 sorti le 18 novembre avec fix mémoire critique.

---

## 🔥 MUST-WATCH (2 vidéos)

### 1. Rethinking Claude Code Best Practices — Lydia Hallie, Anthropic
**URL** : https://www.youtube.com/watch?v=vlfCjWuv4es  
**Date** : 11 novembre 2026 | **Score** : 9/10 | **Source** : Anthropic officiel  
**TL;DR** : Les modèles améliorés (Opus 5.5, Fable 5.2) permettent de passer en mode "out of the loop" — Claude tourne en autonomie pendant des heures. L'humain devient orchestrateur, pas exécuteur.

**Key takeaways pour Ivan :**
- `claude.md` = uniquement ce que Claude ne peut pas déduire du code (éliminer le reste)
- `/doctor prompt-audit` pour optimiser ses instructions
- `settings.json` : configurer `hard_deny` pour bloquer `git reset --hard`, `.env`, APIs tierces
- Cloud sessions = Claude tourne même laptop fermé, secrets réseau sécurisés
- Hooks avec codes de sortie : `exit 2` = Claude revient en arrière et corrige

**Skills proposés** : EcomGuardRails, ShopifyFlowHelper, PromptAuditorEcom

---

### 2. Code Mode Is The Biggest Claude Code Upgrade In a LONG Time
**URL** : https://www.youtube.com/watch?v=ziDQNS3usiA  
**Date** : 19 novembre 2026 | **Score** : 8/10  
**TL;DR** : Code Mode (expérimental) = Claude écrit un script unique qui exécute Bash + Read + Edit en parallèle. Moins de round-trips, moins de tokens, plus de vitesse.

**Key takeaways pour Ivan :**
- Activer : `export CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1`
- Idéal pour : modifier plusieurs fichiers .liquid à la fois, analyser des CSV produits, corriger du SEO en batch
- Le contexte ne reçoit que les métriques clés (ex: `{ edited: 12, tests: "PASS" }`)
- Statut expérimental → tester sur des tâches non-critiques d'abord

**Skill proposé** : CodeModeOrchestrator

---

## 👍 NICE-TO-WATCH (7 vidéos)

| # | Titre | URL | Date | Score |
|---|-------|-----|------|-------|
| 1 | give me 11 minutes, I'll give you Claude Code for free, forever | https://www.youtube.com/watch?v=u5UR_A8vX2Q | 22 nov | 6/10 |
| 2 | Anthropic acaba de hacer el MAYOR cambio en Claude Code | https://www.youtube.com/watch?v=ya1zjTuKYRc | 21 nov | 6/10 |
| 3 | Claude Code for Free With 10 Billion Tokens a Month💀 | https://www.youtube.com/watch?v=mnrCSF__194 | 22 nov | 5/10 |
| 4 | You missed these CRAZY Claude Code Upgrades | https://www.youtube.com/watch?v=o4A03TVuadg | 9 nov | 5/10 |
| 5 | The Best Way to Run Claude Code in 2026 | https://www.youtube.com/watch?v=73DrNNvEKH0 | 14 nov | 5/10 |
| 6 | How to Use Claude Code for FREE with Ollama | https://www.youtube.com/watch?v=NkkAwdm2k7s | 10 nov | 5/10 |
| 7 | Claude Code & Claude AI Full Course 2026 (No Coding Needed) | https://www.youtube.com/watch?v=hVRjUvjDQwE | 12 oct | 4/10 |

---

## ⏭ SKIP

- Contenu hors-focus (non-Claude) ignoré
- Vidéo cours Oct 12 : trop ancienne (>14j), déjà couverte

---

## 📰 Annonces Anthropic (semaine)

| Date | Annonce |
|------|---------|
| 20 nov 2026 | **IPO clôturée** avec exercice intégral de l'option de surallocation |
| 18 nov 2026 | **Claude Code v2.1.330** : mod easel (graphiques), /fork, /workflows, durée /loop portée à 30j |
| 19 nov 2026 | **Claude Code v2.1.329** : /tasks liste les wakeups /loop, /code-review examine toute la branche |
| 17 nov 2026 | **Claude Code v2.1.327** : `claude mcp add-json <nom> -` pour stdin, /status liste les erreurs de config |
| 9 nov 2026 | **Claude Fable 5.2 + Mythos 5.2** : modèles top-tier pour tâches techniques complexes |

---

## 🔌 MCP Updates

| Date | Update |
|------|--------|
| 18 nov 2026 | **MCP v2.5.0** : fix critique mémoire (locks libérés quand le serveur HTTP s'arrête), Python CalVer 2026.11.18 |
| 18 nov 2026 | Merge PR #5590 : fix sécurité git GHSA-r2q8-f657-4r56 |

---

## 🛒 Claude × Shopify (contexte)

- Shopify AI Toolkit (MCP server officiel) : toujours la référence pour connecter Claude Code à l'Admin API Shopify
- Anthropic commerce agents blueprint (sept 2026) : shopping agent + merchant agent open-source
- Shopify Claude connector app (mai 2026) : gestion store depuis Claude directement

---

## 🚀 Skills proposés (3)

| Skill | Description | Source |
|-------|-------------|--------|
| **EcomGuardRails** | Génère settings.json avec deny rules pour projets Shopify | Lydia Hallie best practices |
| **ShopifyFlowHelper** | Structure sessions orchestrées pour objectifs métier Shopify | Lydia Hallie best practices |
| **CodeModeOrchestrator** | Scripts parallèles Code Mode pour tâches multi-fichiers | Code Mode upgrade video |

> ⚠️ Ces skills sont des PROPOSITIONS. Ivan doit les valider et les déployer manuellement.  
> Fichiers dans : `claude-weekly/2026-11-23/skills-proposed/`

---

## 💡 Insight cross-vidéos

Le pattern récurrent cette semaine : **Claude passe du "copilote" à l'"agent autonome"** — les mises à jour (Code Mode, Cloud sessions, Auto mode, Hooks) convergent toutes vers un Claude qui tourne en autonomie pendant des heures, avec des garde-fous configurables, pendant qu'Ivan se concentre sur la stratégie.

---

## Méta

- **Must-watch** : 2 | **Nice** : 7 | **Skip** : 1
- **Analyses Gemini** : 2/2 réussies
- **Skills proposés** : 3
- **Anti-doublons** : toutes URLs ajoutées à seen-urls.txt
