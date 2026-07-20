# Claude Weekly — 2026-07-20

> Veille focus Claude / Claude Code / Skills / MCP · Semaine du 2026-07-07 au 2026-07-20

---

## ACTUALITÉS ANTHROPIC CETTE SEMAINE

### 🎓 Claude for Teachers (14 juillet)
- Accès gratuit premium aux outils Claude pour les enseignants K-12 américains vérifiés
- Inclut des "teaching skills" et connexions curriculum alignées aux 50 états
- Signal : Anthropic mise sur l'éducation comme vecteur d'adoption → watch les skills pédago

### ☁️ Claude Cowork passe au Cloud (9 juillet)
- Sessions et fichiers suivent entre appareils (mobile, web, desktop)
- Tâches en arrière-plan même appareil éteint
- Approbations mobiles, projets partagés, historique cross-device
- **Impact Ivan :** délégation à Cowork possible depuis mobile pendant shooting streetwear

### 🪞 Claude Reflect — Dashboard d'usage (9 juillet)
- Visualise tes habitudes AI : sessions, outils utilisés, patterns
- Disponible en beta Free/Pro/Max avec mémoire activée
- Source : TechCrunch « Anthropic's new Claude feature is quietly selling you on AI »

### 🌍 Fable 5 — Redéploiement mondial (1er juillet — semaine précédente)
- US Department of Commerce a levé les contrôles export
- Accès Fable 5 restauré sur Claude.ai, Claude Code, Claude Cowork
- API inclus via usage credits après 7 juillet

### 🏥 HIPAA Self-Serve (Enterprise)
- Les orgs Enterprise peuvent configurer elles-mêmes la conformité HIPAA
- Pas d'impact direct Ivan mais signal : Anthropic monte en fiabilité enterprise

---

## ⚙️ CLAUDE CODE — RELEASES CRITIQUES (7-20 juillet)

| Version | Date | Feature clé |
|---------|------|-------------|
| 2.1.215 | 19 juil | `/verify` et `/code-review` ne s'auto-lancent plus — invocation manuelle requise |
| 2.1.214 | 18 juil | Fix permission bypass (WSL, long commands >10K chars) · `EndConversation` tool · OpenTelemetry |
| **2.1.212** | **17 juil** | **`/fork` → session arrière-plan · `/subtask` → sous-agent in-session · Cap 200 subagents/session · MCP auto-bg 2min · `/resume` session picker** |
| 2.1.211 | 15 juil | `--forward-subagent-text` : texte sous-agents dans stream-json |
| 2.1.210 | 14 juil | Compteur temps elapsed · Fix `ultracode` se déclenchant sur webhooks/PR comments |
| **2.1.207** | **11 juil** | **Auto mode disponible SANS opt-in sur Bedrock, Vertex AI, Foundry** |

### Changements critiques à appliquer

**`/fork` vs `/subtask` (v2.1.212) :**
```
/fork    → copie la conversation dans une NOUVELLE session arrière-plan (claude agents)
           → tu continues dans la session principale sans interruption
/subtask → lance un sous-agent DANS la session courante
```
**Workflow Ivan :** pendant qu'un `/fork` analyse tes stocks PURESOLE, tu continues à travailler sur TempleTwins dans la même session.

**Auto mode sans opt-in sur Bedrock/Vertex/Foundry (v2.1.207) :**
- Si tu utilises Claude via API AWS ou GCP → tu as maintenant auto mode par défaut
- Désactiver avec `disableAutoMode: true` dans les settings

**Cap subagents = 200 par session (v2.1.212) :**
- Limite configurables via `CLAUDE_CODE_MAX_SUBAGENTS_PER_SESSION`
- MCP calls >2 minutes passent automatiquement en arrière-plan

**Permission fix critique (v2.1.214) :**
- `dir/**` ne couvre plus automatiquement tous les sous-dossiers imbriqués
- Revoir les allow rules dans `.claude/settings.json`

---

## MUST-WATCH — 2 vidéos retenues

### 1️⃣ Claude Code Tutorial for Beginners: Build Website with AI (2026)
**URL :** https://www.youtube.com/watch?v=OdSXY4YgmZA  
**Date :** ~13 juillet 2026 · **Score sélection :** 5/10  
**Score Gemini :** ⭐ 9/10

**TL;DR :** Démontre comment construire des apps full-stack (portfolio + calorie tracker avec IA) via des prompts textuels structurés avec Base44 + Claude Opus 4.8. Compétence clé : planifier avant de prompter.

**Concepts clés :**
- [04:22] Planification pré-prompt obligatoire : définir sections et style visuel AVANT le prompt
- [02:05] Claude Opus 4.8 pour cohérence bases de données/layouts/navigation
- [10:52] Raffinement par prompts successifs (animations, hover states)
- [20:26] Intégration analyse IA dans l'app : passer les données à Claude pour insights
- [30:20] Debug par IA : décrire le problème, pas réécrire le prompt

**Prompt verbatim (portfolio) :**
```
"Please build a premium, highly responsive personal portfolio website from scratch. 
Structure: Hero Section (titre + sous-titre + CTA 'Let's Connect'), About Section 
(2 colonnes : principes + skills), Portfolio Section (grille 3-col projet cards avec 
'View Blueprint' button), Contact Section (formulaire → database). Style: editorial 
dark, charcoal slate background, sharp borders, generous padding."
```

**Prompt verbatim (IA dans app) :**
```
"Please add an AI Analysis Feature. Build a 'Generate AI Insights' button.
When clicked: pass the active meal database table to the internal Claude engine.
The model must analyze patterns, evaluate macro balance, and output 3 personalized 
insights inside a card 'Claude's Coaching Insights'."
```

**Application Ivan :** Prototyper rapidement des landing pages TempleTwins/PURESOLE, des outils de suivi stock/ROAS, ou des pages produit avec recommandations IA — sans dev coûteux.

> *Analyse complète : `claude-weekly/2026-07-20/analyses/OdSXY4YgmZA-website-tutorial.md`*

---

### 2️⃣ I Tested 5 Claude AI Side Hustles — Only These Actually Made Money
**URL :** https://www.youtube.com/watch?v=dvm3nqVlzuo  
**Date :** ~6 juillet 2026 · **Score sélection :** 5/10  
**Score Gemini :** ⭐ 9/10

**TL;DR :** Le vrai side hustle qui marche = construire une audience YouTube puis la monétiser en couches. Claude AI = moteur pour réduire la production de contenu de 15h → 2h par vidéo.

**Concepts clés :**
- [00:54] Problème fondamental de tous les side hustles qui échouent : manque d'audience
- [06:18] YouTube = "Times Square" du trafic constant (vs cold outreach = desert)
- [09:07] Claude AI supprime le goulot d'étranglement : scripts + planification
- [14:52] Produit "Build-Once" (cours/templates/logiciel) → revenu passif via YouTube
- [17:21] "Quiet Monopoly" : petite audience riche > grande audience cheap
- [23:29] Stratégie composée : réinvestir + empiler les monétisations

**Prompts verbatim Claude (directement utilisables) :**

*Niche Validator :*
```
"I want to start a YouTube channel in [NICHE]. Give me: (1) the affluence and 
buying power of this audience, (2) the top three monetization paths beyond AdSense, 
(3) the top 20 video ideas that would specifically attract that affluent audience. 
Sort by potential lifetime value per viewer. Interview me until you have enough context."
```

*Authority Pillar Content :*
```
"I want to build an inbound lead-generation YouTube channel in [NICHE / SKILL]. 
My target buyer is [BUYER PROFILE]. Write me 30 video titles as authority pillar content.
Sort by: highest-intent buyer trigger first. For the top 5, write a 12-minute script 
with hooks structured for my target buyer. Interview me until you have enough context."
```

*Build-Once Product :*
```
"I want to create a [FORMAT] on [TOPIC]. Give me: (1) structured outline, 
(2) first chapter in full, (3) 5-email sales sequence, (4) sales page outline. 
Target: [BUYER PROFILE]. Interview me until you have enough context."
```

*Cold Start Play :*
```
"I have [X] years of experience as a [JOB/ROLE]. I want to start a YouTube channel 
teaching the practical reality of that career. Give me: (1) 30 video titles a beginner 
would search, (2) first 5 scripts of 8 minutes. Direct, no fluff. 
Interview me until you have enough context."
```

**Application Ivan :** Valider la niche streetwear/éco pour un canal YouTube personnel → construire autorité fondateur → vendre cours "Comment lancer une marque de mode durable sur Shopify".

> *Analyse complète : `claude-weekly/2026-07-20/analyses/dvm3nqVlzuo-side-hustles-youtube.md`*

---

## NICE TO WATCH (4-6/10) — 5 contenus

| # | Titre/Source | URL | Pourquoi |
|---|---|---|---|
| 1 | Claude Code Auto Mode sur Bedrock/Vertex | https://www.youtube.com/watch?v=53Uun2Qit0Q | Release v2.1.207 — auto mode sans opt-in maintenant GA |
| 2 | Claude Code Skills vs Hooks vs Subagents vs MCP (Totalum) | https://www.totalum.app/blog/claude-code-skills-totalum | Comparatif complet — context cost: skill 30-50 tokens vs MCP 55K |
| 3 | Claude Skills Every Shopify Merchant Should Set Up | https://www.get-ryze.ai/blog/claude-skills-every-shopify-merchant-should-set-up | Skills Shopify spécifiques — directement actionnable Ivan |
| 4 | Run Your Shopify Store on Autopilot with Claude (2026) | https://www.get-ryze.ai/blog/run-your-shopify-store-on-autopilot-with-claude | Pattern automation store complet |
| 5 | Claude Code Explained: Automate Your Coding Workflow | https://www.youtube.com/watch?v=x8cBAjq3_a8 | Workflows automation 2026 avec code |

---

## SKIP (mention)

- **YKIUt9ytxIE** "Build and Deploy Claude Skills and MCP Servers" — excellent mais > 14j (juin 2026)
- **sX-FmJL7Wd0** "Claude Code Beginners Master 1 Hour" — mai 2026, trop vieux
- **LFrPP9shZEc** "This NEW Claude Code Update Is INSANE!" — ~juin 2026, clickbait + trop vieux
- **UztrFXaSWv0** "Creators of Claude Code don't Prompt Their Agents Anymore" — juin 2026
- **zaDbZt40kRg** Gui Ferreira NDC AI 2026 — déjà dans digest 2026-07-06

---

## 🔌 MCP — ÉCOSYSTÈME (semaine)

### modelcontextprotocol/servers (commits July 6)
- `fix(filesystem)` : déclaration `openWorldHint: false` sur 14 outils
- `fix(filesystem)` : `read_media_file` retourne maintenant le bon content type MCP (image/audio/resource)
- **Pas de nouveaux commits après le 6 juillet** sur le repo officiel

### Chiffres clés MCP 2026
- **9 400+ serveurs MCP** dans le registre officiel
- Coût contexte d'un setup 5 serveurs/58 outils : **~55 000 tokens** avant le premier prompt
- Coût d'un skill classique : **30-50 tokens** jusqu'à invocation
- → Favoriser les skills pour les tâches répétitives, MCP pour l'accès système

### Nouveaux repos MCP/Skills intéressants
- **github.com/AgriciDaniel/claude-youtube** — Skill Claude Code pour YouTubers (audits, SEO vidéo, scripts rétention, thumbnails)
- **github.com/ray-amjad/claude-code-workflow-creator** — Skill pour créer des scripts Workflow (orchestration multi-agents déterministe)

---

## INSIGHTS & PATTERNS SEMAINE

### 🔑 Pattern majeur : Fork-as-parallelism
La feature `/fork` (v2.1.212) change la façon de travailler avec Claude Code :
```
# Workflow avant : séquentiel, une tâche à la fois
/task analyser-stocks-puresole → attends → /task rédiger-descriptions-temple

# Workflow après : parallèle, 2 contextes simultanés
/fork → [arrière-plan] analyser-stocks-puresole
         [avant-plan] rédiger-descriptions-temple
```
**Application Ivan :** Lancer une analyse de pricing competitor PURESOLE en `/fork` pendant qu'on continue à écrire du contenu TempleTwins. Pas de switch de contexte.

### 🔑 Pattern majeur : Skill cost vs MCP cost
La découverte de la semaine côté architecture :
- 1 skill = 30-50 tokens de contexte (quasi gratuit)
- 1 setup MCP 5 serveurs = 55 000 tokens avant le premier message
- **Règle pratique :** MCP pour accès système (Shopify API, GitHub, Postgres), Skills pour workflows répétitifs (rédiger, analyser, poster)

### 🔑 Changement silencieux : /verify et /code-review ne s'auto-lancent plus
v2.1.215 (hier) : ces deux skills ne s'exécutent plus automatiquement.
**Si tu avais des hooks ou habitudes qui supposaient leur auto-exécution → mettre à jour.**

---

## 🚀 SKILLS PROPOSÉS — 3 (à review par Ivan)

> ⚠️ Ces skills sont des propositions issues des analyses Gemini — jamais déployés automatiquement. Ivan review et décide.

### SKILL-1 : `niche-multi-monetisation`
**Source vidéo :** dvm3nqVlzuo (Gemini 9/10) · Prompt Niche Validator  
**Concept :** Prend une niche e-commerce, génère une analyse affluence/audience + 3 voies de monétisation au-delà du produit + 20 idées YouTube tri "valeur vie spectateur".  
**Fichier :** `claude-weekly/2026-07-20/skills-proposed/niche-multi-monetisation/SKILL.md`

### SKILL-2 : `youtube-autorite-pipeline`
**Source vidéo :** dvm3nqVlzuo (Gemini 9/10) · Prompt Authority Pillar Content  
**Concept :** À partir d'une expertise + profil acheteur, génère 30 titres vidéo "authority pillar" triés highest-intent + 5 scripts 12min pour attirer leads pré-qualifiés.  
**Fichier :** `claude-weekly/2026-07-20/skills-proposed/youtube-autorite-pipeline/SKILL.md`

### SKILL-3 : `ecommerce-page-prototyper`
**Source vidéo :** OdSXY4YgmZA (Gemini 9/10) · Pattern Base44 + Claude Opus  
**Concept :** Transforme un brief page e-commerce (landing, produit, collection) en prompt complet ready-to-paste pour construire avec une IA de dev (Claude Code, Base44, Cursor). Inclut structure sections, style branding, fonctionnalités IA intégrées.  
**Fichier :** `claude-weekly/2026-07-20/skills-proposed/ecommerce-page-prototyper/SKILL.md`

---

## SOURCES

- Changelog Claude Code officiel : https://code.claude.com/docs/en/changelog
- Anthropic News (Reflect/Cowork/Teachers) : https://www.anthropic.com/news
- Releasebot Anthropic July 2026 : https://releasebot.io/updates/anthropic
- Freedom.tech Claude Code 2.1.212 : https://freedom.tech/posts/2026-07-17-claude-code-2-1-212/
- MCP Servers repo : https://github.com/modelcontextprotocol/servers/commits/main.atom
- Claude Skills Shopify : https://www.get-ryze.ai/blog/claude-skills-every-shopify-merchant-should-set-up
- Totalum Skills vs Hooks vs MCP : https://www.totalum.app/blog/claude-code-skills-totalum
- Claude Shopify Autopilot : https://www.get-ryze.ai/blog/run-your-shopify-store-on-autopilot-with-claude
- Nexscope E-commerce Claude Code : https://www.nexscope.ai/blog/claude-code-ecommerce-automation
- Claude Directory Skills July 2026 : https://www.claudedirectory.org/for/ai-agent-development
- GitHub Claude YouTube Skill : https://github.com/AgriciDaniel/claude-youtube
- GitHub Workflow Creator Skill : https://github.com/ray-amjad/claude-code-workflow-creator
