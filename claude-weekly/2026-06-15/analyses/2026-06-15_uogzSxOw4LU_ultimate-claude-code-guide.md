# Analyse Gemini — Advanced Claude Code Tutorial (Skills, Subagents, MCP Servers, & More!)

> **URL** : https://www.youtube.com/watch?v=uogzSxOw4LU · **Créateur** : Tech With Tim · **Durée** : 37:40 · **Langue** : en
> **Analysée le** : 2026-06-15 · **Score utilité** : 9/10 · **Modèle** : gemini-2.5-flash

## Pertinence pour Ivan
Le contenu est directement applicable pour Ivan, couvrant la création de skills et subagents réutilisables, l'optimisation des coûts, et l'intégration avec des outils clés pour l'e-commerce et l'automatisation.

## Résumé exécutif
Ce tutoriel avancé présente des fonctionnalités clés de Claude Code pour les utilisateurs expérimentés. Il détaille la gestion des modèles, l'analyse de l'utilisation via des rapports, et la connexion à des serveurs MCP comme GitHub. La vidéo explique également comment créer des compétences et des sous-agents personnalisés pour automatiser des workflows répétables et maintenir une mémoire persistante, optimisant ainsi la productivité et les coûts.

## Concepts clés
- **[01:17] Gestion des modèles Claude** — Utiliser la commande `/model` pour basculer entre les modèles Claude (Opus, Sonnet, Haiku) afin d'optimiser les coûts et la pertinence selon la tâche.
- **[02:16] Rapports d'utilisation de Claude Code** — La commande `/insights` génère un rapport HTML détaillé sur l'utilisation de Claude Code, identifiant les forces, les faiblesses et les suggestions d'amélioration.
- **[03:18] Optimisation du contexte** — La commande `/context` visualise l'utilisation des tokens et des outils MCP chargés, permettant de désactiver les outils inutilisés pour réduire les coûts et améliorer la performance.
- **[05:02] Ajout de serveurs MCP** — Les serveurs MCP (ex: GitHub, Zapier) étendent les capacités de Claude Code, pouvant être ajoutés au niveau du projet, de l'utilisateur ou globalement.
- **[13:30] Création de compétences personnalisées (Skills)** — Une "skill" est un comportement appris par Claude, défini dans un fichier Markdown, permettant d'automatiser des workflows répétables et d'améliorer la cohérence des résultats.
- **[25:54] Sous-agents (Subagents)** — Un sous-agent est un agent IA avec son propre contexte, exécuté en parallèle pour décomposer des tâches complexes et les gérer de manière plus efficace.
- **[33:49] Mémoire persistante avec `Claude.md`** — Créer un fichier `Claude.md` dans la racine du projet permet à Claude de lire et de retenir des informations persistantes entre les sessions.

## Code / Commandes / Prompts (verbatim)

```bash
/model
```
*Contexte : Changer de modèle Claude (Opus, Sonnet, Haiku).*

```bash
/insights
```
*Contexte : Générer un rapport d'analyse des sessions Claude Code.*

```bash
/cost
```
*Contexte : Afficher les coûts d'utilisation actuels de Claude Code.*

```bash
/context
```
*Contexte : Visualiser l'utilisation actuelle du contexte et les outils MCP chargés.*

```bash
/mcp
```
*Contexte : Gérer les serveurs MCP (afficher, activer, désactiver).*

```bash
claude mcp add-json github '{"type":"http","url":"https://api.githubcopilot.com/mcp","headers":{"Authorization":"Bearer YOUR_GITHUB_PAT"}}'
```
*Contexte : Ajouter un serveur MCP GitHub avec un Personal Access Token (PAT).*

```bash
gh repo create Demo --public --source=. --remote=origin --push
```
*Contexte : Créer un nouveau dépôt GitHub public nommé 'Demo' à partir du répertoire actuel et pousser le contenu.*

```
/code-review
```
*Contexte : Invoquer la compétence 'code-review'.*

```
/skills
```
*Contexte : Lister les compétences disponibles.*

```
/agents
```
*Contexte : Gérer les configurations des agents.*

```markdown
---
name: code-review
description: Structured code review following team standards. Use when reviewing code or checking PRs.
---
Follow this structure:
### 1. Security (always first)
- SQL/NoSQL injection, unvalidated input, missing auth, secrets in code, CORS issues
### 2. Error Handling
- Async operations in try/catch, errors logged with context, consistent error format, no empty catches
### 3. Performance
- N+1 queries, missing indexes, unbounded queries, large payloads without pagination
### 4. Code Quality
- Functions under 30 lines, no magic numbers, no 'any' types, dead code removed
### 5. Testing
- Is this testable? Suggest specific test cases if none exist.
For each finding: **Severity** (CRITICAL/WARNING/SUGGESTION), **Location** (file:line), **Issue**
```
*Contexte : Contenu du fichier Markdown de la compétence 'code-review'.*

```markdown
---
name: test-writer
description: Write comprehensive tests for code changes. Use when asked to write tests or when tests are needed after implementation.
model: claude-sonnet-4-20250514
---
You are a testing specialist. Your only job is to write thorough tests.
## Process
1. Read the source file(s) being tested
2. Identify every code path, edge case, and error condition
3. Write tests covering: happy path, validation errors, edge cases, error handling
4. Use the project's existing test framework and patterns
5. Each test should have a clear, descriptive name
## Rules
- One test file per source file
- Group tests with describe blocks by function/method
- Test behavior, not implementation details
- Mock external dependencies (DB, APIs)
- Include at least one test for each error path
```
*Contexte : Prompt système pour le sous-agent 'test-writer' — spécifier le modèle dans le frontmatter YAML d'un agent.*

## Patterns réutilisables
| Pattern | Application | Skill potentiel ? |
|---------|-------------|-------------------|
| Optimisation du coût des modèles Claude | Automation | ✅ |
| Analyse de l'utilisation de Claude Code | Veille | ✅ |
| Gestion du contexte pour l'efficacité | Skills | ✅ |
| Intégration GitHub MCP avec PAT | Automation | ✅ |
| Amélioration capacités via plugins | Skills | ✅ |
| Création de compétences personnalisées | Skills | ✅ |
| Automatisation de la revue de code | Skills | ✅ |
| Gestion visuelle des projets avec Nimbalyst | Veille | ✅ |
| Décomposition de tâches avec sous-agents | Automation | ✅ |
| Audit de documentation par sous-agents | Skills | ✅ |
| Mémoire persistante avec Claude.md et dossiers docs/memory/skills/state | Skills | ✅ |

## Outils / MCP / Apps mentionnés
- **GitHub** — Plateforme de version control et d'hébergement de code → https://github.com
- **Zapier** — Plateforme d'automatisation → https://zapier.com
- **Playwright** — Outil d'automatisation de navigateur et de tests de bout en bout
- **Context7** — Serveur MCP pour la recherche de documentation à jour
- **Superpowers** — Plugin pour le brainstorming, le développement piloté par sous-agents, la revue de code, le TDD
- **Nimbalyst** — Éditeur visuel open-source pour Claude Code et Codex
- **Notion** — Espace de travail pour notes, tâches, bases de données → https://www.notion.so

## Info Anthropic officielle
—

## Warnings
Le plugin 'Superpowers' est mentionné comme étant plus coûteux en tokens et peut ralentir Claude Code, recommandé uniquement avec le plan Max.

## Suite proposée
4 patterns directement actionnables pour Ivan : sous-agents avec modèle spécifié dans frontmatter, structure docs/memory/skills/state, intégration MCP GitHub avec PAT, et revue de code structurée. Distiller via skill-distiller.
