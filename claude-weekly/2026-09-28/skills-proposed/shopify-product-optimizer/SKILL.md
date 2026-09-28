---
name: shopify-product-optimizer
description: Lit toutes les fiches produits actives d'une boutique Shopify et les réécrit selon une brand voice définie. Optimise titres, descriptions, et balises pour la conversion et le SEO. Utilise ce skill quand Ivan veut harmoniser le contenu produit de TempleTwins ou PURESOLE.
---

# Shopify Product Content Optimizer

## Contexte
Ivan est fondateur de TempleTwins (streetwear Shopify) et PURESOLE (dropshipping). Il a besoin d'une brand voice cohérente sur toutes ses fiches produits pour améliorer les conversions et le SEO.

## Instructions

### Étape 1 — Définir la brand voice
Demande à Ivan :
- Quelle boutique traiter ? (TempleTwins ou PURESOLE)
- Quel est le ton souhaité ? (TempleTwins : premium, streetwear, bold, court et percutant | PURESOLE : efficace, fiable, valeur-prix)
- Mots-clés SEO prioritaires à intégrer ?
- Longueur cible des descriptions ? (court 30-50 mots recommandé pour streetwear)

### Étape 2 — Lister les produits actifs
Via le connecteur Shopify ou l'API Admin Shopify :
```
Lis toutes mes fiches produits actives sur [boutique]. 
Ignore les produits archivés et hors stock.
```

### Étape 3 — Réécriture par batch
Pour chaque produit :
1. Titre : accrocheur, inclut le mot-clé principal, < 60 caractères
2. Description courte : 1 ligne impactante, voix de marque
3. Description longue : bénéfices, matières/caractéristiques, CTA implicite
4. Balises meta si disponibles

### Étape 4 — Validation avant mise à jour
Présente un aperçu des 3 premiers produits réécrits.
Attends validation d'Ivan AVANT d'appliquer les changements à la boutique.

### Étape 5 — Application
Après validation, applique les mises à jour via Shopify API ou connecteur.
Log les produits modifiés.

## Exemples

### TempleTwins — Ton attendu
Avant : "T-shirt noir coton 100% regular fit"
Après : "T-shirt oversize premium — coton lourd 280g, drop shoulders, coloris anthracite. Fait pour durer."

### PURESOLE — Ton attendu
Avant : "Baskets blanches taille 42"
Après : "Sneakers lifestyle blanches — confort quotidien, semelle souple, livraison 5-7j. Propre et polyvalent."

## References
- Shopify Admin API products endpoint: https://shopify.dev/docs/api/admin-rest/products
- Brand voice TempleTwins : premium streetwear français, références culture urbaine
- Brand voice PURESOLE : dropship lifestyle accessible, efficacité et valeur
