---
name: claude-md-generator
description: Génère automatiquement un CLAUDE.md de projet complet depuis une description rapide
triggers:
  - nouveau projet
  - initialiser projet
  - créer claude.md
  - setup projet
---

# CLAUDE.md Generator

## Usage
Décris ton projet en quelques phrases → ce skill génère un CLAUDE.md complet prêt à l'emploi.

## Instructions
1. Demande à Ivan : nom projet, stack tech, type (Shopify theme / dropship / autre), objectifs principaux
2. Génère ~/.claude/CLAUDE.md si global, ou ./CLAUDE.md si projet spécifique

## Template output
```markdown
# Projet : {nom}
## Identité
- Développeur : Ivan Vasseur, fondateur TempleTwins + PURESOLE
- Stack : {stack}
- Type : {type}

## Règles absolues
- Ne jamais committer les clés API
- Toujours vérifier les modifications Shopify sur staging d'abord
- Commit atomiques avec messages descriptifs

## Commandes clés
{commandes détectées}

## Architecture
{structure détectée/décrite}

## Préférences de communication
- Français par défaut
- Concis, action-first
- Code commenté seulement si WHY non évident
```
