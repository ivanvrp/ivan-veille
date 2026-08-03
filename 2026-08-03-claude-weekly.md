# Claude Weekly — 2026-08-03

> Veille focus Claude / Claude Code / Skills / MCP · Semaine du 2026-07-07 au 2026-08-03  
> Routine : veille-claude-weekly · Analyses : Gemini 2.5 Flash (mode texte — quota vidéo épuisé)

---

## ACTUALITÉS ANTHROPIC CETTE PÉRIODE

### 🚀 Claude Opus 5 — Nouveau modèle (24 juillet 2026)

- Modèle ID : `claude-opus-5` — nouveau modèle Opus par défaut
- Fenêtre de contexte 1M tokens, 128K output
- Pricing : $5 input / $25 output par Mtok (moitié du prix Fable 5)
- 96% SWE-bench Verified — near-frontier pour le code
- Pensée (thinking) activée par défaut
- Disponible day-one dans Claude Code, API, Cowork, Claude.ai

### 📋 Fable 5 — Disponibilité subscription finalisée (20 juillet 2026)

- **Max & Team Premium** : Fable 5 inclus jusqu'à 50% des limites usage
- **Pro & Team Standard** : passage à crédits usage metered
- Fin des extensions d'accès temporaires — modèle définitif

### 🌐 MCP Spec 2026-07-28 — Release Candidate majeure

- Plus grande réécriture du spec MCP depuis le lancement
- **Sessions supprimées** du protocole (core stateless)
- OAuth et OIDC renforcés
- Extensions versionnées : Apps, Tasks, Embedded UI, Enterprise Auth, Private Network Tunnels
- +400M downloads/mois SDK (+4× cette année)

### 💳 Certifications Claude officielles (8 juillet 2026)

- 4 certifications via Pearson VUE + OnVUE + Credly
- Associate et Developer Foundations + 2 Architect (CCAR-F/CCAR-P)

### 💰 Sonnet 5 Pricing — Fin promo (31 août 2026)

- Pricing promo $2/$10 → standard $3/$15 à partir du 1er septembre

---

## CLAUDE CODE — RELEASES (2.1.202 → 2.1.220)

| Version | Date | Changement clé |
|---------|------|----------------|
| 2.1.220 | 25 juil | Corrections bugs / fiabilité |
| 2.1.219 | 24 juil | **Claude Opus 5** intégré · Subagents imbriqués profondeur 3 · `sandbox.network.strictAllowlist` · Hook `DirectoryAdded` |
| 2.1.218 | 22 juil | `/code-review` en subagent background · Fix Windows (chemins `\u`, copier-coller multiligne) |
| 2.1.217 | 21 juil | Autocomplétion emoji (`:heart:` → ❤️) |
| 2.1.216 | 20 juil | `sandbox.filesystem.disabled` · Fix performance coût quadratique |
| 2.1.215 | 19 juil | `/verify` et `/code-review` ne s'exécutent plus automatiquement |
| 2.1.214 | 18 juil | Tool `EndConversation` · Sécurité Bash/PowerShell · Restrictions `docker` redirect |
| 2.1.212 | 17 juil | `/fork` → session background · `/subtask` remplace subagents in-session · Limite 200 WebSearch/session · Limite 200 subagent spawns/session |
| 2.1.211 | 15 juil | Flag `--forward-subagent-text` pour stream-json |
| 2.1.210 | 14 juil | Compteur temps écoulé pour outils long-running |
| 2.1.208 | 14 juil | Mode lecteur d'écran `--ax-screen-reader` · `vimInsertModeRemaps` · `CLAUDE_CODE_PROCESS_WRAPPER` |
| 2.1.207 | 11 juil | Auto mode sur Bedrock/Vertex/Foundry sans opt-in |
| 2.1.206 | 9 juil | Suggestions chemins `/cd` · `/commit-push-pr` avec `remote.pushDefault` |
| 2.1.205 | 8 juil | Règle auto mode bloquant modif fichiers transcription · Fix Windows NTFS junctions |
| 2.1.203 | 7 juil | **Mode par défaut → "Manual"** · Dialogs `AskUserQuestion` sans auto-continue · Fix sessions background stagnantes |
| 2.1.202 | 6 juil | Setting "Dynamic workflow size" dans `/config` · Améliorations `--resume` |

**⚡ Signaux forts Claude Code cette période :**
- Opus 5 disponible nativement dans Claude Code
- Subagents imbriqués jusqu'à profondeur 3 (workflows complexes possibles)
- `/code-review` et `/verify` ne s'auto-lancent plus (comportement plus prévisible)
- Écosystème Skills : milliers de skills sur GitHub, marketplace Anthropic, repos communautaires

---

## MCP — Repo Officiel (modelcontextprotocol/servers)

- **29 juil** : Dépendances mises à jour (npm, uv, GitHub Actions CI)
- **14 juil** : Annotations sur tous les outils filesystem (sécurité renforcée)
- Spec 2026-07-28 = stateless core → implications pour tous les serveurs existants (migration à prévoir)

---

## MUST-WATCH — 4 vidéos · Score ≥ 7/10

### 1️⃣ System Card: Claude Opus 5 (Jul 2026) · Anthropic officiel
**URL :** https://www.youtube.com/watch?v=1twVQ4jQsnk  
**Score veille :** 9/10 · **Score utilité Ivan :** 6/10  
**TL;DR :** Anthropic présente le modèle Opus 5 — 1M tokens, 96% SWE-bench, pensée par défaut. Documente les capacités, limites et safeguards du modèle.  
**Pour Ivan :** Référence pour comprendre ce qu'Opus 5 peut (ou ne peut pas) faire avant de l'intégrer dans ses workflows Shopify.  
**Skill proposé :** Voir analyse complète → `claude-weekly/2026-08-03/analyses/1twVQ4jQsnk-opus5-system-card.md`

### 2️⃣ These 5 Claude Skills Run My Shopify Store · ~2 semaines
**URL :** https://www.youtube.com/watch?v=jjWZSEIohjk  
**Score veille :** 8/10 · **Score utilité Ivan :** 9/10  
**TL;DR :** 5 SKILL.md custom pour automatiser une boutique Shopify — segmentation clients, forecast stocks, agent CRO, emails, pricing.  
**Pour Ivan :** Le use-case le plus direct de toute la veille — à regarder en priorité pour TempleTwins et PURESOLE.  
**Skill proposé :** `shopify-skills-architect` → voir `claude-weekly/2026-08-03/skills-proposed/shopify-skills-architect/SKILL.md`

### 3️⃣ Claude Code (Opus 5) = Insane Website Workflow · 5 jours
**URL :** https://www.youtube.com/watch?v=PmNiSEAQVcc  
**Score veille :** 7/10 · **Score utilité Ivan :** 8/10  
**TL;DR :** Workflows complets de création et modification de sites avec Claude Code + Opus 5 — démo sur des cas concrets en développement web.  
**Pour Ivan :** Accélérer les modifs de thème Shopify sans développeur externe. Landing pages campagnes en minutes.  
**Skill proposé :** `shopify-theme-dev-agent` → voir `claude-weekly/2026-08-03/skills-proposed/shopify-theme-dev-agent/SKILL.md`

### 4️⃣ Claude Opus 5 + MCP = New King of Algo Trading · < 14 jours
**URL :** https://www.youtube.com/watch?v=Dbof8VUxP9E  
**Score veille :** 7/10 · **Score utilité Ivan :** 4/10  
**TL;DR :** Démonstration Opus 5 + Jesse MCP pour trading algorithmique ETH/USDT end-to-end — montre les capacités MCP orchestration complexe.  
**Pour Ivan :** Peu pertinent e-com, mais le pattern MCP end-to-end (data → analyse → action automatique) est transposable à Shopify.  
**Skill proposé :** Aucun

---

## NICE-TO-WATCH — 6 vidéos · Score 4-6/10

| # | Titre | URL | Score | Note |
|---|-------|-----|-------|------|
| 1 | Claude Code for Beginners — Skills, MCP, Subagents, Hooks (1H) | https://www.youtube.com/watch?v=8PVGtt7Fa7g | 6 | < 14j · Bon tour d'horizon complet |
| 2 | HIGGSFIELD MCP + Claude Opus 5 — What you can Actually Build | https://www.youtube.com/watch?v=MnPygZ3SIOs | 6 | Opus 5 + MCP créatif (vidéo AI) |
| 3 | Build a Shopify Store With AI (Claude Code Tutorial) | https://www.youtube.com/watch?v=YpMaB2S2xcs | 5 | Pertinent Shopify mais date inconnue |
| 4 | We Tested Claude Opus 5 — Frustrating with Flashes of Brilliance | https://www.youtube.com/watch?v=tqF8Ffv7tDs | 5 | Review critique Opus 5 · Équilibré |
| 5 | Claude Just Changed Completely: Here's How It Works (2026) | https://www.youtube.com/watch?v=bj04doEDOY4 | 5 | 3 semaines → borderline 14j |
| 6 | How to Use Claude to Build and Run a Shopify Store | https://www.youtube.com/watch?v=Ih5RapM8XKw | 5 | Shopify + Claude mais date inconnue |

---

## SKIP — Hors périmètre / Trop anciens / Doublons

- `sJVxwwaF0sU` — "Every New Claude Code Feature Explained" → mars 2026, trop ancien
- `YKIUt9ytxIE` — "Build MCP Server from Scratch" → juin 2026, déjà couvert
- `roPfcQHdUtY` — "Máster Claude Code 2026" → espagnol, hors langue fr/en
- `G3gUNZlGALU` — "Claude Code Agent View 2026" → juin 2026, trop ancien
- `3wArVlPvqAk` — "Master Claude Code MCP in 13 minutes" → avril 2026, trop ancien

---

## SKILLS PROPOSÉS — 2 propositions

> ⚠️ Ces skills sont des propositions issues des analyses. Ivan doit les reviewer manuellement avant déploiement.

### 1. shopify-skills-architect
**Source :** Vidéo jjWZSEIohjk  
**Description :** Génère des SKILL.md Shopify sur-mesure à partir d'un brief (type store, objectif, métriques).  
**Fichier :** `claude-weekly/2026-08-03/skills-proposed/shopify-skills-architect/SKILL.md`

### 2. shopify-theme-dev-agent
**Source :** Vidéo PmNiSEAQVcc  
**Description :** Agent Claude Code pour modifications thème Liquid Shopify — scan → plan → implémentation → diff → commit.  
**Fichier :** `claude-weekly/2026-08-03/skills-proposed/shopify-theme-dev-agent/SKILL.md`

---

## INSIGHTS CROSS-VIDÉOS

**Pattern récurrent :** L'écosystème Claude 2026 converge vers un seul modèle opérationnel : **Opus 5 (cerveau) + Skills (instructions métier) + MCP (accès systèmes externes) = agents autonomes par domaine.** Pour Ivan, la traduction concrète est : définir un SKILL.md pour chaque processus Shopify récurrent (CRO, stock, email), connecter le Shopify MCP, et laisser Opus 5 opérer en mode semi-autonome.

---

## TECHNIQUE — Notes de collecte

- `anthropic.com/news` : HTTP 403 → WebSearch fallback ✓
- `reddit.com/r/ClaudeAI` : HTTP 403 → WebSearch fallback ✓
- `releasebot.io` : HTTP 403 → données via changelog officiel ✓
- Gemini API vidéo : quota free tier épuisé (1ère requête vidéo ~250K tokens) → analyses en mode texte ✓
- Gemini modèle utilisé : `gemini-2.5-flash` (texte uniquement)

---

*Généré par veille-claude-weekly le 2026-08-03*
