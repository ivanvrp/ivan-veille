# Claude Weekly — 2026-07-06

> Veille focus Claude / Claude Code / Skills / MCP · Semaine du 2026-06-29 au 2026-07-06

---

## ACTUALITÉS ANTHROPIC CETTE SEMAINE

### 🚀 Claude Sonnet 5 — Nouveau modèle par défaut dans Claude Code (30 juin)
- Modèle le plus agentique de la gamme Sonnet
- Fenêtre de contexte native 1M tokens
- Pricing promo : $2/$10 par Mtok jusqu'au 31 août
- Raisonnement, tool use, coding et gestion autonome renforcés

### 🔬 Claude Science — Workbench pour chercheurs (30 juin)
- Intègre les outils et packages des chercheurs en laboratoire
- Optimisé pharma/science, produit des artifacts auditables
- Accès flexible aux ressources de calcul
- Cible : labo pharma et recherche scientifique

### 🌐 Fable 5 et Mythos 5 — Restrictions export levées (1er juillet)
- US Department of Commerce a retiré les contrôles export
- Anthropic commence à restaurer l'accès à ces modèles
- Impact : disponibilité internationale élargie

### ⚙️ Claude Code — Releases majeures cette semaine

| Version | Date | Changement clé |
|---------|------|----------------|
| 2.1.201 | 3 juil | Fix sessions Sonnet 5 mid-conversation |
| 2.1.200 | 3 juil | **Mode Manuel par défaut** (was "default") · AskUserQuestion sans auto-continue |
| 2.1.199 | 2 juil | Stacked slash-skills (jusqu'à 5 skills chainés) · Préservation réponses partielles |
| 2.1.198 | 1er juil | **Subagents en arrière-plan par défaut** · Claude in Chrome GA · `/dataviz` skill · Background agents auto-commit/push/PR |
| 2.1.197 | 30 juin | Claude Sonnet 5 comme modèle par défaut |

**Changement critique 2.1.200 :** Permission mode passe à "Manual" — vérifier vos settings.json si vous aviez des automatisations en mode "default".

**Changement clé 2.1.198 :** Subagents run in background by default. Claude continue à travailler pendant que les sous-agents exécutent leurs tâches.

### 🔌 MCP — Dépôt officiel (modelcontextprotocol/servers)
- Migration CI/CD vers OIDC trusted publishing (npm)
- 4 juil : refonte complète du processus de release
- Fix deps : python-multipart, cryptography, pyjwt (sécurité)
- Contexte 2026 : +9 400 serveurs MCP dans le registre officiel

---

## MUST-WATCH — 5 vidéos · Score ≥ 7/10

### 1️⃣ What Claude Code Can Do That You Haven't Tried — Gui Ferreira (NDC AI 2026)
**URL :** https://www.youtube.com/watch?v=zaDbZt40kRg  
**Score Gemini :** 9/10 · Date : < 7 jours · Source : NDC Conference  
**Score sélection :** 9/10

**TL;DR :** 40 astuces avancées Claude Code pour fondateur solo — configuration, daily workflow, platform layer, beyond code. Probablement la vidéo la plus dense de la semaine.

**Highlights clés :**
- [6:16] Audit en 3 questions pour `claude.md` (surcharge = -20% performance, +20% coûts)
- [12:38] `permissions.deny` pour garder les secrets hors contexte Claude
- [24:10] `ultrathink` pour forcer un raisonnement profond sur les problèmes complexes
- [26:04] La "Dumb-Zone" du contexte : au-delà de 40% d'utilisation = qualité se dégrade
- [43:55] Skills = dossiers `.claude/skills` avec scripts + références + templates
- [48:19] `/loop 5m check if deploy finished` — monitoring CI/CD automatique
- [53:11] Claude lit un vault Obsidian → "Show me my priorities this week from my journal"

**Patterns Ivan :**
- Audit `claude.md` en 3 questions → garder < 40% contexte utilisé
- `cat log.txt | claude -p "rank errors by frequency" > out.txt` — piping CLI
- `/goal implement the feature. don't stop until tests pass.` — exécution autonome
- `/loop 5m check inventory levels` → monitoring stocks dropship

**Skills proposés :** shopify-seo-product-description, obsidian-insights

---

### 2️⃣ How to Create Sub Agents in Claude Code (2026)
**URL :** https://www.youtube.com/watch?v=ICgTn1JMU9Y  
**Score Gemini :** 9/10 · Date : < 7 jours  
**Score sélection :** 8/10

**TL;DR :** Créer des agents spécialisés avec portée, outils et mémoire configurables — très pertinent avec le release 2.1.198 (background subagents).

**Highlights clés :**
- Configuration d'agents par dossier `.claude/agents/`
- Définir les outils autorisés par agent (least-privilege)
- Mémoire contextuelle persistante par projet
- Modèles adaptés : Sonnet 5 pour tâches complexes, Haiku 4.5 pour léger

**Patterns Ivan :**
- Agent `shopify-theme-dev` : accès limité aux fichiers Liquid/CSS uniquement
- Agent `dropship-research` : outils web + analyse, pas d'écriture fichiers
- Lancer 2-3 agents en parallèle → thème + contenu + analytics simultanément

**Skills proposés :** configure-sub-agent

---

### 3️⃣ Claude Code Just Killed Every Shopify Agency Ever
**URL :** https://www.youtube.com/watch?v=x2pRavsHdls  
**Score Gemini :** 9/10 · Thème : Claude Code + Shopify  
**Score sélection :** 9/10 (use-case Ivan direct)

**TL;DR :** Build complet d'un store Shopify custom avec Claude Code + Gemini — compte partenaire, Shopify CLI, skills génération d'images, hooks, itération HTML avant déploiement Liquid.

**Highlights clés :**
- Workflow HTML-first : prototyper en HTML/CSS avant de toucher au thème Liquid
- Integration Shopify Partner account + CLI pour tests sans vrai store
- Skills spécifiques : génération d'images produit, prototypage HTML
- Hooks post-edit pour auto-refresh du preview navigateur

**Patterns Ivan :**
- Prototyper les sections TempleTwins en HTML → valider visuellement → convertir en Liquid
- PURESOLE : landing pages produit générées depuis brief en < 10 min
- `claude mcp add shopify-dev -- npx -y @shopify/dev-mcp@latest`

**Skills proposés :** shopify-ui-prototyper

---

### 4️⃣ This MCP Builds Entire Branded Websites in Claude Code
**URL :** https://www.youtube.com/watch?v=A0bxjZsLo4k  
**Score Gemini :** 9/10 · Thème : MCP + assets marketing  
**Score sélection :** 8/10

**TL;DR :** Higgsfield MCP génère images produit, vidéos UGC, kits de marque et sections web depuis un brief minimal — branché dans Claude Code.

**Highlights clés :**
- [0:11] Génération d'images produit lifestyle depuis URL produit Shopify
- Vidéos UGC avec script + personnage cohérent
- Adaptation publicités existantes avec nouveau branding
- CLI → tout orchestré par Claude, zéro outil externe

**Patterns Ivan :**
- TempleTwins : visuals lifestyle streetwear sans shooting (~500-2000€ économisés)
- PURESOLE : assets produit depuis URLs fournisseurs → Meta Ads en quelques minutes
- `claude mcp add higgsfield -- npx -y higgsfield-mcp@latest`

**Skills proposés :** ecommerce-asset-generator

---

### 5️⃣ Watch This If You're Just Learning How to Use Claude Code in 2026
**URL :** https://www.youtube.com/watch?v=ECQA6oOyfIk  
**Score Gemini :** 9/10 · Date : < 7 jours  
**Score sélection :** 7/10

**TL;DR :** Fonctionnalités pratiques post-basiques — Équipes d'agents, mode Objectif, mode Automatique, ScaleKit pour SSO sécurisé.

**Highlights clés :**
- Agent Teams : collaboration multi-agents sur projet commun
- Mode Objectif : tâches autonomes avec condition d'arrêt explicite
- Mode Automatique : exécution sans interruption pour pipelines batch
- ScaleKit : gestion sécurisée des accès OAuth dans les apps Claude

**Patterns Ivan :**
- Mode Objectif → "rédige les 20 descriptions produit PURESOLE sans t'arrêter"
- Agent Teams : un agent rédige, un autre vérifie la cohérence de marque

---

## NICE-TO-WATCH — 6 vidéos · Score 4-6

| # | Titre | URL | Note |
|---|-------|-----|------|
| 1 | How to Build Effective Claude Code Agents in 2026 | https://www.youtube.com/watch?v=RzLV8sfFdMM | 3 semaines, agents généraux |
| 2 | FULL Claude Code Tutorial For Beginners (PRO) 2026 | https://www.youtube.com/watch?v=X_zVY3-mbM8 | 6j, très long (> 1M tokens) |
| 3 | The ULTIMATE Beginner Guide to Claude Code in 2026 | https://www.youtube.com/watch?v=cH4WmWPEKC8 | 2 sem, beginner |
| 4 | New Shopify AI Toolkit: Claude Code Setup + Demo | https://www.youtube.com/watch?v=ptnWksC9TXY | Avril 2026, setup MCP Shopify |
| 5 | Build Shopify Themes in MINUTES [Claude Code & MCP] | https://www.youtube.com/watch?v=0tEkfZ4vtcs | Mars 2026, Liquid theming |
| 6 | Claude Code Sub-Agents: Step-by-Step Beginner Tutorial | https://www.youtube.com/watch?v=MbKUeufUZIY | Mars 2026, intro subagents |

---

## SKIP — Ignorés cette semaine

- "Claude Ai Promo Code (Updated 2026)" — spam/hors-sujet
- "CLAUDE CODE FULL COURSE 12 HOURS" — Mai 2026 (> 14j)
- Vidéos generiques "how to use AI" sans focus Claude Code

---

## SKILLS PROPOSÉS — 4 nouveaux

> ⚠️ NON DÉPLOYÉS — Review manuelle Ivan requise

| Skill | Source | Use-case principal | Fichier |
|-------|--------|-------------------|---------|
| `shopify-seo-product-description` | Gui Ferreira NDC AI | Descriptions SEO TempleTwins + PURESOLE | claude-weekly/2026-07-06/skills-proposed/shopify-seo-product-description/SKILL.md |
| `configure-sub-agent` | How to Create Sub Agents | Créer agents spécialisés par projet | claude-weekly/2026-07-06/skills-proposed/configure-sub-agent/SKILL.md |
| `shopify-ui-prototyper` | Shopify Agency Killer | Prototyper sections HTML avant Liquid | claude-weekly/2026-07-06/skills-proposed/shopify-ui-prototyper/SKILL.md |
| `ecommerce-asset-generator` | MCP Branded Websites | Assets marketing IA via Higgsfield MCP | claude-weekly/2026-07-06/skills-proposed/ecommerce-asset-generator/SKILL.md |

---

## INSIGHT CROSS-VIDÉOS

**Pattern récurrent semaine :** La tendance majeure est l'**orchestration background-first** — avec Claude Code 2.1.198, les subagents tournent en arrière-plan par défaut, et toutes les vidéos convergent vers le même modèle : un Claude "chef d'orchestre" qui délègue à des agents spécialisés (code, contenu, assets) pendant que Ivan continue à travailler. Pour TempleTwins et PURESOLE, cela signifie : lancer un batch de 20 descriptions produit en background, continuer à gérer sa boutique, récupérer les résultats quand c'est prêt.

---

## SOURCES COLLECTÉES

- https://www.anthropic.com/news/claude-science-ai-workbench
- https://code.claude.com/docs/en/changelog
- https://github.com/modelcontextprotocol/servers/commits/main.atom
- https://releasebot.io/updates/anthropic/claude-code
- https://www.aljazeera.com/economy/2026/7/1/us-lifts-restrictions-on-powerful-ai-models-fable-mythos-anthropic-says
- https://www.statnews.com/2026/06/30/anthropic-release-claude-science-ceo-dario-amodei/
- https://codersera.com/blog/claude-skills-mcp-servers-practitioner-guide-2026/
- https://www.youtube.com/watch?v=zaDbZt40kRg
- https://www.youtube.com/watch?v=ICgTn1JMU9Y
- https://www.youtube.com/watch?v=x2pRavsHdls
- https://www.youtube.com/watch?v=A0bxjZsLo4k
- https://www.youtube.com/watch?v=ECQA6oOyfIk

---

*Généré par veille-claude-weekly · 2026-07-06 · Gemini 2.5 Flash analyses*
