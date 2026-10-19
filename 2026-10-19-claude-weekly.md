# Claude Weekly — 19 octobre 2026

> Deep-dive hebdomadaire Claude / Claude Code / Skills / MCP pour Ivan Vasseur (TempleTwins + PURESOLE)

---

## 📡 Radar Anthropic cette semaine

### Nouvelles officielles

**Claude Haiku 5.5** (7 oct. 2026) — Nouveau petit modèle, plus rapide et le moins cher de sa catégorie (0,10 $/0,50 $ par Mtok). Idéal pour les tâches à fort volume (génération de descriptions produits en bulk, classification commandes).

**Claude Code Review GA** (15 oct. 2026) — Reviews automatiques sur les PRs, ~3x plus rapides, disponibles pour Team et Enterprise. Settings Quick/Standard/Deep par repo.

**Claude Dashboards & Motion (beta)** (10 oct. 2026) — Connecte BigQuery, Databricks, Snowflake, Salesforce. Les Docs/Slides/Design passent en GA sur tous les plans y compris Free.

**Anthropic for Startups** (6 oct. 2026) — 1 an de Claude Team gratuit + 1 000 $ de crédits API pour les startups qualifiées.

### Changelog Claude Code (semaine du 7 au 18 oct.)

| Version | Date | Points clés |
|---|---|---|
| 2.1.303 | 18 oct. | Corrections bugs |
| 2.1.302 | 16 oct. | `CLAUDE_CODE_AUTO_MODE_MODEL` · Idle compaction dans `/config` · **fork subagents activés par défaut** · 43 fixes |
| 2.1.301 | 15 oct. | `CLAUDE_CODE_RETRY_WATCHDOG_MAX_USAGE_LIMIT_WAIT_MS` · motif `%` vim · rendu LaTeX VS Code |
| 2.1.300 | 14 oct. | `virtualText` pour mods · `/advisor` sur AWS · hook `prompt.change` · **support Slack Connect** |
| 2.1.299 | 14 oct. | `CLAUDE_CODE_DISABLE_FILE_MENTIONS` · compaction veille (200K+ tokens ~54 min) · `/fast` dans vue agents |
| 2.1.296 | 9 oct. | Prix cache Sonnet 5.5 → 0,10 $/Mtok · `CLAUDE_CODE_WORKFLOW_SUBAGENT_MODEL` · `allow_large` pour Read |
| 2.1.295 | 8 oct. | `onFailure: "block"` pour hooks · `$.ui.notify` pour mods · descriptions MCP outils → 16 384 chars (était 2 048) |
| 2.1.293 | 7 oct. | Claude Haiku 5.5 disponible dans Claude Code |

**Changements breaking :** `--sandbox` et `--no-sandbox` supprimés de `claude remote-control` en v2.1.300.

### MCP officiel (modelcontextprotocol/servers)

Activité intense ce 19 oct. :
- Migration vers nouvelle API `MCPServer` : serveurs `fetch`, `time`, `git` migrés
- Node.js minimum passé à v24 pour tous les serveurs TypeScript
- Publication MCP v2.0.0 (fusion `v2/main` → `main`)
- Serveur git : signalement HEAD détaché dans `git_create_branch`

---

## 🎬 Must-Watch (3 vidéos — score ≥ 7)

### 1️⃣ How I Use Claude Code With Skills, MCP, Agents & Plugins
**URL:** https://www.youtube.com/watch?v=jzf7DQa2CAc
**Score:** 9/10 · ~13 426 vues · Durée ~9 min

**TL;DR :** Guide pratique qui explique QUAND utiliser chaque outil d'extension Claude Code avec un cadre de décision clair.

**Points clés (analysés par Gemini) :**
- [00:48] **Skills** = fichiers Markdown avec standards → Claude décide quand les utiliser
- [02:39] **MCP** = connexion aux outils externes (Shopify API, navigateur, BDD)
- [03:59] **Agents** = instances spécialisées exécutables en parallèle
- [06:23] **Slash Commands** = workflows déclenchés manuellement par l'utilisateur
- [07:47] **Plugins** = bundles Skills + MCP + Hooks + Commands

**Cadre de décision (résumé) :**
| Besoin | Outil |
|---|---|
| Définir standards de rédaction | Skill |
| Connecter Shopify API | MCP |
| Tâche parallèle spécialisée | Agent |
| Workflow répétitif à la demande | Slash Command |
| Bundle réutilisable | Plugin |

**Micro-action pour Ivan :** Créer un skill `product-description-generator` (proposé ci-dessous) et une slash command `/new-product` pour TempleTwins.

---

### 2️⃣ I Mapped Every Claude Code Concept So You Don't Have To
**URL:** https://www.youtube.com/watch?v=9JoIpWgAsZ8
**Score:** 8/10 · Mind map exhaustive 2026

**TL;DR :** Cartographie complète de l'écosystème Claude Code : 66 concepts de base + 231 concepts avancés + module revenus passifs avec agents.

**Points clés :**
- Mind map : Authentication → CLAUDE.md → Memory/Context → Skills → Agents → MCP → Hooks
- Module **"$ Earn Passive Income"** : 61 concepts, agents génération contenu, automatisation Instagram/YouTube
- Agent "Faceless YouTube Channel" → crée visuels + scripts + monte + publie automatiquement
- "Sell Your Agents" → Ivan peut revendre ses agents e-commerce à d'autres founders

**Micro-action pour Ivan :** Explorer le module Agents pour automatiser contenu Reels/Shorts TempleTwins.

---

### 3️⃣ Claude Code is all you need in 2026
**URL:** https://www.youtube.com/watch?v=0hdFJA-ho3c
**Score:** 8/10 · Créateur : Brian Castle

**TL;DR :** En 2026, Claude Code "vanilla" + Opus 4.5 suffit pour 90% du dev. Les frameworks complexes sont superflus. Le goulot est la pensée produit humaine, pas le code.

**Points clés :**
- [02:35] Plan mode natif : décrire feature → Claude décompose et plan
- [05:27] Q&A clarificatoire intégré : Claude pose des questions pour affiner le scope
- [09:50] Invoquer un skill `frontend-design` pour garantir cohérence UI
- [11:52] Rôle humain = pensée produit + stratégie = multiplicateur irremplaçable

**Prompt verbatim (plan mode) :**
```
I want to add a trends view to see visual reports, graphs and metrics...
Analyze all of the functionality around those areas and suggest some ideas
for what we might put into this trends view...
```

**Micro-action pour Ivan :** Utiliser le plan mode pour définir la prochaine évolution de la page collection TempleTwins.

---

## 📺 Nice to Watch (4 vidéos — score 4-6)

| # | Titre | URL | Raison |
|---|---|---|---|
| 4 | Claude Code Explained (2026): MCP, Skills, Subagents, Hooks & Plugins | https://alexop.dev/posts/understanding-claude-code-full-stack/ | Article-guide complet, bonne référence |
| 5 | Tutorial Definitivo de Claude Code: Dominá MCP´s, Skills y Ahorrá Tokens | https://www.youtube.com/watch?v=GdUnGz46H4I | MCP + tokens économie (espagnol) |
| 6 | Exploring Claude Code (2026): The Ultimate Guide | https://www.youtube.com/watch?v=PDt0mPCG6xQ | Deep-dive référence |
| 7 | My Claude Code Setup After 4 Months of Daily Use | https://okhlopkov.com/claude-code-setup-mcp-hooks-skills-2026/ | Retour d'expérience pratique |

---

## ❌ Skip

- `X_36We6XDmI` — "Claude Ai Promo Code" : hors sujet
- `Thylf8WVuK8` — "AI Summer 2026" : trop générique
- `c8SJxb52bpw` — "Claude Code: La IA que está revolucionando" : espagnol uniquement
- `x4FxvP5IGQs` — "Claude Code Is Now FREE Forever" : clickbait
- `sJVxwwaF0sU` — "Every New Claude Code Feature Explained" : déjà vu (run précédent)

---

## 🔧 Skills Proposés (3)

> ⚠️ Aucun skill n'est déployé automatiquement. Ivan valide manuellement.

### 1. `product-description-generator`
**Fichier :** `claude-weekly/2026-10-19/skills-proposed/product-description-generator/SKILL.md`
**Source :** vidéo jzf7DQa2CAc
**Usage :** Génère titres + descriptions + CTA optimisés SEO pour Shopify (TempleTwins/PURESOLE). Entrée : nom + caractéristiques + public cible + ton. Sortie : Markdown Shopify-ready.

### 2. `shopify-product-optimizer`
**Fichier :** `claude-weekly/2026-10-19/skills-proposed/shopify-product-optimizer/SKILL.md`
**Source :** vidéo 9JoIpWgAsZ8
**Usage :** Audit produit Shopify existant → optimise titre/description/tags/alt text. Justifie chaque changement SEO.

### 3. `shopify-theme-design-consistency`
**Fichier :** `claude-weekly/2026-10-19/skills-proposed/shopify-theme-design-consistency/SKILL.md`
**Source :** vidéo 0hdFJA-ho3c
**Usage :** Analyse thème Shopify → extrait patterns design → garantit cohérence de tout nouveau code frontend. Élimine les incohérences visuelles.

---

## 💡 Insight cross-vidéos

**Pattern récurrent :** Les 3 vidéos convergent vers la même vision — Claude Code 2026 est un **multiplicateur de pensée produit**, pas un générateur de code aveugle. Le framework optimal = CLAUDE.md + 1-3 Skills métier + 1 MCP Shopify + slash commands pour les workflows récurrents. Moins de complexité, plus de vitesse.

---

## 📊 Résumé

| Métrique | Valeur |
|---|---|
| Must-watch | 3 |
| Nice to watch | 4 |
| Skip | 5 |
| Analyses Gemini | 3/3 |
| Skills proposés | 3 |
| Versions Claude Code sorties cette semaine | 8 (2.1.293 → 2.1.303) |

---

*Généré le 2026-10-19 par routine veille-claude weekly*
