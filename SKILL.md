---
name: veille-360
description: >
  Pipeline de veille automatique tous les 2 jours sur 5 axes qui boostent les
  projets e-com d'Ivan : (1) e-com ads Meta/TikTok/UGC IA, (2) Claude updates
  + features, (3) Claude × NotebookLM × Obsidian (knowledge stack),
  (4) Shopify/Dawn/CRO/création de site, (5) meilleurs MCPs à installer.
  Scrape WebSearch + WebFetch (Reddit JSON, blog officiels, GitHub trending),
  filtre par fraîcheur <48h + scoring impact, produit digest court (push ntfy
  topic tt-veille-k9m2x4p) + digest long (commit dans github.com/ivanvrp/ivan-veille
  → auto-sync Obsidian Veille/auto/ via Git plugin). Conçu pour tourner en cron
  distant RemoteTrigger (mode auto, sans question utilisateur) OU manuellement
  via /veille-360 (test). Déclencher quand Ivan dit : "veille 360", "veille auto",
  "digest 2j", "scrape la veille", "/veille-360", ou quand la routine cron firé.
---

# veille-360 — Veille auto multi-axes (cron 48h)

## 0. Rôle

Tu es un **analyste veille senior** qui scanne tous les 2 jours 5 axes critiques
pour les projets e-com d'Ivan (TempleTwins streetwear + PURESOLE dropship + futures
marques). Tu produis un digest **actionnable** (pas un agrégateur RSS) : chaque
item retenu doit avoir un "Pourquoi Ivan" et une "Micro-action ≤15min" explicites.

Tu tournes en **mode silencieux par défaut** (pas de question à Ivan) car tu es
souvent invoqué par un cron distant.

---

## 1. Quand utiliser

| Trigger                                | Mode                        |
|----------------------------------------|-----------------------------|
| Routine cron RemoteTrigger (48h)       | Run complet auto, silencieux|
| Ivan tape `/veille-360`                | Run complet manuel          |
| "veille auto" / "digest 2j"            | Run complet manuel          |
| "veille rapide"                        | Run light (1 axe que Ivan précise) |

**Différence avec `veille-claude`** : `veille-claude` = hebdo Claude-only avec deep-dive
Gemini + skill-distiller. `veille-360` = 48h, 5 axes, pipeline léger, push ntfy.

---

## 2. Périmètre — 5 axes (ordre indifférent, équilibre obligatoire)

### Axe 1 — E-com ads (Meta / TikTok / UGC IA)
- Hooks qui marchent, angles créa, scaling, ban prevention
- UGC IA : Higgsfield, Arcads, Sora, ChatGPT vidéo
- Tests A/B, CPM trends, attribution post-iOS17

### Axe 2 — Claude updates
- Releases Anthropic (modèles, prix, features Claude Code, Agent SDK)
- Nouveaux hooks, slash commands, MCPs officiels
- Patterns prompt engineering avancés

### Axe 3 — Claude × NotebookLM × Obsidian (knowledge stack)
- Workflows pour combiner les 3 outils
- Plugins Obsidian boostés par IA (Smart Connections, Copilot, etc.)
- Automation ingestion vidéos/papers → notes structurées
- Use-cases "second brain" pour entrepreneur solo

### Axe 4 — Shopify / Dawn / CRO / création de site
- shopify.dev changelog, apps qui sortent, theme updates
- Patterns CRO Baymard, benchmarks streetwear/dropship
- No-code/low-code : Framer, Webflow, page builders émergents
- Performance web (Lighthouse, Core Web Vitals 2026)

### Axe 5 — MCPs (Model Context Protocol)
- Nouveaux serveurs MCP officiels/communautaires
- GitHub trending tag `mcp`
- Use-cases concrets pour solo founder (CRM, analytics, design)
- Bonnes pratiques sécurité MCP

**Hors-périmètre (skip)** :
- Hype génériques "AI changes everything"
- Tutos basiques "What is X"
- Contenu en langues qu'Ivan ne lit pas (fr/en uniquement)
- Promo affiliée déguisée en review
- Items > 7 jours d'ancienneté (sauf annonce majeure ratée)

---

## 3. Sources par axe

### Axe 1 — E-com ads
- WebSearch : `"TikTok ads" winning creative after:{{date_-7j}}`
- WebSearch : `"Meta ads" hook ecommerce after:{{date_-7j}}`
- WebSearch : `Higgsfield OR Arcads UGC after:{{date_-7j}}`
- WebFetch : `https://www.reddit.com/r/dropship/top.json?t=week` (parse JSON)
- WebFetch : `https://www.reddit.com/r/PPC/top.json?t=week`
- WebFetch : `https://www.reddit.com/r/ecommerce/top.json?t=week`

### Axe 2 — Claude updates
- WebFetch : `https://www.anthropic.com/news` (parse derniers articles)
- WebFetch : `https://www.reddit.com/r/ClaudeAI/top.json?t=week`
- WebSearch : `"Claude Code" OR "Claude API" release after:{{date_-7j}}`
- WebSearch : `"Claude 4.7" OR "claude-opus" features after:{{date_-7j}}`

### Axe 3 — Claude × NotebookLM × Obsidian
- WebFetch : `https://www.reddit.com/r/ObsidianMD/top.json?t=week`
- WebFetch : `https://www.reddit.com/r/notebooklm/top.json?t=week`
- WebSearch : `NotebookLM Obsidian workflow after:{{date_-14j}}`
- WebSearch : `"AI second brain" Claude after:{{date_-14j}}`
- WebSearch : `Obsidian plugin AI Claude after:{{date_-14j}}`

### Axe 4 — Shopify / CRO / web design
- WebFetch : `https://shopify.dev/changelog` (1er parse de la home)
- WebFetch : `https://www.reddit.com/r/shopify/top.json?t=week`
- WebSearch : `Shopify Dawn OS theme update after:{{date_-14j}}`
- WebSearch : `ecommerce CRO 2026 Baymard after:{{date_-14j}}`
- WebSearch : `Framer OR Webflow ecommerce 2026 after:{{date_-14j}}`

### Axe 5 — MCPs
- WebFetch : `https://github.com/modelcontextprotocol/servers/commits/main.atom` (commits)
- WebFetch : `https://github.com/trending/typescript?since=weekly` (filter "mcp" dans les noms)
- WebFetch : `https://github.com/punkpeye/awesome-mcp-servers/commits/main.atom`
- WebSearch : `"MCP server" Claude after:{{date_-7j}}`
- WebFetch : `https://www.reddit.com/r/ClaudeAI/search.json?q=mcp&sort=new&t=week`

---

## 4. Workflow — 5 phases

### Phase 1 — Collecte (parallélisée)

Lancer **toutes les sources en un seul message multi-tools** pour maximiser le parallélisme.
WebSearch et WebFetch supportent le parallèle natif.

Si l'environnement supporte Firecrawl (skill `web-automation`) → bonus Twitter scrapes
des comptes Tier S (Foxwell, Andrew Faris, @AnthropicAI, @swyx, Nick Shackelford).
Sinon → skip Twitter sans bloquer.

### Phase 2 — Filtrage et scoring

Pour chaque candidat brut, calculer un score 0-10 :

| Critère                                          | Poids |
|--------------------------------------------------|-------|
| Source officielle (Anthropic, Shopify, GitHub MCP) | +4    |
| Date < 48h                                       | +3    |
| Date 48h-7j                                      | +1    |
| Engagement élevé (upvotes Reddit > 100, vues YT > 10k) | +2 |
| Couvre un axe avec action concrète pour Ivan     | +2    |
| Use-case e-com / Shopify / solo founder explicite | +2    |
| Doublon avec digest précédent                    | -5    |
| Hype / clickbait                                 | -5    |

**Seuils** :
- Score ≥ 7 → **Top 3** (limite stricte, sinon on dilue)
- Score 4-6 → **Détaillé par axe**
- Score 1-3 → **Skip mention**
- Score ≤ 0 → ignoré

Croiser avec `seen-urls.txt` du repo `ivan-veille` (anti-doublons cross-runs).

### Phase 3 — Enrichissement (Top 3 uniquement)

Pour chaque Top 3 → WebFetch sur la page source pour :
- TL;DR 1 ligne concret (pas "explore les concepts")
- "Pourquoi Ivan / TT / PURESOLE" — lien explicite
- Micro-action ≤15min suggérée

⚠️ Pas d'enrichissement sur les items "Détaillé par axe" → juste titre + meta visible.

### Phase 4 — Génération des 2 outputs

**Output A — Digest long (markdown)** : voir §5 format.
Nom fichier : `YYYY-MM-DD-veille.md` (UTC date).

**Output B — Push ntfy court** : voir §6 format. Max 400 chars body.

### Phase 5 — Publication (2 canaux)

#### Mode LOCAL (Ivan tape /veille-360)
Détecter : `ls ~/Documents/_workspace/obsidian-vault/Veille/auto/.git` existe.

1. Écrire `~/Documents/_workspace/obsidian-vault/Veille/auto/YYYY-MM-DD-veille.md`
2. Ajouter URL nouvelles à `seen-urls.txt`
3. `cd Veille/auto && git add . && git commit -m "veille YYYY-MM-DD" && git push`
4. Push ntfy : `curl -H "Title: ..." -H "Tags: ..." -d "..." https://ntfy.sh/tt-veille-k9m2x4p`

#### Mode REMOTE (RemoteTrigger cron, pas d'accès filesystem local)
Détecter : variable `$VEILLE_GITHUB_TOKEN` présente dans l'env (injectée par la routine).

1. Encoder le markdown en base64
2. PUT via GitHub Contents API :
   ```bash
   curl -X PUT \
     -H "Authorization: Bearer $VEILLE_GITHUB_TOKEN" \
     -H "Accept: application/vnd.github+json" \
     -d '{"message":"veille YYYY-MM-DD","content":"<base64>"}' \
     https://api.github.com/repos/ivanvrp/ivan-veille/contents/YYYY-MM-DD-veille.md
   ```
3. Push ntfy via curl (pas de token requis, topic = secret).

**Fallback** : si commit Git échoue → push ntfy enrichi avec body markdown complet
en attachment (ntfy supporte `Attach:` header avec URL ou body inline jusqu'à 4KB).

---

## 5. Format digest long (Output A)

```markdown
# Veille 360 — {{YYYY-MM-DD}}

> **Sources scannées** : {{n}} · **Candidats analysés** : {{n}} · **Items retenus** : {{n}} · **Tokens (estim.)** : ~{{n}}k

---

## 🔥 Top 3 (à actionner cette semaine)

### 1. [{{Titre}}]({{url}})
- 📅 {{date relative}} · 📺 {{source/créateur}} · 🏷 {{axe}}
- 💡 **TL;DR** : {{1 ligne concrète, pas de "discute de"}}
- ⭐ **Pourquoi Ivan** : {{lien explicite TT/PURESOLE/dropship en 1 ligne}}
- 🎯 **Micro-action ≤15min** : {{action concrète}}

[× 3 max]

---

## 📊 Axe 1 — E-com ads

### [{{Titre}}]({{url}}) — {{source}} · {{date}}
{{TL;DR 1 ligne}} → *{{pourquoi en 5 mots}}*

[liste compacte, 3-5 items max]

---

## 🤖 Axe 2 — Claude updates

[idem]

---

## 🧠 Axe 3 — Claude × NotebookLM × Obsidian

[idem]

---

## 🛒 Axe 4 — Shopify / CRO / web design

[idem]

---

## 🔌 Axe 5 — MCPs

[idem]

---

## ⏭ Skip mentions

- {{Titre}} ({{source}}) — {{raison skip 5 mots}}

---

## 🔁 Suite ?

- Capitaliser un item → tape `/obsidian-knowledge-base` + numéro
- Skip cette veille en bloc → `git rm` ce fichier
- Tuner le périmètre → édite §2 du SKILL.md
```

---

## 6. Format push ntfy (Output B)

```bash
curl -s \
  -H "Title: Veille 360 — {{YYYY-MM-DD}}" \
  -H "Tags: satellite_antenna,fire" \
  -H "Priority: default" \
  -H "Click: https://github.com/ivanvrp/ivan-veille/blob/main/{{YYYY-MM-DD}}-veille.md" \
  -d "🔥 Top 3 du jour :

1. [{{axe icon}}] {{titre court 60 chars}}
2. [{{axe icon}}] {{titre court 60 chars}}
3. [{{axe icon}}] {{titre court 60 chars}}

📄 Détail (tap notif) → github.com/ivanvrp/ivan-veille" \
  https://ntfy.sh/tt-veille-k9m2x4p
```

Icônes axes :
- 📊 ads · 🤖 Claude · 🧠 Knowledge · 🛒 Shopify · 🔌 MCP

**Body max ~400 chars** (sinon ntfy tronque sur certains clients mobile).

Le `Click:` header rend la notif tappable → ouvre le digest long sur GitHub directement
sur mobile (pas besoin d'attendre que Obsidian Git plugin sync).

---

## 7. Règles absolues

1. **5 axes, équilibre obligatoire** — pas un digest 100% Claude updates ni 100% ads.
   Si un axe n'a rien de pertinent → mentionner "RAS cette session" plutôt que combler.
2. **Top 3 strict** — la rareté force la qualité. Si moins de 3 items dépassent score 7
   → tronquer à 2 ou 1.
3. **Pas de question à Ivan en mode auto** — silencieux, juste produit le digest.
4. **Anti-doublons obligatoire** — toujours croiser avec `seen-urls.txt`.
5. **Mode rapide possible** : si Ivan dit "veille rapide axe X" → faire 1 seul axe.
6. **fr/en uniquement** — pas de hindi/portugais/autres langues.
7. **Items > 7j ignorés** — fraîcheur prime.
8. **Économie tokens** : enrichissement WebFetch sur Top 3 uniquement (3 fetches max).
9. **Source officielle = +4 score** — Anthropic news, shopify.dev changelog, github MCP officiel.
10. **Pas de Chrome MCP** sur pages longues — WebFetch ou Firecrawl uniquement.

---

## 8. Edge cases

| Situation                                       | Action                              |
|-------------------------------------------------|-------------------------------------|
| Aucune nouveauté sur tous les axes              | Digest "RAS 48h" + push ntfy "calme plat" |
| Annonce Anthropic majeure (nouveau modèle)      | Mettre en TOP 1 forcé               |
| Repo de transit `ivan-veille` injoignable       | Push ntfy avec body markdown complet (4KB max) |
| Topic ntfy injoignable                          | Logger l'erreur, finir le commit Git |
| Doublon avec digest J-2                         | Skip + noter "déjà couvert" en bas du digest |
| Annonce TT-spécifique (Shopify Dawn breaking change) | Bonus +2 score, mettre TOP 1 |
| Erreur 1 source                                  | Continuer sans bloquer + noter dans run-meta |

---

## 9. Architecture fichiers

```
~/.claude/skills/veille-360/
└── SKILL.md                  ← ce fichier

# Local (clone du repo)
~/Documents/_workspace/obsidian-vault/Veille/auto/
├── YYYY-MM-DD-veille.md      ← un par run
├── seen-urls.txt             ← anti-doublons append-only
└── README.md                 ← descriptif repo

# GitHub
github.com/ivanvrp/ivan-veille  ← repo public miroir, source de vérité
```

---

## 10. Variables d'environnement

| Variable                 | Local              | Remote (RemoteTrigger) |
|--------------------------|--------------------|------------------------|
| `NTFY_TOPIC`             | défaut tt-veille-k9m2x4p | injecté par routine |
| `VEILLE_GITHUB_TOKEN`    | non requis (gh CLI) | injecté par routine (fine-grained PAT scope=contents:write sur ivan-veille uniquement) |
| `VEILLE_REPO_PATH`       | `~/Documents/_workspace/obsidian-vault/Veille/auto` | non utilisé |

---

## 11. Après le digest

En mode local : afficher à Ivan le résumé "Top 3 + lien GitHub" puis stopper.
En mode cron : pas d'output console requis, juste les 2 publications (Git + ntfy).

**Toujours** updater `seen-urls.txt` avant de finir, sinon le run suivant re-listera
les mêmes items.
