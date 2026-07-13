---
name: gen-fiche-produit-shopify
description: Génère une description produit Shopify optimisée à partir de notes brutes, dans le ton TempleTwins ou PURESOLE
trigger: /gen-fiche-produit-shopify
source_video: https://www.youtube.com/watch?v=O_z9vDLgvoY
source_weekly: 2026-07-13
status: PROPOSED — Ivan review required before deployment
---

# Skill : /gen-fiche-produit-shopify

## Objectif

À partir de notes brutes sur un nouveau produit (matériaux, dimensions, caractéristiques, public cible, inspiration), génère une description complète pour Shopify, dans le ton exact de la marque.

## Prompt du skill

```
Tu es le copywriter de TempleTwins / PURESOLE. À partir des notes brutes ci-dessous sur un nouveau produit, génère :

1. **Titre Shopify** (max 70 chars, accrocheur, avec mot-clé principal)
2. **Sous-titre** (1 ligne vendeuse)
3. **Description courte** (2-3 phrases, ton streetwear/direct, sans jargon corporate)
4. **Bullet points** (5 points clés : matière, fit, occasion, différenciateur, soin)
5. **Description longue** (1 paragraphe narratif, 80-120 mots, storytelling)
6. **Tags suggérés** (10 max)
7. **Variantes à créer** (si applicable)

Ton de marque :
- TempleTwins : streetwear urbain, langage direct, références culture jeune, pas "Best Quality", pas "Premium"
- PURESOLE : propre, minimaliste, axé confort/style, légèrement plus accessible

NOTES PRODUIT :
{notes}

MARQUE CIBLE (précise si différent) :
{marque}
```

## Entrée attendue

Coller les notes brutes du produit + préciser la marque (TempleTwins ou PURESOLE).

## Sortie

Description prête à copier/coller dans Shopify admin.

## Notes

- Inspiré de la méthode "créer un skill assisté par Claude" vue dans la vidéo
- Itérer en ajoutant des exemples de descriptions existantes qui ont bien converti
- Peut être étendu avec un skill `/gen-fiche-produit-batch` pour traiter plusieurs produits à la fois
