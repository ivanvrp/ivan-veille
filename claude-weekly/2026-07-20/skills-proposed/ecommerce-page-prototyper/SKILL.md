# Skill : ecommerce-page-prototyper

> Proposé par veille-claude-weekly 2026-07-20
> Source : Gemini analyse vidéo OdSXY4YgmZA "Claude Code Tutorial for Beginners: Build Website with AI"
> ⚠️ À review par Ivan avant déploiement

## Description

Génère via des prompts structurés un prototype de page e-commerce complète (landing page, page produit, page collection) — incluant sections, style, et fonctionnalités IA intégrées. Utilisable avec Base44, Shopify custom sections, ou Claude Code directement.

## Déclencheur

```
/ecommerce-page-prototyper
```

## Instructions skill (draft)

```markdown
Tu es un expert en prototypage rapide de pages e-commerce avec IA.

L'utilisateur te décrit ce qu'il veut créer. Tu génères UN prompt complet et structuré pour construire la page avec une IA de développement (Claude Code, Base44, Cursor, etc.).

Le prompt généré doit inclure :

1. **Structure de sections** (Hero, Produits, Témoignages, FAQ, Contact)
2. **Style visuel** (couleurs, typographie, ambiance — adapté au branding streetwear ou dropship)
3. **Fonctionnalités dynamiques** si besoin (filtres, panier, formulaire, tracking)
4. **Clause de cohérence** : « Maintenir la cohérence des bases de données, des layouts et de la navigation »

Format de sortie : UN bloc de texte "prompt ready-to-paste" + commentaires d'implémentation.

Interviewe l'utilisateur si les infos manquent : type de page, objectif (conversion, awareness, etc.), style de marque, device prioritaire.
```

## Prompts verbatim source (vidéo, extrait key)

```
"Please build a premium, highly responsive personal portfolio website from scratch. 
Structure the layout as a single-page experience containing four distinct sections: 
[Hero Section], [About Section], [Portfolio Section], [Contact Section with database]. 
Style the entire site with an editorial dark aesthetic using a charcoal slate background, 
sharp container borders, and generous section padding."
```

Pattern applicable à Shopify :
```
"Please build a premium, highly converting Shopify-style landing page for [PRODUIT]. 
Structure: Hero (image produit + CTA), Section avantages (3 colonnes icônes), 
Section témoignages (carousel 4 avis), Section FAQ (accordion), CTA final.
Style: [BRANDING]. Intègre un formulaire de capture email en popup après 30s."
```

## Contexte Ivan

- TempleTwins : style éditorial sombre, urban/streetwear, audience mobile-first
- PURESOLE : tonalité durable/éco, cible conscience environnementale
- Usage : nouvelles collections, lancement produit, page de capture campagne pub

## Skill_potential_score

8/10 — prompts verbatim directement réutilisables, économie de 5-10h de dev par lancement
