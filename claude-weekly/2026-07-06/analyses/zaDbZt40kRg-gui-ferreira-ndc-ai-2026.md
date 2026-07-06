Voici l'analyse de la vidéo "What Claude Code Can Do That You Haven't Tried" pour Ivan :

---

## Résumé exécutif

Cette présentation offre à Ivan des stratégies pratiques pour optimiser l'utilisation de Claude Code, allant de la gestion des configurations aux workflows quotidiens, en passant par l'extension des capacités et l'application au-delà du simple codage. Les points clés incluent la maîtrise de la gestion du contexte pour réduire les coûts, l'automatisation des tâches répétitives et l'intégration de Claude comme un "second cerveau" pour l'analyse stratégique et la génération de contenu.

## Concepts clés avec timestamps

*   **0:30** **96 Slash Commands & Évolution Rapide :** Le speaker souligne la richesse des commandes (96 à l'époque du talk) et la vitesse d'évolution des LLM, rendant difficile de tout maîtriser.
*   **0:55** **Guilherme "Gui" Ferreira, Speaker Intro :** Présentation de l'orateur, un ingénieur logiciel et éducateur, qui partage son expérience pratique.
*   **1:48** **Quatre Axes de la Présentation :**
    1.  **Setup :** Configuration unique pour un bénéfice continu.
    2.  **Daily Workflow :** Astuces pour améliorer la productivité quotidienne.
    3.  **The Platform Layer :** Points d'extension et personnalisation.
    4.  **Beyond Code :** Utiliser Claude au-delà du développement pur.
*   **2:30** **Non pas un "Getting Started" :** Le talk s'adresse à ceux qui ont déjà une base avec Claude, se concentrant sur des astuces avancées ("rapid fire" de 40 astuces).
*   **3:57** **Où Utiliser Claude Code :** Disponible sur desktop, CLI (interface en ligne de commande) et VS Code. La CLI reçoit les nouvelles fonctionnalités en premier.
*   **4:40** **Bucket 1: Setup Stuff (Configuration) :**
    *   **5:05** **Le Fichier `claude.md` :** Cœur de l'agent, décrit les règles, frameworks, commandes, etc.
    *   **5:31** **Ne Pas Dupliquer (`@RULES.md @schema.json`) :** Référencer des fichiers existants au lieu de dupliquer les informations dans `claude.md`.
    *   **6:16** **Ne Pas Tout Mettre dans `claude.md` :** Une étude d'ETH Zurich montre qu'une surcharge d'informations dégrade la performance de 3% et augmente les coûts de 20%+. Les agents obéissent, ils ne filtrent pas.
    *   **8:24** **L'Audit en 3 Questions :**
        1.  Nécessaire pour chaque tâche ? → Reste dans `claude.md`.
        2.  Tâche spécifique/occasionnelle ? → Fichier de "skill" ou de règles séparé.
        3.  L'agent peut-il le trouver seul ? → Supprimer.
    *   **11:18** **Trois Scopes de `claude.md` :**
        1.  `claude.md` (partagé avec l'équipe).
        2.  `claude.local.md` (personnel, ignoré par Git).
        3.  `~/.claude/claude.md` (préférences globales de l'utilisateur).
    *   **12:38** **Garder les Secrets Hors Contexte (`permissions.deny`) :** Utiliser `.claude/settings.json` pour bloquer la lecture de fichiers sensibles (`.env`, identifiants, secrets) par Claude.
    *   **15:05** **Toujours Connaître sa Branche, son Modèle et la Taille du Contexte (`/statusline`) :** Afficher des informations contextuelles importantes pour optimiser l'utilisation.
*   **16:15** **Bucket 2: Daily Workflow (Flux de Travail Quotidien) :**
    *   **17:36** **Éditer le Plan comme un Document (`Shift+Tab`, `Ctrl+G`) :** Modifier la proposition de plan de Claude dans un éditeur externe pour affiner la stratégie.
    *   **18:30** **Laisser Claude Vous Interviewer (AskUserQuestion) :** Utiliser cet outil pour que Claude pose des questions et clarifie les attentes, évitant les hypothèses.
    *   **21:12** **Annuler une Mauvaise Décision (`Esc + Esc` ou `/rewind`) :** Revenir à un point de contrôle antérieur dans la conversation.
    *   **22:27** **Changer de Modèle en Cours de Tâche (`/model`) :** Permet de basculer entre des modèles plus puissants (pour le raisonnement) et moins chers (pour l'exécution).
    *   **23:33** **Ajuster le Niveau de Raisonnement (`/effort high/low`) :** Gérer les ressources selon la complexité de la tâche.
    *   **24:10** **Raisonnement Plus Approfondi (`ultrathink`) :** Forcer Claude à une réflexion plus poussée pour les problèmes complexes.
    *   **24:47** **Poser une Question Annexe (`$/btw`) :** Poser des questions sans interrompre le travail en cours de Claude.
    *   **25:16** **Voir l'Utilisation Actuelle (`/usage`) :** Afficher les statistiques de consommation de tokens par modèle.
    *   **26:04** **La "Dumb-Zone" du Contexte (40%) :** La qualité des réponses se dégrade fortement au-delà de 40% d'utilisation de la fenêtre de contexte.
    *   **28:50** **Réinitialiser une Conversation Stale (`/compact`) :** Remplace l'historique par un résumé structuré, réduisant le contexte et améliorant la qualité.
    *   **31:25** **Exécuter une Commande Shell sans Quitter (`! git status`) :** Accéder au terminal directement depuis Claude pour des actions rapides.
    *   **33:53** **Reprendre là où vous vous êtes Arrêté (`--continue` / `--resume`) :** Charger la dernière session ou une session spécifique.
    *   **36:00** **Continuer à Travailler en Déplacement (`/remote-control`) :** Transférer une session en cours vers l'application desktop (ou mobile).
    *   **36:55** **"Rubber Ducking" (`/voice`) :** Dicter ses pensées à Claude pour structurer les idées, Claude s'occupe de la transcription.
    *   **38:00** **Intégrer des Captures d'Écran (`Ctrl+V` ou drag-and-drop) :** Utiliser des images comme entrée pour les tâches multimodales (UI/UX).
    *   **38:52** **Travailler en Sessions Parallèles (`--worktree`) :** Gérer plusieurs agents sur des branches Git isolées pour différents aspects d'un projet.
    *   **39:45** **Distinguer vos Sessions (`/color`, `/rename`) :** Attribuer des couleurs et des noms pour organiser les sessions multiples.
    *   **40:00** **Laisser Claude Travailler jusqu'à Achèvement (`/goal`) :** Définir un objectif mesurable et une condition d'arrêt (ex: "implémenter le endpoint, ne pas arrêter tant que les tests ne passent pas").
    *   **41:05** **Surveiller Chaque Agent en une seule fois (`claude agents`) :** Tableau de bord pour gérer et visualiser l'état de plusieurs agents simultanément.
*   **42:05** **Bucket 3: The Platform Layer (Couche Plateforme) (suite) :**
    *   **42:36** **Détecter les Erreurs Plus Tôt (`hooks` dans `settings.json`) :** Exécuter des commandes post-action (ex: lancer des tests unitaires après chaque écriture de code) pour économiser de l'argent et du temps.
    *   **43:55** **"Skills" (Compétences) :** Capacités réutilisables, pas juste des prompts. Un dossier `.claude/skills` peut contenir des scripts, références, templates.
    *   **46:20** **Refactoring à l'Échelle du Code (`/batch`) :** Décomposer de grandes tâches de refactoring en unités plus petites pour des agents parallèles.
    *   **47:20** **Nettoyer ce que vous venez d'écrire (`/simplify`) :** Utiliser 3 agents parallèles pour réviser et simplifier le code/les changements récents.
    *   **48:19** **Surveillance CI/CD (`/loop`) :** Configurer Claude pour exécuter un prompt à intervalles réguliers (ex: vérifier le déploiement toutes les 5 minutes).
    *   **49:01** **Installer des Extensions depuis le Marketplace (`/plugin`) :** Accéder à un marketplace officiel pour des extensions et plugins pré-fabriqués.
    *   **50:20** **Partager les MCPs avec votre Équipe (`.mcp.json`) :** Inclure ce fichier dans le dépôt Git pour que l'équipe clone les mêmes configurations d'agents.
    *   **50:45** **Exécuter sans Intervention Humaine (`claude "summarise this folder" --print`) :** Exécuter des tâches en arrière-plan sans UI.
    *   **51:32** **"Pipeliner" comme n'importe quelle CLI (`cat log.txt | claude -p "rank errors by frequency" > out.txt`) :** Intégrer Claude dans des chaînes de commandes shell existantes.
    *   **52:30** **Nettoyage des Téléchargements (`Organise these files`) :** Exécuter Claude pour trier, renommer et déplacer des fichiers dans un dossier désordonné.
    *   **53:11** **Un Second Cerveau que Claude Peut Lire :** Claude peut lire et interagir avec votre "vault" (dossier) Obsidian (fichiers Markdown). Poser des questions comme "Montre-moi mes priorités cette semaine de mon journal".
    *   **54:25** **Récapituler sa Semaine :** Demander à Claude de résumer les réalisations basées sur les contributions (ex: "Qu'est-ce que j'ai livré la semaine dernière ?").
    *   **55:01** **Analyser les Fichiers de Logs :** Utiliser Claude pour analyser de grands volumes de logs, classer les erreurs par fréquence, trouver des corrélations.
    *   **57:37** **Voir vos Propres Patrons (`/insights`) :** Obtenir un rapport de Claude sur vos propres habitudes d'utilisation, vos forces et faiblesses.

## Code/prompts verbatim

*   `@RULES.md @schema.json` (Exemple de référencement de fichiers)
*   `interview me about everything I might have missed` (Prompt pour l'auto-interview)
*   `Esc + Esc` ou `/rewind` (Commande pour annuler une action)
*   `/model` (Commande pour changer de modèle)
*   `/effort high` (Commande pour ajuster le niveau d'effort)
*   `ultrathink` (Commande pour un raisonnement plus approfondi)
*   `$/btw what was the name of that config file?` (Exemple de question annexe)
*   `/usage` (Commande pour voir l'utilisation actuelle)
*   `/compact` (Commande pour réinitialiser une conversation stale)
*   `! git status` (Exemple d'exécution de commande shell)
*   `--continue` ou `--resume` (Arguments pour reprendre une session)
*   `/remote-control` (Commande pour travailler en déplacement)
*   `/voice` (Commande pour le mode vocal)
*   `Ctrl+V` (pour coller une image depuis le presse-papiers)
*   `--worktree` (Argument pour travailler en sessions parallèles)
*   `/color` / `/rename` (Commandes pour distinguer les sessions)
*   `/goal implement the endpoint. don't stop until tests pass.` (Exemple de définition d'objectif)
*   `claude agents` (Commande pour le tableau de bord des agents)
*   `hooks` dans `settings.json` (Configuration pour l'automatisation post-action)
*   `/batch migrate tests/ from Moq to NSubstitute` (Exemple de commande de refactoring de codebase)
*   `/simplify` (Commande pour nettoyer et simplifier le code)
*   `/loop 5m check if the deploy finished` (Exemple de surveillance CI/CD)
*   `/plugin` (Commande pour installer des extensions)
*   `.mcp.json` (Fichier pour partager les MCPs avec l'équipe)
*   `claude "summarise this folder" --print` (Exemple d'exécution sans intervention humaine)
*   `cat log.txt | claude -p "rank errors by frequency" > out.txt` (Exemple de piping CLI)
*   `"Organise these files"` (Prompt pour le nettoyage des téléchargements)
*   `"Show me my priorities this week from my journal"` (Prompt pour gérer le vault Obsidian)
*   `"What did I ship last week?"` (Prompt pour récapituler la semaine)
*   `/insights` (Commande pour voir ses propres patterns d'utilisation de Claude)

## Patterns réutilisables pour Ivan

1.  **Optimisation des Coûts et de la Performance (Setup & Workflow):**
    *   **Gestion du Contexte :** Ivan peut structurer ses fichiers `claude.md` et `.local.md` pour définir le "rôle" de Claude (ex: "générateur de descriptions produit", "analyste de logs Shopify") et éviter d'inonder Claude d'informations non pertinentes.
    *   **Audit des Informations :** Appliquer l'audit en 3 questions pour s'assurer que seules les informations critiques résident dans `claude.md`, réduisant la consommation de tokens et améliorant la pertinence des réponses.
    *   **Secrets Sécurisés :** Utiliser `permissions.deny` dans `.claude/settings.json` pour empêcher Claude d'accéder aux clés API Shopify, identifiants de bases de données de dropshipping, etc.
    *   **Choix du Modèle et de l'Effort :** Utiliser `/model` et `/effort high/low` pour adapter Claude à la tâche :
        *   `effort low` pour la génération de brouillons de contenu marketing rapide.
        *   `effort high` pour des analyses complexes de données de vente ou des prévisions de stock.

2.  **Génération et Optimisation de Contenu (Workflow & Beyond Code):**
    *   **Affinement du Plan (`Shift+Tab`, `Ctrl+G`) :** Pour des campagnes marketing complexes, Ivan peut laisser Claude esquisser un plan, puis le modifier précisément dans son éditeur pour s'assurer qu'il correspond à sa vision.
    *   **Clarification des Objectifs (`AskUserQuestion`) :** Avant de demander à Claude de rédiger des descriptions de produits ou des publicités, Ivan peut le faire s'auto-interviewer pour clarifier le public cible, les points de vente uniques et le ton de voix, évitant ainsi des révisions coûteuses.
    *   **"Rubber Ducking" Vocal (`/voice`) :** Ivan peut dicter ses pensées pour brainstormer des idées de produits, des stratégies marketing ou des solutions logistiques, laissant Claude les organiser. C'est particulièrement utile pour les fondateurs qui sont souvent seuls.
    *   **Intégration Visuelle (Captures d'Écran) :** Pour le design de sa boutique Shopify ou de ses publicités, Ivan peut coller des captures d'écran et demander à Claude des suggestions d'amélioration ou d'intégration de nouveaux éléments visuels.
    *   **Nettoyage de Contenu (`/simplify`) :** Après une génération de contenu (descriptions, posts), `/simplify` peut aider à rendre le texte plus concis, percutant et adapté au SEO.

3.  **Automatisation et Analyse de Données (Platform Layer & Beyond Code):**
    *   **Compétences Personnalisées (Skills) :** Ivan peut créer des "skills" pour :
        *   **`skill_generate_product_description` :** Prend en entrée les spécifications d'un produit et génère plusieurs descriptions optimisées pour le SEO de Shopify.
        *   **`skill_analyze_shopify_logs` :** Lit les logs d'accès à la boutique Shopify pour identifier les problèmes de performance ou les tentatives d'attaque.
        *   **`skill_competitor_price_check` :** Scrappe les prix des concurrents et les compare aux siens.
    *   **Automatisation de Tâches Répétitives (`hooks`, `/loop`) :**
        *   Un hook pourrait lancer un script Python pour publier automatiquement les descriptions générées par Claude sur Shopify après un "Edit/Write" dans un fichier Markdown.
        *   `/loop 5m check inventory levels` pourrait surveiller les stocks de dropshipping et alerter Ivan si un produit est bas.
    *   **Analyse de Fichiers de Logs :** Indispensable pour le dropshipping et Shopify. Ivan peut utiliser Claude pour détecter des anomalies, des erreurs fréquentes, des goulots d'étranglement de performance ou des problèmes de sécurité sur ses sites.
    *   **Traitement de Fichiers en Pipeline (`Piping CLI`) :** Utiliser Claude pour traiter des CSV de commandes, des listes de produits ou des rapports financiers générés par d'autres outils CLI.

4.  **Gestion de Projet et Productivité (Workflow & Beyond Code):**
    *   **Sessions Parallèles et Gestion Visuelle (`--worktree`, `/color`, `/rename`, `claude agents`) :** Ivan peut gérer plusieurs projets ou tâches critiques simultanément, chaque session ayant sa propre branche Git, un nom et une couleur distincte pour une meilleure organisation.
    *   **"Second Cerveau" Obsidian :** Lier Claude à son vault Obsidian pour :
        *   Obtenir des résumés de ses notes de réunion ou de ses recherches sur des niches de produits.
        *   Poser des questions sur ses stratégies de croissance ou ses plans d'affaires.
        *   Identifier des lacunes ou des opportunités dans ses pensées.
    *   **Récapitulatif Automatisé (`Recap your week`) :** Obtenir un aperçu rapide de ses réalisations de la semaine ou du mois, utile pour la planification et le reporting.
    *   **Détection des Patterns d'Usage (`/insights`) :** Comprendre comment il utilise Claude, quelles commandes sont les plus efficaces pour lui, et comment il peut améliorer son interaction.

## Skill_potential

*   **Skill : Assistant SEO pour descriptions produit**
    *   **Description :** Génère et optimise des descriptions de produits pour Shopify ou d'autres plateformes de dropshipping, en intégrant des mots-clés SEO pertinents et un ton de marque défini.
    *   **Déclencheur :** `/product_description {produit_id} {mots_cles}`
*   **Skill : Analyseur de performance Shopify**
    *   **Description :** Analyse les fichiers de logs ou les rapports de performance Shopify (après export) pour identifier les erreurs, les lenteurs ou les anomalies.
    *   **Déclencheur :** `cat shopify_logs.txt | claude -p "analyze performance issues and rank by severity"`
*   **Skill : Moniteur de prix concurrentiel**
    *   **Description :** Utilise des outils de scraping web (si autorisé) pour collecter et comparer les prix des produits concurrents, fournissant un rapport sur les écarts.
    *   **Déclencheur :** `/monitor_competitor_prices {liste_urls_produits}`
*   **Skill : Organisateur de fichiers de téléchargement**
    *   **Description :** Trie et organise les fichiers d'un dossier spécifié (ex: Téléchargements) en créant des sous-dossiers par type (images, documents, archives, etc.).
    *   **Déclencheur :** `/organize_downloads_folder {chemin_du_dossier}`
*   **Skill : Aide à la décision stratégique (Obsidian)**
    *   **Description :** Lit et synthétise les notes d'un vault Obsidian pour extraire des informations clés, identifier des tendances ou répondre à des questions stratégiques complexes.
    *   **Déclencheur :** `/obsidian_insights "show me key learnings from last month's business journal"`
*   **Skill : Babysitter de déploiement CI/CD**
    *   **Description :** Surveille l'état d'un déploiement CI/CD à intervalles réguliers et envoie des notifications ou un résumé final.
    *   **Déclencheur :** `/loop 10m check deploy status for "my_shopify_app_deploy"`

## Score utilité 0-10

**9/10**

**Justification :** Ce talk est extrêmement utile pour Ivan. Il ne se contente pas de présenter des fonctionnalités, mais contextualise leur usage avec des exemples concrets qui résonnent directement avec les défis d'un fondateur de e-commerce. L'accent mis sur la productivité, la réduction des coûts liés au contexte et l'automatisation via des "skills" est crucial. L'idée d'utiliser Claude comme un "second cerveau" pour la stratégie est également très puissante. La présentation est rapide, mais Gui fournit suffisamment d'informations pour que Ivan puisse explorer les commandes pertinentes de manière autonome.