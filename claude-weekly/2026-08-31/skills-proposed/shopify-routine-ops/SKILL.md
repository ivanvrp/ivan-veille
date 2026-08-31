# shopify-routine-ops

Skill Claude Code pour déclencher des routines automatiques de gestion opérationnelle Shopify (stock, alertes, reporting) — pattern "Routines" présenté à Code with Claude 2026.

## Contexte

Claude Code 2026 "Routines" = agents cloud déclenchés par événement (webhook, schedule, GitHub issue). Appliqué à Shopify : surveillance stock, alertes commandes, génération de reports hebdo — sans intervention manuelle d'Ivan.

## Usage

```
/shopify-routine-ops setup
```

Configure les routines interactives :
1. **Alerte stock bas** : vérifie ≤ X unités → Slack + commande préparée
2. **Report hebdo** : chaque lundi 8h → résumé ventes, best-sellers, CA, marge nette
3. **Alerte abandon panier** : >N abandons en 24h → email séquence auto
4. **Nouveau produit dropship** : vérifie fournisseur toutes les 24h → alerte si nouveau SKU

## Patterns réutilisables

```text
Routine template pour Shopify :
trigger: schedule "0 8 * * 1"  # Lundi 8h
action: 
  - fetch Shopify orders API (semaine passée)
  - calcul CA, marge, top 5 produits
  - format rapport markdown
  - send to Slack/email
```

## Prérequis

- MCP Shopify Admin (ou API key dans env vars)
- MCP Slack ou email pour notifications
- Claude Code v2.1.233+ pour `Routines`

## Cas d'usage Ivan (TempleTwins + PURESOLE)

- TempleTwins : alerte quand un coloris/taille < 5 unités → relance prod
- PURESOLE : quand marge brute < 25% → proposition ajustement prix fournisseur
- Commun : report chaque lundi avant standup solo

## Skill_source

Code with Claude 2026 SF Keynote — Timestamp 37:00 (Boris Cherny)
YouTube: https://www.youtube.com/watch?v=GMIWm5y90xA

## Statut

Proposé — à reviewer manuellement par Ivan avant déploiement.
