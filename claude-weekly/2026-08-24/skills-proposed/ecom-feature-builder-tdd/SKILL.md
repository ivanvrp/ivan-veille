---
name: ecom-feature-builder-tdd
description: >
  Pattern Navigator/Driver TDD adapté aux features Shopify e-com : nouveau
  payment gateway, custom variant, custom shipping calculator, integration
  API PostNL/Colissimo. Handoffs via fichiers markdown pour traçabilité.
  Trigger : "implement new [feature] for e-commerce" ou
  `/ecom-feature-builder-tdd "…"`.
source: How to Use Multi-Agent Workflows in Claude Code — Skills, Subagents & Handoffs (YouTube qiDalcMeBFk)
status: DRAFT — nécessite subagent types custom dans .claude/agents/
---

# ecom-feature-builder-tdd — DRAFT

## Architecture (2 subagents + 1 skill orchestrateur)

### Subagent `navigator-ecom`
- PLAN → RED (écrit tests échoués)
- REVIEW (relit code du driver)
- N'ÉCRIT JAMAIS de code de prod
- Sait lire les schémas Shopify GraphQL, les webhooks, les rate limits

### Subagent `driver-ecom`
- GREEN (fait passer les tests)
- REFACTOR
- N'ÉCRIT JAMAIS de tests
- Sait utiliser `@shopify/dev-mcp` pour valider chaque query avant exécution

### Skill orchestrateur (celui-ci)
Trigger keywords : "implement", "build", "create", "pair program", "tdd",
"shopify feature", "checkout extension".

## Handoff files
- `.claude/handoff/requirements.md` (input Ivan)
- `.claude/handoff/navigator.md` (plan + tests)
- `.claude/handoff/driver.md` (code + résultats tests)
- `.claude/handoff/review.md` (feedback navigator)

## Prompt template (verbatim, adapté du talk)
```
MODE: PLAN
TASK: Analyze requirements.md and design an implementation + test strategy
FILES: requirements.md, .claude/shopify-schema.graphql
DONE_WHEN: Strategy saved to .claude/handoff/navigator.md

MODE: RED
TASK: Write failing tests using shopify-dev-mcp validation
FILES: .claude/handoff/navigator.md
TESTS: npm test
DONE_WHEN: Test fails with expected error

MODE: GREEN
TASK: Implement minimum code to pass tests
FILES: .claude/handoff/navigator.md
TESTS: npm test
DONE_WHEN: All tests pass

MODE: REVIEW
TASK: Read driver output, check spec compliance + security
FILES: .claude/handoff/driver.md, .claude/handoff/navigator.md
DONE_WHEN: review.md written, APPROVED or CHANGES_REQUESTED
```

## Anti-pattern
NE JAMAIS déployer sans passer `MODE: REVIEW` — un checkout cassé = perte
sèche de CA immédiate.
