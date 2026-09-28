# Claude Weekly — 28 septembre 2026
> Deep-dive Claude / Claude Code / Skills / MCP | Routine hebdomadaire Ivan Vasseur

---

## 📡 ACTUALITÉS ANTHROPIC (semaine du 22–28 sept 2026)

### 🚀 Claude Opus 5.5 — Lancement majeur (22 sept)
- **Performances Fable 5.1** à **40% moins cher** que Opus 5
- **1M tokens de contexte**, jusqu'à 128k output tokens
- **Vitesse +30%** vs Opus 5
- **Prix API** : $4/$20 per M tokens, cache reads $0.20/Mtok
- Disponible sur tous les plans Claude Code dès la v2.1.280
- **Impact Claude Code** : Opus 5.5 est désormais le modèle par défaut (v2.1.283, 25 sept)
- Plans Pro : migrés de Sonnet vers Opus automatiquement

### 🛠️ Claude Code Changelog (17–25 sept 2026)
| Version | Date | Changement clé |
|---------|------|----------------|
| 2.1.283 | 25 sept | Opus 5.5 par défaut, header `x-claude-code-prompt-id` pour gateways |
| 2.1.282 | 24 sept | Paramètre `maxProseWidth`, corrections sessions continuées |
| 2.1.281 | 23 sept | Support Claude apps gateway Bedrock/STS, vérifications MCP plugins |
| 2.1.280 | 22 sept | **Claude Opus 5.5** ($4/$20, 1M ctx), corrections MCP/plugin |
| 2.1.278 | 19 sept | Auto mode par défaut serveur (API/Enterprise/Bedrock/Vertex) |
| **2.1.277** | **18 sept** | **Support AGENTS.md** (alternative CLAUDE.md multi-agents) |
| 2.1.275 | 17 sept | Clé send-now (ctrl+enter), **sync skills claude.ai** |

**Points clés pour Ivan :**
- **AGENTS.md** : équivalent CLAUDE.md, compatible avec d'autres agents IA. Si le repo n'a pas de CLAUDE.md, Claude Code utilise AGENTS.md automatiquement.
- **Skills sync claude.ai** : les skills sont maintenant synchronisés entre Claude.ai et Claude Code
- **Auto mode serveur** : sans coût supplémentaire de classification côté API

### 🌐 MCP — Commits récents (modelcontextprotocol/servers)
- Fix subscriptions disconnect (22 sept) — cleanup sessions sur déconnexion transport
- Multiple fixes mémoire : race conditions, déduplication, validation graph, tilde paths

### 🛒 Claude for Commerce (lancé 2 sept 2026)
Blueprint open-source Apache 2.0 avec deux agents de référence :
- **Shopping Agent** : recherche produits, compare, construit panier, handoff checkout
- **Merchant Agent** : analyse ventes, rédige listings, prix, campagnes
- Partners : Shopify, Visa, Mastercard, Accenture
- Repo : https://github.com/Shopify/claude-for-commerce-examples
- **Ivan** : PURESOLE et TempleTwins = candidats idéaux pour les deux agents

---

## 🎬 MUST-WATCH (4 vidéos — toutes analysées par Gemini)

### 1️⃣ La Nouvelle Manière de Réussir Sur Shopify avec Claude IA en 2026
🔗 https://www.youtube.com/watch?v=JyNd6mk4ngM
📊 Score Gemini Ivan : **9/10**

**TL;DR :** Claude Code rend les thèmes Shopify et les apps tierces obsolètes. Créer pages, bundles, sections entières depuis screenshots/instructions. Focus humain = stratégie + brand, pas exécution.

**Micro-action :** Prendre un screenshot d'une section TempleTwins à améliorer → demander à Claude de la recréer en Liquid sans app. Tester le prompt "copie exactement ce que tu vois au détail près."

**Skill proposé :** `shopify-code-generator` ← généré cette semaine

---

### 2️⃣ Better With This Setup (CLAUDE.md + Skills + MCPs)
🔗 https://www.youtube.com/watch?v=pBHKTojO1YY
📊 Score Gemini Ivan : **9/10**

**TL;DR :** Transformer Claude Code en station de travail complète via CLAUDE.md global+projet, skills officiels Anthropic (document-skills, frontend-design), 6 MCPs starter (GitHub, Context7, Brave Search, Playwright, Sequential Thinking, Filesystem), et Agent Teams expérimental.

**Micro-action :** Créer `~/.claude/CLAUDE.md` avec profil Ivan (TempleTwins + PURESOLE, stack, règles sécurité API keys, ton de voix "parle comme un collègue"). Installer MCP Brave Search pour recherche tendances streetwear.

**Skills proposés :** `E-commerce Launchpad`, `Audit SEO E-commerce` ← voir analyses/

---

### 3️⃣ Claude Code Skills just Built me an AI Agent Team (2026 Guide)
🔗 https://www.youtube.com/watch?v=OdtGN27LchE
📊 Score Gemini Ivan : **9/10**

**TL;DR :** Skills = SOPs pour agents IA. Démo concrète d'un skill "Twitter X Post" entraîné sur le style personnel de l'auteur, connecté à l'API Typefully pour planifier les tweets automatiquement. Pattern "do what's in my queue" depuis Obsidian.

**Micro-action :** Créer un skill `.claude/skills/brand-voice/SKILL.md` avec exemples de posts TempleTwins existants → l'entraîner à reproduire le ton puis générer 10 idées de posts depuis la dernière collection.

**Skills proposés :** `Shopify Product Listing`, `E-commerce Ad Copy Generator`, `Customer Support Email Responder` ← voir analyses/

---

### 4️⃣ How to Use Claude to Build and Run a Shopify Store
🔗 https://www.youtube.com/watch?v=Ih5RapM8XKw
📊 Score Gemini Ivan : **9/10**

**TL;DR :** Créer et gérer une boutique Shopify entièrement via requêtes Claude en langage naturel. Check-in quotidien automatique (ventes, stocks, best sellers), stratégie de prix data-driven (quoi hausser/remiser/bundler avec projections CA).

**Micro-action :** Installer "Shopify Claude Connector" sur TempleTwins, puis tester le prompt check-in quotidien : "quels sont mes meilleurs et pires produits ce mois-ci, et quels produits sont presque en rupture ?"

**Skills proposés :** `shopify-daily-report`, `shopify-product-optimizer`, `Shopify Pricing Strategist` ← voir analyses/

---

## 📻 NICE-TO-WATCH (sans analyse Gemini)

| # | Titre | URL | Pourquoi |
|---|-------|-----|----------|
| 1 | Claude Opus 5.5 is out! | https://www.youtube.com/watch?v=gX0L0aFA2xg | Quick overview du nouveau modèle — 4 jours |
| 2 | Claude Fable 5.1 Review: Why Anthropic Still Says Start With Opus 5 | https://www.youtube.com/watch?v=-KNLl5hHzbM | Contexte modèles, benchmarks comparatifs |
| 3 | Introducing Claude Opus 5.5 (Anthropic officiel) | https://www.youtube.com/watch?v=1f13Bl1sYkw | Bande-annonce officielle, branding seulement |

---

## 🚫 SKIP

| Vidéo | Raison |
|-------|--------|
| Claude Code is all you need in 2026 (0hdFJA-ho3c) | DÉJÀ VU (seen-urls.txt) |
| Full Claude Code + MCP Tutorial Beginners (uEUP4iHJO1Q) | Trop ancien (16 août 2026) |
| Claude Ai Promo Code 2026 (X_36We6XDmI) | Hors-sujet (code promo, pas technique) |

---

## 🔧 SKILLS PROPOSÉS CETTE SEMAINE (3)

> ⚠️ À review manuellement par Ivan avant déploiement

### 1. `shopify-product-optimizer`
📁 `claude-weekly/2026-09-28/skills-proposed/shopify-product-optimizer/SKILL.md`
**Source :** Vidéos 1 + 3 + 4 (JyNd6mk4ngM, OdtGN27LchE, Ih5RapM8XKw)
Réécrit toutes les fiches produits actives d'une boutique selon une brand voice définie. Optimise titres, descriptions, SEO. Validation avant application.

### 2. `shopify-daily-report`
📁 `claude-weekly/2026-09-28/skills-proposed/shopify-daily-report/SKILL.md`
**Source :** Vidéo 4 (Ih5RapM8XKw)
Check-in quotidien des boutiques en < 2 min : ventes, best sellers, alertes stock. Format de briefing matinal sans ouvrir le dashboard Shopify.

### 3. `shopify-code-generator`
📁 `claude-weekly/2026-09-28/skills-proposed/shopify-code-generator/SKILL.md`
**Source :** Vidéo 1 (JyNd6mk4ngM)
Génère des sections Shopify en Liquid/HTML/CSS depuis screenshots ou descriptions. Remplace apps tierces par du code custom : bundles, accordéons, badges, sections avancées.

---

## 💡 INSIGHT CROSS-VIDÉOS

> **Le pattern récurrent cette semaine :** Claude Code + Shopify = solo founder augmenté. Les 4 must-watch convergent sur le même message : l'exécution technique (code, contenu, analytics, prix) est délégable à Claude, libérant Ivan pour la stratégie marque, le positionnement et la conversion — les seuls domaines où l'humain garde un avantage compétitif durable.

---

## 📊 RÉSUMÉ EXÉCUTIF

```
DIGEST_DATE: 2026-09-28
MUST_WATCH: 4 · NICE: 3 · SKIP: 3
GEMINI_ANALYSES: 5 (5 tentatives — 1 promo video score 2/10 → reclassée Nice)
SKILLS_PROPOSED: 3 (shopify-product-optimizer · shopify-daily-report · shopify-code-generator)
FOCUS: Opus 5.5 + CLAUDE.md setup + Skills automation + Shopify Claude integration
GITHUB: https://github.com/ivanvrp/ivan-veille/blob/main/2026-09-28-claude-weekly.md
```

---

*Routine veille-claude weekly — Générée automatiquement le 2026-09-28 07:21 UTC*
