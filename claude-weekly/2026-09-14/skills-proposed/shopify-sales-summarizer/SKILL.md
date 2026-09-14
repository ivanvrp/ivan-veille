# Skill : shopify-sales-summarizer
**Source :** Analyse vidéo Jxu4EOA4QKE (GOING DEEPER with CLAUDE)
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Objectif
Connexion à l'API Shopify via MCP → génération automatique d'un résumé quotidien/hebdomadaire des ventes TempleTwins et PURESOLE.

## Ce que fait le skill
1. Se connecte au MCP Shopify configuré
2. Récupère les commandes sur la période (jour/semaine)
3. Génère un rapport structuré :
   - Top produits vendus
   - CA total + comparatif période précédente
   - Stocks critiques (<5 unités)
   - Anomalies (pic de retours, commandes bloquées)
4. Envoie résumé via ntfy (optionnel)

## Prérequis
- Serveur MCP Shopify configuré (`claude mcp add shopify ...`)
- Token API Shopify en variable d'environnement

## Usage
```
/shopify-sales-summarizer
/shopify-sales-summarizer --period week --store puresole
```

## Valeur pour Ivan
Remplace la vérification manuelle du dashboard Shopify → 30 min/jour économisées.
Idéal en tâche planifiée (chaque matin à 8h).

## Notes implémentation
- Nécessite MCP Shopify Server (https://github.com/Shopify/dev-mcp ou custom)
- Modèle recommandé : Sonnet (coût/efficacité)
- Ajouter à `.claude/skills/` du repo store
