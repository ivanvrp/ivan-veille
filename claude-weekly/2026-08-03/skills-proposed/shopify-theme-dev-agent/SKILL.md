# Skill : shopify-theme-dev-agent

> Généré automatiquement par veille-claude-weekly 2026-08-03  
> Source : Analyse vidéo PmNiSEAQVcc "Claude Code Opus 5 = Insane Website Workflow"  
> **⚠️ À REVIEW manuellement par Ivan avant tout déploiement**

## Contexte & motivation

Inspiré par la vidéo montrant Claude Code + Opus 5 pour des workflows de développement web complets. Adapté aux thèmes Liquid Shopify de Ivan (TempleTwins + PURESOLE).

## Description

Ce skill transforme Claude Code en **agent de développement thème Shopify**. Il scanne le thème actif, comprend la structure, applique des modifications ciblées en Liquid/JS/CSS, et propose un diff avant commit.

## Déclenchement

Invoquer quand Ivan dit :
- "modifie mon thème pour [fonctionnalité]"
- "ajoute [feature] à la page produit"
- "/shopify-theme-dev [description changement]"

## Comportement attendu

1. **Scan thème** : lire la structure du thème Shopify (sections, snippets, templates)
2. **Plan de modification** : proposer les fichiers à modifier et la logique
3. **Implémentation** : écrire le code Liquid / CSS / JS
4. **Diff review** : afficher les changements avant application
5. **Commit** : si approuvé, committer avec message descriptif

## Capacités

- Modifier sections Liquid (product, collection, cart)
- Ajouter des snippets réutilisables
- Optimiser la performance (lazyload images, CSS critique)
- Créer des landing pages pour campagnes spécifiques
- Ajouter des metafields et logique conditionnelle

## Prérequis

- Thème Shopify synchronisé localement via Shopify CLI
- Accès MCP Shopify ou Git du thème

## Cas d'usage Ivan

- TempleTwins : ajouter un bandeau "édition limitée" sur les pages produits streetwear
- PURESOLE : modifier le template collection pour afficher le délai de livraison dropshipping
- Les deux : ajouter un popup email capture avec offre de bienvenue
- Landing page campagne : créer rapidement une LP spécifique pour une promo Meta Ads
