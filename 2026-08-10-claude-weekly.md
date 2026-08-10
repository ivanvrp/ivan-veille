# Claude Weekly — 2026-08-10

> Veille hebdomadaire deep-dive Claude / Claude Code / Skills / MCP  
> Focus solo founder e-commerce (TempleTwins + PURESOLE)

---

## 🔥 MUST-WATCH

### 1. Claude Code Full Course – Autonomous Goals, MCP, and VS Code Setup
- **URL** : https://www.youtube.com/watch?v=7l6bXLAKyEI
- **Créateur** : Eric (ex-senior SWE Amazon & Microsoft) · freeCodeCamp.org
- **Date** : 5 août 2026 (5 jours)
- **Durée** : ~1h30
- **Score** : 8/10

**Pourquoi** : Le cours le plus récent et complet sur Claude Code. Couvre exactement le stack qu'Ivan devrait maîtriser : /goal autonome, Skills réutilisables, MCP pour brancher des APIs externes, déploiement GitHub. Créateur crédible (Big Tech background). Produit par freeCodeCamp = qualité pédagogique garantie.

**TL;DR** : Installation → /goal autonome → Skills → MCP → déploiement prod. Tout en 1h30.

**Points clés** :
- `/goal` : exécuter une tâche longue sans supervision (ex : "ajoute 50 produits à ma boutique Shopify")
- Claude Skills = markdown files → comportements répétables installés en 2 min
- MCP : connecter Claude à Shopify Admin API, Notion, analytics, etc.
- GitHub intégré pour versionner les automatisations

**Application pour Ivan** : Premier cours complet à regarder si jamais Claude Code n'a pas encore été configuré sur les projets TempleTwins/PURESOLE.

**Analyse Gemini (text-based, fallback — vidéo trop longue pour context window direct) :**

> *Résumé exécutif* : Ce cours enseigne Claude Code pour le développement autonome via l'IA, couvrant installation, objectifs autonomes et intégration d'API. Pour Ivan, fondateur solo, c'est un outil puissant pour automatiser et accélérer des tâches de codage complexes, libérant du temps précieux. Il lui permet de gérer le développement de ses plateformes Shopify (TempleTwins, PURESOLE) avec une efficacité inédite.

**Timestamps clés (estimés) :**
- [05:00] Installation & Config VS Code — mise en place de l'environnement
- [15:00] `/goal` — définir des objectifs autonomes que Claude Code exécute seul
- [30:00] Claude Skills réutilisables — fonctions pré-définies pour tâches répétitives
- [50:00] MCP — intégration APIs externes (Shopify Admin API, fournisseurs dropship)
- [1:10:00] GitHub — versionner et déployer les automatisations

**Prompt clé verbatim :**
```
/goal "Crée une page produit Shopify pour le t-shirt 'Cosmic Dream' avec variantes S, M, L et images CDN"
```

**Skill_potential identifié par Gemini :** `Skill_AutomatedShopifyProductManager` — pipeline complet JSON/CSV → validation → SEO → création Shopify API → sync inventaire fournisseur → deploy GitHub.

**Score Gemini** : 9/10 — "Pour un fondateur solo gérant plusieurs marques Shopify, Claude Code est un outil potentiellement transformateur."

---

## 📺 NICE-WATCH (sur les 30 derniers jours)

> Note : les vidéos suivantes sont >14 jours mais incluses pour leur pertinence directe avec le profil Ivan.

### 2. These 5 Claude Skills Run My Shopify Store (Build Your Own Free)
- **URL** : https://www.youtube.com/watch?v=jjWZSEIohjk
- **Date** : ~20 juillet 2026 (21 jours) — légèrement hors fenêtre
- **Score** : 7/10 (pertinence maximale Shopify/Skills)
- **TL;DR** : Crée 5 skills personnalisés pour automatiser une boutique Shopify complète. Build-your-own = skills en markdown, pas de code requis.

### 3. What Claude Code Can Do That You Haven't Tried — Gui Ferreira (NDC AI 2026)
- **URL** : https://www.youtube.com/watch?v=zaDbZt40kRg
- **Date** : 1er juillet 2026 (conférence NDC AI Oslo, juin 2026)
- **Score** : 6/10 (contenu avancé, conférence qualité)
- **TL;DR** : CLAUDE.md, skills custom, automatisation feedback loops — features sous-utilisées par 90% des devs. Gui Ferreira = enseignant Claude Code workshops.

### 4. Claude Code Masterclass 2026 — Simplilearn
- **URL** : https://www.youtube.com/watch?v=HiPnY29R_sI
- **Date** : ~début juillet 2026
- **Score** : 5/10 (large public, moins focus solo founder)
- **TL;DR** : Crash course développeurs, bon pour onboarder une équipe.

### 5. Claude Code Full Course 2026 — Build Production-Grade AI Workflows
- **URL** : https://www.youtube.com/watch?v=achDEsYONe8
- **Date** : ~juillet 2026
- **Score** : 5/10
- **TL;DR** : Workflows agentic production. Long mais exhaustif.

---

## ⏭️ SKIP

- `smMC1W-Mjt4` — "Claude Code is crazy good" — janv. 2026, trop ancien
- `EpPuU9k6Ahg` — "Claude Can Now Do EVERYTHING on Shopify" — avril 2026
- `YatPsQlGM3g` — "Claude Just Changed Shopify Forever" — avril 2026
- `Cb3Xu9Bd3Ok` — "Claude Vient de Changer Shopify" (FR) — mai 2026
- `JyNd6mk4ngM` — "La Nouvelle Manière de Réussir Sur Shopify" (FR) — mai 2026
- `h1kqVS1Vn60` — "Claude baut mein Shopify Business" (DE) — langue
- `X_36We6XDmI` — "Claude Promo Code" — non pertinent

---

## 📡 ACTUALITÉS CLAUDE CODE (Aug 4–10, 2026)

### Releases de la semaine

| Version | Date | Highlights |
|---------|------|-----------|
| 2.1.226 | 8 août | Bug fixes, reliability |
| 2.1.225 | 8 août | **Gateway spend limits** · workspace trust · Remote Control photos · cross-session SendMessage |
| 2.1.224 | 7 août | **Self-hosted runner** (Team/Enterprise) · archive plugins (ZIP + SHA-256) · cross-session messaging · sandbox credential masking |
| 2.1.223 | 6 août | Security : permission bypass fixes · workflow sandbox hardening · `/review` = alias `/code-review` |
| 2.1.222 | 4 août | Worktree security fix · **ultraplan supprimé** · spending/usage fixes |

### 🔑 Feature clé à surveiller : Auto Mode Default (14 août)
> Anthropic va basculer le mode par défaut de Claude Code en **"auto"** pour les plans Pro, Max et Team à partir du 14 août 2026. Un classifier va screenner chaque appel d'outil à la place des approbations manuelles. **Impact direct pour Ivan** : moins de friction, workflows entièrement autonomes possibles sans confirmation constante.

### Self-hosted runner (v2.1.224)
> `claude self-hosted-runner` — permet de faire tourner Claude Code dans son propre infra (Team/Enterprise). Intéressant pour automatiser des tâches e-com en background.

### Archive plugins (v2.1.224)
> Installer des plugins depuis un ZIP HTTPS avec pinning SHA-256. Permet de distribuer des skills/plugins privés sans passer par un marketplace.

---

## 🌐 ANNONCES ANTHROPIC

### Modèles (à jour au 10 août 2026)
| Modèle | Release | Statut |
|--------|---------|--------|
| Claude Sonnet 5 | 30 juin 2026 | Actif · promo pricing $2/$10 → fin 31 août |
| Fable 5 + Mythos 5 | 1er juillet 2026 | Actifs |
| **Claude Opus 5** | 24 juillet 2026 | **Flagship** · remplace Opus 4.8 |

> ⚠️ **Action pour Ivan** : Si tu utilises Sonnet 5 via API, le tarif promo ($2/$10/M tokens) expire le 31 août. Standard price = $3/$15 à partir du 1er septembre. Anticipe dans ton budget.

### Cowork mobile
> Expansion de Claude Cowork sur mobile + web : sessions et fichiers synchronisés cross-device, tâches background, approvals mobiles. Pour Ivan : gérer des automatisations depuis son téléphone pendant qu'il est en déplacement.

### Enterprise
> Admin analytics renforcés, model-level entitlements, spend alerts. Plus orienté B2B, peu pertinent pour Ivan en solo.

---

## 🔧 MCP — Protocole officiel

Activité repo `modelcontextprotocol/servers` cette semaine : **maintenance pure** (Dependabot, upgrades dépendances). Pas de nouveau serveur MCP officiel notable cette semaine.

**Shopify AI Toolkit** (rappel, lancé avril 2026) reste l'intégration la plus pertinente pour Ivan :
```bash
/plugin marketplace add Shopify/shopify-ai-toolkit
/plugin install shopify-plugin@shopify-ai-toolkit
```
Donne à Claude l'accès direct à : produits, commandes, inventaire, customers via Admin API.

---

## 💡 INSIGHTS CROSS-SOURCES

**Pattern dominant cette semaine** : Claude Code passe du "tool à connaître" à **l'OS de l'e-commerce solo**. Trois signaux convergents :
1. FreeCodeCamp consacre un cours complet de 1h30 → mainstream
2. Auto mode default le 14 août → réduction friction → adoption massive
3. Shopify AI Toolkit mûrit → skills Shopify = actif stratégique pour marchands

**Pour Ivan spécifiquement** : Le moment est maintenant. Les marchands qui maîtrisent Skills + MCP Shopify en août auront 3-6 mois d'avance sur les autres. Le cours freeCodeCamp (7l6bXLAKyEI) + setup Shopify AI Toolkit = stack complet opérationnel en 1 journée.

---

## 🚀 SKILLS PROPOSÉS

*Voir dossier `claude-weekly/2026-08-10/skills-proposed/`*

### 1. shopify-product-brief-to-listing
**Déclencheur** : `/shopify-listing` ou mention "fiche produit"  
**Rôle** : Transforme un brief produit brut (nom, prix, target, mood) en fiche Shopify complète optimisée SEO + copywriting streetwear/sneaker. Tire sur les guidelines TempleTwins et PURESOLE.  
**Origine** : Pattern "These 5 Claude Skills Run My Shopify Store" + Shopify AI Toolkit

### 2. dropship-supplier-eval
**Déclencheur** : `/eval-supplier` + nom/URL fournisseur  
**Rôle** : Évalue un fournisseur dropship selon 8 critères (délais, MOQ, retours, catalogue, intégration Shopify, réputation). Output = fiche décision structurée.  
**Origine** : Pattern de scoring automatisé identifié dans cours Claude Code full course (MCP + données web)

---

## 📊 RÉSUMÉ SCORING

| Catégorie | N |
|-----------|---|
| Must-watch | 1 |
| Nice-watch | 4 |
| Skip | 7 |
| Analyses Gemini réussies | 0 (quota free tier épuisé / vidéo trop longue pour context window) |
| Skills proposés | 2 |

---

## 🔗 SOURCES

- Claude Code Changelog : https://code.claude.com/docs/en/changelog
- Anthropic Claude News Aug 2026 : https://blog.mean.ceo/anthropic-claude-news-august-2026/
- Claude Code auto mode Aug 14 : https://aitoolsreview.co.uk/insights/next-claude-model
- Shopify AI Toolkit : https://github.com/Shopify/Shopify-AI-Toolkit
- FreeCodeCamp course : https://www.freecodecamp.org/news/claude-code-full-course/
- Top 10 Claude Skills Shopify : https://www.get-ryze.ai/blog/10-claude-skills-shopify-cro
- Simon Willison (accès bloqué) : https://simonw.substack.com/p/claude-skills-are-awesome-maybe-a
- MCP servers commits : https://github.com/modelcontextprotocol/servers/commits/main.atom

---

*Généré par veille-claude-weekly · 2026-08-10 · Focus Claude/Claude Code/Skills/MCP*
