# Claude Weekly — 2026-06-01

> **Focus** : Claude Code · Skills · MCP · Plugins · Shopify-AI  
> **Période** : 19 mai – 1 juin 2026  
> **Gemini analyses** : ⚠️ Indisponibles (API 503 haute demande + quota free tier dépassé au moment de l'exécution)

---

## 🔥 RELEASE MAJEURE DE LA SEMAINE : Claude Opus 4.8 + Dynamic Workflows

**Date** : 28 mai 2026 — 41 jours après Opus 4.7

### Ce qui a changé

| Feature | Impact Ivan |
|---------|-------------|
| **Dynamic Workflows** (research preview) | Orchestrer 10–1 000 sous-agents en parallèle — migrations massives, audits catalogue entiers |
| **Ultracode** = `/effort xhigh` + auto-workflow | Lancer une tâche complexe, Claude décide seul si workflow nécessaire |
| **Fast mode Opus 4.8** | 2.5× plus rapide, 3× moins cher que l'ancien ($10/$50 /M tokens) |
| **Effort labels** | "Faster" / "Smarter" (anciens "Speed"/"Intelligence") |
| Messages API mid-conversation | System entries dans l'array `messages` → update instructions sans casser le cache |

### Dynamic Workflows — détails techniques
- Max **1 000 sous-agents** par run, **16 concurrent**
- Claude écrit un **script JS d'orchestration** à partir d'une requête en langage naturel
- Disponible : Pro (opt-in `/config`), Max et Team (on par défaut), Enterprise (admin enable)
- Exemple réel : Bun (750 000 lignes Zig→Rust, 99.8% tests passants, 11 jours)

---

## 📦 Claude Code — Changelog semaine (v2.1.154 → v2.1.159)

### v2.1.157 — 29 mai ⭐
- **Plugins auto-chargés** depuis `.claude/skills/` sans marketplace
- `claude plugin init <name>` pour créer un nouveau plugin
- Autocomplete sur les arguments `/plugin`
- `EnterWorktree` peut switcher entre worktrees managed by Claude

### v2.1.154 — 28 mai ⭐⭐ MAJEUR
- Opus 4.8 = défaut (effort `xhigh`)
- Dynamic Workflows + Ultracode
- `! <command>` pour sessions shell background
- `/simplify` refactorisé (cleanup + review + auto-fixes)
- Lean system prompt par défaut

### v2.1.149 — 22 mai
- **`/usage` breakdown** par catégorie : skills / subagents / plugins / MCP
- GFM task lists (checkboxes `- [x]`)

### v2.1.147 — 21 mai
- Sessions background **épinglées** (restart in-place sur updates)
- `/code-review` (ancien `/simplify`)

---

## 🔌 Plugins officiels Anthropic

Anthropic a lancé **`claude.com/plugins`** — marketplace officiel avec 55+ plugins curated.
Repo GitHub : `anthropics/claude-plugins-official`

### Plugin security (nouveau)
- Monitoring real-time des éditions de code
- Flagging automatique avant push
- Install : `/plugins` → rechercher "security-guidance"

### Community
- `awesome-claude-plugins` (rdmgator12) : 132 bundles (skills + MCP + hooks + agents)

---

## 🛍️ DIRECT IVAN : Shopify AI Toolkit MCP

**Lancé le 9 avril 2026** — open-source sous MIT.

Claude Code (+ Cursor, VS Code, Codex, Gemini CLI) se connecte directement à :
- Docs Shopify (recherche sémantique)
- GraphQL Admin API schemas
- Opérations live sur le store

### Install en 1 commande
```bash
claude mcp add --transport stdio shopify-dev-mcp -- npx -y @shopify/dev-mcp@latest
```

### Use-cases Ivan
- Mettre à jour les descriptions produits TempleTwins via langage naturel
- Gérer l'inventaire PURESOLE sans écrire de requêtes GraphQL
- Auditer le catalogue, créer des collections, analyser les ventes

### Trio e-com MCP (21 jours de fenêtre)
| MCP | Date | Utilité |
|-----|------|---------|
| Shopify | 9 avril | Store control |
| Meta | 29 avril | Paid distribution |
| Higgsfield | 30 avril | Creative AI |

---

## 📺 MUST-WATCH (5 vidéos — Gemini analyses non disponibles cette semaine)

| # | Titre | ID | Score | Pourquoi |
|---|-------|----|-------|----------|
| 1 | Opus 4.8 is NOT Claude's biggest release today (Ultracode & Dynamic Workflows) | `2rhZOisVXZM` | 7/10 | Angle analytique sur Ultracode vs Opus 4.8 — ce qui compte vraiment |
| 2 | Opus 4.8 + Claude Code's NEW Dynamic Workflows is INSANE (Full Walkthrough) | `ReTx6ku4_dc` | 6/10 | Walkthrough pratique pas-à-pas Dynamic Workflows |
| 3 | Claude Skills Tutorial (2026): Chat, Cowork, and Claude Code | `O_z9vDLgvoY` | 6/10 | Tuto Skills complet, publié il y a 5 jours |
| 4 | I Tried Claude's New Dynamic Workflows (Honest Results) | `f6C5wvXjn5k` | 6/10 | Retour terrain "honest results" — pragmatique |
| 5 | Complete Claude Code Course In 2 Hours For Developers | `TAKDIvvUdc4` | 5/10 | Cours complet 2h pour développeurs — référence |

**URLs :**
- https://www.youtube.com/watch?v=2rhZOisVXZM
- https://www.youtube.com/watch?v=ReTx6ku4_dc
- https://www.youtube.com/watch?v=O_z9vDLgvoY
- https://www.youtube.com/watch?v=f6C5wvXjn5k
- https://www.youtube.com/watch?v=TAKDIvvUdc4

---

## 📼 NICE-TO-WATCH (5 vidéos)

| Titre | URL | Note |
|-------|-----|------|
| The Claude Update Everyone Missed (Dynamic Workflows) | https://www.youtube.com/watch?v=-tLlZqrXpo8 | Angle "missed update" |
| Claude Code v2.1.154 — Opus 4.8 & Hundred-Agent Workflows | https://www.youtube.com/watch?v=0yP_cQqwSqA | Changelog deep-dive |
| Claude Code Just Dropped Workflows (An Actual Game Changer) | https://www.youtube.com/watch?v=ua2YA7TiLEk | Concis |
| Claude Code Dynamic Workflows Clearly Explained | https://www.youtube.com/watch?v=jZgcWCzxh1I | Pédagogique |
| Anthropic Just Dropped the Update Everyone's Obsessed With | https://www.youtube.com/watch?v=c0gVowvMR-g | Vue d'ensemble |

---

## ❌ SKIP

- Tutoriels beginners génériques (non spécifiques Dynamic Workflows)
- Vidéos > 14 jours sans annonce Anthropic majeure
- Shorts YouTube (< 3 min)
- Contenus en russe/langues non fr/en

---

## 🧠 MCP Officiel — Mises à jour (modelcontextprotocol/servers)

Semaine du 24–31 mai :
- **Memory server** : tool annotations ajoutées aux 9 outils du knowledge graph
- **Filesystem server** : fix dollar sign literal replacements
- **Everything-server** : migration Zod v4 + MCP SDK 1.29.0
- Sécurité npm/Python : correctifs sur dépendances

---

## 💡 SKILLS PROPOSÉS (2) — À REVIEW PAR IVAN

> ⚠️ Ces skills sont proposés mais NON déployés. Ivan review manuellement avant usage.

### Skill 1 : `shopify-ultracode-ops`
**Concept** : Utiliser Ultracode (xhigh effort + auto-workflow) pour des opérations Shopify à grande échelle via le MCP. Ex: migrer tout le catalogue PURESOLE vers de nouvelles descriptions, auditer 500 SKUs, synchroniser inventaire.

**Trigger** : Quand Ivan mentionne une tâche Shopify répétitive ou à grande échelle.

**Commandes clés** :
```bash
claude mcp add --transport stdio shopify-dev-mcp -- npx -y @shopify/dev-mcp@latest
# Puis dans Claude Code: /effort xhigh
# "Met à jour toutes les descriptions produits PURESOLE avec les nouvelles guidelines SEO"
```

### Skill 2 : `claude-weekly-digest-enhancer`
**Concept** : Skill pour enrichir automatiquement le digest claude-weekly avec les insights extraits des vidéos must-watch, structurés pour Ivan (TempleTwins + PURESOLE context).

**Trigger** : Exécuté automatiquement si Gemini analyses disponibles en Phase 3.

---

## 📊 Insights cross-sources

### Pattern récurrent cette semaine
**L'orchestration multi-agents devient mainstream** : Dynamic Workflows, Ultracode, plugins auto-chargés depuis `.claude/skills/` — tout converge vers Claude comme coordinateur autonome. Le solo founder qui maîtrise ces outils peut exécuter des projets de l'envergure d'une équipe de 5.

### Action immédiate pour Ivan
1. **Activer le Shopify MCP** : 1 commande, accès direct à TempleTwins et PURESOLE
2. **Tester Ultracode** sur une tâche Shopify complexe (audit catalogue, refactor liquid themes)
3. **Installer le security plugin** : monitoring proactif des vulnérabilités code
4. **Regarder #1 must-watch** : `2rhZOisVXZM` pour comprendre quoi utiliser en premier

---

## 📁 Fichiers générés

```
claude-weekly/2026-06-01/
  analyses/        ← vide (Gemini API 503 au moment de l'exécution)
  skills-proposed/ ← voir section Skills proposés ci-dessus
```

---

*Généré le 2026-06-01 | veille-claude-weekly*
