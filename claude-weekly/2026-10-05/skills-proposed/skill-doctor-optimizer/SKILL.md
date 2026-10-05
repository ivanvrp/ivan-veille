# Skill Proposal: skill-doctor-optimizer

> **Proposé par**: veille-claude weekly 2026-10-05
> **Source**: Analyse Gemini — vidéo u1dW4z5Ye90 (Claude Code 3.0 features)
> **Statut**: À reviewer par Ivan — skill simple, peu de risques

## Description

Un skill de routine d'optimisation qui utilise `/skill-doctor` et `claude plugin eval` pour auditer régulièrement le coût en tokens des skills et plugins d'Ivan, et suggère lesquels désactiver ou optimiser.

## Trigger

Invocation : `/optimize-skills` ou `/skill-audit`

Cadence suggérée : mensuelle, ou après ajout de nouveaux skills/plugins.

## Comportement

1. Lance `/skill-doctor` → liste les skills avec coût tokens
2. Lance `claude plugin eval .` sur les plugins actifs
3. Analyse les résultats : identifie les skills > 5% du contexte total
4. Propose un plan d'action :
   - Skills à désactiver (jamais utilisés ou trop coûteux)
   - Skills à raccourcir (SKILL.md trop verbeux)
   - Skills à conserver tels quels

## Pourquoi ce skill

Ivan accumule des skills. Sans audit, le contexte gonfle et les coûts augmentent sans s'en rendre compte. Ce skill force une revue régulière.

## Implémentation

Skill Claude simple dans `.claude/skills/skill-audit/SKILL.md` — pas de code, juste les instructions pour Claude.

## Risques

Faibles. Lecture seule, pas d'actions automatiques. Ivan décide quoi désactiver.
