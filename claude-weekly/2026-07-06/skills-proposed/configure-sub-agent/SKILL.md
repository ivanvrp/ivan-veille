# Skill : configure-sub-agent

**Source vidéo :** ICgTn1JMU9Y — How to Create Sub Agents in Claude Code (2026)  
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Description

Permet à Claude de guider l'utilisateur dans la création ou la modification d'un sous-agent spécialisé dans Claude Code. Ce skill prend en charge la définition de la description de l'agent, ses outils autorisés, son contexte initial et sa portée (projet vs global).

## Déclencheur suggéré

```
/configure-sub-agent {nom_agent} {role}
```

## Cas d'usage Ivan

- Créer un agent "shopify-theme-dev" dédié au code Liquid/CSS Shopify
- Créer un agent "dropship-research" pour la recherche produits PURESOLE
- Créer un agent "content-writer" pour les réseaux sociaux TempleTwins

## Pattern d'implémentation

```yaml
# .claude/agents/{nom_agent}.md
description: |
  Agent spécialisé {role}. Contexte : {description_projet}.
  Toujours utiliser {contraintes_spécifiques}.
tools:
  - {liste_outils_autorisés}
model: claude-sonnet-5  # ou haiku-4-5 pour tâches légères
```

## Valeur

Les subagents permettent de paralléliser le travail sur plusieurs tâches Shopify simultanément : pendant qu'un agent rédige des descriptions produit, un autre peut analyser les métriques, un troisième peut tester le code.
