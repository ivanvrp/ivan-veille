# Claude Weekly — 2026-10-12

> Routine veille-claude weekly · deep-dive Claude + Claude Code + MCP + Skills
> Focus solo founder e-commerce (TempleTwins / PURESOLE)

---

## 📣 Annonces Anthropic (7 derniers jours)

| Date | Annonce | Pertinence Ivan |
|------|---------|------------------|
| 2026-10-08 | 2026 Usage Policy update | Faible |
| 2026-10-07 | **Claude Haiku 5.5** — modèle le plus rapide/moins cher, 1M tokens context, $0.10/$0.50 /MTok | ⭐⭐⭐ Agents haute fréquence peu coûteux |
| 2026-10-06 | Cyber Verification Program élargi | Faible |
| 2026-09-28 | **Claude Sonnet 5.5** — plus rapide, moins cher que Sonnet 5 | ⭐⭐⭐ Workhorse principal |

→ **Action Ivan** : Tester Haiku 5.5 pour les tâches répétitives (génération descriptions produits, réponses clients). Prix divisé par 5 vs Sonnet pour des tâches simples.

---

## 🛠️ Claude Code Changelog (2-9 octobre 2026)

### v2.1.296 (9 oct) — highlights
- `autoCompactWindow` dans frontmatter subagents
- `CLAUDE_CODE_WORKFLOW_SUBAGENT_MODEL` : forcer tous les agents workflow sur un même modèle
- MCP tool descriptions : 2048 → **4096 chars** (plus de contexte disponible)
- `allow_large` dans l'outil Read (lire fichiers volumineux d'un coup)

### v2.1.295 (8 oct) — highlights
- **`onFailure: "block"`** pour les hooks command/HTTP (bloque l'action si hook échoue)
- Program Status Protocol (OSC 7501) — afficher état CC dans terminal
- `$.ui.notify` pour les mods

### v2.1.292 (6 oct) — highlights
- **`claude plugin install --marketplace <source>`** — install direct depuis marketplace
- Paramètre `effort` pour l'outil Agent
- `prompt.autocomplete` pour les mods

### v2.1.290 (5 oct) — highlights
- `claude attach <name>` — attacher à une session par nom partiel
- `/claude-api managed-agents-onboard` — onboarding Managed Agents
- Budget WebSearch : **100 appels/heure** (se recharge)

### v2.1.288 (2 oct) — highlights
- `$.ui.selection()` pour mods (texte sélectionné en mode plein écran)
- **`gh api` intégré** dans les sessions cloud sans GitHub CLI
- `--max-findings <n>|all` pour `/code-review`

→ **Key insight pour Ivan** : Le hook `onFailure: "block"` est un game-changer pour la sécurité en production Shopify — voir skill proposé `production-safety-policy`.

---

## 🔌 MCP officiel (modelcontextprotocol/servers)

- **Version 1.0.0 publiée** (11 oct 2026) — milestone majeur
- Fix filesystem server : gestion robuste de `roots/list` et appels en attente
- Annotations outil `fetch` améliorées
- NPM : chaque SDK MCP a dépassé **1 milliard de téléchargements** cumulés (TypeScript + Python)

---

## 📹 Sélection Vidéos

### 🔥 MUST-WATCH (5 vidéos)

#### 1. Ultimate Claude Code Tutorial: How to Use Claude Code for Beginners in 2026
- **URL** : https://www.youtube.com/watch?v=WdZjoMi6W7Y
- **Date** : ~5 oct 2026 (< 7 jours)
- **Score** : 9/10
- **Résumé Gemini** : Claude Code permet à Ivan de construire, modifier et déboguer des applications web, scripts et extensions localement via l'IA. Automatisation de tâches, prototypage rapide, maintenance autonome des plateformes Shopify. La vidéo couvre CLAUDE.md, Projects beta, et workflows agents.
- **Key insight** : Décomposer les problèmes complexes en étapes gérables → briefs ultra-spécifiques pour chaque task Claude Code
- **Durée** : ~30 min

#### 2. Watch This If You're Just Learning How to Use Claude Code in 2026
- **URL** : https://www.youtube.com/watch?v=ECQA6oOyfIk
- **Date** : Récente (< 14 jours estimé)
- **Score** : 9.5/10
- **Résumé Gemini** : Claude Code + ScaleKit pour construire des agents IA avec auth multi-tenant. Montre comment un solo founder peut déployer des agents qui agissent directement sur ses systèmes (Shopify, CRM) avec permissions déléguées et sécurisées. Architecture multi-agents sur worktrees isolés.
- **Key insight** : Pattern ScaleKit = couche auth réutilisable entre agents Claude → évite de re-gérer les tokens API à chaque fois
- **Durée** : estimée 20-30 min

#### 3. Build a Shopify Store With AI (Claude Code Tutorial)
- **URL** : https://www.youtube.com/watch?v=YpMaB2S2xcs
- **Date** : Récente (estimée < 14 jours)
- **Score** : 9/10
- **Résumé Gemini** : Démontre comment utiliser Claude Code avec Shopify pour automatiser les tâches e-commerce — création produits (CSV → Shopify), gestion remises automatiques, création de landing pages listicles, analyse des ventes avec charts. Met en lumière l'importance d'un "Master Prompt" stocké dans CLAUDE.md.
- **Key insight** : Le "Master Prompt" dans CLAUDE.md = connaissance métier persistante → Claude comprend ton shop sans re-expliquer à chaque session
- **Durée** : estimée 20-35 min

#### 4. I Mapped Every Claude Code Concept So You Don't Have To (Full 2026 Roadmap)
- **URL** : https://www.youtube.com/watch?v=9JoIpWgAsZ8
- **Date** : Récente (< 14 jours estimé)
- **Score** : 9/10
- **Résumé Gemini** : Roadmap complète de l'écosystème Claude AI (Chat, Code, Desktop, Design). Couvre agents, hooks, skills, MCP, workflows, et notamment les "loops" comme pattern d'automatisation continue (veille, monitoring, tâches répétitives).
- **Key insight** : Le pattern "loop" de Claude Code = monitoring automatique de KPIs boutique (stock, prix concurrents, avis clients) sans intervention humaine
- **Durée** : estimée 30-45 min

#### 5. Hooks in Claude Code
- **URL** : https://www.youtube.com/watch?v=IkaPHiMDazM
- **Date** : ~45 jours ago (borderline — inclus car contenu technique fondamental)
- **Score** : 9/10
- **Résumé Gemini** : Les hooks Claude Code (PreToolUse, PostToolUse) permettent d'exécuter des commandes déterministes à des moments précis du cycle de vie. Pratique : auto-format Liquid/JS, blocage commandes dangereuses, quality gates avant push. `onFailure: "block"` (v2.1.295) les rend encore plus puissants.
- **Key insight** : Hook `PreToolUse` sur `Bash` = filet de sécurité ultime pour dev Shopify en production
- **Durée** : estimée 15-25 min

---

### 👍 NICE (6 vidéos)

| # | Titre | URL | Score | Raison |
|---|-------|-----|-------|--------|
| 1 | Claude Code Full Course 2026 (luxury e-commerce storefront) | https://www.youtube.com/watch?v=u2QqWkMv3Lg | 6/10 | Sept 25 (borderline) — storefront de luxe, bon pour inspiration |
| 2 | FULL Claude Code Tutorial For Beginners in 2026! | https://www.youtube.com/watch?v=X_zVY3-mbM8 | 5/10 | Généraliste débutants |
| 3 | How to Create an Ecommerce Website with Claude Code | https://www.youtube.com/watch?v=KLYWjuOqMO8 | 6/10 | E-commerce direct, date inconnue |
| 4 | Hooks in Claude Code — Full Theory + Practical Use | https://www.youtube.com/watch?v=oo1oADOiVmM | 5/10 | Complément hooks, potentiellement ancien |
| 5 | Claude Code Hooks — Explained & Demoed | https://www.youtube.com/watch?v=3Y4XQ2obPIo | 5/10 | Démo hooks |
| 6 | Build a Shopify Store With AI (Claude Code Tutorial — FR) | https://www.youtube.com/watch?v=yPhD4nMTywU | 6/10 | Version espagnole, 8 usages réels Shopify |

---

### ⏭️ SKIP

- "Claude Ai Promo Code (Updated 2026)" — hype/inutile
- "AI Summer 2026" — 125 jours, trop vieux
- Vidéos cours longs > 4h — not worth time vs. action

---

## 🔌 Shopify × Claude (Signal fort cette semaine)

**Claude Commerce Agents** (open-source, publié 2 sept 2026) :
- Storefront agent : guide les acheteurs dans le checkout
- Merchant agent : gestion store via langage naturel
- Connecteur Shopify officiel : create/update produits, orders (read-only), analytics, discounts, collections

**Guides pratiques notables** :
- [Claude for Shopify: 12 Workflows](https://www.get-ryze.ai/blog/claude-for-shopify-12-workflows-for-store-owners)
- [Claude Code Setup for Shopify](https://www.fudge.ai/guides/shopify-ai-toolkit-claude-code-setup/)
- [Connect Claude and Shopify Directly](https://rubydigitalagency.com/claude-and-shopify-automation-reporting-guide/)

---

## 🧰 Skills Proposés (3)

> ⚠️ Aucun skill n'est déployé automatiquement. Review manuel d'Ivan requis.

### 1. `shopify-product-launcher`
**Dossier** : `claude-weekly/2026-10-12/skills-proposed/shopify-product-launcher/SKILL.md`
**Description** : Lance des produits Shopify depuis CSV ou description vocale. Génère descriptions SEO, gère variantes, images, stocks. Output : produits en DRAFT.
**Impact** : 2-4h → 15min par lancement collection

### 2. `ecom-multichannel-campaign`
**Dossier** : `claude-weekly/2026-10-12/skills-proposed/ecom-multichannel-campaign/SKILL.md`
**Description** : Brief produit → 15 assets marketing cohérents (3× Instagram, TikTok script, email, 2× Meta Ads). Tout en un run.
**Impact** : 6-8h copywriting → 30min review

### 3. `production-safety-policy`
**Dossier** : `claude-weekly/2026-10-12/skills-proposed/production-safety-policy/SKILL.md`
**Description** : Configure les hooks Claude Code pour bloquer commandes destructives, protéger `.env`, auditer les modifications. `onFailure: "block"` v2.1.295.
**Impact** : Zéro incident prod Shopify accidentel

---

## 💡 Insight cross-vidéos

**Pattern récurrent cette semaine** : Le "CLAUDE.md comme mémoire métier persistante" — toutes les vidéos avancées montrent que les meilleurs setups stockent le contexte complet du business dans CLAUDE.md (stack Shopify, tone of voice, règles métier, credentials safe). C'est la fondation qui multiplie la pertinence de TOUTES les interactions suivantes.

**Action recommandée pour Ivan** : Créer un `CLAUDE.md` maître dans chaque repo (TempleTwins, PURESOLE) décrivant : stack technique, persona marque, règles de gestion des produits, contacts clés, et accès API. Une demi-journée d'investissement = mois de gain de contexte.

---

## 📊 Stats de la run

| Métrique | Valeur |
|----------|--------|
| Sources collectées | 7 |
| Vidéos candidates évaluées | 14 |
| Must-watch retenus | 5 |
| Nice-to-watch | 6 |
| Skip | 3 |
| Analyses Gemini tentées | 5 |
| Analyses Gemini réussies | 5 |
| Skills proposés | 3 |
| Nouvelles URLs dans seen-urls.txt | 11 |

---

*Généré par veille-claude-weekly · 2026-10-12*
