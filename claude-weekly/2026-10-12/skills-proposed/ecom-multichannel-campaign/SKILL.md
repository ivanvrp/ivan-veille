# Skill: ecom-multichannel-campaign

> **STATUS: PROPOSÉ — Review manuel Ivan requis avant déploiement**
> Source: Analyse Gemini vidéo 9JoIpWgAsZ8 (I Mapped Every Claude Code Concept)
> Date proposition: 2026-10-12

## Description

Génère une campagne marketing complète et cohérente sur tous les canaux à partir d'un seul brief produit. Un brief → Instagram + TikTok + Newsletter + Meta Ads.

## Use case Ivan

- Lancement nouvelle collection TempleTwins : brief 1 page → 15 assets prêts à publier
- Promo flash PURESOLE : 1 description produit → 4 posts Instagram + 1 email + 2 variantes Meta Ads
- Gain estimé : 6-8h de copywriting → 30min de review + ajustements

## Déclenchement

```
/ecom-multichannel-campaign
```

## Input requis

```markdown
Produit: [nom + description courte]
Prix: [normal] → [promo si applicable]
Cible: [audience principale, ex: "homme 20-30 ans, streetwear, Paris"]
Ton: [décontracté/premium/urgence/storytelling]
Date publication souhaitée: [YYYY-MM-DD]
```

## Output généré

### 1. Posts Instagram (×3 variations)
- Caption (150 mots max)
- Hashtags (20-30, mix niche + populaire)
- Idée visuelle pour le créateur

### 2. Script TikTok/Reels (60s)
- Hook (3 premières secondes)
- Structure narrative
- Call to action
- Suggestions transitions/effets

### 3. Email newsletter
- Objet (A/B : 2 variantes)
- Preheader
- Corps (250 mots)
- CTA bouton

### 4. Annonces Meta Ads (×2)
- Headline (40 chars max)
- Primary text (125 chars max)
- Description
- Variation A (bénéfice) + Variation B (urgence/social proof)

## Instructions détaillées

1. Analyse le brief et identifie l'angle principal (unicité produit, prix, lifestyle, storytelling)
2. Génère d'abord le "message master" : 1 phrase-clé qui unifie tous les assets
3. Décline sur chaque canal en respectant ses codes natifs
4. Sauvegarde dans `campaigns/YYYY-MM-DD-{slug-produit}/`
5. Crée un `BRIEF.md` récapitulatif avec tous les assets

## Fichier output structure

```
campaigns/2026-10-12-templetins-hoodie-drop/
├── BRIEF.md
├── instagram-posts.md
├── tiktok-script.md
├── email-newsletter.md
└── meta-ads.md
```
