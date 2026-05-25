---
name: ecom-content-autopilot
description: Agent autonome qui analyse les tendances sociales, génère du contenu marketing (textes + prompts visuels) pour TempleTwins (streetwear) et PURESOLE (dropship), adapté aux formats Instagram/TikTok/YouTube Shorts.
triggers:
  - "Je lance une nouvelle collection et je veux saturer les réseaux sociaux sans y passer des heures"
  - "Je souhaite identifier les prochaines grandes tendances en dropshipping pour PURESOLE et créer du contenu autour"
  - "Ma dernière campagne Instagram n'a pas eu beaucoup d'engagement, propose-moi des approches différentes"
  - "Je dois maintenir une présence constante sur TikTok mais je manque de temps pour créer chaque jour"
  - "Génère 10 posts Instagram pour la nouvelle collection TempleTwins avec hashtags et descriptions optimisés"
source_video: https://www.youtube.com/watch?v=9JoIpWgAsZ8
source_analysis: ../analyses/9JoIpWgAsZ8-claude-concept-roadmap.md
proposed: 2026-05-25
status: À VALIDER — copier vers ~/.claude/skills/ pour activer
---

# Skill : ecom-content-autopilot

## Pourquoi ce skill existe

Déduit de la vidéo "I Mapped Every Claude Code Concept So You Don't Have To" (mai 2026).
Les agents autonomes Claude + MCP (accès web, APIs réseaux sociaux) permettent à un solo founder
de maintenir une présence marketing continue sans y passer des heures quotidiennes.

## Workflow détaillé

### Étape 1 — Input Ivan (5 paramètres)
```
Marque : TempleTwins | PURESOLE
Produit/Collection : [ex: Hoodie Oversized "Tokyo Nights"]
Plateformes cibles : Instagram | TikTok | YouTube Shorts
Objectif : Engagement | Vente | Notoriété
Budget contenu : N posts | Fréquence hebdomadaire
```

### Étape 2 — Analyse des tendances (via Web + MCP)
```bash
# Rechercher les tendances actuelles pour la niche
WebSearch: "streetwear TikTok trends {mois_année}" OR "dropship {catégorie} Instagram viral"
# Extraire : styles visuels, hashtags performants, formats qui fonctionnent
```

### Étape 3 — Génération de contenu structuré

**Pour Instagram (Feed + Reels) :**
```markdown
Post #{N}
- Type : Carousel / Single / Reel
- Accroche : {titre captivant 10 mots max}
- Description : {150-200 mots, ton streetwear/lifestyle, CTA}
- Hashtags : {30 hashtags : 10 niche, 10 mid, 10 broad}
- Prompt visuel : {description précise pour Midjourney/DALL-E}
```

**Pour TikTok :**
```markdown
Video #{N}
- Durée cible : 15s | 30s | 60s
- Hook (0-3s) : {phrase d'accroche visuelle}
- Script voix-off : {texte complet si nécessaire}
- Texte on-screen : {overlays clés}
- Sound suggestion : {type de son tendance}
- Hashtags : {5-8 hashtags TikTok}
```

**Pour YouTube Shorts :**
```markdown
Short #{N}
- Titre SEO : {avec keyword principal}
- Description : {500 mots, incluant liens store}
- Tags : {10-15 tags}
- Thumbnail text : {texte court accrocheur}
```

### Étape 4 — Livrable final
Génère un fichier `content_calendar_{marque}_{YYYY-MM}.md` avec :
- Planning semaine par semaine
- Tous les textes prêts à copier-coller
- Tous les prompts visuels pour la génération d'images
- Checklist de publication

## Personnalisation par marque

### TempleTwins (streetwear)
- Ton : urban, authentique, aspirationnel, communauté
- Visuels : looks city, backstage, flat lay products, street photography
- Hashtags pool : #streetwear #urbanfashion #hypebeast #streetstyle #ootd

### PURESOLE (dropship)
- Ton : pratique, orienté bénéfice, UGC-style
- Visuels : produit en situation, avant/après, témoignage client
- Hashtags pool : selon catégorie produit (à définir par Ivan)

## Validation requise

**Ivan doit :**
1. Vérifier que le ton correspond bien à l'identité de chaque marque
2. Ajouter ses hashtags "maison" déjà éprouvés dans la section personnalisation
3. Tester sur 3 posts avant de valider le workflow complet
4. Copier vers `~/.claude/skills/ecom-content-autopilot.md` pour activer
5. Déclencher avec : "Génère le contenu Instagram pour la nouvelle collection TempleTwins"

## Note

Ce skill génère les textes et prompts visuels — la génération d'images elle-même
nécessite un MCP ou accès API à Midjourney/DALL-E/Flux (non inclus ici).
