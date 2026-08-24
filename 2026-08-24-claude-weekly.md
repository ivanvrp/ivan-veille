# Claude Weekly — 2026-08-24

> Deep-dive Claude / Claude Code / Skills / MCP · Semaine du 2026-08-17 au 2026-08-24
> Analyses Gemini 2.5 Flash sur 5 vidéos YouTube must-watch · 5 skills proposés

---

## ACTUALITÉS ANTHROPIC CETTE SEMAINE

### 🌐 Claude Cowork débarque dans Chrome side panel (12 août)
- Le Chrome side panel de Claude in Chrome devient une **session Cowork** complète
- Skills, plugins et connecteurs **fonctionnent enfin dans le navigateur** sans setup
- Sessions synchronisées : commencer dans un tab → finir sur desktop/web/mobile
- Dispo aujourd'hui sur Max/Team, rollout Pro sur les prochaines semaines
- Cas d'usage démo Anthropic : **month-end close** en lisant les onglets de factures ouverts
- URL : https://claude.com/blog/cowork-chrome-side-panel

### 🎓 Claude Academy — Hub d'apprentissage (20 août)
- Cours, tutoriels, badges, recommandations personnalisées
- Focus : "delegate, verify, and learn with Claude"
- Positioning : fluency AI pratique, mindsets d'apprentissage élargis

### 🤖 Claude Tag ("read even more of the room") — 13 août
- Améliorations contextuelles côté @claude Slack
- Prend en compte plus large de la conversation, moins d'ambiguïtés

### 💰 Rappel pricing : promo Sonnet 5 termine 31 août
- Passe de $2/$10 → **$3/$15 par Mtok** au 1er septembre
- Fenêtre étroite pour finir les runs batch coûteux

### 🔌 Skills API + Files API GA (Claude Platform)
- Plus besoin du header `skills-2025-10-02` beta
- Computer use + browser use aussi GA
- Skills API et Files API dispo aussi via Microsoft Foundry

### 🛡️ Managed Agents : gouvernance renforcée
- **Session budgets**, advisor models, **inference geo pinning**
- **GitHub-hosted skills** : plus besoin de copier les skills, référencer un repo
- Admin API user-management GA (plus besoin de `ce-user-management-2026-07-13` header)

### ⚙️ Claude Code — Releases majeures cette semaine

| Version | Date | Changement clé |
|---------|------|----------------|
| 2.1.241 | 23 août | Bug fixes |
| 2.1.240 | 22 août | Bug fixes |
| 2.1.239 | 21 août | **`/claude-api upgrade` skill** (migration anthropic 0.x→1.x) · MCP elicitation scroll · fix `.md` avec BOM |
| 2.1.238 | 20 août | **`headersHelper` marketplaces** (short-lived tokens) · `--defer-shutdown-max-min` self-hosted runners |
| 2.1.237 | 20 août | **Output style "Concise" built-in** (leads with results, no preamble) |
| 2.1.236 | 19 août | **`ANTHROPIC_DEFAULT_MODEL`** env var · `notify_when_idle` in `SendMessage` |
| 2.1.235 | 18 août | Spellcheck opt-in (aspell/hunspell) · Agent tool ne suggère plus des agents indisponibles |
| 2.1.234 | 17 août | **GitLab MR badges** dans footer · `CLAUDE_CODE_PROJECT_DIR_NAME` · **auto-continue quand claude.ai reset le limit** |
| 2.1.233 | 14 août | GitLab MR support dans `--worktree` · **`forward_user_identity`** apps gateway · `CLAUDE_CODE_TOOL_MEMORY_LIMIT` (cgroup Linux) |
| 2.1.232 | 13 août | **Subagent forking par défaut ON** (inherit conv + cache) · **`@` mentions pour SendMessage** · `crossSessionInbound` (accept/hold/refuse) · **GitLab dans plugin marketplaces** · Fable 5 dans `/advisor` |

**Changements critiques cette semaine :**
1. **Cowork dans Chrome (12 août)** — game-changer pour tâches admin/finance
2. **Subagent fork par défaut** (2.1.232) — inherit context, plus rapide, moins de re-briefing
3. **`@name` mentions cross-session** (2.1.232) — ping ta session Slack Claude depuis Claude Code
4. **Output style Concise** (2.1.237) — activer si tu payes les tokens de tes réponses
5. **GitLab MR support** (2.1.233-234) — pas ta stack, mais montre l'expansion post-GitHub

### 🔌 MCP — Spec 2026-07-28 supportée
- Stateless core, OAuth/OIDC renforcés, extensions versionnées (Apps + Tasks)
- Dépôt officiel modelcontextprotocol/servers : PR #4663 (18 août) — pin `mcp>=1.29.0,<2` sur fetch/git/time (compat MCP 2.0.0)
- Dependabot bumps massifs (29 juillet) : gitpython, mcp, pydantic-settings, hono, body-parser

---

## MUST-WATCH — 5 vidéos analysées Gemini

### 1️⃣ Matt Pocock's Claude Code Skills Beat Superpowers Now
**URL :** https://www.youtube.com/watch?v=8D8ewFBJfFM
**Score sélection :** 9/10 · **Score Gemini utilité Ivan :** 9/10 · Date : ~2 semaines

**TL;DR :** Matt Pocock (13M downloads) publie une suite de **skills modulaires** qui remplace les frameworks agentiques monolithiques (Superpowers, GStack). Chaque skill fait UNE chose : `grill-me` interviewe l'user pour le contexte, `/to-spec` gèle les décisions dans un `SPEC.md` sans code, `/to-tickets` découpe par **feature** (pas par layer), `/implement` en TDD strict red-first, `/code-review` avec checklist 12 code smells de Fowler.

**Highlights clés :**
- **[00:25] `grill-me`** = 2ème skill le + téléchargé. 5 règles : RELENTLESSLY / DECISION TREE / ONE AT A TIME / RECOMMEND ONE / DO NOT ACT
- **[07:11] `/to-spec`** = spec **sans code** (QUOI, pas COMMENT). "HOW pourrit, WHAT perdure"
- **[08:39] "Slice by Feature, Not by Layer"** — 1 ticket = login complet (UI+API+DB), pas "ajoute un endpoint"
- **[10:04] TDD "Red First. Always."** — écris le test qui échoue avant tout code
- **[16:21] "Deep is Not One Giant Room"** — encapsuler logique dans `processCheckout()` unique = 1 porte à comprendre pour l'IA
- **[17:48] "Deletion Test"** — supprime la fonction ; si rien ne casse = coquille vide, à virer
- **[21:11] Opus 5** — Anthropic a supprimé **80% du system prompt** ; les skills futurs sont minimaux, mots-guides > garde-fous

**Commandes verbatim :** `npx skills add mattpocock/skills` · `grill-me` · `/to-spec` · `/to-tickets` · `/implement` · `/tdd` · `/code-review` · `/writing-for-agents` · `/improve-codebase-architecture`

**Patterns Ivan :**
- Utiliser `grill-me` avant chaque nouvelle feature Shopify pour freezer le WHAT
- `/to-spec` → fiche technique claire à envoyer aux freelances
- Slice by feature = "customiseur t-shirt complet" pas "endpoint POST /customize"
- Deletion Test sur le code TempleTwins actuel : combien de helpers sont des coquilles vides ?

**→ Skill proposé :** `solo-founder-ideation` (voir `skills-proposed/`)

---

### 2️⃣ Claude Cowork is now your Chrome side panel
**URL :** https://www.youtube.com/watch?v=C-5wF6tkQ2Q
**Score sélection :** 8/10 · **Score Gemini utilité Ivan :** 10/10 · Date : 12 août

**TL;DR :** Démo Anthropic officielle du **month-end close automatique** : Claude lit les onglets Chrome ouverts (factures Stripe, Shopify, apps SaaS), extrait chaque montant, détecte les anomalies (retards, renouvellements annuels), et pousse le tout dans une Google Sheet. Le side panel Cowork = accès contextuel sans quitter le browser.

**Highlights clés :**
- **[00:00] Chrome side panel = session Cowork complète** (skills + plugins + connecteurs actifs)
- **[00:09] Prompt en langage naturel** — pas de setup complexe
- **[00:16] Traitement visuel multi-tabs** — Claude "lit" chaque onglet
- **[00:26] Alertes anomalies** — factures en retard, hausse coûts, renouvellements

**Prompt verbatim :** `Run my month-end close on these tabs. Pull each invoice and get it into the monthly report.`

**Patterns Ivan :**
- Consolidation dépenses multi-plateformes (Meta Ads + TikTok Ads + Shopify + apps)
- Analyse marges par produit en croisant orders Shopify + factures fournisseur
- Gestion litiges transporteur : Claude synthétise 3 onglets (email fournisseur + tracking + commande)
- Détection anomalies financières (hausse CPA inattendue, sub apps qui explose)
- Préparation compta trimestrielle → cadeau au comptable

**→ Skill proposé :** `rapport-financier-ecom` (voir `skills-proposed/`)

---

### 3️⃣ How to Use Multi-Agent Workflows in Claude Code: Skills, Subagents & Handoffs (2026)
**URL :** https://www.youtube.com/watch?v=qiDalcMeBFk
**Score sélection :** 8/10 · **Score Gemini utilité Ivan :** 9/10 · Date : < 14j

**TL;DR :** Pattern **Navigator/Driver TDD** avec 2 subagents Claude Code : le Navigator plan + écrit les tests échoués (RED), le Driver écrit le code qui passe (GREEN). Communication via fichiers markdown de handoff (`.claude/handoff/navigator.md`, `driver.md`) pour traçabilité complète. Skill orchestrateur triggered par "implement", "tdd", "pair program".

**Highlights clés :**
- **[00:35] Navigator** = planificateur, écrit tests, NE CODE JAMAIS
- **[01:00] Driver** = implémenteur, écrit code, N'ÉCRIT JAMAIS DE TESTS
- **[01:10] Skill `driver-navigator-tdd`** orchestre PLAN → RED → GREEN → REVIEW → REFACTOR
- **[01:37] Handoff via markdown files** — audit trail complet, Ivan peut lire à tout moment

**Prompt verbatim :**
```
MODE: PLAN
TASK: Analyze requirements.md and design an implementation and test strategy
DONE_WHEN: Strategy saved to .claude/handoff/navigator.md

MODE: RED
TASK: Read navigator.md and write failing tests for the first feature
DONE_WHEN: Test fails with expected error

MODE: GREEN
TASK: Read navigator.md and implement the minimum code required to pass the tests
DONE_WHEN: All tests pass
```

**Patterns Ivan :**
- Chaque nouvelle intégration (payment gateway, shipping calc) via TDD strict
- Handoff files = journal automatique pour reprendre à froid dans 3 semaines
- Divise/conquiers : freelance peut prendre le driver.md et coder l'implémentation

**→ Skill proposé :** `ecom-feature-builder-tdd` (voir `skills-proposed/`)

---

### 4️⃣ I Tried 100+ Claude Code Skills. These 6 Are The Best
**URL :** https://www.youtube.com/watch?v=eRS3CmvrOvA
**Score sélection :** 7/10 · **Score Gemini utilité Ivan :** 9/10 · Date : < 14j

**TL;DR :** 400h dans Claude Code → 6 skills "ennuyeux mais efficaces" qui rapportent vraiment : **Skill Creator**, **Superpowers**, **GSD**, **/review + /ultrareview**, **Context Mode**, **Claude Mem**, + bonus **Frontend Design**. La vidéo apprend aussi à vendre le OUTCOME (temps gagné, erreurs évitées) pas le workflow.

**Highlights clés :**
- **[00:45] Skill Creator** (officiel Anthropic) — écris tes skills en langage naturel
- **[02:23] Skill vs Plugin** — skill = 1 fichier .md ; plugin = package (skills + hooks + MCP)
- **[02:56] Superpowers** — force TDD, environnement isolé, self-review
- **[04:36] GSD** = fresh sub-agent windows pour éviter le context rot
- **[06:15] `/review` vs `/ultrareview`** — Opus 4.7+ requis pour ultra (fleet parallel en cloud)
- **[08:03] Context Mode** — route tool calls via sandbox, retourne uniquement le pertinent
- **[09:49] Claude Mem** — persistance cross-sessions via SQLite + vector search

**Commandes verbatim :**
- `/plugin install skill-creator@claude-plugins-official`
- `/plugin install superpowers@claude-plugins-official`
- `npx get-shit-done-cc --claude --global`
- `/plugin marketplace add mksglu/context-mode && /plugin install context-mode@context-mode`
- `/plugin marketplace add thedotmack/claude-mem && /plugin install claude-mem`
- `/plugin install frontend-design@claude-plugins-official`

**Patterns Ivan :**
- Utiliser **Skill Creator** pour créer les 5 skills du digest de cette semaine
- **Superpowers + GSD** pour chaque script d'intégration Shopify critique
- **`/ultrareview`** avant tout déploiement checkout (perte CA immédiate si bug)
- **Context Mode + Claude Mem** pour gérer 2+ marques sans re-briefer

**→ Skills proposés :** `shopify-product-description-stylist`, `dropship-product-analyzer` (voir `skills-proposed/`)

---

### 5️⃣ I Scraped 85,000 Claude Skills. These Are The Most Popular
**URL :** https://www.youtube.com/watch?v=1GgyJfCK608
**Score sélection :** 7/10 · **Score Gemini utilité Ivan :** 9/10 (Frontend Design 10/10) · Date : < 14j

**TL;DR :** Top 12 skills sur 85k scrapés. 99% sont "hot garbage", **13% ont des issues sécurité** (11k skills à risque). Recommandation : stack de **3-5 skills max** pour éviter context rot. Top pick pour un solo founder e-com : **Frontend Design** (anti-AI-slop) + **Superpowers** (méthode) + **Context7** (docs à jour).

**Highlights clés :**
- **[00:19] 85 000 skills communautaires** ; 99% mauvais → prudence
- **[01:31] 13% des skills = risques sécurité** — n'installe que depuis sources vérifiées
- **[03:00] LSP skills** = GPS temps réel de la codebase, moins d'hallucinations
- **[05:30] MCP** = pont vers services externes (GitHub, Shopify, etc.)
- **[08:20] Superpowers** — discipline, brainstorm avant code, TDD, tâches atomiques
- **[12:22] Ne vends pas le workflow — vends l'outcome**
- **[12:27] Frontend Design** — force un style visuel distinctif avant d'écrire une ligne d'UI (anti "AI slop violet gradient")
- **[13:40] agentskills.io** — standard ouvert, skills portables Cursor/Copilot

**Commandes verbatim :**
- `claude plugin install frontend-design@claude-plugins-official`
- `claude plugin install context7@claude-plugins-official`
- `claude plugin install superpowers@claude-plugins-official`
- `/plugin install pr-review-toolkit@claude-plugins-official`
- Meta-prompt : `based on this conversation, build me a skill so we can do this faster next time.`

**Patterns Ivan :**
- **Frontend Design** = **must-install immédiat** pour TempleTwins (streetwear = image de marque)
- Meta-prompt "build me a skill from this convo" à ajouter en réflexe
- Pile recommandée : Frontend Design + Context7 + Superpowers + 1-2 metier
- **NE JAMAIS installer un skill sans lire son SKILL.md** (13% de skills piégés)

**→ Skills proposés :** cf `shopify-product-description-stylist` + `dropship-product-analyzer`

---

## NICE — 5-10 vidéos à parcourir (score 4-6)

| # | Titre | URL | Pourquoi |
|---|-------|-----|----------|
| 1 | Top 5 Claude Code Skills That Will 10x Your Productivity (2026) | https://www.youtube.com/watch?v=Xs942zwWfdY | Overlap avec must-watch #4, angle différent |
| 2 | 8 Claude Code Skills Every Developer Needs in 2026 | https://www.youtube.com/watch?v=Va-U1dqhwzk | Listicle utile mais moins ciblé e-com |
| 3 | The Only Claude Skills You Need in 2026 | https://www.youtube.com/watch?v=2BFN2DtcQMw | Curation opinionated, bon check croisé |
| 4 | Claude Code is all you need in 2026 | https://www.youtube.com/watch?v=0hdFJA-ho3c | Vision d'ensemble Claude Code |
| 5 | Claude Skills Tutorial (2026): Build, Run, and Share | https://www.youtube.com/watch?v=O_z9vDLgvoY | Tuto build de zéro, utile si Ivan veut créer un skill from scratch |
| 6 | Claude Code Tutorial for Beginners (2026) — Master It in 1 Hour | https://www.youtube.com/watch?v=sX-FmJL7Wd0 | Refresher complet Skills + Subagents + Hooks + MCP |
| 7 | Anthropic Just Dropped Their Claude Skills Secrets | https://www.youtube.com/watch?v=VhhVoUXEGeo | Bonus resources : "15 Skills I Can't Live Without" |
| 8 | The ONLY Claude Skills Tutorial Beginners Need in 2026 | https://www.youtube.com/watch?v=TyB7kLZPVKo | 100x Engineers, beginner-friendly |

---

## SKIP

- Anthropic Claude News August 2026 (Startup Edition) — trop générique, blog aggregator
- Tutorials FR/DE/ES/PL beginner-only (Ivan est au-delà)
- Rants "Claude vs GPT-6 vs Fable 5" — sans valeur actionnable

---

## SKILLS PROPOSÉS (5) — review Ivan avant merge

Dossier : `claude-weekly/2026-08-24/skills-proposed/`

| Skill | Source | 1-liner |
|-------|--------|---------|
| `solo-founder-ideation` | Matt Pocock #1 | `grill-me` pattern adapté e-com : interview jusqu'au spec sans code |
| `rapport-financier-ecom` | Cowork Chrome #2 | Month-end close via Claude in Chrome side panel + Google Sheet |
| `ecom-feature-builder-tdd` | Multi-agent #3 | Navigator/Driver TDD strict pour features Shopify |
| `shopify-product-description-stylist` | Skills scrapes #4 #5 | 3 variantes description + JSON-LD Product ready |
| `dropship-product-analyzer` | Skills scrapes #5 | Go/No-go dropship candidat avec marge + saturation |

**Aucun n'est déployé automatiquement.** Ivan doit review chaque SKILL.md et les
copier manuellement dans `~/.claude/skills/` s'il valide.

---

## INSIGHT CROSS-VIDÉOS DE LA SEMAINE

**Le pattern qui traverse les 5 vidéos : la modularité fine-grained bat les
frameworks monolithiques.** Matt Pocock (grill-me/to-spec/to-tickets),
la démo Cowork (1 prompt = 1 action multi-tabs), la stack Navigator/Driver,
les 6 "ennuyeux mais efficaces", les 12 top skills — tous convergent vers :
**1 skill = 1 job**, orchestrés par un skill de niveau supérieur ou par
l'utilisateur, avec des **handoff files markdown** pour la traçabilité.

Les frameworks agentiques "tout-en-un" (Superpowers, GStack au sens
monolithique) sont en fin de cycle. **Anthropic va dans ce sens** :
Opus 5 a perdu **80% de son system prompt** — la tendance est aux
prompts minimaux avec **mots-guides** (vocabulaire technique dense
comme "code smell") qui laissent le modèle raisonner, pas des
garde-fous rigides.

**Implication concrète pour Ivan :** ne pas construire *un* méga-skill
"e-commerce-assistant". Construire **5-10 petits skills** ultra-focus
(1 par job réel : description produit, close mensuel, analyse dropship,
etc.) et les orchestrer manuellement. C'est ce que fait le digest
proposé cette semaine.

---

## RESSOURCES ANTHROPIC OFFICIELLES CETTE SEMAINE

- Cowork Chrome side panel : https://claude.com/blog/cowork-chrome-side-panel
- Product announcements : https://claude.com/blog-category/announcements
- Claude Code changelog : https://code.claude.com/docs/en/changelog
- Claude Academy : https://claude.com/resources/tutorials
- MCP servers repo : https://github.com/modelcontextprotocol/servers
- Shopify AI Toolkit (rappel avril, actif) : https://github.com/Shopify/Shopify-AI-Toolkit

---

_Analyses générées via Gemini 2.5 Flash sur URLs YouTube (fileData). 5/5 succès (2 retries après quota reset)._
