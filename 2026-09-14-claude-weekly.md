# Claude Weekly — 14 septembre 2026

> Veille deep-dive Claude / Claude Code / Skills / MCP — Ivan Vasseur (TempleTwins + PURESOLE)

---

## 🔥 Résumé exécutif

Semaine marquée par un **gros batch de releases Claude Code (v2.1.265→270)** avec l'arrivée du `plugin eval`, de l'`/output-style`, et des diffs bash. Côté MCP, le serveur Memory reçoit 9 correctifs en 3 jours. L'annonce **Claudeforce (Salesforce × Anthropic)** positionne Claude comme colonne vertébrale CRM enterprise. Pour Ivan : 3 vidéos analysées par Gemini → 4 skills concrets proposés, tous orientés automatisation Shopify.

---

## 📦 Claude Code — Releases (8–12 sept 2026)

### v2.1.269 — 11 sept 2026 ⭐ MAJEURE
- **`claude plugin eval`** : évaluation reproductible de plugins/skills avec scoring JSON + HTML → A/B test intégré dans le terminal
- **`/output-style`** : changer le style de sortie en cours de session
- **Diff des fichiers modifiés par commandes Bash** : visibilité sur ce que Claude modifie
- Variables d'environnement pour **OpenTelemetry** et configuration du **Workflow tool**
- Corrections : cache de prompt, sessions reprises, touches F1/F2/F4 (kitty terminal)

### v2.1.268 — 10 sept 2026
- `pricing` dans `gateway.yaml` pour synchroniser les tarifs
- `gatewayInternalNetworks` pour contrôler l'accès au gateway
- `--json` ajouté à plusieurs commandes plugin
- Fix : WebFetch timeout infini (maintenant 300s max)
- Fix : erreurs HTTP 400 sur endpoints compatibles Anthropic

### v2.1.267 — 9 sept 2026
- **`maxEffortLevel`** : plafonner le niveau d'effort max (contrôle coût)
- **`--system-prompt-snapshot off`** : rafraîchir le prompt système à chaque requête
- Corrections : tâches planifiées Cowork, sessions reprises, `/context`, auth

### v2.1.265-266 — 8 sept 2026
- Support `--plugin-dir` pointant vers un dossier de plugins
- Cap 1 GB sur résultats d'outils sauvegardés
- Fix critique : régression configurations LLM-gateway/proxy

---

## 🔗 MCP Servers — Corrections (2–3 sept 2026)

**9 fixes sur le serveur Memory en 2 jours :**
- Sérialisation des mutations pour éviter les race conditions d'écriture concurrente
- Dé-duplication des entités/relations dans les batch imports
- Validation des entrées knowledge graph au chargement
- Cap 2048 chars sur les requêtes `search_nodes`
- Expansion `~` dans `MEMORY_FILE_PATH`
- Fix : `git_log` schema unifié (serveur git)

**Impact Ivan :** le serveur MCP Memory est maintenant stable pour les workflows de base de connaissances produits (descriptions, historiques de collection, etc.)

---

## 📣 Anthropic — Annonces

### Claudeforce (26 août 2026)
**Salesforce × Anthropic** → Claude intégré directement dans Salesforce CRM. Disponible en pilote, open beta prévue septembre 2026. Permet des expériences agentiques dans l'écosystème Salesforce (Commerce Cloud inclus).

**Pertinence Ivan :** indicateur que Claude devient infrastructure commerce mainstream. Le **Commerce Blueprint** d'Anthropic fournit un point de départ pour agents commerce agentique.

### Claude Code — Plugin Eval (11 sept 2026)
`claude plugin eval` : créer des cas de test, scorer les runs, comparer avec/sans plugin. Idéal pour valider les skills Shopify avant déploiement sur les stores.

---

## 🎬 MUST-WATCH (3 vidéos analysées Gemini)

### 1. GOING DEEPER with CLAUDE — Skills, MCP, Scheduled Tasks & CLAUDE CODE
- **URL :** https://www.youtube.com/watch?v=Jxu4EOA4QKE
- **Date :** Jun 19, 2026 | **Score :** 9/10 | **Durée :** ~12 min
- **TL;DR :** Skills = packs d'instructions réutilisables installables en 2 min. MCP = USB-C pour IA. Best practices Claude Code concrètes.
- **Key takeaways pour Ivan :**
  - Menu Customize → Skills Directory → pré-validés Anthropic & Partners
  - `/skill-creator` pour créer ses propres skills sans coder
  - Best practice : décrire QUOI, pas COMMENT + screenshots pour révisions UI
- **Skills proposés :** `/ecommerce-product-explainer`, `/social-media-content-creator`, `/shopify-sales-summarizer`
- 📄 [Analyse complète](claude-weekly/2026-09-14/analyses/Jxu4EOA4QKE-going-deeper-skills-mcp.md)

### 2. What Claude Code Can Do That You Haven't Tried — Gui Ferreira — NDC AI 2026
- **URL :** https://www.youtube.com/watch?v=zaDbZt40kRg
- **Date :** Jul 1, 2026 | **Score :** 9/10 | **Durée :** ~50 min (conférence)
- **TL;DR :** 96 commandes slash, la plupart inconnues. Les 4 piliers : Config → Workflow → Plateforme → Au-delà du code. Techniques avancées pour solo founder.
- **Key takeaways pour Ivan :**
  - Audit CLAUDE.md en 3 questions → -3% perf + -20% coût si trop grand
  - `/btw` : question parallèle sans couper la tâche en cours
  - `/loop` + hooks = monitoring CI/CD/Shopify automatique
  - `/batch` : tâche complexe → agents parallèles sur worktrees Git séparés
  - `/remote-control` : continuer session terminal sur mobile
- **Skills proposés :** `/shopify-ops-monitor`, `/claude-md-auditor`
- 📄 [Analyse complète](claude-weekly/2026-09-14/analyses/zaDbZt40kRg-what-claude-code-can-do.md)

### 3. Claude Code MCP | How to Add MCP Servers (2026) Full Tutorial
- **URL :** https://www.youtube.com/watch?v=dbb1v7QKYBU
- **Date :** ~Août 2026 | **Score :** 9/10 | **Durée :** ~3 min
- **TL;DR :** Deux méthodes pour ajouter un MCP server : GUI desktop ou CLI. Inclut commande exacte et auth OAuth.
- **Key takeaways pour Ivan :**
  ```bash
  claude mcp add -s user --transport http nexlev <URL_MCP>
  /mcp  # Vérifier + authentifier les serveurs
  ```
  - Tout outil avec API REST peut devenir connecteur MCP personnalisé
  - Shopify, Klaviyo, GA4 tous connectables en < 5 min
- **Skills proposés :** `/ecommerce-mcp-connector`
- 📄 [Analyse complète](claude-weekly/2026-09-14/analyses/dbb1v7QKYBU-mcp-servers-full-tutorial.md)

---

## 👍 NICE-TO-WATCH (non analysés Gemini)

| Vidéo | URL | Date | Pourquoi intéressant |
|-------|-----|------|---------------------|
| Claude Code Full Course 2026 — Build Production-Grade AI Workflows | https://www.youtube.com/watch?v=achDEsYONe8 | Jul 14 | 9h course, workflows production complets |
| I Mapped Every Claude Code Concept (Full 2026 Roadmap) | https://www.youtube.com/watch?v=9JoIpWgAsZ8 | May 18 | Cartographie exhaustive de tous les concepts |
| Watch This If You're Just Learning Claude Code 2026 | https://www.youtube.com/watch?v=ECQA6oOyfIk | Jun 29 | Guide setup pour débutants |
| Claude Code Tutorial for Beginners — Build Website | https://www.youtube.com/watch?v=OdSXY4YgmZA | Jul 11 | Cas pratique site web e-com |
| AI Summer 2026 — Claude Code & Choosing the Right Model | https://www.youtube.com/watch?v=Thylf8WVuK8 | Jun 8 | Choix modèle + compréhension agents |

---

## ⏭️ SKIP

- "Claude AI Promo Code" (X_36We6XDmI) — clickbait
- Vidéos en espagnol non pertinentes pour Ivan
- "Claude Code is all you need in 2026" (0hdFJA-ho3c) — déjà vu, >7 mois

---

## 🚀 SKILLS PROPOSÉS (4) — Review manuelle Ivan requise

> ⚠️ Ces skills ne sont PAS déployés automatiquement. Ivan doit les review et décider.

### 1. `/shopify-sales-summarizer`
Connexion API Shopify (MCP) → résumé ventes daily/weekly automatique avec alertes stocks critiques.
📄 [SKILL.md](claude-weekly/2026-09-14/skills-proposed/shopify-sales-summarizer/SKILL.md)

### 2. `/shopify-ops-monitor`
Hook + `/loop` : monitoring continu métriques Shopify (stock, CPA pub, commandes bloquées) + alertes ntfy proactives.
📄 [SKILL.md](claude-weekly/2026-09-14/skills-proposed/shopify-ops-monitor/SKILL.md)

### 3. `/claude-md-auditor`
Analyse CLAUDE.md avec méthode 3 questions → rapport optimisation + CLAUDE.md nettoyé → économies perf + coût.
📄 [SKILL.md](claude-weekly/2026-09-14/skills-proposed/claude-md-auditor/SKILL.md)

### 4. `/ecommerce-mcp-connector`
Guide interactif pour connecter Shopify/Klaviyo/GA4/Meta Ads à Claude via MCP en < 5 min. Génère la commande `claude mcp add` automatiquement.
📄 [SKILL.md](claude-weekly/2026-09-14/skills-proposed/ecommerce-mcp-connector/SKILL.md)

---

## 💡 Insight cross-vidéos

**Le pattern de la semaine : Skills + MCP + Hooks = le trio du solo founder agentique.** Les trois vidéos convergent vers le même message : Claude Code n'est pas un outil de coding, c'est une plateforme d'automatisation opérationnelle. Pour Ivan, la prochaine étape logique est de connecter un MCP Shopify et de créer 1-2 skills métier (ventes + contenu produit) pour libérer les 20-30h/semaine de travail répétitif identifiées dans les études 2026.

---

## 📊 Stats

- **Must-watch :** 3
- **Nice-to-watch :** 5
- **Skip :** 3
- **Analyses Gemini :** 3/3 réussies
- **Skills proposés :** 4
- **Gemini model :** gemini-2.5-flash

---

*Généré automatiquement par veille-claude-weekly · 2026-09-14*
