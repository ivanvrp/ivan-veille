# advisor-executor-shopify

Skill Claude Code pour orchestrer des tâches e-commerce complexes avec la stratégie Advisor/Executor vue au Code with Claude 2026 SF.

## Contexte

Présenté à Code with Claude 2026 (Anthropic, SF) : pattern où un agent rapide (Executor = Sonnet) exécute les tâches courantes, et un agent puissant (Advisor = Opus) supervise et valide les décisions à fort impact. Résultat : coût réduit, qualité préservée.

## Usage pour Ivan

```
/advisor-executor-shopify task="Optimiser les prix dropshipping PURESOLE pour la rentrée"
```

Le skill lance :
1. Executor (Sonnet) → analyse les données produits, génère des propositions de prix
2. Advisor (Opus) → valide la cohérence marges/positionnement, signale les risques
3. Résultat consolidé présenté à Ivan avec décision recommandée

## Cas d'usage typiques

- Repricing saisonnier (rentrée, Black Friday, Noël)
- Sélection des nouveaux produits dropship à ajouter
- Décisions de stock : quand réapprovisionner / quoi arrêter
- Arbitrage budgets pub : quelle campagne scale vs. pause

## Configuration agent.md

```yaml
model: claude-sonnet-5
subagentModel: claude-opus-5
description: Executor tasks, Advisor validates high-stakes decisions
```

## Pattern verbatim (source: Code with Claude 2026 SF)

```
Executor: fast iteration, broad search, draft outputs
Advisor: spot-checks quality, flags edge cases, approves final decision
```

## Skill_source

Code with Claude 2026 SF Keynote — Timestamp 22:18 (Katelyn Lesse, Angela Jiang)
YouTube: https://www.youtube.com/watch?v=GMIWm5y90xA

## Statut

Proposé — à reviewer manuellement par Ivan avant déploiement.
