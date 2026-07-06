Voici l'analyse de la vidéo "How to Create Sub Agents in Claude Code (2026)", adaptée à Ivan (fondateur de TempleTwins et PURESOLE).

---

## Résumé exécutif
La vidéo présente la création de sous-agents personnalisés dans Claude Code pour automatiser des tâches spécifiques. Ivan peut créer des agents dédiés à l'amélioration du code, à la vérification de la logique métier ou à la génération de contenu, en configurant leur portée, leurs outils et leur mémoire pour chaque projet ou usage personnel, optimisant ainsi son flux de travail de développement et de création de contenu.

## Concepts clés avec timestamps
*   **0:12** : Initiation du processus de création/gestion d'agents via la commande `/agents`.
*   **0:50** : Choix de la portée de l'agent, soit pour un `Projet` spécifique (`./.claude/agents/`) soit `Personnel` pour une utilisation transversale (`~/.claude/agents/`).
*   **1:24** : Sélection de la méthode de création d'agent : "Generate with Claude" (recommandé pour une configuration guidée) ou "Manual configuration".
*   **1:40** : Description de l'objectif de l'agent, qui sert de "prompt système" pour définir son comportement et ses responsabilités (par exemple, "agent d'amélioration de code").
*   **2:05** : Attribution des outils que l'agent peut utiliser : "Read-only tools" (pour la lecture), "Edit tools" (pour la modification), "Execution tools" (pour l'exécution de commandes), "RCP tools", "Other tools". Le choix dépend de la tâche de l'agent.
*   **2:27** : Sélection du modèle linguistique pour l'agent (Sonnet, Opus, Haiku, ou Hériter du parent). Le modèle détermine les capacités de raisonnement et la vitesse de l'agent.
*   **2:40** : Configuration de la mémoire de l'agent : `User scope` (persistant, recommandé), `None` (pas de mémoire), `Project scope` (mémoire liée au projet actuel), ou `Local scope`. Cela définit ce que l'agent peut "se souvenir" entre les interactions ou les sessions.
*   **3:24** : Utilisation d'un sous-agent créé en mentionnant son nom dans le prompt principal (par exemple, "Use the code-improver agent...").

## Code/prompts verbatim
*   **Pour démarrer la gestion des agents :**
    ```
    /agents
    ```
*   **Description de l'agent d'amélioration de code (utilisé à 1:40) :**
    ```
    A code improvement agent that scans files and suggests improvements for readability, performance, and best practices. It should explain each issue, show the current code, and provide an improved version.
    ```
*   **Exemple de prompt pour utiliser l'agent (utilisé à 3:24) :**
    ```
    Use the code-improver agent to suggest improvements in this project
    ```

## Patterns réutilisables pour Ivan

Pour Ivan, fondateur de TempleTwins (streetwear Shopify) et PURESOLE (dropship), la capacité de créer des sous-agents spécialisés offre plusieurs opportunités :

1.  **Agent de Révision de Code Shopify (qualité/performance) :**
    *   **Description :** Similaire à l'exemple, cet agent pourrait scanner les fichiers Liquid, JavaScript et CSS de ses thèmes Shopify ou ses applications personnalisées. Il suggérerait des améliorations pour l'optimisation des performances (temps de chargement), la lisibilité du code, la conformité aux meilleures pratiques (sécurité, SEO technique) et l'identification de bugs potentiels.
    *   **Outils :** `Read-only tools` (pour analyser), potentiellement `Edit tools` (pour proposer des modifications directes et interactives).
    *   **Mémoire :** `Project scope` pour chaque boutique Shopify, afin de mémoriser les spécificités du code d'un projet donné.

2.  **Agent de Vérification de Logique Métier (dropshipping/e-commerce) :**
    *   **Description :** Un agent pour valider les scripts ou la logique qui gère les promotions, les variations de produits, la gestion des stocks (en dropshipping, l'état "en stock" est critique), ou les calculs de prix spécifiques. Il pourrait s'assurer que ces logiques correspondent aux exigences d'affaires d'Ivan.
    *   **Outils :** `Read-only tools` pour la vérification, `Execution tools` pour simuler des scénarios si Claude Code supporte l'exécution dans un environnement sandbox.
    *   **Mémoire :** `Project scope` pour des logiques spécifiques à une marque (TempleTwins ou PURESOLE).

3.  **Agent de Génération/Optimisation de Contenu Marketing :**
    *   **Description :** Cet agent serait entraîné sur le ton de voix de ses marques (streetwear pour TempleTwins, pureté/minimalisme pour PURESOLE). Il générerait ou optimiserait des descriptions de produits, des titres SEO, des légendes pour les réseaux sociaux, des brouillons d'e-mails marketing, des idées de blog, etc.
    *   **Outils :** Principalement `Read-only tools` (pour analyser le contenu existant et les directives de marque), puis capacité de `TaskCreate` pour générer du nouveau contenu.
    *   **Mémoire :** `User scope` ou `Personal` pour se souvenir des préférences de style et de marque générales, mais aussi `Project scope` si le ton de voix varie entre TempleTwins et PURESOLE.

4.  **Agent d'Automatisation des Tâches Répétitives (dev/ops) :**
    *   **Description :** Un agent pour automatiser des tâches courantes comme la configuration de nouveaux environnements de développement, la création de fichiers de base pour un nouveau composant, ou même des vérifications d'intégration simples avant un déploiement.
    *   **Outils :** `Execution tools` et `Edit tools` pour interagir directement avec le système de fichiers et les commandes.
    *   **Mémoire :** `Project scope` ou `User scope` selon la nature des tâches (spécifiques au projet ou génériques).

La capacité de créer des agents avec une portée et une mémoire spécifiques est cruciale pour Ivan, lui permettant de structurer ses interactions avec Claude et de maintenir un contexte pertinent pour chaque tâche sans "polluer" la mémoire ou les compétences d'autres agents.

## Skill_potential

Oui, ce pattern est un skill Claude réutilisable.

**Nom du Skill :** `ConfigureSubAgent`

**Description du Skill :** Permet à Claude de guider l'utilisateur dans la création ou la modification d'un sous-agent spécialisé dans Claude Code. Ce skill prend en charge la définition de la description de l'agent, la sélection de sa portée (personnelle ou projet), l'assignation d'outils spécifiques (lecture, édition, exécution), le choix du modèle linguistique, et la configuration de sa mémoire persistante, garantissant une création d'agent optimisée et conforme aux objectifs de l'utilisateur.

**Arguments possibles :**
*   `agent_name`: `string` (Nom unique de l'agent, ex: "CodeQualityImprover")
*   `description`: `string` (Description détaillée du rôle et des tâches de l'agent)
*   `scope`: `string` (`personal` ou `project`. Défaut : `personal`)
*   `tools`: `list<string>` (Liste des types d'outils, ex: `read-only`, `edit`, `execution`, `rcp`, `other`. Défaut : `read-only`)
*   `model`: `string` (`Sonnet`, `Opus`, `Haiku`, `inherit`. Défaut : `Sonnet`)
*   `memory_config`: `string` (`user_scope`, `none`, `project_scope`, `local_scope`. Défaut : `user_scope` pour `personal` scope, `project_scope` pour `project` scope)
*   `background_color`: `string` (Couleur d'arrière-plan pour l'agent, ex: `yellow`, `blue`, `green`. Défaut : `automatic`)

**Exemple de prompt pour Ivan :**
"Claude, utilise le skill `ConfigureSubAgent` pour créer un agent nommé 'DescriptionProduitTT' qui va générer des descriptions de produits pour TempleTwins. Sa description devrait être 'Génère des descriptions de produits streetwear uniques et engageantes, optimisées SEO, en respectant le ton de voix de TempleTwins.' Il aura une portée personnelle, utilisera des outils de lecture et de création de tâches, le modèle Opus, et une mémoire persistante à portée utilisateur. Choisis une couleur de fond violette."

## Score utilité 0-10
**9/10**

**Justification :** Cette fonctionnalité est extrêmement utile pour Ivan. Elle lui permet de transformer Claude Code d'un simple assistant généraliste en une équipe d'IA spécialisée, capable de gérer des tâches complexes et spécifiques à ses différentes entreprises (développement, marketing, gestion de contenu) de manière cohérente et efficace. La modularité des sous-agents, avec leur propre contexte, outils et mémoire, réduit la surcharge cognitive et améliore la précision des résultats, ce qui est un avantage considérable pour l'optimisation des opérations en e-commerce et le développement. Le seul point manquant pour un 10/10 serait une intégration encore plus poussée et automatisée avec les plateformes Shopify ou des outils de dropshipping spécifiques, mais la flexibilité actuelle est déjà très performante.