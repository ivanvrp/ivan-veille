# Claude Weekly — 2026-10-05

> Deep-dive hebdo : Claude / Claude Code / Skills / MCP
> Routine : `veille-claude weekly` | Analyses : Gemini 2.5 Flash

---

## 🔥 TL;DR de la semaine

**Claude Code Mods est la news de la semaine** : une mise à jour majeure (v2.1.287, Oct 1) qui transforme Claude Code en plateforme extensible via des plugins TypeScript. Simultanément, Anthropic lance Claude Sonnet 5.5 (30% plus rapide, 30% moins cher) et Opus 5.5 (performances Fable 5.1 à -40%). Pour Ivan : Mods ouvre des automatisations e-commerce inédites, et le nouveau Sonnet 5.5 réduit directement les coûts API.

---

## 📅 Actualités Anthropic (Sep 22 – Oct 5)

| Date | News | Impact Ivan |
|------|------|-------------|
| Sep 22 | **Claude Opus 5.5** — Performances = Fable 5.1, coût -40% | Tâches complexes moins chères |
| Sep 28 | **Claude Sonnet 5.5** — Default dans Claude Code, 30% plus rapide, 30% moins cher | Coût API réduit dès maintenant |
| Oct 1 | **Claude Code Mods** — TypeScript plugins qui modifient le comportement de l'agent | Game-changer pour automation e-com |
| Oct 1 | **Claude Frontier Academy** — Anthropic investit $100M pour former 10k ingénieurs | Signal long-terme : talent IA |
| Oct 1 | **Barclays scales Claude** — Déploiement enterprise Barclays | Crédibilité B2B pour contexte TempleTwins |
| Sep 2 | **Claude Commerce Agents** — Open-source avec Shopify, Visa, Mastercard | Direct Shopify → voir section dédiée |

---

## 🎬 Claude Code Changelog (v2.1.283 → v2.1.289)

Semaine très active. Highlights :

- **v2.1.287** — Système de Mods complet, `/diff` intégré en mod, mod `sec-default` sécurité
- **v2.1.288** — `$.ui.selection()` pour mods, `gh api` built-in dans MCP, auto-compaction context
- **v2.1.289** — Fix mod failures, agent spawn via MCP, idle/waiting states dans agent list
- **v2.1.284** — Sonnet 5.5 comme modèle par défaut, Ultracode comme toggle indépendant
- **v2.1.283** — `/doctor prompt-audit` pour auditer CLAUDE.md/skills (très utile pour Ivan)

---

## 🎬 YouTube — Sélection de la semaine

### ✅ MUST-WATCH (2 vidéos analysées par Gemini)

#### 1. "Anthropic's NEW Claude Code Mods Are INSANE, What You Need to Know"
- **ID**: xTRZhPLhQ5E | **Chaîne**: ClaudeDevs | **Date**: Oct 4 (1j)
- **Score**: 7/10 | **Durée**: ~6 min
- **URL**: https://www.youtube.com/watch?v=xTRZhPLhQ5E
- **Analyse Gemini** → voir `claude-weekly/2026-10-05/analyses/xTRZhPLhQ5E-claude-code-mods-insane.md`
- **TL;DR**: Hook UserPromptSubmit, routage intelligent via logique locale (type JEV), mini-marketplaces de plugins, accès ressources machine. Score utilité Ivan : **8/10**.
- **Micro-action Ivan**: Créer un mod de routage e-commerce (voir skill proposé `claude-code-mod-ecommerce-router`)

#### 2. "Claude Code 3.0: Anthropic has SILENTLY dropped their BIGGEST NEW Feature!"
- **ID**: u1dW4z5Ye90 | **Date**: ~Oct 3 (2-3j)
- **Score**: 6/10 | **Durée**: ~6 min
- **URL**: https://www.youtube.com/watch?v=u1dW4z5Ye90
- **Analyse Gemini** → voir `claude-weekly/2026-10-05/analyses/u1dW4z5Ye90-claude-code-30-mods-biggest-feature.md`
- **TL;DR**: AGENTS.md support, panneau diff en direct, Projects beta multi-agent cloud, `/skill-doctor`, `claude plugin eval`. Score utilité Ivan : **8/10**.
- **Micro-action Ivan**: Lancer `/skill-doctor` maintenant pour auditer ses skills actuels

### 📌 NICE (à regarder si temps)

| Titre | ID | Date | Raison |
|-------|-----|------|--------|
| Don't Miss These 7 Claude Code Updates | shYJ0P-vvdI | Sep 18 (~17j) | 7 features utiles, légèrement hors fenêtre |
| Claude AI FREE Unlimited? 1M API Requests | 3FyBGgkkjSw | Oct 3 | Potentiellement sur OmniRoute gateway — à vérifier |
| Claude Code: MCPs e Skills - Tutorial Completo | Kjh4gdaEE0A | ~Sep-Oct | Tutorial espagnol, complet sur MCP+Skills |
| MCP Tutorial for Beginners: Connect Claude to Any Tool | 40k3SIwlFVM | ~juin 2026 | Référence MCP solide même si ancienne |

### ⏭️ SKIP

- **"Claude Code is all you need in 2026"** (0hdFJA-ho3c) — fév. 2026, trop vieux
- **"Boris Cherny: We Cut 80% of Claude Code's Prompt"** (qyPCVqFUyDo) — juil. 2026, >14j
- **"Claude AI FREE Unlimited"** — clickbait "FREE Unlimited" fort, contenu incertain

---

## 🔌 MCP Protocol — Nouvelles de la semaine

- **v2.0.0 en préparation** : contribution policy et PR templates synchronisés (commits Oct 4)
- **Claude Code Mods encapsulent MCP** : un mod peut désormais contenir un serveur MCP, skills ET tools dans un seul plugin installable
- **MCP agent spawn** : ajouté dans Claude Code v2.1.289 — les agents peuvent spawner d'autres agents via MCP
- **`gh api` built-in** dans Claude Code MCP (v2.1.288) — plus besoin de configurer le GitHub MCP séparément

---

## 🛒 Spécial Ivan — Claude × Shopify/E-commerce

### Claude Commerce Agents (lancé Sep 2)
Anthropic a open-sourcé deux agents de référence :
1. **Shopping Agent** (côté client) — aide les clients à trouver produits, construire panier, checkout
2. **Merchant Agent** (côté staff) — automatisation opérations store

**Repo** : `github.com/anthropics/commerce-agents` (Apache-2.0)
**Webinar** : "Building Claude Commerce Agents" — Ali Shazal, Sep 10 (enregistrement dispo)
**Plugin Claude Code inclus** : scaffold direct depuis les blueprints existants

→ **Action Ivan** : Cloner le repo `commerce-agents` et explorer le blueprint "retail" — potentiellement applicable à TempleTwins.

### Shopify Admin Redesign
- Nouveau look Shopify Admin avec Sidekick flottant sur chaque page
- Polaris 2.0 RC disponible pour thèmes
- Limite variants produit portée à 2048 — utile pour PURESOLE dropship

---

## 🧠 Insights Cross-Sources

**Pattern récurrent cette semaine** : Claude Code devient une **plateforme extensible** (Mods + MCP spawn + Projects). La direction est claire : des agents qui se coordonnent et s'auto-modifient, pas juste un outil en ligne de commande. Pour Ivan en solo founder, cela signifie qu'investir maintenant dans la compréhension des Mods et de MCP lui donnera une avance significative sur les workflows e-commerce automatisés dans 3-6 mois.

---

## 🚀 Skills proposés cette semaine (3)

> ⚠️ À reviewer manuellement par Ivan — JAMAIS déployés automatiquement

| Skill | Fichier | Complexité | Priorité |
|-------|---------|------------|----------|
| `shopify-product-fiche-seo` | `skills-proposed/shopify-product-fiche-seo/SKILL.md` | Faible (skill texte) | ⭐⭐⭐ Haute |
| `claude-code-mod-ecommerce-router` | `skills-proposed/claude-code-mod-ecommerce-router/SKILL.md` | Moyenne (TypeScript mod) | ⭐⭐ Moyenne |
| `skill-doctor-optimizer` | `skills-proposed/skill-doctor-optimizer/SKILL.md` | Faible (skill texte) | ⭐⭐ Moyenne |

---

## 📊 Ressources supplémentaires

- [Customize Claude Code with mods](https://claude.com/blog/claude-code-mods) — blog officiel Anthropic
- [Building Claude Commerce Agents](https://www.anthropic.com/webinars/building-claude-commerce-agents) — webinar Sep 10
- [Claude Skills and MCP Servers Practitioner Guide 2026](https://codersera.com/blog/claude-skills-mcp-servers-practitioner-guide-2026/) — guide pratique récent
- [My Claude Code Setup After 4 Months](https://okhlopkov.com/claude-code-setup-mcp-hooks-skills-2026/) — retour d'expérience utilisateur

---

## 📁 Fichiers générés

```
claude-weekly/2026-10-05/
├── analyses/
│   ├── xTRZhPLhQ5E-claude-code-mods-insane.md       ← Gemini OK
│   └── u1dW4z5Ye90-claude-code-30-mods-biggest-feature.md ← Gemini OK
└── skills-proposed/
    ├── shopify-product-fiche-seo/SKILL.md
    ├── claude-code-mod-ecommerce-router/SKILL.md
    └── skill-doctor-optimizer/SKILL.md
```

---

*Généré automatiquement — veille-claude weekly — 2026-10-05*
