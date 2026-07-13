# Claude Weekly — 13 juillet 2026

> Veille focus Claude / Claude Code / Skills / MCP  
> Générée automatiquement par `veille-claude-weekly`

---

## 🔥 Annonces Anthropic cette semaine

### Claude Code v2.1.207 (11 juillet)
- **Auto mode désormais activé par défaut** sur Bedrock, Vertex AI et Foundry (désactivable via `disableAutoMode`)
- Correction du gel terminal sur longs blocs de code/tables — bug critique résolu
- Correction des faux positifs d'injection de prompt

### Claude Code v2.1.206 (9 juillet)
- Suggestions de chemins pour `/cd` (like `/add-dir`)
- `/doctor` pour nettoyer les `CLAUDE.md` inutiles
- `/commit-push-pr` supporte `remote.pushDefault`
- Gateway : support des endpoints publics Anthropic dans `/login`

### Claude Code v2.1.203 (7 juillet)
- **MCP `roots/list` inclut maintenant les répertoires de travail additionnels** — utile pour multi-projets
- Badge `⏸` mode manuel en footer
- Auto-recovery des sessions d'agent non-réactives

### Claude Code v2.1.202 (6 juillet)
- **"Dynamic workflow size"** dans `/config` (small/medium/large) — contrôle la taille des workflows
- Attributs OpenTelemetry `workflow.run_id` et `workflow.name`
- Meilleure qualité `/code-review` sur claude-opus-4-8

### Feature Reflect (9 juillet — TechCrunch)
- Nouveau tableau de bord d'usage personnel : topics, jour le plus actif, heure de pointe
- Beta sur Free/Pro/Max plans (web + desktop), nécessite Memory activée
- Settings > Time and focus : break reminders + quiet hours

### Claude Cowork — expansion web + mobile
- Claude Cowork désormais disponible sur web et mobile
- Sessions et fichiers synchronisés cross-devices
- Microsoft 365 write tools : emails, calendrier, OneDrive/SharePoint

### Nouveaux modèles
- **Claude Sonnet 5** (`claude-sonnet-5`) : 1M context window, 128k output, pricing introductoire
- **Claude Opus 4.8** : 1M context window par défaut sur API, Bedrock, Vertex

---

## 🎬 Must-Watch (3/3)

### 1. Claude Skills Tutorial (2026): Build, Run, and Share
**URL :** https://www.youtube.com/watch?v=O_z9vDLgvoY  
**Date :** Récent (juillet 2026) | **Score :** 9/10  
**Analyse Gemini :** ✅ Disponible (`analyses/O_z9vDLgvoY-claude-skills-tutorial-build-run-share.md`)

**TL;DR :** Guide complet sur la création de Skills Claude via l'interface assistée, leur exécution cross-plateforme (Chat/Cowork/Code), et toutes les méthodes de partage (zip, Org Skills Teams/Enterprise, Google Drive, Git).

**Points clés pour Ivan :**
- [01:15] Création assistée : Claude pose les bonnes questions pour designer le skill
- [04:30] Skills chargés on-demand seulement (pas de surcharge contexte)
- [09:00] Skills globaux (`~/.claude/skills/`) vs project (`.claude/skills/`)
- [11:25] Org Skills pour partager à toute une équipe (Teams/Enterprise)
- [12:16] Partage via Google Drive (expérimental, attention aux dossiers `.dot`)

**Micro-action :** Créer `/gen-fiche-produit-shopify` ce weekend (voir skills-proposed/)

---

### 2. The NEW Way to Generate Leads in 2026 (With AI / Claude Code)
**URL :** https://www.youtube.com/watch?v=SmCodMPSDlE  
**Date :** ~7 juillet 2026 (1 semaine) | **Score :** 9/10  
**Analyse Gemini :** ✅ Disponible (`analyses/SmCodMPSDlE-new-way-generate-leads-claude-code.md`)

**TL;DR :** 6 changements dans la génération de leads via Claude Code : Company Waterfall Sourcing, Contact Finding IA, Agentic Cron Jobs quotidiens, Goal Mode (objectif → agents parallèles → campagne auto), AI Auto-Research sur les campagnes, et Open-Source Stack (Browser Use, Gemma 4, parseurs HTML→Text).

**Points clés pour Ivan :**
- [00:44] Contact Finding via OpenWebNinja : trouve emails même si pas sur LinkedIn
- [04:55] Agentic Cron Job daily : `"every day, find me 5 companies hiring for X"`
- [06:40] Goal Mode : donner un objectif à Claude Code, il déploie des agents en parallèle
- [08:05] Browser Use (open-source) : scrape prix concurrents, vérif régulations dropship
- [08:37] Gemma 4 (open-source) : génération contenu sans coûts API

**Micro-action :** Tester Goal Mode sur Claude Code pour identifier 20 micro-influenceurs streetwear UK/US

---

### 3. Build and Deploy Claude Skills and MCP Servers | The Complete 2026 Guide
**URL :** https://www.youtube.com/watch?v=YKIUt9ytxIE  
**Date :** 2026 | **Score :** 8/10  
**Analyse Gemini :** ❌ Échec (vidéo trop longue pour quota free tier)

**TL;DR web :** Guide complet build + deploy : structure de skill (SKILL.md + scripts), publication sur MCP servers, orchestration Skills + MCP. Pattern recommandé 2026 : 1 MCP par système externe (GitHub, Postgres, Linear), Skills pour orchestrer.

**Micro-action :** À regarder (long format) pour comprendre l'architecture Skills+MCP avant de builder le premier MCP Shopify

---

## 📺 Nice-to-Watch (2)

| # | Titre | URL | Score | Note |
|---|-------|-----|-------|------|
| 1 | Claude Code Tutorial for Beginners: Build Website with AI (2026) | https://www.youtube.com/watch?v=OdSXY4YgmZA | 5 | Publié il y a 2 jours — basics mais récent |
| 2 | Claude Code Tutorial (1h) \| Skills, Subagents, Hooks & MCP | https://www.youtube.com/watch?v=sX-FmJL7Wd0 | 5 | Mai 2026 (>14j) — référence complète |

---

## ⏭️ Skip

- `zaDbZt40kRg` — Gui Ferreira NDC AI 2026 (déjà vu semaine précédente)
- `RzLV8sfFdMM` — "How to Use Claude Code Better Than 98%" (déjà vu)
- `ECQA6oOyfIk` — "Just Learning Claude Code 2026" (déjà vu)
- `X_zVY3-mbM8` — "FULL Tutorial Beginners" (déjà vu)
- `uogzSxOw4LU` — "Ultimate Guide MCP Skills" (>14j)
- `0hdFJA-ho3c` — "Claude Code is all you need" (janvier 2026)
- `Thylf8WVuK8` — "AI Summer 2026 Model Choice" (juin, >14j)

---

## 🚀 Skills Proposés (3)

> **Rappel :** Skills proposés uniquement. Ivan review manuellement avant déploiement.

### 1. `/gen-fiche-produit-shopify`
→ `claude-weekly/2026-07-13/skills-proposed/gen-fiche-produit-shopify/SKILL.md`  
Génère titre + bullets + description longue + tags Shopify à partir de notes brutes, dans le ton TempleTwins ou PURESOLE. Pattern direct depuis la vidéo O_z9vDLgvoY.

### 2. `/resum-fournisseur-dropship`
→ `claude-weekly/2026-07-13/skills-proposed/resum-fournisseur-dropship/SKILL.md`  
Résume threads fournisseur dropship, extrait les actions requises, rédige brouillon de réponse. Gain de temps immédiat sur opérations PURESOLE.

### 3. `/influencer-matchmaking-ecom`
→ `claude-weekly/2026-07-13/skills-proposed/influencer-matchmaking-ecom/SKILL.md`  
Plan structuré de recherche micro-influenceurs streetwear/mode avec critères, hashtags, template outreach DM — sans dépenser en outils payants. Pattern "Contact Finding" de SmCodMPSDlE.

---

## 💡 MCP Servers — Quoi de neuf

**Dépôt officiel (modelcontextprotocol/servers) — commits du 1-7 juillet :**
- Fix filesystem : annotation `openWorldHint: false` sur les 14 outils (conformité spec)
- Fix filesystem : type de contenu MCP correct pour fichiers image/audio
- Sécurité : mise à jour PyJWT → 2.13.0 (CVE-2026-48526)
- Infrastructure : migration OIDC trusted publishing npm
- **Aucun nouveau serveur MCP ajouté cette semaine**

**Ecosystème :** 9 400+ serveurs MCP dans le registry officiel (2026). Pattern dominant : 1 MCP/système externe + Skills pour orchestrer.

**Shopify + Claude (contexte) :**
- Shopify AI Toolkit (Q1 2026) : 4 MCP natifs officiels
- Pattern gagnant : MCP Shopify Admin → Skills pour automatiser fiches produits, emails, reporting
- ROI observé : 48% gain productivité, 15-25h/semaine économisées (sources multiples)

---

## 📊 Synthèse & Insight Cross-Vidéos

**Pattern récurrent cette semaine :** Les Skills Claude s'imposent comme la **couche d'orchestration** entre l'utilisateur et les MCPs. On ne code plus des workflows complexes — on crée des Skills légers qui pilotent des MCPs spécialisés. Pour un solo founder e-com comme Ivan : 1 skill = 1 tâche répétitive = quelques minutes de gain par occurrence.

**Signal fort :** Goal Mode dans Claude Code (vidéo SmCodMPSDlE) + Dynamic Workflow Size dans `/config` (Claude Code 2.1.202) convergent vers le même paradigme : donner un **objectif** à Claude, laisser l'IA décomposer et paralléliser. Niveau d'abstraction qui monte.

**À surveiller :** Org Skills (Teams/Enterprise) — si Ivan embauche un freelance ou un VA, le partage de skills devient le "onboarding IA" de l'équipe.

---

## 📁 Fichiers de cette session

```
claude-weekly/2026-07-13/
├── analyses/
│   ├── O_z9vDLgvoY-claude-skills-tutorial-build-run-share.md  ✅ Gemini OK
│   └── SmCodMPSDlE-new-way-generate-leads-claude-code.md     ✅ Gemini OK
└── skills-proposed/
    ├── gen-fiche-produit-shopify/SKILL.md
    ├── resum-fournisseur-dropship/SKILL.md
    └── influencer-matchmaking-ecom/SKILL.md
```

**Gemini analyses :** 2/4 réussies (YKIUt9ytxIE trop longue >10800 frames ; OdSXY4YgmZA timeout)

---

*veille-claude-weekly · 2026-07-13 · claude-sonnet-4-6*
