# REVIEW — claude-context-optimizer

## Pourquoi ce skill ?
Issu de la vidéo : Advanced Claude Code Tutorial (Tech With Tim) — https://www.youtube.com/watch?v=uogzSxOw4LU
Patterns extraits : `Optimisation du coût des modèles Claude` + `Analyse de l'utilisation de Claude Code` + `Gestion du contexte pour l'efficacité`
Application pour Ivan : Ivan a beaucoup de MCPs chargés (Shopify, firecrawl, meigen, memory-service, obsidian, together-ai) — probable que certains sont inutiles en session builder ou Tora.

## Score utilité (hérité de Gemini)
9/10 — Ivan mentionne régulièrement des lenteurs et coûts. Ce skill centralise le diagnostic en 3 commandes.

## Comment installer (si validé)
```bash
mv /Users/ivanvasseur/Code/_workspace/ivan-veille/claude-weekly/2026-06-15/skills-proposed/claude-context-optimizer \
   /Users/ivanvasseur/.claude/skills/claude-context-optimizer
```
Puis recharger Claude Code (Cmd+R) ou relancer la session.

## Comment tester
1. "optimise mon contexte Claude Code" → doit lister les MCPs actifs et identifier ceux à désactiver
2. "c'est lent ce soir" → doit proposer 3 actions concrètes (modèle, MCP, compact)
3. "check mes coûts" → doit interpréter /cost et dire si c'est normal ou élevé

## Alternatives considérées
- **`token-optimize`** → compresse le contexte (action), ce skill-ci DIAGNOSTIQUE d'abord — complémentaires, pas doublons
- **Note Obsidian** → trop actionnable pour rester en note, c'est un workflow récurrent

## Risques / limites
- Dépend des commandes natives Claude Code (`/context`, `/cost`, `/insights`) — vérifier disponibilité selon la version
- `/insights` génère un fichier local HTML, pas visible directement dans le chat

## Si rejet
```bash
rm -rf /Users/ivanvasseur/Code/_workspace/ivan-veille/claude-weekly/2026-06-15/skills-proposed/claude-context-optimizer
```
