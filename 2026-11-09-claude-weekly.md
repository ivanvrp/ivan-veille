# Claude Weekly — 2026-11-09
> Deep-dive hebdomadaire Claude / Claude Code / Skills / MCP pour Ivan Vasseur (TempleTwins + PURESOLE)

---

## 📊 Résumé exécutif

| Indicateur | Valeur |
|---|---|
| Must-watch | 5 |
| Nice-to-watch | 4 |
| Skills proposés | 6 |
| Analyses Gemini | 3/5 (quota free tier 20 req/jour atteint) |
| Nouveautés Claude Code | 7 releases (2.1.310 → 2.1.319) |
| Annonces Anthropic | 1 majeure (Haiku 5.5) + Don Agent Skills à AAF |

---

## 🔥 Must-Watch (score ≥ 7)

### 1. Claude Code vs Cowork: 17 Skills + 11 Plugins Setup
**Score : 9/10 · Analyse Gemini : OUI**
🔗 https://www.youtube.com/watch?v=k2ZOFBu3MJk

**TL;DR :** Anthropic propose DEUX cockpits distincts — Claude Code (dev, terminal) et Claude Cowork (knowledge worker, desktop) — avec des dépôts de skills séparés. Confondre les deux = sous-performance.

**Concepts clés :**
- [02:05] Claude Code : 17 skills officiels, 135k ⭐ — pour le code, les specs, les boilerplates
- [02:40] Claude Cowork : 11 plugins officiels (Slack, Notion, Asana) — pour la gestion, le marketing, le CRM
- [09:05] **"Taxe de contexte"** : chaque skill installé = ~60 tokens/session. Cible 8-12 skills max pour Claude Code, 3-5 plugins pour Cowork
- [11:30] Construire des skills/plugins custom pour les workflows répétitifs à forte valeur, pas les ponctuels
- [12:33] **Audit mensuel** : lister les skills, identifier ceux inutilisés sur 30j, supprimer, re-baseline

**Pour Ivan :**
- Séparer ses usages : Code pour dev Shopify/automatisations, Cowork pour marketing/CRM/réponses clients
- Créer des skills "crossover" : brand guidelines utilisables dans les deux cockpits
- **Skill proposé :** `product-launch-workflow` — workflow complet lancement produit dropshipping

---

### 2. Agent Skills or MCP in the Era of Claude Code?
**Score : 8/10 · Analyse Gemini : OUI**
🔗 https://www.youtube.com/watch?v=pvxNcQTcIy4

**TL;DR :** Skills et MCP sont complémentaires, pas concurrents. MCP = cloud/réseau/auth ; Skills = local/statique/scripts. Le chevauchement existe sur les CLIs.

**Concepts clés :**
- [04:44] Skill = SKILL.md + `resources/` (données statiques) + `scripts/` (bash/Python exécutables)
- [07:19] MCP pour données temps réel + auth OAuth ; Skills pour connaissances locales + scripts CLI
- [08:00] Un script de skill qui appelle une CLI peut faire ce qu'un MCP ferait dans d'autres contextes
- [02:16] HTTP Streamable MCP : facilite déploiement et gestion réseau des serveurs MCP
- [02:56] OAuth 2.1 MCP : meilleure gestion auth pour agents locaux interfaçant des services cloud (ex: Shopify API)

**Pour Ivan :**
- Structurer ses skills avec `resources/` (catalogues fournisseurs, brand guides) + `scripts/` (API Shopify)
- MCP pour les intégrations live (Shopify Admin API, fournisseurs dropship en temps réel)
- **Skills proposés :** `shopify-inventory-sync`, `dropship-order-automation`, `streetwear-trend-analyzer`

---

### 3. How I Use Claude Code With Skills, MCP, Agents & Plugins
**Score : 8/10 · Analyse Gemini : OUI**
🔗 https://www.youtube.com/watch?v=jzf7DQa2CAc

**TL;DR :** Guide pratique complet des 4 outils Claude Code : Skills (standards), MCP (outils externes), Agents (parallélisation), Commands (workflows à la demande). Avec prompts verbatim.

**Prompts/commandes verbatim :**
```bash
# Lister les skills installés
/skills

# Lister les MCPs
/mcp

# Lister les agents disponibles
/agents

# Lister les plugins
/plugin

# Installer un MCP Chrome DevTools
claude-cli add chrome-devtools --server npm:chrome-devtools-mcp
```

**Prompt pour créer une commande `/tweet` (build-in-public) :**
```
At the user-level Claude folder, make me a command which analyzes the git diffs on 
the current branch, and generates a natural language three-line tweet that is based 
off the changes in the branch. Generates a casual, authentic 3-line tweet that:
1. what you worked on today (start with an action verb);
2. a specific detail or win from the work;
3. a forward-looking statement or call-to-action.
```

**Pour Ivan :**
- Créer skill "landing-page-copy" adapté TempleTwins/PURESOLE avec tone guide
- Commande `/stock-alert` : vérification stocks + alertes via API Shopify
- Commande `/daily-report` : rapport ventes + trafic quotidien
- Agent spécialisé SEO : audit des fiches produits en parallèle pendant dev
- **Skills proposés :** `product-description-seo`, `ad-campaign-analyzer`

---

### 4. Better With This Setup (CLAUDE.md + Skills + MCPs)
**Score : 7/10 · Analyse Gemini : ÉCHEC (quota)**
🔗 https://www.youtube.com/watch?v=pBHKTojO1YY

**TL;DR :** Setup personnel optimisé combinant CLAUDE.md, skills et MCPs. Config pratique et réutilisable.
*Analyse Gemini indisponible — quota free tier épuisé. À regarder en priorité.*

---

### 5. Beyond the Basics with Claude Code
**Score : 7/10 · Analyse Gemini : ÉCHEC (quota)**
🔗 https://www.youtube.com/watch?v=tuY2ChJIx48

**TL;DR :** CLAUDE.md avancé, MCP wiring, packaging des connaissances équipe en skills.
*Analyse Gemini indisponible — quota free tier épuisé. À regarder en priorité.*

---

## 📺 Nice-to-Watch (score 4-6)

| # | Titre | URL | Score | Raison |
|---|---|---|---|---|
| 1 | Claude out of the box is the weakest version of Claude | https://www.youtube.com/watch?v=IBb7DGuY5qs | 5 | Concept skill-augmentation |
| 2 | Make Claude Code Do Anything - Custom MCP Server Tutorial | https://www.youtube.com/watch?v=eXqSmNS-QtM | 5 | MCP custom Python from scratch |
| 3 | How To Enable Ultrathink In Claude Code | https://www.youtube.com/watch?v=ll7h8yORy6c | 5 | Tip ultrathink spécifique |
| 4 | Claude Code Is Now FREE Forever! Full Tutorial (2026) | https://www.youtube.com/watch?v=x4FxvP5IGQs | 4 | Tutoriel basique débutants |

---

## 🛠️ Skills Proposés (6) — À REVIEWER MANUELLEMENT

> ⚠️ Ces skills ne sont PAS déployés automatiquement. Ivan doit les valider et les installer lui-même.

| Skill | Source | Utilité estimée | Chemin |
|---|---|---|---|
| `product-launch-workflow` | k2ZOFBu3MJk | 9/10 | `claude-weekly/2026-11-09/skills-proposed/product-launch-workflow/SKILL.md` |
| `shopify-inventory-sync` | pvxNcQTcIy4 | 8/10 | `claude-weekly/2026-11-09/skills-proposed/shopify-inventory-sync/SKILL.md` |
| `dropship-order-automation` | pvxNcQTcIy4 | 9/10 | `claude-weekly/2026-11-09/skills-proposed/dropship-order-automation/SKILL.md` |
| `streetwear-trend-analyzer` | pvxNcQTcIy4 | 7/10 | `claude-weekly/2026-11-09/skills-proposed/streetwear-trend-analyzer/SKILL.md` |
| `product-description-seo` | jzf7DQa2CAc | 9/10 | `claude-weekly/2026-11-09/skills-proposed/product-description-seo/SKILL.md` |
| `ad-campaign-analyzer` | jzf7DQa2CAc | 8/10 | `claude-weekly/2026-11-09/skills-proposed/ad-campaign-analyzer/SKILL.md` |

---

## 🚀 Nouveautés Claude Code (semaine du 23 oct → 6 nov 2026)

### Releases majeures

**v2.1.311 — 26 octobre** ⭐ Important
- `ultrathink` disponible en effort `xhigh` sur Opus 5.5, Sonnet 5.5, Haiku 5.5 et **Fable 5.1**
- Correction : Claude Code ne réessaie plus les requêtes marquées non-réessayables par l'API

**v2.1.314 — 30 octobre**
- Nouveau : `permissions.blockWritesOutsideWorkingDirectories` — sécurité accrue
- Compaction automatique dans VS Code + Claude Desktop pour conversations > 200k tokens

**v2.1.316 — 31 octobre** ⚠️ Dépreciation
- `CLAUDE_CODE_DISABLE_ULTRATHINK`, `CLAUDE_CODE_SUBAGENT_EFFORT` disponibles
- **Mode rapide Opus 4.8 déprécié** depuis le 30 oct → suppression le 30 nov 2026. Migrer vers Opus 5.5.

**v2.1.317 — 3 novembre**
- `onFailure: "block"` pour les callbacks de hooks SDK
- Read tool : ne dit plus "file unchanged" — renvoie le contenu directement ✓
- Nouvelle vérification avant qu'un outil web envoie votre email sur le réseau

**v2.1.319 — 6 novembre** ⭐ Important
- Support tâches MCP dans le terminal avec passage en arrière-plan immédiat
- `permissions.denyInsteadOfPrompting` : refus auto des outils sans prompt permission
- `/loop` mode auto-rythmé se termine si aucune reprogrammation → plus propre

---

## 📡 MCP Officiel (commits 29 oct → 4 nov)

- **v2026.11.4** (4 novembre) : release Python CalVer
- Fix sécurité : `filesystem` → minimatch ^11.0.4 (CVE GHSA-g3hv-75wg-m249)
- Fix sécurité : `qs` → >=6.16.1 (CVE GHSA-6pq8-jhm2-2vcw)
- Fix `sequentialthinking` : dimensionnement thought box + bounds stderr
- Fix `gzip-file-as-resource` : attribution correcte du resource ID

---

## 🏢 Annonces Anthropic (octobre 2026)

**Don des Agent Skills à l'Agentic AI Foundation (22 oct)**
Anthropic a cédé le standard "Agent Skills" à l'Agentic AI Foundation (AAF), un consortium open source. 70+ plateformes ont déjà intégré le standard. Cela signifie que les SKILL.md sont maintenant un **standard ouvert multi-plateforme**, pas uniquement Claude.

**Claude Haiku 5.5 (7 oct)**
Petit modèle pour tâches à fort volume : résumés, sous-agents, navigation. Idéal pour sous-agents dans les workflows Ivan.

---

## 🛒 Claude × E-commerce (mois écoulé)

- **Claude Commerce (Anthropic, 2 sept)** : Blueprint open-source pour shopping agent + merchant agent. Shopify a publié `claude-for-commerce-examples` avec implémentations concrètes.
- **Shopify Storefront MCP** : activé par défaut sur les boutiques Plus depuis mars 2026.
- **Easyship MCP** (avril 2026) : serveur MCP pour gestion expéditions, compatible Claude Code.
- **Claude pour Shopify** : connecteur officiel dans le répertoire Anthropic. Coût minimum estimé : plan Shopify + ~17-20€/mois Claude Pro.

---

## 💡 Insight Cross-Sources

> **Le pattern récurrent de la semaine :** L'écosystème Claude se structure autour d'une architecture à 3 couches — (1) les **Skills** pour les connaissances métier locales (Markdown + scripts), (2) les **MCPs** pour les données live et les auth cloud, (3) les **Agents** pour la parallélisation. La distinction Code/Cowork d'Anthropic et le don du standard Skills à l'AAF confirment que cette architecture est durable. Pour Ivan, l'enjeu est de construire ses skills métier e-commerce maintenant pendant que l'écosystème se stabilise.

---

*Généré par veille-claude weekly — 2026-11-09 07:20 UTC*
*Prochaine édition : semaine du 16 novembre 2026*
