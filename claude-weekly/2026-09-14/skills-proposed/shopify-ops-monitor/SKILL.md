# Skill : shopify-ops-monitor
**Source :** Analyse vidéo zaDbZt40kRg (What Claude Code Can Do — NDC AI 2026)
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Objectif
Hook + `/loop` combiné pour surveiller les métriques Shopify (stock critique, CPA pub, commandes bloquées) et envoyer alertes ntfy en temps réel.

## Ce que fait le skill
1. `/loop` toutes les 30 min via tâche planifiée
2. Vérifie via MCP Shopify :
   - Stocks < seuil configuré
   - Commandes en erreur ou bloquées > 2h
   - CPA Facebook/Meta > seuil (via Meta Ads API MCP)
3. Si alerte détectée → push ntfy avec contexte + action recommandée
4. Log dans fichier ops-monitor.log

## Usage
```
/shopify-ops-monitor --store templetwins --alert-stock 3 --alert-cpa 25
/shopify-ops-monitor start  # Mode daemon continu
```

## Valeur pour Ivan
Monitoring automatique sans dashboard = libère temps mental. Alertes proactives = réaction rapide sur incidents stock ou pub hors budget.

## Notes implémentation
- Combine `/loop`, hooks settings.json et MCP Shopify
- Nécessite config ntfy token dans env vars
- Peut déclencher `/shopify-sales-summarizer` si anomalie détectée
