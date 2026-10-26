# shopify-seo-optimizer

> Skill proposé le 2026-10-26 — à valider manuellement par Ivan avant déploiement.
> Source: analyse Gemini vidéo "Every New Claude Code Feature Explained! (2026)" — youtube.com/watch?v=sJVxwwaF0sU

## Description

Analyse une ou plusieurs pages produit Shopify et génère des optimisations SEO concrètes : title tag, meta description, balises alt, mots-clés dans la description, structure heading.

## Usage

```
/seo-check [url_produit OU coller_description_produit]
```

## Ce que ça fait

1. Analyse le titre produit, description, balises existantes
2. Identifie les mots-clés manquants à fort volume (streetwear, sneakers, etc.)
3. Rédige un title tag optimisé (≤60 chars)
4. Rédige une meta description optimisée (≤155 chars)
5. Propose 3 variantes de description produit SEO-friendly
6. Checklist des balises alt pour les images

## Exemple de sortie

```
Produit : "Hoodie Temple Classic"
Title actuel : "Hoodie Temple" (12 chars — trop court)
→ Nouveau title : "Hoodie Streetwear Temple Classic | TempleTwins" (46 chars ✅)
Meta description → "Hoodie oversized collection Temple Classic. Coton premium, coupe streetwear. Livraison France 24h. Découvrez la collection TempleTwins."
Mots-clés suggérés à intégrer : hoodie oversized, streetwear français, hoodie coton premium
```

## Pertinence Ivan

Fort — le SEO organique sur Shopify est souvent négligé par les fondateurs solo. Un audit rapide par produit peut générer du trafic gratuit sur TempleTwins et PURESOLE sans budget pub supplémentaire.
