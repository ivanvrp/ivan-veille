# Skill proposé : shopify-product-loop

**Source** : Analyse vidéo Matthew Berman "How an amateur learned to loop" (https://www.youtube.com/watch?v=1iIOGpJXSgQ)
**Statut** : À REVIEW par Ivan (jamais déployé auto)
**Priorité estimée** : Haute (PURESOLE + TempleTwins)

---

## Problème résolu

Générer ou optimiser un grand nombre de descriptions/métadonnées produits Shopify (ex: 50-500 produits) sans que Claude perde en qualité sur la durée. Les long runs dégradent les modèles ("dumb zone") — le pattern loop les évite.

## Ce que fait ce skill

Lance une boucle Claude Code sur le catalogue Shopify :
1. Récupère les produits sans description ou avec description courte (< 100 mots) via MCP Shopify
2. Les traite par **batch de 5-10** produits par session
3. Génère descriptions + balises SEO + bullet points pour chaque produit
4. Checkpoint qualité après chaque batch (longueur, keywords, cohérence de marque)
5. Met à jour les produits via MCP Shopify automatiquement
6. Reprend au produit suivant (loop) jusqu'à épuisement du catalogue

## Usage type

```
/shopify-product-loop
Génère des descriptions pour tous les produits PURESOLE sans description.
Style : casual sneaker, ton direct, SEO orienté "limited drops".
Batch de 10, checkpoint après chaque batch.
```

## Prérequis

- MCP Shopify configuré (Shopify AI Toolkit)
- CLAUDE.md avec contexte marque (TempleTwins ou PURESOLE)
- Accès liste produits via MCP

## Implémentation suggérée

```markdown
<!-- .claude/skills/shopify-product-loop/SKILL.md -->
Ce skill génère ou optimise les descriptions produits Shopify en boucle par batch.

Étapes :
1. Appelle mcp__Shopify__search_products pour lister les produits cibles
2. Pour chaque batch de 10 produits :
   a. Génère description + SEO + bullet points (style marque du CLAUDE.md)
   b. Vérifie : > 80 mots, inclut au moins 2 keywords, ton cohérent
   c. Met à jour via mcp__Shopify__update-product
   d. Log le batch complété
3. Continue au batch suivant
4. Rapport final : N produits traités, N erreurs
```

## Estimation de valeur

- TempleTwins : ~200 produits SKUs dropship → 2h de travail manuel → 15min avec le skill
- PURESOLE : catalogue en croissance → utile à chaque ajout massif
- ROI estimé : 15-20h économisées / mois
