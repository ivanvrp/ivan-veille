---
name: shopify-product-description
description: Génère descriptions produits streetwear optimisées SEO pour Shopify TempleTwins
triggers:
  - fiche produit
  - description shopify
  - nouveau drop
  - product description
---

# Shopify Product Description — TempleTwins

## Usage
Donne un nom de produit + caractéristiques → génère description Shopify complète, SEO-ready.

## Instructions
1. Input : nom produit, matière, coloris, sizing, prix, points clés
2. Output : titre SEO, description courte (meta), description longue HTML Shopify, tags

## Format
```
Titre SEO : {produit} — {matière} | TempleTwins
Meta (160 chars) : {...}

Description Shopify (HTML) :
<p>{hook culturel}</p>
<ul>
  <li>Matière : {matière}</li>
  <li>Coupe : {coupe}</li>
  <li>Sizing : {tableau tailles}</li>
</ul>
<p>{storytelling marque}</p>
<p>{CTA urgence/exclusivité}</p>

Tags : streetwear, {produit}, {couleur}, {saison}, {drop-name}
```

## Notes
- Ton : authentique, pas marketing générique
- Référencer le drop/collection si applicable
- Optimization mots-clés streetwear FR + EN
