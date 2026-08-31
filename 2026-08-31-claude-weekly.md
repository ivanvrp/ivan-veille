# Claude Weekly — 2026-08-31

> Deep-dive Claude / Claude Code / Skills / MCP · Semaine du 2026-08-24 au 2026-08-31  
> Analyses Gemini 2.5 Flash sur 2 vidéos YouTube must-watch · 2 skills proposés

---

## ACTUALITÉS ANTHROPIC CETTE SEMAINE (24-31 août)

### ⚙️ Claude Code — Releases majeures

| Version | Date | Changement clé |
|---------|------|----------------|
| 2.1.251 | 28 août | **`PreModelSwitch` / `PostModelSwitch` hooks** : bloquer/confirmer les changements de modèle · Streaming live des appels d'outils subagents vers Remote Control |
| 2.1.248 | 27 août | **`--restricted` mode** : supprime outils CLI et WebFetch (sandboxing agents) · `experimental.cacheTtl` dans frontmatter agent (5m ou 1h) · Labels custom self-hosted runner |
| 2.1.247 | 26 août | **`SendFeedback` tool** : Claude rédige des rapports de feedback · **Skill `/claude-api cost-optimize`** |
| 2.1.246 | 25 août | Tab auto mode dans `/permissions` · Avertissement wildcard Bash · Affichage temps d'exécution |
| 2.1.243 | 25 août | **`promptCacheTtl` + `subagentPromptCacheTtl`** : gestion cache par scénario · `modelPicker` setting |

### 🔌 MCP officiel — Corrections critiques (fin août)

- **filesystem** : reject Windows paths on POSIX, permissions préservées, Unicode normalisé
- **memory** : écriture atomique du knowledge graph (plus de corruption)
- **sequential-thinking** : synchronisation version dynamique
- Compatibilité containers Docker/Podman/SELinux pour fetch, git, time servers

### 💰 Pricing Sonnet 5

- Promo terminée au 1er septembre : $2/$10 → **$3/$15 par Mtok**
- **Agir maintenant** : finir les runs batch coûteux avant minuit le 31 août

### 📋 Managed Agents — Contrôles avancés (recap)

- **Session budgets**, advisor models, **inference geo pinning**
- **GitHub-hosted skills** : référencer un repo GitHub directement (plus de copier/coller)
- Mid-conversation tool changes en beta sur Fable 5, Mythos 5, Opus 4.8, Opus 5

---

## SCORING VIDÉOS

| Score | Vidéo | Action |
|-------|-------|--------|
| 8/10 | Code with Claude 2026 SF — Opening Keynote | MUST-WATCH |
| 8/10 | Code with Claude Tokyo 2026 — Opening Keynote | MUST-WATCH |
| 5/10 | Claude Code Is Defaulting To Auto Mode — Explained | NICE |
| 5/10 | Claude Code's New Upgrade: Automate Any Task | NICE |
| 5/10 | What Claude Code Can Do That You Haven't Tried (NDC AI 2026) | NICE |
| 4/10 | The ULTIMATE Beginner Guide to Claude Code 2026 | NICE |
| 4/10 | Claude Code: Full Course Autonomous Goals MCP VS Code | NICE |
| -5 | Claude Code Tutorial for Beginners + Skills MCP | SKIP (doublon) |
| -5 | Claude Skills Tutorial Build Run Share | SKIP (doublon) |
| -5 | Claude Code is all you need 2026 | SKIP (doublon) |

---

## 🔥 MUST-WATCH (2)

### 1. Code with Claude 2026 — Opening Keynote (SF)
**URL :** https://www.youtube.com/watch?v=GMIWm5y90xA  
**Chaîne :** Anthropic (officiel)  
**Date :** 6 mai 2026  
**Score :** 8/10 · Exception Anthropic majeure  
**Analyse Gemini :** ✅ Disponible

**Résumé exécutif :**  
Keynote Anthropic présentant l'évolution exponentielle de Claude Code — agents autonomes, Routines déclenchées par événements, orchestration multi-agents, pattern Advisor/Executor. Pas de nouveau modèle annoncé mais infrastructure agent de production complète. API volume Anthropic +17x YoY pendant la keynote.

**Concepts clés :**
- `[04:20]` Stripe : 50k lignes Scala → Java en 4 jours (vs 10 semaines manuelles)
- `[22:18]` **Stratégie Advisor/Executor** : Executor Sonnet (rapide/économique) + Advisor Opus (valide décisions critiques)
- `[25:25]` **Dreaming agents** : apprennent de leurs propres sessions passées pour s'améliorer
- `[37:00]` **Routines** : agents cloud déclenchés webhook/schedule/GitHub issues
- `[40:17]` Claude Code = +200% vitesse développement pour certaines entreprises

**Patterns Ivan :**
1. Routines Shopify — stock bas → alerte Slack + commande auto
2. Advisor/Executor pour decisions prix dropship (Sonnet cherche, Opus valide)
3. Dreaming : alimenter l'agent des données perf pub pour auto-optimisation

**Skills proposés :** `advisor-executor-shopify`, `shopify-routine-ops`

---

### 2. Code with Claude Tokyo 2026 — Opening Keynote
**URL :** https://www.youtube.com/watch?v=N4efO8viXXo  
**Chaîne :** Anthropic (officiel)  
**Date :** 10 juin 2026  
**Score :** 8/10 · Exception Anthropic majeure  
**Analyse Gemini :** ❌ Échec (connexion reset — à regarder manuellement)

**Contexte :** Keynote de la tournée Asia-Pacific. Focus Managed Agents pour enterprises, démonstrations locale au marché japonais. Anthropic annonce des partenariats studio de jeux et fintech.  
**TL;DR :** Même infrastructure agent que SF mais use-cases production — complémentaire, pas dupliqué.

---

## 📺 NICE-TO-WATCH (5)

### 3. Claude Code Is Defaulting To Auto Mode — Explained
**URL :** https://www.youtube.com/watch?v=jHRIJAzVOx0  
**Date :** ~14 août 2026  
**Pourquoi :** Auto mode = défaut depuis le 14 août sur Pro/Max/Team. Changement comportemental majeur pour les workflows Ivan. Comprendre les implications pour les sessions automatisées (routines veille, etc.)  
**Micro-action :** Vérifier ses settings `/permissions` pour s'assurer que le mode auto est bien configuré pour ses projets.

### 4. Claude Code's New Upgrade: Automate Any Task (Full Tutorial 2026)
**URL :** https://www.youtube.com/watch?v=ZbawXiYm4Go  
**Date :** ~10 août 2026  
**Pourquoi :** Recap des upgrades récents (fork mode, cross-session messaging, self-hosted environments) avec demo pratique. Bon complément du changelog.  
**Micro-action :** Tester `/subtask` pour paralléliser une tâche veille pendant qu'Ivan travaille sur autre chose.

### 5. What Claude Code Can Do That You Haven't Tried — Gui Ferreira (NDC AI 2026)
**URL :** https://www.youtube.com/watch?v=zaDbZt40kRg  
**Date :** 1er juillet 2026  
**Pourquoi :** Talk de conférence = use-cases avancés peu documentés. Patterns hidden features par un speaker reconnu.  
**Micro-action :** Regarder en 1.5× pour extraire les 3 features que vous n'utilisez pas encore.

### 6. The ULTIMATE Beginner Guide to Claude Code in 2026
**URL :** https://www.youtube.com/watch?v=cH4WmWPEKC8  
**Pourquoi :** Onboarding si Ivan veut intégrer un collaborateur ou un stagiaire sur son stack Claude Code.

### 7. Claude Code Full Course – Autonomous Goals, MCP, and VS Code Setup
**URL :** https://www.youtube.com/watch?v=7l6bXLAKyEI  
**Pourquoi :** freeCodeCamp, coverage complète MCP + VS Code extension + `/goal` command. Référence quand on setup un nouveau projet.

---

## 🛠️ SKILLS PROPOSÉS (2)

> ⚠️ Skills proposés — JAMAIS déployés auto. Ivan review manuellement avant installation.

### 1. `advisor-executor-shopify`
**Chemin :** `claude-weekly/2026-08-31/skills-proposed/advisor-executor-shopify/SKILL.md`  
**Source :** Code with Claude SF 2026 — timestamp 22:18  
**Résumé :** Orchestration coût-efficace Sonnet (Executor) + Opus (Advisor) pour décisions e-commerce à fort impact (repricing, sélection produits dropship, arbitrage budgets pub).

### 2. `shopify-routine-ops`
**Chemin :** `claude-weekly/2026-08-31/skills-proposed/shopify-routine-ops/SKILL.md`  
**Source :** Code with Claude SF 2026 — timestamp 37:00  
**Résumé :** Routines Claude Code pour automatiser les opérations Shopify — alertes stock bas, report hebdo ventes, suivi abandon panier. Déclenché par schedule ou webhook.

---

## 🔧 CLAUDE CODE CHANGELOG DIGEST (24-31 août)

### Features majeures cette semaine

**`PreModelSwitch` / `PostModelSwitch` hooks (v2.1.251)**  
Les admins peuvent maintenant bloquer ou confirmer les changements de modèle mid-session. Utile pour forcer Sonnet sur les tâches répétitives et Opus sur les décisions critiques.
```json
{
  "hooks": {
    "PreModelSwitch": [{
      "matcher": "model:opus",
      "hooks": [{ "type": "command", "command": "echo 'Opus upgrade — confirmer?' && read" }]
    }]
  }
}
```

**`--restricted` mode (v2.1.248)**  
Lance Claude Code sans outils CLI (Bash) et sans WebFetch. Idéal pour sandboxer des agents de génération de contenu qui ne doivent pas toucher au système.
```bash
claude --restricted -p "Génère 20 descriptions produits pour PURESOLE"
```

**`experimental.cacheTtl` (v2.1.248)**  
Dans le frontmatter des agents `.claude/agents/*.md` :
```yaml
---
model: claude-sonnet-5
experimental:
  cacheTtl: "1h"   # ou "5m" pour sessions courtes
---
```
Optimise les coûts sur les veilles longues (comme cette routine).

**Cross-session `@mention` (v2.1.232)**  
Taper `@nom-session` dans le prompt envoie un message à une autre session Claude Code active. Permet à la veille de notifier une session de dev en cours.

---

## 🔌 MCP OFFICIEL — ÉTAT

### Serveurs recommandés (stables fin août)

| Serveur | Version stable | Usage Ivan |
|---------|---------------|------------|
| `filesystem` | Fixes critiques 28 août | Lecture/écriture repo veille |
| `memory` | Atomic writes 28 août | Knowledge graph TempleTwins |
| `sequential-thinking` | Fix Zod schema 28 août | Planification drops |
| `fetch` | SELinux containers 30 août | Scraping tendances |

### À surveiller
- **`shopify` MCP** : deprecated storefront cart tools au 31 août → migrer vers UCP/Hydrogen si utilisé
- Pas de nouveau serveur MCP officiel cette semaine

---

## 📊 RÉCAPITULATIF

```
DIGEST_DATE: 2026-08-31
MUST_WATCH:  2 · NICE: 5 · SKIP: 3 (doublons)
GEMINI_ANALYSES: 1 sur 2 tentatives (SF: OK, Tokyo: échec connexion)
SKILLS_PROPOSED: 2 (advisor-executor-shopify, shopify-routine-ops)
GITHUB_URL: https://github.com/ivanvrp/ivan-veille/blob/main/2026-08-31-claude-weekly.md
```

---

## 💡 INSIGHT CROSS-SOURCES

Le pattern central de la semaine : **Claude Code devient une plateforme d'orchestration**, pas juste un assistant de code. Fork mode par défaut + cross-session messaging + Routines + hooks PreModelSwitch = on peut maintenant construire des systèmes autonomes qui se surveillent eux-mêmes. Pour Ivan, le levier concret est dans les Routines Shopify + Advisor/Executor pour décisions stratégiques — sans coder.
