---
name: dropship-product-analyzer
description: >
  Analyse un produit dropship candidat pour PURESOLE : viabilité marge,
  concurrence, saturation, niche potentielle. Prend URL AliExpress / CJ /
  supplier + URL 3 concurrents. Sortie : go/no-go + marge estimée + angle
  marketing suggéré. Trigger : `/dropship-product-analyzer "url"` ou
  "analyse ce produit dropship".
source: I Scraped 85,000 Claude Skills (YouTube 1GgyJfCK608)
status: DRAFT — nécessite skill Playwright installé + MCP shopify pour benchmark prix
---

# dropship-product-analyzer — DRAFT

## Input
- URL produit fournisseur (AliExpress / CJ / Zendrop / Doba)
- URL 3 concurrents Shopify (ou top-3 Amazon)
- Marché cible (FR par défaut)

## Étapes
1. **Scrape fournisseur** (Playwright) : prix, MOQ, temps de livraison, review count, note
2. **Scrape concurrents** : prix vente, positioning, uniques selling points, review count
3. **Calcul marge estimée** :
   - Coût produit + shipping air / sea
   - Coût ads estimé (CPA moyen niche → règle 25% CPA/AOV)
   - Marge nette prévisionnelle
4. **Score de saturation** : nb de listings Amazon FR + nb pubs Facebook Ad Library (top 5)
5. **Angle marketing suggéré** : problème résolu, hook créatif, cible démographique
6. **Verdict** : GO / TEST / SKIP + raison en 1 phrase

## Sortie template
```markdown
# {Product name} — {GO|TEST|SKIP}

- Coût all-in : {X}€
- Prix vente cible : {Y}€
- Marge nette estimée : {Z}€ ({%})
- Saturation : {LOW|MID|HIGH} ({N} concurrents actifs)
- Angle : {1-liner}
- Risque principal : {liste courte}
```

## Anti-pattern
- Ne JAMAIS scorer GO si marge nette < 30%
- Ne JAMAIS scorer GO si delivery > 20j (retour taux explose)
- Ne JAMAIS scorer GO si review fournisseur < 4.5/5 ou < 500 reviews
