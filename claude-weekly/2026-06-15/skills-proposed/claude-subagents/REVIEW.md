# REVIEW — claude-subagents

## Pourquoi ce skill ?
Issu de la vidéo : Advanced Claude Code Tutorial (Tech With Tim) — https://www.youtube.com/watch?v=uogzSxOw4LU
Pattern extrait : `Décomposition de tâches avec des sous-agents` + `Audit de documentation par sous-agents`
Application pour Ivan : fan-out pour des tâches batch (10 fiches produit Shopify en parallèle, audit de toute la codebase Tora, génération de variantes copy ads).

## Score utilité (hérité de Gemini)
9/10 — Directement applicable pour accélérer les tâches répétitives/parallélisables qu'Ivan fait déjà séquentiellement.

## Comment installer (si validé)
```bash
mv /Users/ivanvasseur/Code/_workspace/ivan-veille/claude-weekly/2026-06-15/skills-proposed/claude-subagents \
   /Users/ivanvasseur/.claude/skills/claude-subagents
```
Puis recharger Claude Code (Cmd+R) ou relancer la session.

## Comment tester
1. "crée un sous-agent test-writer pour les fichiers TypeScript de mon projet Tora" → doit créer `.claude/agents/test-writer.md` avec `model: claude-sonnet-4-20250514`
2. "lance en parallèle 3 agents, chacun analyse une vidéo de ma liste" → doit générer 3 fichiers agents distincts
3. "décompose l'audit SEO de 10 pages produit en agents" → fan-out pattern, 10 agents ou 2 batches de 5

## Alternatives considérées
- **Skill `prompt-engineer`** → crée des prompts mais pas des agents Claude Code avec frontmatter YAML — scope différent
- **Note Obsidian seule** → le pattern est trop structuré et répétable pour rester en note

## Risques / limites
- Nécessite Claude Code ≥ version supportant les agents (`.claude/agents/`)
- La description de l'agent dans le frontmatter doit être soigneusement rédigée pour le routing automatique
- Si le contexte maître déborde (>5 agents simultanés), les résultats se dégradent

## Si rejet
```bash
rm -rf /Users/ivanvasseur/Code/_workspace/ivan-veille/claude-weekly/2026-06-15/skills-proposed/claude-subagents
```
