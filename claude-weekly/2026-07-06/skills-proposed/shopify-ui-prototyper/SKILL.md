# Skill : shopify-ui-prototyper

**Source vidéo :** x2pRavsHdls — Claude Code Just Killed Every Shopify Agency Ever  
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Description

Prend une description textuelle d'une section ou d'une page Shopify et génère un fichier HTML/CSS autonome et stylisé (avec des tokens de design configurables) pour une prévisualisation rapide et itérative du design, avant déploiement sur le thème réel.

## Déclencheur suggéré

```
/shopify-ui-prototyper {section_description} [--brand-colors] [--style]
```

## Cas d'usage Ivan

- TempleTwins : prototyper une nouvelle section hero pour une drop capsule
- PURESOLE : tester rapidement une landing page produit avant intégration Shopify
- Valider le design visuellement dans le navigateur avant de toucher au thème

## Pattern d'implémentation

```
Workflow (extrait vidéo) :
1. Décrire la section en langage naturel
2. Claude génère HTML/CSS standalone avec design tokens
3. Ouvrir dans le navigateur (live preview)
4. Itérer sur le HTML jusqu'à satisfaction
5. Convertir en Liquid Shopify avec le MCP shopify-dev
```

## Prérequis

- MCP shopify-dev configuré : `claude mcp add shopify-dev -- npx -y @shopify/dev-mcp@latest`
- Compte Shopify Partner (gratuit) pour les tests

## Insight clé

Approche : HTML-first avant Liquid. Réduit les allers-retours coûteux sur le thème réel.
