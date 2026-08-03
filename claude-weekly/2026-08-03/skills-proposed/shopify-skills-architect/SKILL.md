# Skill : shopify-skills-architect

> Généré automatiquement par veille-claude-weekly 2026-08-03  
> Source : Analyse vidéo jjWZSEIohjk "These 5 Claude Skills Run My Shopify Store"  
> **⚠️ À REVIEW manuellement par Ivan avant tout déploiement**

## Contexte & motivation

Inspiré par la vidéo YouTube montrant 5 SKILL.md pour automatiser une boutique Shopify. Ce skill permet de générer des SKILL.md Shopify sur-mesure à partir d'un brief.

## Description

Ce skill transforme Claude en **architecte de skills Shopify**. À partir d'un brief (type de store, objectifs, métriques clés), il génère un SKILL.md complet et opérationnel pour un cas d'usage Shopify spécifique.

## Déclenchement

Invoquer quand Ivan dit :
- "crée-moi un skill pour [tâche Shopify]"
- "génère un SKILL.md pour [objectif e-com]"
- "/shopify-skills-architect [brief]"

## Comportement attendu

1. **Brief collection** : demander store (TempleTwins ou PURESOLE), objectif (CRO / stock / clients / marketing), métriques clés
2. **Génération SKILL.md** : créer un SKILL.md avec rôle, contexte store, tâches, output format, exemples
3. **Preview** : afficher le SKILL.md généré pour review
4. **Sauvegarde optionnelle** : proposer de sauvegarder dans `.claude/skills/[nom-skill]/SKILL.md`

## Exemple de skills générables

- `shopify-vip-segmenter` : identifier et segmenter les clients VIP par comportement d'achat
- `shopify-stock-forecaster` : prévoir les stocks des 30 prochains jours selon les tendances
- `shopify-cro-agent` : analyser les pages produits et proposer des optimisations CRO
- `shopify-email-campaigner` : générer des campagnes email personnalisées par segment
- `shopify-competitor-monitor` : surveiller les prix / collections concurrents

## Output type

Fichier SKILL.md avec sections : Role, Context, Task, Output Format, Examples, Tools needed.

## Cas d'usage Ivan

- TempleTwins : skill pour brief collection streetwear basé sur les tendances Instagram
- PURESOLE : skill pour optimiser les listings dropshipping selon les saisons
- Les deux : skill pour répondre aux tickets SAV en français/anglais automatiquement
