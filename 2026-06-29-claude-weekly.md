# Claude Weekly Digest — 29 juin 2026

> Veille focus Claude / Claude Code / Skills / MCP
> Période couverte : 22–29 juin 2026
> MUST-WATCH: 3 · NICE: 5 · SKIP: 3 · Gemini analyses: 0/2 (API 429+503) · Skills proposés: 2

---

## 🔴 MUST-WATCH

### 1. How an amateur (me) learned to loop — w/ Matthew Berman
**URL** : https://www.youtube.com/watch?v=1iIOGpJXSgQ
**Source** : Matthew Berman (Tier S) · **Date** : 23 juin 2026 · **Score** : 9/10

**Analyse** : ⚠️ Gemini indisponible (429+503) — synthèse web

Matthew Berman interviewe un amateur qui a maîtrisé les loops Claude Code. La vidéo couvre les patterns concrets pour diriger des agents : planning system, vérification entre étapes, chaîner des sessions multiples pour éviter la dégradation de contexte ("dumb zone" des modèles). Format interview → accessible, concret, pas théorique.

**Pour Ivan** : Directement applicable — looper des tâches répétitives PURESOLE (descriptions produits en masse) et TempleTwins (optimisation catalogue). Le pattern "agent planificateur + agents exécutants" est la clé.

**Skill extrait** : `shopify-product-loop` → voir `claude-weekly/2026-06-29/skills-proposed/shopify-product-loop/`

---

### 2. EVERY Loop From Matthew Berman's New Loop Library! (Copy & Paste!)
**URL** : https://www.youtube.com/watch?v=9QaD8Avfu2Q
**Source** : Matthew Berman channel · **Date** : ~18-20 juin 2026 · **Score** : 8/10

**Analyse** : ⚠️ Gemini indisponible — synthèse web

Loop Library lancée le 18 juin 2026 (612K vues). 26 loops disponibles en copier-coller. Chaque loop = template complet CLAUDE.md + hooks + prompt. Format ultra-pratique : zéro configuration théorique. Inclut research loops, content loops, verification loops. Disponibles sur https://forwardfuture.com/

**Pour Ivan** : Format copier-coller = déployable en 10 min. Loops adaptables pour weekly analytics Shopify, competitor spy, génération contenu social.

**Skill extrait** : `loop-library-shopify` → voir `claude-weekly/2026-06-29/skills-proposed/loop-library-shopify/`

---

### 3. Introducing Claude Tag — Claude dans Slack comme coéquipier
**URL** : https://www.anthropic.com/news/introducing-claude-tag
**Source** : Anthropic officiel · **Date** : 23 juin 2026 · **Score** : 9/10

Anthropic lance Claude Tag, un **Claude permanent dans Slack** qui agit comme coéquipier d'équipe (pas chatbot privé). Tout le monde dans le canal peut voir et diriger Claude. Il mémorise le contexte des canaux, peut planifier des tâches futures, et en mode "ambient" proactive il remonte les infos importantes sans être sollicité.

**Features clés** :
- Taguer `@Claude` dans n'importe quel canal Slack → déléguer une tâche
- Travaille en arrière-plan pendant que l'équipe fait autre chose
- Context mémoire cross-canaux
- Disponible en beta publique Enterprise et Team (Opus 4.8)
- Anthropic en interne : 65% du code produit généré par leur version de Claude Tag

**Pour Ivan** : Pas immédiatement pour solo founder (Team/Enterprise). Mais signale la direction : Claude devient une **présence permanente**, pas un outil ponctuel. À surveiller pour quand TempleTwins scale.

---

## 🟡 NICE-TO-WATCH

### 4. Claude Code's NEW Open Source Repo Builds AI Agents in MINUTES!
**URL** : https://www.youtube.com/watch?v=Bex_292yJfU
**Date** : ~26 juin 2026 · **Score** : 5/10

Couvre le repo open source Anthropic `launch-your-agent` (https://github.com/anthropics/launch-your-agent). Permet de bootstrapper un agent Claude Code en quelques minutes. Utile si Ivan veut créer un agent custom rapidement sans partir de zéro.

---

### 5. This Open Source Repo Solves Claude Code's Biggest Problem
**URL** : https://www.youtube.com/watch?v=aTPTUYC44ds
**Date** : ~25-28 juin 2026 · **Score** : 5/10

Examine une solution open source aux limitations de Claude Code (probablement liée à la gestion du contexte long ou aux loops). À vérifier pour le contenu exact.

---

### 6. How to Build Effective Claude Code Agents in 2026
**URL** : https://www.youtube.com/watch?v=RzLV8sfFdMM
**Date** : ~15 juin 2026 · **Score** : 5/10

Guide complet pour diriger des agents Claude Code efficacement. Contenu : planning vs verification, "dumb zone" des modèles, chaining de sessions. Complémentaire à la vidéo Matthew Berman #1.

---

### 7. Claude Code 2.1.186 — Skills dans /plugin (nouveau!)
**URL** : https://code.claude.com/docs/en/changelog
**Date** : 22 juin 2026 · **Score** : 6/10

Update importante : **section "Skills" apparaît maintenant dans `/plugin`**. Plus besoin de naviguer manuellement — les skills locaux sont listés et activables depuis l'UI. Aussi : `claude mcp login/logout <name>` sans menu interactif.

---

### 8. Claude Code 2.1.191 — /rewind et sandox.credentials
**URL** : https://code.claude.com/docs/en/changelog
**Date** : 24 juin 2026 · **Score** : 6/10

Deux features très utiles :
- `/rewind` : reprendre une conversation depuis avant `/clear` → plus de perte de contexte accidentelle
- `sandbox.credentials` : bloquer l'accès aux fichiers credentials depuis le sandbox → meilleure sécurité pour sessions longues

---

## ⚪ SKIP

- **"NEW Claude Code Update is INSANE!"** (https://www.youtube.com/watch?v=QOf8Z4iS8pk) — Clickbait, contenu redondant avec changelog officiel
- **"Claude Code AI Training || Visualpath"** (https://www.youtube.com/watch?v=0hFrV_8G1OM) — Canal formation basique, pas adapté solo founder avancé
- **"Claude AI Promo Code"** (https://www.youtube.com/watch?v=X_36We6XDmI) — Hors scope

---

## 🛠️ SKILLS PROPOSÉS (2)

### 1. `shopify-product-loop`
**Valeur** : Générer/optimiser 50-500 descriptions produits Shopify en boucle automatique, par batch de 10, avec checkpoint qualité.  
**Source** : Pattern Matthew Berman loops + MCP Shopify existant  
**Dossier** : `claude-weekly/2026-06-29/skills-proposed/shopify-product-loop/SKILL.md`

### 2. `loop-library-shopify`
**Valeur** : Adapter les 26 loops de Matthew Berman pour contexte e-commerce : weekly analytics, competitor spy, content calendar.  
**Source** : Loop Library https://forwardfuture.com/  
**Dossier** : `claude-weekly/2026-06-29/skills-proposed/loop-library-shopify/SKILL.md`

⚠️ Ces skills ne sont PAS déployés — review manuelle par Ivan requise.

---

## 📡 NEWS ANTHROPIC SEMAINE

| Date | Annonce |
|------|---------|
| 23 juin | **Claude Tag** (beta) — Claude dans Slack comme coéquipier, Enterprise/Team |
| 26 juin | Claude Code 2.1.195 — CLAUDE_CODE_DISABLE_MOUSE_CLICKS, dictation macOS amélioré |
| 25 juin | Claude Code 2.1.193 — autoMode.classifyAllShell, OpenTelemetry events |
| 24 juin | Claude Code 2.1.191 — /rewind, sandbox network permissions |
| 23 juin | Claude Code 2.1.187 — sandbox.credentials, restrictions modèles par org |
| 22 juin | Claude Code 2.1.186 — **Skills dans /plugin**, mcp login/logout CLI |
| 22-29 | **Self-hosted sandboxes** (beta) — outil execution sur infra propre (Cloudflare, Modal, Vercel) |
| 22-29 | **Claude sur Apple Foundation Models** — iOS 27 / iPadOS 27 / macOS 27 |
| ~27 juin | Fast mode Claude Opus 4.7 déprécié (→ migrer vers Opus 4.8) |

---

## 🔌 MCP UPDATE

**Memory Server** (17 juin) : Le graphe de connaissances est maintenant exposé comme **Resource MCP** (`memory://knowledge-graph`). Les clients peuvent subscribe aux mises à jour en temps réel. C'est un changement majeur — on peut désormais construire des agents qui *lisent* l'état du graphe mémoire sans appeler d'outils.

**Sécurité MCP** (16 juin) : Correctifs critiques (GHSA-5xrq RCE vitest, CVE-2026-27735 git). Mise à jour de tous les serveurs recommandée.

---

## 💡 INSIGHT CROSS-SOURCES

**Le pattern de la semaine : Loops + Mémoire continue.**

Matthew Berman popularise les loops (26 templates, 612K vues en 11 jours), le Memory MCP expose son graphe comme Resource, et Claude Tag apporte la persistance à l'échelle de l'équipe. La convergence est claire : **Claude passe du mode "réponse ponctuelle" au mode "agent en cours d'exécution permanente"**. Pour Ivan, l'action concrète = commencer à boucler les tâches répétitives PURESOLE/TempleTwins maintenant, avant que ce soit la norme et que la courbe d'apprentissage soit plus raide.

---

## 📊 STATS RUN

```
MUST_WATCH: 3 · NICE: 5 · SKIP: 3
GEMINI_ANALYSES: 0/2 (API 429 quota + 503 surcharge)
SKILLS_PROPOSED: 2
GITHUB_URL: https://github.com/ivanvrp/ivan-veille/blob/main/2026-06-29-claude-weekly.md
```
