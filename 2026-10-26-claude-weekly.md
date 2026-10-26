# Claude Weekly — 2026-10-26

> Routine : veille-claude weekly | Focus Claude / Claude Code / Skills / MCP
> Périmètre : 14 derniers jours | Analyses Gemini : 5/5

---

## 🔥 ACTUALITÉS MAJEURES DE LA SEMAINE

### 1. Agent Skills → Agentic AI Foundation (22 oct 2026)
**Source officielle :** https://www.anthropic.com/news/donating-agent-skills-to-the-agentic-ai-foundation

Anthropic confie la **gouvernance du standard Agent Skills** à l'Agentic AI Foundation — déjà intégré par plus de 70 plateformes d'agents. Ce mouvement standardise la façon dont les skills circulent entre agents et plateformes. **Impact direct pour Ivan** : les skills créés dans Claude Code deviendront potentiellement portables vers d'autres agents, et l'écosystème Skills va s'accélérer.

### 2. Claude Duet — Research Preview (21 oct 2026)
**Sources :** https://9to5mac.com/2026/10/21/anthropic-takes-on-chatgpt-dots-and-meta-muse-with-claude-duet/ | https://www.tomsguide.com/ai/anthropics-claude-duet-ai-agent-can-manage-your-work-across-thousands-of-connected-apps-heres-how-it-works

- Agent proactif "always-on" propulsé par Claude Opus 5.5
- Fonctionne sur une VM cloud avec son propre navigateur
- Envoie un briefing matin + alertes ciblées (pas de flood)
- Demande TOUJOURS approbation avant actions sensibles (paiement, envoi email)
- Disponible en liste d'attente pour abonnés Pro/Max US
- ⚠️ Les vérifications background comptent dans ton quota d'utilisation

**Pour Ivan :** Monitoring client, alertes stock, suivi fournisseurs dropship sans ouvrir 10 onglets.

### 3. Claude Code v2.1.310 (23 oct 2026)
- **Monitor tool** disponible sur Bedrock, Vertex et Foundry
- Rôles personnalisés Enterprise pour sessions cloud
- Script de configuration chargeable depuis un fichier (bouton UI)

### 4. MCP Servers v2.1.0 publiée (24 oct 2026)
- Release majeure avec format CalVer (2026.10.24)
- SDK TypeScript MCP → v2.4.0 + Node.js adapter → v2.1.2
- Nombreux correctifs sécurité (zod 4.6, undici, body-parser)

### 5. Nouvelle version API Anthropic 2026-10-21
- Breaking change : **suppression du paramètre temperature**
- Versions SDK et `ant` CLI envoient cette version par défaut
- Claude Security (scan repos continu) en public beta Enterprise

---

## 🎬 MUST-WATCH (5 vidéos — Score ≥ 7/10)

### 1️⃣ "Claude Duet: Anthropic's Proactive Agent"
- **URL :** https://www.youtube.com/watch?v=0sI-GTYetD8
- **Score :** 8/10 | **Date :** ~21 oct 2026 (<7j)
- **TL;DR :** Vidéo officielle Anthropic présentant Claude Duet — agent always-on, VM cloud, briefings matinaux, demande d'approbation avant actions.
- **Skill_potential Gemini :** GérerServiceClientèleEcommerce, SurveillerOpérationsDropshipping, AssistantComptabilitéAuto
- **Micro-action :** S'inscrire sur la liste d'attente claude.ai (Pro/Max US)

### 2️⃣ "Anthropic Just Released Claude DUET (Full Breakdown)"
- **URL :** https://www.youtube.com/watch?v=c3WW9bR4ejM
- **Score :** 8/10 | **Date :** ~22 oct 2026 (<7j)
- **TL;DR :** Breakdown détaillé des cas d'usage Duet : emails partenariats, support client omnicanal, rapports perf quotidiens avec Shopify + Stripe.
- **Skill_potential Gemini :** GererPartenariatsEcom, SupportClientOmnicanal, **SuiviPerformanceEcom** ✅ (créé)
- **Micro-action :** Configurer le MCP Shopify pour préparer l'arrivée de Duet

### 3️⃣ "Every New Claude Code Feature Explained! (2026)"
- **URL :** https://www.youtube.com/watch?v=sJVxwwaF0sU
- **Score :** 9/10 | **Date :** récent 2026
- **TL;DR :** Walkthrough complet des dernières fonctionnalités Claude Code : /auto-mode-setup, /claude-api managed-agents, fork sub-agents, Code Review levels.
- **Skill_potential Gemini :** DailyMarketBriefing, **ShopifySEOOptimizer** ✅ (créé), SocialMediaContentGenerator, EmailCampaignOptimizer
- **Micro-action :** Tester `/auto-mode-setup` pour booster la productivité Claude Code

### 4️⃣ "How Complete Beginners Master Claude Code MCP in 19 minutes"
- **URL :** https://www.youtube.com/watch?v=dhsyihMpqZQ
- **Score :** 9/10 | **Date :** 22 oct 2026 (<7j) | **Durée :** 19 min ✅ sweet spot
- **TL;DR :** Tutoriel pratique MCP → Claude Code : stdio vs HTTP, ajout serveur, `/mcp` pour vérifier, Notion + filesystem. Parfait pour démarrer sans codebase.
- **Skill_potential Gemini :** Gestionnaire de Contenu Multiformat, Orchestrateur de Workflow Multi-Systèmes
- **Micro-action :** Ajouter le MCP Shopify Polar Analytics (existant dans seen-urls) pour TempleTwins

### 5️⃣ "Claude Skills Tutorial (2026): Build, Run, and Share"
- **URL :** https://www.youtube.com/watch?v=O_z9vDLgvoY
- **Score :** 9/10 | **Date :** 2026
- **TL;DR :** Comment transformer un prompt répété en skill réutilisable. SKILL.md, dossier ~/.claude/skills/, partage cross-plateformes Chat/Cowork/Claude Code.
- **Skill_potential Gemini :** customer-feedback-summary, **customer-reply-draft**, **product-launch-sanity-check** ✅ (créé)
- **Micro-action :** Créer `/product-launch-check` pour prochain lancement TempleTwins

---

## 📺 NICE-TO-WATCH (5-10 vidéos — Score 4-6)

| Titre | URL | Score | Note |
|---|---|---|---|
| "Claude Skills Explained: SKILL.md Tutorial" | https://www.youtube.com/watch?v=YKQEe3RR7r4 | 6 | Bonne intro SKILL.md débutants |
| "MCP Tutorial for Beginners: Connect Claude to Any Tool" | https://www.youtube.com/watch?v=40k3SIwlFVM | 5 | Généraliste mais solide |
| "Beyond the basics with Claude Code" | https://www.youtube.com/watch?v=tuY2ChJIx48 | 5 | Avancé, post-onboarding |
| "Claude Code is all you need in 2026" | https://www.youtube.com/watch?v=0hdFJA-ho3c | 5 | Bilan usage quotidien |
| "Claude Code Full Course 2026" | https://www.youtube.com/watch?v=hVRjUvjDQwE | 4 | 5h, trop long, référence |
| "Anthropic Just Dropped Claude Duet (Full Breakdown)" | https://www.youtube.com/watch?v=nv1aaP3dHzs | 4 | Doublon avec c3WW9bR4ejM |

---

## ⏭️ SKIP

- "Claude AI Promo Code (Updated 2026)" — hors sujet, commercial
- "Claude Code: La IA que está revolucionando la programación" — espagnol, générique
- "Claude Code Tutorial for Beginners" — trop basique, déjà vu

---

## 🛠️ SKILLS PROPOSÉS (3 — à valider par Ivan)

> ⚠️ Skills proposés uniquement, jamais déployés automatiquement. Ivan review manuellement.

### 1. `product-launch-check`
**Fichier :** `claude-weekly/2026-10-26/skills-proposed/product-launch-check/SKILL.md`
Vérifie un produit Shopify avant mise en ligne : SEO, cohérence marque, prix, champs manquants. Retourne une checklist Go/No-Go.

### 2. `suivi-perf-ecom`
**Fichier :** `claude-weekly/2026-10-26/skills-proposed/suivi-perf-ecom/SKILL.md`
Briefing quotidien/hebdo des métriques Shopify (revenus, stock critique, anomalies). Remplace l'ouverture manuelle de 4 dashboards chaque matin.

### 3. `shopify-seo-optimizer`
**Fichier :** `claude-weekly/2026-10-26/skills-proposed/shopify-seo-optimizer/SKILL.md`
Optimise title tags, meta descriptions et descriptions produits pour le SEO organique. Génère des suggestions concrètes par produit.

---

## 💡 INSIGHT CROSS-VIDÉOS

Le pattern récurrent cette semaine : **Claude se transforme en opérateur proactif** (Duet) pendant que le standard Skills devient portable entre plateformes (donation à l'Agentic AI Foundation) — les deux mouvements pointent vers un Claude qui agit sans qu'Ivan ait à tout déclencher manuellement, ce qui est exactement ce dont un solo founder a besoin.

---

## 📰 SOURCES & ARTICLES NOTABLES

- **Shopify MCP guide solo founder :** https://www.polaranalytics.com/post/shopify-mcp-server-connect-your-store-to-claude-ai
- **Claude for Shopify complet 2026 :** https://www.eesel.ai/blog/claude-for-shopify
- **Skills vs MCP comparison :** https://glama.ai/blog/2026-01-10-what-are-claude-skills
- **Claude Duet + Agentic AI Foundation :** https://dataconomy.com/2026/10/22/anthropic-claude-duet-personal-ai-agent-research-preview/
- **Claude Code changelog (clokedcode) :** https://clockedcode.com/blog/claude-code-changelog
- **Build MCP Server step-by-step :** https://www.aiforanything.io/blog/how-to-build-mcp-server-claude-2026

---

*Généré par veille-claude-weekly — 2026-10-26 07:xx UTC*
