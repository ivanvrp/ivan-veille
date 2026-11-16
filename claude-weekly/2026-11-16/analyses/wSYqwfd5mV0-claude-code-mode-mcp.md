# Analyse Gemini — Claude Code Finally Got MCP Code Mode (Setup + Test)
**Video ID:** wSYqwfd5mV0  
**URL:** https://www.youtube.com/watch?v=wSYqwfd5mV0  
**Analysé le:** 2026-11-16

## Résumé exécutif
Le Mode Code de Claude Code permet à Claude d'écrire et d'exécuter du JavaScript pour appeler des outils, offrant un contrôle précis sur les données qui entrent dans le contexte du LLM. Cela réduit significativement la consommation de tokens et améliore la performance pour les tâches de lecture complexes, notamment avec des services tiers, bien que la fonctionnalité soit encore expérimentale et limitée au terminal.

## Concepts clés avec timestamps
- [0:02] Introduction au Mode Code : Anthropic a ajouté un "Code Mode" expérimental à Claude Code, permettant à Claude d'écrire du JavaScript pour interagir avec ses outils (MCP).
- [0:20] Principe de fonctionnement et économie de contexte : Le Mode Code permet à Claude d'exécuter plusieurs appels d'outils en une seule étape et de choisir sélectivement les résultats à réinjecter dans le contexte, réduisant drastiquement la quantité de tokens.
- [0:31] Problématique des LLM : En mode standard, les définitions des outils et tous les résultats des appels sont chargés dans le contexte, rendant le LLM "plus bête" et coûteux.
- [1:01] Statut et limitations : Mode expérimental, désactivé par défaut. Ne fonctionne pas avec Agent Teams. Limité au terminal uniquement.
- [1:17] Exemple comparatif (YouTube MCP) — Sans : 22s, contexte 3%→7% (44.8k tokens). Avec : 30s, contexte 2%→4% (23.5k tokens) = -50% tokens.
- [2:33] Bilan : Plus efficace pour les tâches de lecture intensive (filtrage, résumé de données) que pour l'écriture de code.
- [2:54] Ingénierie du contexte : Nettoyer les anciens serveurs MCP, skills et fichiers claude.md pour optimiser le LLM.
- [4:27] Exemple comparatif (OpenRouter MCP) — Sans : 44s, 14% contexte (116k tokens). Avec : 39s, 5% contexte (28.7k tokens) = -75% tokens.
- [5:48] Mode Verbeux (Ctrl+O) : Voir le code JavaScript généré et exécuté.
- [6:02] Support des connecteurs distants : Fonctionne avec les connecteurs MCP distants (APIs tierces).

## Code/prompts/commandes verbatim
```bash
# Mise à jour de Claude Code
claude update

# Lancement avec Code Mode activé
CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1 claude
```

Exemple prompt OpenRouter :
```
Using only my OpenRouter MCP (read-only lookups, dont call send-message, generate-* or any billed tool): find models with at least 1M context that support tool calling, take the 5 cheapest by prompt price, then for each of those 5 look up its provider endpoints and report the cheapest provider and its uptime. Give me one compact table.
```

## Patterns réutilisables pour Ivan
1. **Optimisation des coûts API pour la recherche produits/fournisseurs** : Filtrer les résultats des APIs Shopify ou fournisseurs dropshipping via JS avant injection dans le contexte.
2. **Analyse de données ciblée** : Récupérer rapports de performance Shopify, filtrer par canal marketing, produit, période avant traitement par Claude.
3. **Automatisation multi-étapes** : Chaîner requêtes APIs (description produit → images → reformatage) en une seule exécution JavaScript.
4. **Préparation contenu SEO/ads** : Extraire tendances de mots-clés, filtrer, générer suggestions optimisées.

## Skill_potential
**ContextualDataFilter** : Un skill qui permettrait de spécifier des règles de filtrage (JSON) pour les données renvoyées par n'importe quel appel d'outil avant leur réintégration dans le contexte LLM.

Exemple : `{{ ContextualDataFilter(tool_output, rules={ "min_price": 10, "max_inventory": 100, "category": "electronics" }) }}`

**APIOrchestratorJS** : Un skill avancé qui prendrait une série d'appels d'API avec un script JavaScript de transformation, pour orchestrer les appels et traiter les réponses en une seule opération.

## Score utilité 0-10 pour Ivan
**9/10** — Adresse directement la problématique coûts/contexte pour l'automatisation e-commerce. Réduction 50-75% des tokens sur les tâches de lecture intensive (APIs produits, inventaire, analytics). Expérimental mais stratégiquement important.
