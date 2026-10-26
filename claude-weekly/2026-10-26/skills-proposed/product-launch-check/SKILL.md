# product-launch-check

> Skill proposé le 2026-10-26 — à valider manuellement par Ivan avant déploiement.
> Source: analyse Gemini vidéo "Claude Skills Tutorial (2026)" — youtube.com/watch?v=O_z9vDLgvoY

## Description

Vérifie un nouveau produit Shopify (TempleTwins ou PURESOLE) avant sa mise en ligne : description, SEO, prix, cohérence de marque. Signale les omissions et propose des corrections.

## Usage

```
/launch-check [nom_produit]
```

Fournir en entrée : texte de description, balises SEO, prix, variantes.

## Ce que ça fait

1. Analyse la description produit contre les guidelines de marque
2. Vérifie les balises title/description SEO (longueur, mots-clés)
3. Contrôle la cohérence des prix avec la gamme existante
4. Signale les champs manquants (images, poids, SKU)
5. Retourne une checklist Go/No-Go avec suggestions

## Exemple de sortie

```
✅ Description : OK (longueur 120 mots, ton streetwear respecté)
⚠️  SEO title : trop long (68 chars > 60 chars max) → suggère [...]
❌ Prix manquant pour variante "Taille XL"
✅ Images : 3 photos trouvées
```

## Pertinence Ivan

Fort — évite les erreurs au lancement (prix manquant, mauvais SEO) qui coûtent des ventes et du trafic organique. Utile sur TempleTwins et PURESOLE.
