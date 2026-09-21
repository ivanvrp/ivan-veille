# Claude Weekly — 2026-09-21

> Deep-dive hebdomadaire Claude / Claude Code / Skills / MCP pour Ivan Vasseur  
> Focus : TempleTwins (streetwear Shopify) + PURESOLE (dropship)

---

## 🔥 MUST-WATCH (3 vidéos)

### 1. NEW Claude Code Update is WILD! ⚡
**URL :** https://www.youtube.com/watch?v=Nhmyrh9I_bA  
**Publié :** 20 sept. 2026 (< 24h au moment de la veille)  
**Chaîne :** Claude Code Updates  
**Score Gemini utilité Ivan : 9/10**

**TL;DR :** Claude Code Projects arrive — agents IA parallèles persistants dans le cloud. Tu donnes un objectif, Claude le découpe en threads autonomes qui tournent même quand tu fermes ton ordi. Rôle de Ivan = décideur, pas exécuteur.

**Concepts clés :**
- [0:11] Ancien workflow (1 tâche à la fois) → Nouveau (objectif → multi-threads parallèles)
- [0:47] Exécution persistante ("always-on") : les agents continuent dans le cloud
- [5:50] Mémoire partagée entre threads = cohérence de marque garantie

**Prompts verbatim :**
```
p99 on /checkout doubled after deploy #4812, find it and fix it. 
Also draft Friday's release notes, and bump stripe-node to v15.
```
```
Grow the AI Profit Boardroom. Audit the current landing page and rewrite it 
to convert better [...] Then write a five-email welcome sequence for new members 
that gets them to their first win in 48 hours.
```

**Action Ivan :** Tester Claude Code Projects dès son lancement (annoncé 17 sept.). Préparer un brief projet pour le lancement collection TempleTwins Hiver.

---

### 2. Claude Can Now Do EVERYTHING on Shopify
**URL :** https://www.youtube.com/watch?v=EpPuU9k6Ahg  
**Score Gemini utilité Ivan : 9/10**

**TL;DR :** Installation du Shopify AI Toolkit dans Claude Code en 3 min. Audit SEO des balises alt, analyse CVR par page, identification des opportunités AOV — tout ça avec des prompts naturels.

**Concepts clés :**
- [00:46] 3 méthodes d'install : plugin (recommandé), agent skills, MCP Dev server
- [02:37] Terminal Claude Code : CTRL+` (accent grave)
- [04:04] Après install → `/shop` pour accéder à toutes les compétences Shopify

**Commandes verbatim :**
```
/plugin marketplace add Shopify/shopify-ai-toolkit
/plugin install shopify-plugin/shopify-plugin
/reload-plugins
```
```
What is my conversion rate over the last 30 days on my Shopify store?
```
```
I want to increase my average order value. Can you run a report to find out 
what products people are buying more than one of, or products that I should 
be trying to sell together?
```

**Action Ivan :** Installer Shopify AI Toolkit sur TempleTwins et PURESOLE. Lancer l'audit alt tags + analyse CVR pages. Utilise le skill proposé `shopify-cro-analyzer`.

---

### 3. J'ai créé une boutique Shopify complète avec Claude IA — Tutoriel 2026
**URL :** https://www.youtube.com/watch?v=VC0ec2xD1AE  
**Score Gemini utilité Ivan : 9/10**

**TL;DR :** Méthode complète — boutique Shopify en 24h, zéro code. Analyser un concurrent (Facebook Ad Library), extraire sa structure avec Claude (E-commerce White Labeler), générer le copywriting, produire les images via Higgsfield. Spécialement pertinent pour PURESOLE (lancement rapide de niches dropship).

**Concepts clés :**
- [01:07] Identifier boutiques concurrentes via Auto-DS + Facebook Ad Library (1200+ pubs actives = validation)
- [07:05] Prompt "E-commerce White Labeler" : Claude génère wireframe HTML + design system à partir d'une URL concurrente
- [10:41] Prompt "White Label Copywriter" inspiré des grands copywriters (Hopkins, Ogilvy, Kennedy)
- [18:20] Higgsfield pour images produit photoréalistes (prompts générés par Claude)
- [32:20] Intégration code HTML dans Shopify via template `.liquid` custom

**Prompt clé (White Labeler) :**
```
Bonjour, je suis prêt à opérer en tant qu'E-commerce White Labeler pour Shopify.
Étape 1 - Wireframe : Envoyez-moi une URL de page produit concurrente + screenshot
→ Je génère un wireframe HTML complet avec placeholders.
Étape 2 - Copy : Envoyez-moi votre brief → je remplis les placeholders.
[...]
```

**Prompt images Higgsfield (généré par Claude) :**
```
PRODUCT LOOK: matte white with VYLA branding. No glossy. No rival branding.
PHOTOREALISTIC: No stylization. No CGI.
SHOT QUALITY: premium DTC brand campaign photography.
ASPECT RATIO: 3:2 | QUALITY: Maximum | STYLE: Photorealistic
```

**Action Ivan :** Appliquer la méthode "White Labeler" pour le prochain produit PURESOLE. Identifier 2-3 concurrents via FB Ads Library, générer wireframe + copy en 1 session Claude.

---

## 👍 NICE-TO-WATCH (5 vidéos)

| # | Titre | URL | Pertinence |
|---|-------|-----|------------|
| 4 | Claude Code New Features Explained (AI Employee Map 8 étapes) | https://www.youtube.com/watch?v=SkY-tR9kf-k | Setup Claude Code comme "employé IA" structuré |
| 5 | Every New Claude Code Feature Explained! 2026 | https://www.youtube.com/watch?v=sJVxwwaF0sU | Panorama features récentes |
| 6 | Claude + Shopify Creates $700k/m Stores (1hr Tutorial) | https://www.youtube.com/watch?v=qpbGtEd23us | Shopify automation deep-dive (vidéo longue) |
| 7 | Claude Just Got Cheaper, Smarter — Daily AI News Sep 2 | https://www.youtube.com/watch?v=qgYbzDu7hjQ | Claude Fable 5.1 launch résumé |
| 8 | The Most Important Feature 2026 : Claude Managed Agents | https://www.youtube.com/watch?v=NrhsHEmNNo8 | Context: Managed Agents API |

---

## ⏭️ SKIP (raisons)

- Vidéos "Claude AI Promo Code" → spam/clickbait
- Vidéos cours génériques 4h+ → trop long, peu de nouveauté
- Vidéos Claude Shopify de mai-juillet 2026 → > 14 jours, déjà couvertes

---

## 📰 ACTUALITÉS CLAUDE CODE (changelog semaine)

### Claude Code v2.1.278 — 19 sept. 2026 ⭐
- **AGENTS.md fallback** : Si pas de CLAUDE.md, Claude lit AGENTS.md → plus besoin de fichiers dupliqués
- **Auto mode serveur** : Classificateur côté serveur pour API/Enterprise (sans frais classif)
- **Skills sync** : Les skills/plugins activés sur claude.ai se synchronisent en session terminal
- `CLAUDE_GATEWAY_PROXY_IS_EGRESS_BOUNDARY=1` pour les gateways

### Claude Code v2.1.277 — 18 sept. 2026
- `/skill doctor` : affiche coût contexte et usage de chaque skill
- Corrections majeures : sessions décrochées après `/clear`, messages perdus avec `/resume`

### Claude Code v2.1.275 — 17 sept. 2026
- **ctrl+enter** : envoi immédiat (interruption + queue)
- `/plugin install <plugin> --marketplace <source>` ajouté
- Skills sync introduit

### Autres news Anthropic (sept. 2026)
- **Projects redesign** (17 sept.) : Projets → format conversation
- **Claude Cowork + Chat unifiés** (16 sept.) : une seule interface
- **Claude Fable 5.1 + Mythos 5.1** (1 sept.) : nouveau modèle frontier
- **Claude Commerce Agents** (2 sept.) : blueprint open-source pour agents e-commerce Shopify/Visa/Mastercard — +35% panier moyen, +60% taux completion

---

## 🚀 SKILLS PROPOSÉS (3)

> ⚠️ **Rappel : ces skills ne sont PAS déployés automatiquement. Ivan valide manuellement.**

### 1. `shopify-cro-analyzer`
**Source :** Vidéo EpPuU9k6Ahg (Shopify AI Toolkit)  
**Quoi :** Analyse CVR par page Shopify sur 30j, identifie star/underperformers, génère recommandations CRO priorisées.  
**Fichier :** `claude-weekly/2026-09-21/skills-proposed/shopify-cro-analyzer/SKILL.md`

### 2. `shopify-aov-strategist`
**Source :** Vidéo EpPuU9k6Ahg (Shopify AI Toolkit)  
**Quoi :** Analyse co-occurrences d'achat sur 90j, propose bundles/cross-sells/volume discounts avec impact AOV calculé.  
**Fichier :** `claude-weekly/2026-09-21/skills-proposed/shopify-aov-strategist/SKILL.md`

### 3. `ecom-project-planner`
**Source :** Vidéos Nhmyrh9I_bA + SkY-tR9kf-k  
**Quoi :** Transforme un objectif e-commerce en ROADMAP.md multi-agents parallèles (marketing + contenu + tech + data).  
**Fichier :** `claude-weekly/2026-09-21/skills-proposed/ecom-project-planner/SKILL.md`

---

## 💡 INSIGHT CROSS-VIDÉOS

**Pattern dominant cette semaine :** Claude évolue de chatbot → OS de l'e-commerce solo founder. Les trois vidéos must-watch montrent le même arc : (1) agents persistants qui tournent sans toi, (2) accès natif Shopify via plugins, (3) génération de boutiques complètes en heures. Pour Ivan, la pièce manquante n'est plus l'outil — c'est le BRIEF. Celui qui maîtrise l'art du brief e-commerce multi-agents (Project Planner) sera 10x plus rapide que celui qui fait des tâches unitaires.

---

## 📊 STATS RUN

| Métrique | Valeur |
|----------|--------|
| Sources collectées | 7 |
| Vidéos candidates | 18 |
| Must-watch | 3 |
| Nice-to-watch | 5 |
| Skip | 10 |
| Analyses Gemini réussies | 4/5 (1 échec : vidéo trop longue > 1h) |
| Skills proposés | 3 |
| Doublons seen-urls | 0 |

---

*Généré par veille-claude-weekly · 2026-09-21 07:12 UTC*
