# Skill : claude-md-auditor
**Source :** Analyse vidéo zaDbZt40kRg (What Claude Code Can Do — NDC AI 2026)
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Objectif
Analyse le CLAUDE.md du projet courant avec la méthode des 3 questions de Gui Ferreira → rapport d'optimisation + CLAUDE.md nettoyé.

## Ce que fait le skill
1. Lit le CLAUDE.md du projet
2. Pour chaque section, applique l'audit en 3 questions :
   - Nécessaire pour CHAQUE tâche ? → Garde
   - Tâche spécifique/occasionnelle ? → Recommande de déplacer en skill
   - Claude le trouve seul en lisant le code ? → Recommande suppression
3. Génère rapport avec :
   - Sections à garder
   - Sections à déplacer en skill (avec ébauche de skill)
   - Sections à supprimer
   - Estimation économie de tokens (coût)
4. Propose CLAUDE.md optimisé (avec diff)

## Usage
```
/claude-md-auditor
/claude-md-auditor --apply  # Applique les recommandations après confirmation
```

## Valeur pour Ivan
CLAUDE.md trop large = dégradation performances 3% + surcoût 20%. Ce skill maintient la configuration efficace.

## Notes implémentation
- Skill auto-applicable (peut lire ses propres instructions)
- Modèle recommandé : Opus (analyse nuancée)
- Fréquence : 1x/mois ou après ajout de nouvelles instructions
