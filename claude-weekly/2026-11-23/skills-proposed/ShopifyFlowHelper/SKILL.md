# Skill: ShopifyFlowHelper

**Source** : Lydia Hallie – Rethinking Claude Code Best Practices (Anthropic, Nov 11 2026)  
**Vidéo** : https://www.youtube.com/watch?v=vlfCjWuv4es  
**Statut** : Proposé — À valider par Ivan avant déploiement

## Description
Prend un objectif métier Shopify (ex: "Ajouter une option de pré-commande", "Intégrer un nouveau mode de livraison") et génère une structure de session orchestrée avec des sous-tâches, des hooks de vérification et des points de contrôle qualité.

## Cas d'usage pour Ivan
- Déployer une nouvelle fonctionnalité sur TempleTwins ou PURESOLE sans casser l'existant
- Orchestrer des sessions Claude longues (migration thème, refacto catalogue)
- Hooks automatiques : vérif rendu thème, tests E2E staging Shopify

## Pattern core
```
Objectif : {description_objectif_shopify}

Sous-tâches :
1. Analyse de l'existant (lecture fichiers thème/app)
2. Implémentation (éditions ciblées)
3. Vérification hooks : linting + tests staging
4. Rapport final

Critères de succès : {done_when}
```

## Instructions skill (ébauche)
1. Recevoir l'objectif métier en entrée
2. Décomposer en sous-tâches atomiques avec critères de succès
3. Définir les hooks de vérification (exit 1 = ok, exit 2 = retry)
4. Générer le prompt de session orchestrateur
