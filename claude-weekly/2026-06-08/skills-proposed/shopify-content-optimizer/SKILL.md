---
name: shopify-content-optimizer
trigger: /shopify-content [product_id] [brand]
source_video: GMIWm5y90xA (Code with Claude SF 2026) + 0WDkwMxj13s (AI OS Nate Herk)
score_ivan: 9/10
status: PROPOSED — à reviewer manuellement avant déploiement
---

# Skill : Shopify Content Optimizer

## Objectif

Génère titres, descriptions et tags Shopify optimisés SEO pour un produit TempleTwins ou PURESOLE, en respectant la voix de marque et les guidelines de chaque store.

## Usage

```
/shopify-content [product_id_ou_nom] [marque: TempleTwins|PURESOLE]
```

**Exemple :**
```
/shopify-content SKU-TT-042 TempleTwins
```

## Ce que fait le skill

1. Lit les données produit depuis le contexte ou un fichier local (caractéristiques, matériaux, prix, variantes)
2. Charge le guide de style de la marque depuis `CLAUDE.md` ou `brands/[marque]/voice-guide.md`
3. Génère :
   - **Titre** : max 70 chars, keyword-first, sans majuscule abusive
   - **Description** : 150-200 mots, storytelling + specs techniques, 2-3 mots-clés naturels
   - **Tags** : 8-12 tags Shopify (collections, matériaux, usage, style)
   - **Meta description** : 155 chars max pour SEO
4. Propose 2 variantes (courte et longue) pour A/B test

## Fichiers requis

- `brands/TempleTwins/voice-guide.md` — style streetwear, ton de marque
- `brands/PURESOLE/voice-guide.md` — style dropship, ton commercial
- `products/[product_id].json` ou feuille Google Sheets connectée

## Patterns clés (tiré de l'analyse)

- Utiliser le contexte comme "carburant unique" — ne pas générer générique
- "Treat tokens like money" : fournir le signal (specs produit), pas le bruit
- Reverse-engineer le workflow manuel existant d'Ivan pour créer ce skill

## À faire avant déploiement

- [ ] Créer `brands/TempleTwins/voice-guide.md` avec exemples copy existants
- [ ] Créer `brands/PURESOLE/voice-guide.md`
- [ ] Tester sur 3 produits existants, comparer avec copy actuel
- [ ] Valider SEO avec Semrush / Ubersuggest
