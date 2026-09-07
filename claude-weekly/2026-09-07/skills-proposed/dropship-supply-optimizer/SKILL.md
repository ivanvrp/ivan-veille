# Skill : dropship-supply-optimizer

> Proposé le 2026-09-07 — Source : Analyse Gemini #yeMhldEJLN4 (Fable 5.1 agents)
> **Statut : PROPOSITION — À reviewer par Ivan avant déploiement**

## Description

Optimise les flux de supply chain dropshipping pour PURESOLE : sélection fournisseurs, itinéraires d'expédition, anticipation des retards et recommandations coût/délai.

## Déclencheur

Ivan donne une liste de SKUs à commander → le skill analyse les options et recommande la config optimale.

```
/supply-optimize
SKUs: [liste de produits]
Délai max client: [X jours]
Budget expédition: [X€ par commande]
```

## Workflow

1. **Input parsing** : liste SKUs + contraintes délai/budget
2. **Fournisseur matching** : croiser les SKUs avec les fournisseurs connus, availability, prix
3. **Route optimization** : calculer délais d'expédition par route (aliexpress standard vs ePacket vs fournisseur EU)
4. **Risk assessment** : signaler les fournisseurs avec historique de retards ou ruptures récentes
5. **Recommandation** : config optimale + alternative si fournisseur principal indisponible

## Output format

```markdown
## Plan d'approvisionnement — [Date]

### Config recommandée
- Fournisseur A → SKUs [X, Y, Z] → délai [N jours] → coût [X€]
- Fournisseur B → SKUs [A, B] → délai [N jours] → coût [X€]

### Alertes
- ⚠️ Fournisseur C : délais +5j signalés cette semaine
- ⚠️ SKU #123 : stock faible, commander avant [date]

### Alternative si rupture
- [Plan B]
```

## Dépendances suggérées

- Accès aux données fournisseurs PURESOLE (à configurer dans CLAUDE.md)
- MCP éventuel pour intégration AliExpress / CJDropshipping si disponible

## Estimation valeur Ivan

⭐⭐⭐⭐ — Le goulot d'étranglement #1 en dropshipping = la supply chain. Ce skill anticipe les retards avant qu'ils impactent les clients.
