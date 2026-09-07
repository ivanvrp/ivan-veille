# Skill : shopify-debug-master

> Proposé le 2026-09-07 — Source : Analyse Gemini #yeMhldEJLN4 (Fable 5.1 agents)
> **Statut : PROPOSITION — À reviewer par Ivan avant déploiement**

## Description

Diagnostique automatiquement les bugs complexes Shopify (Liquid, JavaScript, intégrations d'apps, appels API Admin) et génère des patchs de code actionnables.

Inspiré par le cas "Millennium crash" de Fable 5.1 : résolution d'un bug rare (1 sur un million) en désassemblant une librairie tierce + comparaison avec memory dump.

## Déclencheur

Ivan colle :
- Un log d'erreur Shopify
- Un extrait de code Liquid/JS problématique
- Une description de comportement inattendu sur son store

→ Claude diagnostique la cause profonde et propose un patch prêt à coller.

## Workflow

1. **Analyse du symptôme** : classifier l'erreur (Liquid, API, app tiers, JS frontend, webhook)
2. **Collecte contexte** : demander les informations manquantes (version theme, apps installées, logs complets)
3. **Diagnostic root cause** : identifier la ligne/fonction/config source du problème
4. **Patch generation** : générer le code corrigé avec explication en 1 ligne
5. **Test suggestion** : proposer comment tester le fix sans impacter les clients en production

## Exemples d'usage

```
/shopify-debug-master
[coller log d'erreur ou code Liquid]
```

```
Symptôme : les calculs de réduction s'appliquent 2× lors de l'utilisation d'un code promo avec un bundle app
[coller extrait du code de calcul]
```

## Dépendances suggérées

- MCP Shopify Admin (pour accéder aux logs en temps réel)
- Fable 5.1 recommandé pour les bugs complexes multi-fichiers

## Estimation valeur Ivan

⭐⭐⭐⭐⭐ — Un bug non résolu sur Shopify = ventes perdues. Ce skill économise des heures de debug.
