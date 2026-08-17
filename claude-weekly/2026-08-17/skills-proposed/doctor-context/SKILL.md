---
name: doctor-context
description: Audit de santé du système agentique d'Ivan selon les 6 nouvelles règles Anthropic. Vérifie CLAUDE.md, skills, mémoire et structure.
triggers:
  - /doctor-context
---

# Skill : doctor-context

Version légère du `/doctor-plus` de Jay (adapté aux 6 nouvelles règles Anthropic pour Claude 5).

## Ce que fait ce skill

Effectue un bilan de santé du système agentique selon les 6 shifts Anthropic :

### Shift 1 — Règles → Jugement
- [ ] Flag les occurrences de NEVER/ALWAYS/MANDATORY dans les SKILL.md
- [ ] Suggère de les remplacer par des guidelines ouvertes

### Shift 2 — Exemples → Interfaces
- [ ] Détecte les templates inline dans les skills (blocs fencés > 5)
- [ ] Suggère de les déplacer vers `references/`

### Shift 3 — Tout upfront → Divulgation progressive
- [ ] Vérifie que CLAUDE.md est un routeur (pas > 200 lignes)
- [ ] Flag les SKILL.md > 500 lignes
- [ ] Vérifie l'existence de fichiers département (TempleTwins/, PURESOLE/, etc.)

### Shift 4 — Répétition → Descriptions simples
- [ ] Détecte les instructions dupliquées entre CLAUDE.md et skills
- [ ] Suggère suppressions

### Shift 5 — Mémoire manuelle → Mémoire auto
- [ ] Vérifie que `/calibrate-store` est configuré
- [ ] Liste les infos dans CLAUDE.md qui devraient être en mémoire auto

### Shift 6 — Specs Markdown → Références riches
- [ ] Identifie les specs visuelles dans des .md qui bénéficieraient du format HTML
- [ ] Suggère la création de `references/brand-*.html`

## Output

Génère un rapport `claude-weekly/YYYY-MM-DD/doctor-report.md` avec :
- Tableau des 6 shifts avec verdict (OK/FLAG/SKIP)
- Pire offenseur par shift
- Fix suggéré (1 ligne)
- Score global de santé /10

## Source

Issu de l'analyse de : https://www.youtube.com/watch?v=gQeRjkb_Hlc
Semaine : 2026-08-17
