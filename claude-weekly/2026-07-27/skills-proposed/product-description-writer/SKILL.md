---
name: product-description-writer
description: Génère des descriptions produit SEO-optimisées pour Shopify selon le ton de marque (TempleTwins streetwear ou PURESOLE dropship). Extraire caractéristiques → produire description longue + courte + balises méta.
source: Analyse Gemini — Claude Skills Just Fixed MCP's Biggest Problem (2026-07-27)
status: proposed — review manuelle Ivan requise
---

## Contexte Ivan
- **TempleTwins** : streetwear premium, ton jeune/authentique/urbain, cible 18-30 ans passionnés mode
- **PURESOLE** : dropshipping, ton informatif/efficace, mise en avant rapport qualité-prix et délais

## Usage
Invoquer avec : `/product-description-writer` ou décrire la tâche à Claude.

## Entrées requises
1. Nom du produit
2. Caractéristiques techniques (matière, taille, couleur, composition)
3. Marque cible : `TempleTwins` ou `PURESOLE`
4. Mots-clés SEO prioritaires (3-5)
5. Prix (pour ancrage valeur)

## Sortie attendue

### Description longue (200-300 mots)
Pour la page produit Shopify — narrative, bénéfices d'usage, storytelling selon marque.

### Description courte (50-80 mots)
Pour les collections et les aperçus.

### Balises SEO
- `<title>` : 60 chars max
- `meta description` : 160 chars max
- Alt text image suggéré

## Prompts internes

### Pour TempleTwins
```
Tu es copywriter streetwear premium pour TempleTwins. Ton : authentique, urban, confident, pas corporate.
Évite : "luxe", "premium", "de qualité". Utilise : mouvement, culture, communauté, expression.
Intègre naturellement ces mots-clés : {keywords}.
Produit : {nom} — {caractéristiques}. Prix : {prix}€.
```

### Pour PURESOLE
```
Tu es copywriter e-commerce efficace pour PURESOLE (dropshipping). Ton : clair, rassurant, axé bénéfices.
Focus : rapport qualité-prix, facilité de livraison, satisfaction garantie.
Intègre naturellement ces mots-clés : {keywords}.
Produit : {nom} — {caractéristiques}. Prix : {prix}€.
```

## Fichiers de référence
- `brand_tones/templetwins.md` — exemples de copywriting validés TempleTwins
- `brand_tones/puresole.md` — exemples de copywriting validés PURESOLE
- `seo_checklist.md` — checklist SEO Shopify

## Notes
- Générer 2 variantes pour A/B testing si possible
- Éviter le contenu dupliqué fournisseur (surtout PURESOLE)
- Longueur descriptions : Google indexe mieux 200+ mots
