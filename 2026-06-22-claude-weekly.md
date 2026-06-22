# Claude Weekly Digest — 22 juin 2026

> Veille focus Claude / Claude Code / Skills / MCP
> Période couverte : 8–22 juin 2026
> MUST-WATCH: 2 · NICE: 4 · SKIP: 6 · Gemini analyses: 1/2 · Skills proposés: 1

---

## 🔴 MUST-WATCH

### 1. Artifacts in Claude Code: share your work as it happens
**URL** : https://www.youtube.com/watch?v=m7TJqx8CYG8
**Source** : Anthropic officiel · **Date** : 18 juin 2026 · **Score** : 10/10

**Analyse Gemini** : ✅ Disponible (partielle)

Claude Code génère maintenant des rapports HTML interactifs partageables via `claude.ai/code/artifact/` — sans compte Claude requis. La démo montre l'analyse d'un tunnel de conversion : 90 jours de données, identification du point de friction (68% d'échec sur l'étape export), maquettes "avant/après", plan A/B tests. Le rapport se met à jour en temps réel avec les itérations Claude.

**Pour Ivan** : Directement applicable — analyser les funnels TempleTwins/PURESOLE, partager des rapports avec des prestataires, générer des dashboards Shopify sans outils externes.

**Skill extrait** : `shopify-funnel-artifact` → voir `claude-weekly/2026-06-22/skills-proposed/`

---

### 2. Code with Claude Tokyo 2026: Opening Keynote
**URL** : https://www.youtube.com/watch?v=N4efO8viXXo
**Source** : Anthropic officiel (Code with Claude Tokyo, 10-11 juin 2026) · **Score** : 9/10

**Analyse Gemini** : ⚠️ Échec (timeout sur vidéo longue)

Premier événement Code with Claude en Asie-Pacifique. Keynote des leaders engineering/product Anthropic. Couvre les dernières features : subagents imbriqués (5 niveaux), commande `/cd`, safe mode, `fallbackModel`. Contexte : Anthropic en pleine montée en puissance post-Fable 5.

**Pour Ivan** : Snapshot de la direction Anthropic — important pour anticiper les features à venir.

---

## 🟡 NICE-TO-WATCH

### 3. Anthropic Just Dropped Claude Code Artifacts (endless possibilities)
**URL** : https://www.youtube.com/watch?v=uVKr50faO7E
**Date** : ~18-20 juin 2026 · **Score** : 6/10
Couverture communautaire des Artifacts Claude Code. Utile si la vidéo officielle (must-watch #1) n'est pas assez concrète.

### 4. Claude Just Released LIVE Artifacts... (Amazing Results)
**URL** : https://www.youtube.com/watch?v=K4_uPtfLfJg
**Date** : ~18-20 juin 2026 · **Score** : 5/10
Autre couverture communautaire. Peut donner des use-cases supplémentaires.

### 5. The ULTIMATE Beginner Guide to Claude Code in 2026
**URL** : https://www.youtube.com/watch?v=cH4WmWPEKC8
**Date** : 19 juin 2026 · **Score** : 4/10
Bon guide récapitulatif si un collaborateur découvre Claude Code.

### 6. How to Install and Use Claude Code for FREE (2026)
**URL** : https://www.youtube.com/watch?v=3s_p0PoLmoc
**Date** : ~8-9 juin 2026 · **Score** : 3/10
Setup guide. Utile pour onboarder.

---

## ⏭️ SKIP

- `X_36We6XDmI` — Claude Promo Code guide. Hors sujet.
- `ASAaKhK1B5w` — Anthropic Engineers Workflow (avril 2026, >14j)
- `efRIrLXoOVA` — Agent Harnesses Masterclass (mai 2026, >14j)
- `sJVxwwaF0sU` — Every New Claude Code Feature (déjà en seen-urls)
- `lpVkxuVmaLk` — Claude Massive Update (déjà en seen-urls)
- `05aY2LRIC3s` — Claude Code Full Course 12h (mai 2026, >14j)

---

## 📢 ANNONCES ANTHROPIC (8–22 juin 2026)

### Claude Code Artifacts — 18 juin 2026 ⭐ MAJEUR
- Claude Code génère des artifacts HTML interactifs partageables en temps réel
- URL publique `claude.ai/code/artifact/{id}` — accessible sans compte Claude
- Beta : Claude Team et Enterprise (CLI + desktop app)
- Use-cases : dashboards PR walkthrough, system explainers, release checklists, rapports analytics

### Claude Fable 5 & Mythos 5 — 9 juin 2026 ⭐ MAJEUR
- Fable 5 = modèle flagship public : thinking adaptatif always-on, 1M tokens contexte, 128K output
- Mythos 5 = même capacités sans classifiers sécurité — accès limité (Project Glasswing)
- Accès temporairement suspendu mi-juin (directive gouvernementale, source CNBC), puis rétabli

### Claude Code — Changelog 8–20 juin (v2.1.172 → v2.1.185)

| Version | Date | Feature clé |
|---------|------|-------------|
| v2.1.185 | 20 juin | Message "stream-stall" amélioré (20s au lieu de 10s) |
| v2.1.183 | 19 juin | Blocage git destructif en auto mode + WebSearch dans subagents |
| v2.1.181 | 17 juin | `/config key=value` en ligne de prompt |
| v2.1.178 | 15 juin | Skills en répertoires imbriqués `.claude/skills` ; spawn direct subagents par `name` |
| v2.1.176 | 12 juin | Titres de session multilingues ; `language` setting |
| v2.1.172 | 10 juin | **Subagents peuvent spawner leurs propres subagents (5 niveaux max)** |

### Claude Managed Agents — cron schedules — 10 juin 2026
- Agents planifiés via cron depuis le CLI Claude Code
- Credential vault pour les secrets des agents
- Route vers un nouveau paradigme "agent autopilot" — Ivan peut automatiser des tâches répétitives Shopify

### Claude Design Update — 17 juin 2026
- Imports de design systems, édition directe sur canvas, meilleurs exports
- Intégration plus poussée avec Claude Code

---

## 🔌 MCP OFFICIEL — Semaine du 8–22 juin

### Memory server : knowledge graph as MCP Resource (17 juin)
- `feat(memory)`: Le graphe de connaissances est maintenant exposé comme une ressource MCP lisible
- Support souscriptions aux ressources
- Pattern : connecter Obsidian/notes à Claude Code via MCP memory → knowledge graph actif

### Security hardening (14-16 juin)
- Dépendances Python/npm mises à jour (idna, starlette, vitest)
- `git_add` renforcé
- 9,400+ serveurs dans le registry officiel MCP

### AWS MCP Server — GA (juin 2026)
- AWS lance son MCP Server officiellement disponible
- Accès direct aux services AWS depuis Claude Code

---

## 🛍️ CLAUDE × SHOPIFY

- **Shopify AI Toolkit** : GA depuis avril 2026 — MCP officiel Shopify (store ops, product updates, analytics ShopifyQL)
- **SimGym** : Shopify lance un simulateur AI en research preview pour tous les marchands éligibles
- **Shopify Summer 2026 Editions** : Nouveau Unified Commerce Platform, Checkout & Accounts Configuration API, Shopify CLI 4.0

**Lecture recommandée** :
- https://www.fudge.ai/guides/shopify-ai-toolkit-claude-code-setup/
- https://checkoutpage.com/blog/best-mcp-servers-for-ecommerce

---

## 💡 SKILLS PROPOSÉS (1)

### `shopify-funnel-artifact`
**Inspiré de** : "Artifacts in Claude Code" (Anthropic, 18 juin)
**Dossier** : `claude-weekly/2026-06-22/skills-proposed/shopify-funnel-artifact/SKILL.md`

Skill Claude Code qui :
1. Interroge le MCP Shopify pour extraire les données de conversion (ShopifyQL)
2. Identifie les dropoffs par étape du funnel (product → cart → checkout → payment)
3. Génère un artifact HTML interactif avec visualisations, hypothèses, propositions A/B
4. Produit un lien partageable pour prestataires/agences

⚠️ **REVIEW MANUEL REQUIS avant tout déploiement**

---

## 📊 INSIGHT CROSS-VIDÉOS

**Pattern dominant cette semaine** : Anthropic pousse fort vers l'**artifact partageable** comme output primaire de Claude Code — le code n'est plus la finalité, c'est le rapport/dashboard live qui permet de collaborer sans friction. Combiné aux subagents imbriqués (5 niveaux) et aux cron schedules, Claude Code évolue vers un "système nerveux opérationnel" du solo founder.

---

## 📁 ANNEXES

- Analyses Gemini : `claude-weekly/2026-06-22/analyses/`
  - `m7TJqx8CYG8-artifacts-claude-code.md` ✅ (partielle)
  - `N4efO8viXXo-tokyo-keynote.md` ⚠️ (échec timeout)
- Skills proposés : `claude-weekly/2026-06-22/skills-proposed/shopify-funnel-artifact/`

---

*Généré par veille-claude-weekly · 22 juin 2026*
