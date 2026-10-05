# Analyse Gemini: Claude Code 3.0 New Mods Feature
**ID**: u1dW4z5Ye90
**URL**: https://www.youtube.com/watch?v=u1dW4z5Ye90

---

Voici l'analyse de la vidéo pour Ivan :

## Résumé exécutif (3 lignes max)
La mise à jour de Claude Code introduit la prise en charge de `AGENTS.md` pour des instructions de projet partagées, un système de "mods" pour personnaliser le comportement de Claude, et une nouvelle gestion de projet multi-agent avec sessions cloud. Ces fonctionnalités visent à améliorer la coordination, l'efficacité et la flexibilité pour les développeurs.

## Concepts clés avec timestamps
- **[00:08] Support de `AGENTS.md`** : Claude Code peut désormais lire le fichier `AGENTS.md` pour des instructions de projet génériques, évitant la duplication si plusieurs agents sont utilisés.
- **[00:19] Les "Mods" pour Claude Code** : Les mods sont des extensions qui permettent de personnaliser le "harness" (logiciel autour du modèle) de Claude, modifiant son comportement par des "hooks" de fonction.
- **[02:52] Panneau de Diff en direct** : Une nouvelle interface qui affiche les modifications de fichiers et le nombre de lignes mises à jour en temps réel pendant que Claude travaille ou exécute des commandes.
- **[03:24] Projets repensés (Beta)** : Un nouveau système de coordination pour les projets, permettant de décomposer le travail en plusieurs threads exécutés dans le cloud, de déléguer des tâches et de revoir les résultats.
- **[04:19] Utilisation de l'ordinateur en arrière-plan** : Sur macOS 15+, Claude peut travailler dans des applications approuvées en arrière-plan pendant que l'utilisateur utilise son ordinateur.
- **[04:45] Reprendre une session terminale dans l'application** : Possibilité de reprendre une session Claude lancée via le terminal directement dans l'application, en conservant le contexte.
- **[04:58] Claude Fable 5.1 (modèle)** : Un nouveau modèle avec une fenêtre de contexte d'un million de jetons, offrant une compréhension plus profonde des projets.
- **[05:29] `/skill-doctor` (outil)** : Une commande pour vérifier le coût en jetons et l'utilisation de vos "skills" (plugins), aidant à identifier ceux qui consomment trop de contexte.
- **[05:46] `claude plugin eval` (outil)** : Un outil pour évaluer l'efficacité de vos plugins personnalisés en les comparant à une ligne de base sans plugin, utile pour justifier leur coût et leur complexité.

## Code/prompts/commandes verbatim
- `/config`
- `claude-md-or-agents-md`
- `claude-md-and-agents-md`
- `pnpm test`
- `pnpm install`
- `pnpm lint`
- `/resume`
- `/model fable`
- `/skill-doctor`
- `$ claude plugin eval .`

## Patterns réutilisables pour Ivan
- **Standardisation des instructions de projet** : Ivan peut créer un fichier `AGENTS.md` pour définir des conventions de test (`pnpm test`), de gestion de paquets (`pnpm`), et des dossiers générés (`src/generated/`) pour ses projets. Cela assure une cohérence pour Claude et tout autre outil ou membre d'équipe.
- **Feedback précis et efficace** : Le panneau de "diff" en direct sera très utile pour Ivan. Il lui permettra de valider rapidement les modifications proposées par Claude et de donner un feedback ciblé sur des lignes de code spécifiques, améliorant l'itération et la qualité du code.
- **Gestion de projets complexes (futur)** : Pour des fonctionnalités plus importantes qui touchent l'API et le frontend de ses boutiques Shopify/dropship, Ivan pourrait utiliser la nouvelle fonctionnalité "Projets" pour coordonner les tâches sur plusieurs "threads" de Claude Code, même si cela n'est pas encore accessible en exécution locale.
- **Optimisation des coûts du LLM** : La commande `/skill-doctor` est essentielle pour Ivan en tant que solo founder. Elle lui permettra de voir quels "skills" (plugins) consomment le plus de jetons et de désactiver ceux qui ne sont pas essentiels, réduisant ainsi ses coûts d'utilisation.
- **Validation des plugins personnalisés** : Si Ivan développe des plugins spécifiques à ses besoins (par exemple pour l'automatisation de tâches de dropshipping ou des intégrations Shopify), `claude plugin eval .` lui offrira une méthode rigoureuse pour s'assurer que ses plugins apportent une réelle valeur ajoutée par rapport au coût et à la complexité qu'ils introduisent.

## Skill_potential
- **[02:45] Optimisation contextuelle pour monorepo/multi-dossiers** : Basé sur la suggestion vidéo, un skill pourrait être développé pour qu'un mod assemble les instructions spécifiques et le contexte pertinent uniquement pour la partie du projet sur laquelle Claude travaille (ex: `web/` vs `api/` dans un monorepo), sans charger les règles de toutes les équipes dans chaque tâche. Cela réduirait considérablement la taille du contexte et donc les coûts.

## Score utilité 0-10 pour Ivan
**8/10**

**Justification :**
L'ajout du support de `AGENTS.md` est un gain immédiat pour la standardisation. Les outils comme `/skill-doctor` et `claude plugin eval` sont très pertinents pour un solo founder comme Ivan, car ils l'aident à optimiser ses coûts et la performance de ses outils personnalisés. La fonctionnalité "Projets" et les "Mods" offrent un potentiel considérable pour les workflows plus complexes et la personnalisation, même si leur accès et leur stabilité sont encore en développement (Beta/Early Access), ce qui nuance un peu l'utilité immédiate mais promet beaucoup pour l'avenir. Le panneau de diff est un plus pour l'efficacité des révisions.
