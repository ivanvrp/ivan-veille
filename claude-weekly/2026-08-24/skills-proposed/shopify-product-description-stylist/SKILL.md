---
name: shopify-product-description-stylist
description: >
  Génère descriptions produit Shopify SEO-optimisées avec ton streetwear
  distinctif (TempleTwins) ou dropship pragmatique (PURESOLE). Prend en input
  nom produit + specs + mots-clés cibles. Sortie : 3 variantes copy + 3
  titres SEO + bullet points + JSON-LD Product ready.
  Trigger : `/shopify-product-description-stylist "product name"` ou "génère description produit".
source: I Scraped 85,000 Claude Skills (YouTube 1GgyJfCK608) + Anthropic Skill Creator pattern
status: DRAFT — nécessite tone guides `.claude/brand/templetwins.md` et `puresole.md`
---

# shopify-product-description-stylist — DRAFT

## Input attendu
- Nom du produit (ex: "Oversized Skull Hoodie Black")
- Caractéristiques (matière, poids, coupe, care, sizing range)
- Mots-clés cibles SEO (ex: "streetwear paris", "hoodie oversize noir")
- Marque : TempleTwins | PURESOLE (détermine le tone guide)
- Optionnel : URL image produit → analyse visuelle Vision API

## Références externes
- `.claude/brand/templetwins.md` — ton "urban chic, mystique, français avec touches EN"
- `.claude/brand/puresole.md` — ton "pragmatique, valeur-first, dropship-honnête"
- `.claude/seo/shopify-metafields.md` — schéma metafields TempleTwins actuels

## Sortie
1. **3 descriptions** (short 50 mots, medium 120 mots, long 250 mots avec
   H2/H3, une par intent SEO)
2. **3 titres accrocheurs** (< 60 chars pour SERP)
3. **Bullet points** (4-6, format "material + benefit + emotion")
4. **JSON-LD Product** prêt à coller dans le theme
5. **Meta description** (< 155 chars)
6. **Alt-text** suggéré pour image principale

## Anti-pattern
- Interdit : "élevé au grain", "premium quality", "made with love" → AI slop
- Interdit : mots-clés stuffing (max 2 occurrences du keyword principal)
- Interdit : mentir sur origine si dropship (PURESOLE)
