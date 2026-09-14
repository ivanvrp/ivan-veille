# GOING DEEPER with CLAUDE — Skills, MCP, Scheduled Tasks & CLAUDE CODE
**URL:** https://www.youtube.com/watch?v=Jxu4EOA4QKE
**Date:** Jun 19, 2026
**Score Ivan:** 9/10

## Résumé exécutif
Vidéo présentant les skills Claude comme packs d'instructions réutilisables, le protocole MCP pour connecter Claude à des outils externes, et les meilleures pratiques pour Claude Code. Très orientée pratique avec exemples concrets et démonstrations de création de skill.

## Concepts clés avec timestamps
- [00:05] Skills : packs d'instructions réutilisables, stored dans dossier projet ou compte global
- [00:30] Fonctionnement : fichiers + guides étape-par-étape, chargés uniquement si nécessaire
- [01:17] Menu Customize : accès Skills et Connectors depuis sidebar gauche
- [02:20] Skills Directory : bibliothèque pré-validée Anthropic & Partners
- [03:30] Deux modes : implicite (Claude choisit) vs explicite (/nom-skill)
- [04:02] Exemple création skill "Explain Like I'm 5" via /skill-creator
- [05:20] Sauvegarde skill : bouton "Save skill" dans panneau prévisualisation
- [06:33] MCP : standard ouvert créé Anthropic (adopté OpenAI, Google) = "USB-C pour l'IA"
- [07:07] Applications MCP : Gmail, Calendar, Drive, Slack, Notion, etc.
- [08:50] Best practices : décrire QUOI pas COMMENT, screenshots pour révisions, itérer petit

## Code/prompts/commandes verbatim
```
Create a new skill called Explain Like I'm 5 that explains any concept in three parts: the essence, an analogy, and why it matters. Use it whenever I ask you to explain something simply.
```
```
/explain-like-im-5 Help me understand MCP
```

## Patterns réutilisables pour Ivan
1. Skill génération descriptions produits Shopify (tone + focus configurable)
2. Skill social media posts depuis description produit (Instagram/X/Facebook)
3. Skill résumé ventes Shopify via MCP + API Shopify
4. Skill analyse concurrence (URLs → tableau comparatif)
5. Best practice : planifier avant coder, screenshots pour révisions UI

## Skill_potential
- `/ecommerce-product-explainer` : URL produit Shopify → description optimisée SEO + contenu marketing
- `/social-media-content-creator` : description produit → posts multi-plateformes + hashtags (style TempleTwins/PURESOLE)
- `/shopify-sales-summarizer` : connexion API Shopify (MCP) → résumé ventes daily/weekly
- `/competitor-analysis-assistant` : URLs concurrents → tableau comparatif prix/offres/marketing

## Score utilité 0-10 pour Ivan
**9/10** — Automatisation tâches répétitives e-commerce + MCP = game-changer pour solo founder
