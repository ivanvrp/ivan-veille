# Skill : shopify-seo-product-description

**Source vidéo :** zaDbZt40kRg — Gui Ferreira NDC AI 2026  
**Score source :** 9/10  
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Description

Génère et optimise des descriptions de produits pour Shopify ou d'autres plateformes de dropshipping, en intégrant des mots-clés SEO pertinents et un ton de marque défini.

## Déclencheur suggéré

```
/product_description {produit_id} {mots_cles}
```

## Cas d'usage Ivan

- TempleTwins : générer des descriptions streetwear percutantes avec keywords SEO mode
- PURESOLE : descriptions dropship rapides, multi-produits, ton cohérent

## Pattern d'implémentation

```
Rôle : Tu es un expert SEO e-commerce spécialisé en streetwear/mode.
Entrée : nom du produit, catégorie, 3-5 mots-clés cibles, ton de marque (ex: "urbain, direct, authentique")
Sortie :
  - Titre SEO Shopify (60 chars max)
  - Description courte (150 chars, balise meta)
  - Description longue (300-500 mots, H2/H3, bullets)
  - Tags suggérés
  - Score SEO estimé 0-100
```

## Référence

Pattern extrait de : "La présentation (Gui Ferreira) — Skills = capacités réutilisables, pas juste des prompts. Dossier `.claude/skills` avec scripts, références, templates. Le skill encapsule la logique d'orchestration + les contraintes métier."
