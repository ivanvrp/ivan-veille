---
name: shopify-product-manager
description: Pipeline complet de création/mise à jour produits Shopify via prompt ou fichier CSV/JSON. Valide, génère SEO, crée via Admin API, synchronise inventaire fournisseur dropship.
trigger: /shopify-product-manager
version: 0.1-proposed
source: claude-weekly-2026-08-10 (Gemini analysis freeCodeCamp course)
status: PROPOSED — à valider par Ivan avant déploiement
---

# Skill : Shopify Product Manager Automatisé

## Déclencheur
`/shopify-product-manager` suivi du chemin vers un fichier JSON/CSV ou un brief produit inline.

## Ce que fait le skill

À partir d'un fichier de données produit (JSON ou CSV) ou d'un brief textuel, ce skill :

1. **Valide** les données d'entrée (champs obligatoires : nom, prix, catégorie)
2. **Génère** une description SEO-friendly + méta-balises si absentes
3. **Crée ou met à jour** le produit sur Shopify via l'API Admin (MCP Shopify AI Toolkit)
4. **Associe les images** (URLs CDN ou uploads)
5. **Synchronise l'inventaire** avec l'API fournisseur dropship si ID fournisseur fourni
6. **Commit GitHub** si des changements de thème sont inclus

## Format d'entrée exemple

```json
{
  "name": "Cosmic Dream Tee",
  "price": 49.90,
  "variants": ["S", "M", "L", "XL"],
  "images": ["https://cdn.x.com/img/cosmic-dream.jpg"],
  "collections": ["Nouveautés", "Streetwear"],
  "tags": ["streetwear", "limited", "coton-bio"],
  "supplier_id": "SUPPLIER_001",
  "seo_keywords": ["t-shirt streetwear", "cosmic dream", "coton bio"]
}
```

## Pré-requis

- Shopify AI Toolkit MCP installé : `/plugin marketplace add Shopify/shopify-ai-toolkit`
- SHOPIFY_ADMIN_TOKEN configuré dans les variables d'environnement Claude Code
- (Optionnel) API fournisseur configurée pour sync inventaire

## Notes Ivan

Ce skill est particulièrement utile pour :
- **TempleTwins** : création de fiches streetwear avec tone-of-voice cohérent
- **PURESOLE** : import en masse depuis catalogues fournisseurs dropship

**À personnaliser** : ajouter les templates SEO spécifiques à chaque marque (TempleTwins vs PURESOLE ont des univers différents).
