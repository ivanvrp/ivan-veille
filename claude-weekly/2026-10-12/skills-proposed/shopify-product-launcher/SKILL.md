# Skill: shopify-product-launcher

> **STATUS: PROPOSÉ — Review manuel Ivan requis avant déploiement**
> Source: Analyse Gemini vidéo YpMaB2S2xcs (Build a Shopify Store With AI)
> Date proposition: 2026-10-12

## Description

Skill pour lancer rapidement des produits sur Shopify à partir d'un fichier CSV ou d'une description vocale/texte. Génère descriptions SEO, gère variantes, images et stocks.

## Use case Ivan

- TempleTwins : lancer une nouvelle drop streetwear depuis une feuille Excel
- PURESOLE : importer un catalogue fournisseur dropship en masse
- Gain estimé : 2-4h → 15min par lancement produit

## Déclenchement

```
/shopify-product-launcher
```

Ou : `Utilise le skill shopify-product-launcher pour créer ces produits`

## Instructions

Tu es un assistant spécialisé dans la gestion de catalogue Shopify. Quand on t'invoque :

1. **Analyse l'input** : CSV fourni en argument, ou demande les détails si absent
   - Champs requis : titre, description_courte, prix, variantes (taille/couleur), stock_initial
   - Champs optionnels : tags, images_url, collection, weight, sku

2. **Génère les descriptions** : Pour chaque produit, enrichis la description_courte en une description produit SEO (150-300 mots) adaptée au style de la marque (streetwear ou dropship selon contexte).

3. **Prépare le payload Shopify** : Utilise l'API Shopify Admin GraphQL (ou le connecteur Shopify si disponible) pour créer chaque produit en statut DRAFT.

4. **Vérification** : Après création, liste les produits créés avec leurs URLs d'administration.

5. **Rapport final** :
   ```
   PRODUITS CRÉÉS: N
   ERREURS: N
   URLS: [liste]
   TEMPS TOTAL: Xs
   ```

## Commandes MCP requises

- Connecteur Shopify Claude (ou MCP server shopify-admin)
- Permissions : products.write, collections.read

## Exemple d'usage

```
/shopify-product-launcher --file=new_collection_automne.csv --brand=templetins --status=draft
```

## Notes

- Créer toujours en DRAFT pour review avant publication
- Respecter le rate limit Shopify (2 req/s max)
- Sauvegarder le rapport dans `launches/YYYY-MM-DD-rapport.md`
