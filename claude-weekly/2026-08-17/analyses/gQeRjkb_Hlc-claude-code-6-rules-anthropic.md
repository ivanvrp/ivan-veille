# Analyse Gemini — "Claude Code Just Changed Forever (6 NEW Rules by Anthropic Engineers)"
**URL:** https://www.youtube.com/watch?v=gQeRjkb_Hlc
**Analysé le:** 2026-08-17

## Résumé exécutif
Cette vidéo décrypte un article majeur d'un ingénieur d'Anthropic sur les "nouvelles règles de l'ingénierie de contexte" pour les modèles Claude 5. Elle met en lumière six changements fondamentaux dans la façon d'interagir avec les IA, passant de la rigidité à plus de jugement et d'efficacité. L'objectif est d'optimiser les systèmes d'IA ("Second Cerveau" ou "systèmes opératifs agentiques") pour des résultats plus rapides, moins coûteux et de meilleure qualité.

## Concepts clés avec timestamps

- [0:45] **Introduction à l'ingénierie de contexte** : le prompt n'est qu'une petite partie du contexte global de l'IA (Applications, Routines, Mémoire, Compétences).
- [1:29] **Framework ARMS** (Applications, Routines, Mémoire, Compétences) : organiser le contexte de l'IA — les Skills sont des SOPs invocables via commandes.
- [2:45] **80% du prompt système supprimé** : Anthropic a retiré >80% du prompt système de Claude Code pour Opus 5/Fable 5 sans perte de performance — les modèles sont assez intelligents.
- [3:20] **Score Claude 5** : 61% sur l'Artificial Analysis Intelligence Index vs 31% pour Opus 4 — doublement en un an.
- [5:38] **Shift 1 — Règles → Jugement** : trop de règles contraignent les modèles intelligents. Nouveau conseil : "Write code that reads like the surrounding code: match its comment density, naming, and idiom."
- [8:24] **Shift 2 — Exemples → Interfaces** : créer des "Brand Books" HTML au lieu de donner des exemples figés — lignes directrices vs copies.
- [10:50] **Shift 3 — Tout upfront → Divulgation progressive** : CLAUDE.md comme routeur vers un arbre de fichiers spécifiques — économie de tokens, pas de contexte inutile.
- [15:02] **Shift 4 — Répétition → Descriptions simples** : les modèles intelligents n'ont plus besoin de répétitions; descriptions d'outils concises et directes.
- [16:23] **Shift 5 — Mémoire manuelle → Mémoire automatique** : Claude enregistre automatiquement les souvenirs pertinents. Skill `/calibrate` pour capitaliser en fin de session.
- [18:04] **Shift 6 — Specs simples → Références riches** : préférer les artefacts HTML aux Markdown simples pour les design systems/spécifications visuelles.
- [19:35] **Outil `/doctor-plus`** : skill custom de Jay (en plus du `/doctor` natif Anthropic) qui vérifie l'alignement de la config avec les 6 nouvelles règles — identifie les goulots, suggère des corrections.

## Code/prompts verbatim

**Ancien prompt système (trop rigide) :**
```
In code: default to writing no comments. Never write multi-paragraph
docstrings or multi-line comment blocks — one short line max.
```

**Nouveau prompt système (jugement) :**
```
Write code that reads like the surrounding code: match its comment density, naming, and idiom.
```

**Skill "surprise-me" (Shift 1) :**
```markdown
Ambition is ramped up front. The brief is "demonstrate extreme capability, taste, artistic flavor" - not "make a page." Aim every decision at showcase, not adequate.
```

**Skill `/calibrate` (Shift 5) :**
```markdown
Review the current conversation and applies the best safe updates to skills,
CLAUDE.md rules, memory, or workflows based on what just happened. Jay only
needs to pick manually when he asks for review/suggest/re-apply mode.
```

**Rapport `/doctor-plus` (exemple) :**
```
Shift 1 Rules→judgement | FLAG | SKILL.md - 37 NEVER/ALWAYS/MANDATORY hits | Demote workflow-preference MANDATORYs to plain statements.
Shift 3 Upfront→progressive | FLAG | last30days/SKILL.md - 2090 lines total | Transform in router.
```

## Patterns réutilisables pour Ivan

1. **CLAUDE.md comme routeur** → PURESOLE et TempleTwins ont chacun leur "département" séparé, évitant de charger tout le contexte à chaque session.
2. **Brand Book HTML** → créer un `references/brand-templetwins.html` et `references/brand-puresole.html` qui servent d'interface de design pour toutes les créations visuelles (landing pages, emails, ads).
3. **Skill `/calibrate`** → à la fin de chaque session de travail sur les stores, appeler `/calibrate` pour capitaliser les apprentissages Shopify automatiquement.
4. **Descriptions de skills concises** → auditer ses SKILL.md et supprimer les règles NEVER/ALWAYS/MANDATORY qui contraignent Claude 5.
5. **Mémoire automatique** → laisser Claude mémoriser les préférences de pricing, fournisseurs, seuils de marge — ne plus les répéter à chaque session.

## Skill_potential

**Skill proposé : `/calibrate-store`**
Adaptation du pattern `/calibrate` pour solo founder e-commerce. En fin de session sur un store Shopify, le skill :
1. Review la conversation et extrait les décisions produit/pricing/fournisseur
2. Met à jour les fichiers mémoire du store (préférences, contraintes, insights)
3. Met à jour le CLAUDE.md du store si de nouvelles règles ont émergé
4. Log les actions faites dans un fichier `sessions/YYYY-MM-DD.md`

**Skill proposé : `/doctor-context`**
Version légère du `/doctor-plus` adaptée à la structure d'Ivan :
- Vérifie que CLAUDE.md est un routeur (pas un monolithe)
- Flag les SKILL.md trop longs (>500 lignes)
- Vérifie les 6 shifts pour chaque skill
- Génère un rapport de santé du système agentique d'Ivan

## Score utilité 0-10

**9/10** — Informations de première main d'un ingénieur Anthropic, directement applicables. Les 6 shifts restructurent complètement l'approche des SKILL.md et CLAUDE.md. Le pattern `/calibrate` et le Brand Book HTML sont immédiatement utilisables pour TempleTwins/PURESOLE.
