# Skill: claude-weekly-digest-enhancer

## Description
Enrichit automatiquement le digest claude-weekly avec les insights Gemini extraits des vidéos must-watch, structurés pour le contexte Ivan (TempleTwins streetwear Shopify + PURESOLE dropship).

## Trigger
Déclenché automatiquement en Phase 3 de la routine veille-claude-weekly quand les analyses Gemini sont disponibles. Consolide les sections Skill_potential de chaque analyse.

## Format de sortie attendu
Pour chaque vidéo analysée :
```markdown
### [titre-vidéo]
**TL;DR** : [1 phrase]
**Timestamp clé** : [mm:ss] concept actionnable
**Action Ivan** : [micro-action concrète]
**Skill potentiel** : [nom-du-skill ou "Aucun"]
```

## Condition d'activation
- Gemini API disponible (non 503/quota)
- Au moins 1 analyse réussie sur les 5 must-watch
- Section Skill_potential non vide

## Notes
- Créé suite à l'indisponibilité Gemini le 2026-06-01
- Proposé le 2026-06-01 | NON déployé, review Ivan requis
