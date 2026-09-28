---
name: shopify-code-generator
description: Génère des sections de pages Shopify complètes et fonctionnelles (Liquid, HTML, CSS, JavaScript) à partir d'instructions textuelles et/ou d'exemples visuels (screenshots, URLs). Remplace les apps tierces par du code custom. Utilise ce skill quand Ivan veut modifier ou créer des composants Shopify sans app.
---

# Shopify Code Generator

## Contexte
Ivan veut créer et modifier des sections Shopify sans apps tierces coûteuses ou développeurs. Claude Code génère du Liquid/HTML/CSS/JS propre.

## Instructions

### Entrées acceptées
1. Screenshot d'une page ou section existante
2. URL d'une boutique à reproduire
3. Description textuelle de la fonctionnalité
4. Demande de modification d'un code Shopify existant

### Processus
1. Analyse le style : layout, couleurs, typo, espacement
2. Identifie les composants
3. Génère le code Liquid/HTML/CSS selon conventions Shopify 2.0
4. Fournis instructions d'installation en 3 étapes max

### Types de composants couverts
- Sections produit avancées (variantes, badges "Rupture", "Best-seller")
- Pop-ups de bundle (X produits pour Y€)
- Accordéons (FAQ, infos livraison, composition)
- Tableaux comparatifs de produits
- Carousels de collections
- Bannières promotionnelles

### Règles
- Code semantic et accessible (ARIA labels)
- Mobile-first (breakpoints 320px, 768px, 1024px)
- Compatible Shopify 2.0 (JSON templates)
- Variables CSS pour les couleurs
- Pas de dépendances externes non incluses dans Shopify

## References
- Shopify Liquid : https://shopify.dev/docs/api/liquid
- Dawn theme (référence) : https://github.com/Shopify/dawn
