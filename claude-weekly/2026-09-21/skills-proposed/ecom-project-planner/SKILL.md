---
name: ecom-project-planner
description: Transforme un objectif e-commerce en plan d'action multi-agents parallèles (marketing + dev + contenu + data)
trigger: "lancer collection" OR "plan projet ecom" OR "décompose cet objectif" OR "planifie ce projet"
---

# E-commerce Project Planner (Multi-agent)

## Ce que fait ce skill

Prend un objectif e-commerce ambitieux (ex: "Lancer la collection Hiver TempleTwins") et le décompose en tâches parallèles assignables à plusieurs agents Claude, avec des dépendances, un calendrier et des critères de succès.

## Workflow

1. Analyse l'objectif et identifie les 4 dimensions : Marketing, Contenu, Technique, Data
2. Pour chaque dimension : liste les tâches, durée estimée, dépendances
3. Génère un brief par thread/agent avec contexte de marque partagé
4. Crée un fichier ROADMAP.md prêt à commit dans le repo du projet

## Prompt de déclenchement

```
Je suis solo founder d'une marque streetwear (TempleTwins) sur Shopify.
Objectif : [DÉCRIRE L'OBJECTIF EN 1 PHRASE]
Délai : [DATE OU DURÉE]
Ressources : Claude Code, Shopify Admin, Canva/Higgsfield pour visuels

Décompose cet objectif en threads parallèles :
- Thread Marketing : campagnes, emails, social
- Thread Contenu : fiches produit, blog, visuels
- Thread Technique : développement Shopify, intégrations
- Thread Data : analytics, reporting, A/B tests

Pour chaque thread : liste les tâches, ordre, durée, dépendances inter-threads.
Format: ROADMAP.md prêt à commit.
```

## Use-case Ivan

- Lancement collection capsule TempleTwins (streetwear)
- Onboarding nouveaux fournisseurs PURESOLE (dropship)
- Optimisation pré-Black Friday des deux boutiques en parallèle

## Source

Extrait de l'analyse Gemini du 2026-09-21 — vidéo Nhmyrh9I_bA "Claude Code Projects : NEW Claude Code Update is WILD"
Méthodologie "AI Employee Map" — vidéo SkY-tR9kf-k

## ⚠️ À valider par Ivan avant déploiement
