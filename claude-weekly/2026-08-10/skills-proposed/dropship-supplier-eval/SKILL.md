---
name: dropship-supplier-eval
description: Évalue un fournisseur dropship selon 8 critères (délais, MOQ, retours, catalogue, intégration Shopify, réputation, pricing, support). Output = fiche décision structurée.
trigger: /eval-supplier
version: 0.1-proposed
source: claude-weekly-2026-08-10 (pattern cross-sources MCP + web research)
status: PROPOSED — à valider par Ivan avant déploiement
---

# Skill : Dropship Supplier Evaluator

## Déclencheur
`/eval-supplier [nom du fournisseur ou URL]`

## Ce que fait le skill

Recherche et synthétise les informations disponibles sur un fournisseur dropship pour aider Ivan à décider rapidement si un fournisseur vaut la peine d'être intégré à PURESOLE ou TempleTwins.

## Critères d'évaluation (8 axes)

| Critère | Description | Poids |
|---------|-------------|-------|
| Délais de livraison | Moyen EU/FR, tracking disponible ? | 20% |
| MOQ | Minimum order quantity, flexible ? | 10% |
| Politique retours | Délai, frais, processus | 15% |
| Catalogue | Largeur, exclusivité, tendances | 15% |
| Intégration Shopify | Plugin dédié, API, CSV auto | 20% |
| Réputation | Avis marchands, ancienneté | 10% |
| Pricing & marges | Marges réalistes pour e-com | 5% |
| Support | FR/EN, réactivité, account manager | 5% |

## Output format

```markdown
## Fournisseur : [NOM]
**URL** : [URL]
**Évaluation globale** : [score /10]

### ✅ Points forts
- ...

### ⚠️ Points faibles  
- ...

### 🔗 Intégration Shopify
[Plugin / API / Méthode]

### 💰 Estimation marge
[Fourchette %]

### 🏁 Verdict
[ ] À intégrer immédiatement
[ ] À tester (1 commande test)
[ ] À éviter — raison : ...

### Sources consultées
- ...
```

## Pré-requis

- Accès web (WebSearch / WebFetch)
- (Optionnel) MCP Shopify pour vérifier compatibilité plugins

## Notes Ivan

Utile avant de signer avec un nouveau fournisseur PURESOLE. Lance le skill en passant juste le nom du fournisseur, il fait la recherche tout seul.
