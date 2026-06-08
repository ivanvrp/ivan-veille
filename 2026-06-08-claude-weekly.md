# Claude Weekly — 2026-06-08

> Focus : Claude Code · Skills · MCP · Agents · Shopify AI
> Période couverte : 25 mai – 8 juin 2026

---

## 📊 Stats hebdo

| Metric | Valeur |
|--------|--------|
| Must-watch | 3 |
| Nice | 3 |
| Skip | 7 |
| Gemini analyses | 2/3 (1 échec : London keynote inaccessible) |
| Skills proposés | 3 |

---

## 🔥 MUST-WATCH

### 1. Code with Claude SF 2026: Opening Keynote
**🔗** https://www.youtube.com/watch?v=GMIWm5y90xA
**📅** 6 mai 2026 | **Source :** Anthropic officiel | **Score Ivan :** 9/10

> Keynote de lancement de la conférence Code with Claude à San Francisco. Ami Vora, Boris Cherny, Dianne Penn. Annonces majeures sur Claude Managed Agents, Dynamic Workflows, Claude Design, Routines et CI auto-fix.

**Highlights Gemini (analyse complète) :**
- [04:00] Stripe : 50 000 lignes Scala → Java en **4 jours** (vs 10 semaines estimées)
- [07:00] Volume API ×17 YoY — les devs passent 20h/sem avec Claude
- [09:20] **Rate limits doublés** sur Claude Code Pro/Max/Team/Enterprise
- [11:10] Pattern "Executor + Advisor" : Sonnet exécute, Opus conseille → réduction coûts
- [11:20] **Claude Managed Agents** : sandboxing, error recovery, auth, memory, checkpointing en prod
- [11:50] **Routines** : tâches automatiques via schedule/webhook/API
- [12:00] **CI auto-fix** : PRs toujours vertes, rebase auto
- [25:17] **Claude Design** : génération de designs graphiques interactifs depuis un prompt

**Micro-action Ivan :** Regarder la section Routines [11:50-12:30] et identifier 1 tâche PURESOLE automatisable cette semaine.

**Analyse complète :** `claude-weekly/2026-06-08/analyses/GMIWm5y90xA-code-with-claude-sf-keynote.md`

---

### 2. Code with Claude London 2026: Opening Keynote
**🔗** https://www.youtube.com/watch?v=6amLO7I9xdg
**📅** 19 mai 2026 | **Source :** Anthropic officiel | **Score estimé :** 8/10

> Suite directe du keynote SF, focus "Rethinking how we build". Boris Cherny (Head of Claude Code) keynote. Claude Managed Agents avec sandboxes privés + MCP tunnels. Shift complet vers l'agentic software development.

**Points clés (sources secondaires) :**
- Claude Managed Agents : operate in **sandbox you control** + connect to private MCP servers
- Multiagent orchestration : lead agent délègue à des agents spécialisés en parallèle sur shared filesystem
- "Dreaming" : scheduled process qui review sessions passées, identifie patterns, améliore la mémoire automatiquement
- Distance idée → production qui se rétrécit exponentiellement

**Micro-action Ivan :** Playlist complète London → `https://www.youtube.com/playlist?list=PLmWCw1CzcFilPJdvw6scjHjbBripZWFps`

**Note :** Analyse Gemini échouée (vidéo inaccessible). Voir notes dans `analyses/6amLO7I9xdg-code-with-claude-london-keynote.md`

---

### 3. I Turned Claude Opus 4.8 Into My Entire AI Operating System
**🔗** https://www.youtube.com/watch?v=0WDkwMxj13s
**📅** ~1 semaine | **Créateur :** Nate Herk | **Score Ivan :** 9/10

> Méthode complète pour faire de Claude Code dans VS Code un "AI OS" centralisé : second cerveau + assistant exécutif. Framework des 4C + 3M. Particulièrement actionnable pour solo founder gérant 2 marques.

**Highlights Gemini (analyse complète) :**
- [07:12] **4C Framework** : Contexte → Connexions → Capacités → Cadence
- [01:57] **"AI isn't king. Context is king."** — le contexte unique d'Ivan = avantage concurrentiel
- [05:33] **"Treat tokens like money"** — signal > bruit dans les fichiers contextuels
- [15:23] **Permissions = clés** : ne donner que ce que l'agent peut toucher (read-only first)
- [18:02] **"Bike method"** : read-only → petites écritures → gros travaux → autonomie
- [20:13] **Reverse-engineer** : faire la tâche manuellement 1x → en faire un skill réutilisable
- [22:25] **`/session-handoff`** : résumé session (décisions, fichiers, next steps)
- `/insights` : rapport d'usage des sessions Claude Code

**Micro-action Ivan :** Créer `brands/TempleTwins/voice-guide.md` + `brands/PURESOLE/voice-guide.md` dans son workspace VS Code → base du skill `shopify-content-optimizer`.

**Analyse complète :** `claude-weekly/2026-06-08/analyses/0WDkwMxj13s-opus-48-ai-operating-system.md`

---

## 👀 NICE (à regarder selon temps dispo)

### 4. AI News: Claude Opus 4.8, Insane Omni Use-Case...
**🔗** https://www.youtube.com/watch?v=7TG78vIYI-Q
**📅** ~1 semaine | **Score :** 6/10
> Roundup des annonces Claude Opus 4.8 : effort controls, dynamic workflows, fast mode pricing. Format news rapide.

### 5. FREE UNLIMITED Claude Code (No NVIDIA NIM, No Ollama!)
**🔗** https://www.youtube.com/watch?v=j51TzPC5ya4
**📅** ~20h | **Score :** 4/10
> Méthode pour utiliser Claude Code sans frais API. Intéressant pour tester/prototyper mais pas pour production. Attention : hype territory.

### 6. Ultimate Claude Code Guide: How to Use Claude Code for Beginners in 2026
**🔗** https://www.youtube.com/watch?v=RywmhLTFeFk
**📅** ~5j | **Score :** 4/10
> Guide complet pour débutants. Utile si Ivan veut onboarder quelqu'un sur ses marques.

---

## ⏭️ SKIP (> 14j ou hors scope)

- `0hdFJA-ho3c` — Claude Code is all you need in 2026 (janv.) → trop ancien
- `VbSF8TUpsjE` — Claude Tutorial Masterclass (1 mois) → trop ancien
- `fWESHHKssKA` — Ultimate Claude AI Masterclass (mars) → trop ancien
- `bqJzIWAEn40` — Full Claude Code Tutorial Non-Technical (avr.) → trop ancien
- `6q8joS_592k` — Claude Code Tutorial Build App (janv.) → trop ancien
- `MGDlG4JyjVk` — Cold Email Playbook Claude Code (1 mois) → trop ancien
- `OX80FZjHJ7o` — Claude Code + Remotion (1 semaine) → créatif, hors focus e-com

---

## 🚀 Claude Code Changelog — Semaines 22-23 (25 mai – 8 juin 2026)

### Semaine 22 (v2.1.150–v2.1.157) — 25-29 mai

| Feature | Commande | Impact Ivan |
|---------|---------|------------|
| **Claude Opus 4.8** nouveau default | `/model claude-opus-4-8` ou `/effort xhigh` | ★★★★★ Mieux pour tâches complexes PURESOLE |
| **Dynamic Workflows** (research preview) | `> create a workflow that [tâche complexe]` | ★★★★☆ Lancement produit multi-étapes |
| **Security guidance plugin** | `/plugin install security-guidance@claude-plugins-official` | ★★★☆☆ Code Shopify plus sécurisé |
| **Fast mode sur Opus 4.8** | `/fast` → $10/$50 per MTok (2.5x speed) | ★★★★☆ Tâches rapides moins chères |
| Plugins auto-load depuis `.claude/skills` | Automatique | ★★★★★ Simplification workflow |
| `claude plugin init <name>` | Scaffolding plugin | ★★★★☆ Créer skills plus vite |
| `/reload-skills` | Re-scan sans restart | ★★★☆☆ Dev itératif |
| Agent CLI : `! <cmd>` | Background job dans claude agents | ★★★☆☆ Parallélisation tâches |
| `MessageDisplay` hook | Transform/hide assistant text | ★★☆☆☆ Customisation UI |

### Semaine 23 (v2.1.158–v2.1.168) — 30 mai – 8 juin

| Feature | Version | Impact Ivan |
|---------|---------|------------|
| **fallbackModel** (jusqu'à 3 modèles) | v2.1.166 | ★★★★☆ Résilience si Opus surchargé |
| Glob support dans deny rules | v2.1.166 | ★★★☆☆ Sécurité fichiers sensibles |
| Cross-session security renforcée | v2.1.166 | ★★★☆☆ Sécurité MCP |
| **`/plugin list`** | v2.1.163 | ★★★☆☆ Inventaire plugins installés |
| `requiredMinimumVersion` managed settings | v2.1.163 | ★★★☆☆ Orgs avec Claude géré |
| `--json` output `claude agents` | v2.1.162 | ★★★☆☆ Scripting agents |
| Slash commands autocomplete | v2.1.162 | ★★★☆☆ UX |
| Remote Control → footer pill | v2.1.162 | ★★☆☆☆ UI |
| Tool call parallelization | v2.1.161 | ★★★★☆ Agents plus rapides |
| Voice mode | v2.1.160 | ★★★☆☆ Mains libres |
| acceptEdits + build-tool config | v2.1.160 | ★★★☆☆ Auto-accept edits |
| Auto mode Bedrock/Vertex/Foundry | v2.1.158 | ★★☆☆☆ Enterprise |

**Commande fast-start Opus 4.8 :**
```bash
/model claude-opus-4-8
/effort xhigh
/fast   # si besoin de vitesse > précision
```

**FallbackModel config (v2.1.166+) :**
```json
// .claude/settings.json
{
  "fallbackModel": ["claude-sonnet-4-6", "claude-haiku-4-5"]
}
```

---

## 🌐 Écosystème MCP — Semaine du 8 juin

- **MCP officiel commits** : correction boucle infinie URL elicitation, bump sécurité gitpython/urllib3, annotations outils memory graph
- **Plugin marketplace** : Frontend Design (829K installs), Superpowers (752K), Context7 (348K) — chiffres Anthropic public directory juin 2026
- **Shopify AI Toolkit** (avril 2026, toujours d'actualité) : MCP server open-source connectant Claude → Admin API Shopify, 7 outils, gratuit. Repo : `github.com/Shopify/Shopify-AI-Toolkit`

---

## 💡 Insights transverses Claude/Anthropic

### Annonces Anthropic juin 2026
- **Subscription split (15 juin)** : séparation des plans Claude — impact à surveiller pour coûts
- **Claude for Legal** : 20+ nouveaux MCP connectors + 12 plugins par pratique — signal que le modèle de plugins sectoriels s'accélère
- **Managed Agents GA** : dreaming, multiagent orchestration, outcomes, webhooks — infrastructure prod disponible

### Pattern récurrent semaine
**"Context is the moat"** — toutes les analyses convergent : le modèle IA est une commodité, le contexte métier unique (voix de marque, données clients, historique produits) est l'avantage concurrentiel réel. Pour Ivan : construire des fichiers contexte riches pour TempleTwins et PURESOLE avant de scaler l'usage IA.

---

## 🛠️ Skills proposés (3 — à reviewer manuellement)

> ⚠️ Ces skills ne sont PAS déployés. Ivan doit les reviewer et décider.

### 1. `shopify-content-optimizer`
**Trigger :** `/shopify-content [product_id] [brand]`
**Source :** SF Keynote + AI OS video
**Valeur :** Génère titre/description/tags Shopify optimisés SEO avec voix de marque TempleTwins/PURESOLE
**Fichier :** `claude-weekly/2026-06-08/skills-proposed/shopify-content-optimizer/SKILL.md`
**Prérequis :** Créer `brands/[marque]/voice-guide.md`

### 2. `ai-os-session-handoff`
**Trigger :** `/session-handoff`
**Source :** AI OS video (Nate Herk)
**Valeur :** Résumé fin de session (décisions, fichiers, next steps) → reprendre proprement le lendemain
**Fichier :** `claude-weekly/2026-06-08/skills-proposed/ai-os-session-handoff/SKILL.md`
**Prérequis :** Aucun — peut être installé immédiatement

### 3. `ecom-routine-manager`
**Trigger :** `/ecom-routine [tache]`
**Source :** SF Keynote (Routines + Dynamic Workflows)
**Valeur :** Orchestrateur tâches e-com récurrentes — check-stock, daily-brief, product-launch
**Fichier :** `claude-weekly/2026-06-08/skills-proposed/ecom-routine-manager/SKILL.md`
**Prérequis :** MCP Shopify (read-only) + Claude Code v2.1.154+

---

## 🔗 URLs importantes semaine

- https://code.claude.com/docs/en/whats-new/2026-w22 — Changelog W22 officiel
- https://www.youtube.com/watch?v=GMIWm5y90xA — Code w/ Claude SF Keynote
- https://www.youtube.com/watch?v=6amLO7I9xdg — Code w/ Claude London Keynote
- https://www.youtube.com/playlist?list=PLmWCw1CzcFim2obQ-w3ohbULOfwp5lApR — SF playlist
- https://www.youtube.com/playlist?list=PLmWCw1CzcFilPJdvw6scjHjbBripZWFps — London playlist
- https://claude.com/code-with-claude/tokyo-extended — Tokyo Extended (11 juin — bientôt)
- https://github.com/Shopify/Shopify-AI-Toolkit — Shopify MCP officiel
- https://codersera.com/blog/claude-skills-mcp-servers-practitioner-guide-2026/ — Guide complet Skills + MCP 2026

---

*Généré par veille-claude-weekly — 2026-06-08 | Pipeline : WebSearch × 8 + Gemini 2/3 + Claude Code changelog W22-W23*
