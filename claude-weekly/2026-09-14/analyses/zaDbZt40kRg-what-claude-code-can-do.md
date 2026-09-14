# What Claude Code Can Do That You Haven't Tried — Gui Ferreira — NDC AI 2026
**URL:** https://www.youtube.com/watch?v=zaDbZt40kRg
**Date:** Jul 1, 2026 (NDC AI conference)
**Score Ivan:** 9/10

## Résumé exécutif
Conférence NDC AI 2026 par Gui Ferreira couvrant les 4 piliers de Claude Code : Configuration, Workflow Quotidien, Couche Plateforme et Au-delà du Code. La plupart des utilisateurs n'exploitent que 5-10% des 96 commandes slash disponibles. Très orientée techniques avancées et optimisation concrète.

## Concepts clés avec timestamps
- [00:30] 5-10% seulement des capacités utilisées : 96 commandes slash disponibles
- [04:54] CLAUDE.md : cœur de la configuration agent, règles + frameworks + commandes
- [05:31] Éviter duplication : `@fichier.md` / `@schema.json` dans CLAUDE.md
- [07:17] Limite CLAUDE.md trop grand : dégradation perf 3%, coût +20% (agents obéissent, ne filtrent pas)
- [08:24] Audit CLAUDE.md en 3 questions : nécessaire chaque tâche ? → reste. Tâche spécifique ? → skill/rules. Agent le trouve seul ? → supprimer.
- [11:18] 3 portées config : CLAUDE.md (repo partagé), CLAUDE.local.md (perso git-ignored), ~/.claude/CLAUDE.md (global)
- [13:51] Garder secrets hors contexte : `permissions.deny` dans settings.json
- [15:06] `/statusline` : branche Git + modèle + taille contexte en permanence
- [17:36] Éditer plan avec Ctrl+G avant exécution : évite prompts répétés
- [19:12] `AskUserQuestion` : force Claude à poser questions pour clarifier
- [21:24] `Esc+Esc` ou `/rewind` : revenir à un checkpoint précédent
- [22:28] `/model` : changer modèle en cours de tâche (Opus complexe, Sonnet simple)
- [22:57] `/effort high/low` : ajuster profondeur raisonnement
- [24:47] `/btw` : question secondaire sans interrompre tâche principale
- [28:51] `/compact` : compacter conversation dégradée en résumé structuré
- [31:26] `! commande` : lancer shell depuis Claude, output intégré au contexte
- [33:01] `--continue` / `--resume` : reprendre session précédente avec tout le contexte
- [34:01] `/remote-control` : transférer session terminal → desktop/mobile
- [35:43] `/voice` : dictée vocale pour interagir avec Claude
- [36:56] Screenshots : glisser-déposer ou presse-papiers pour analyse visuelle
- [38:50] Hooks dans settings.json : actions auto après événements (ex: tests après code write)
- [39:55] Skills : dossiers avec scripts, templates, références pour tâches complexes répétitives
- [46:42] `/batch` : tâche complexe → petites unités gérées en parallèle sur worktrees Git séparés
- [47:30] `/simplify` : 3 agents parallèles pour réviser complexité/style du code récent
- [48:21] `/loop` : Claude surveille CI/CD ou tâche périodique, libère temps solo founder

## Code/prompts/commandes verbatim
```
# Audit CLAUDE.md (3 questions)
1. Nécessaire pour CHAQUE tâche ? → Garde dans CLAUDE.md
2. Tâche spécifique/occasionnelle ? → Crée un skill ou fichier rules
3. Claude le trouve seul ? → Supprime

# Pattern hooks settings.json
"hooks": {
  "PostToolUse": [{"matcher": "Write|Edit", "hooks": [{"type": "command", "command": "npm test"}]}]
}

# Commandes quick-reference
/model opus          # Switch modèle
/effort high         # Raisonnement max
/btw <question>      # Question parallèle
/compact             # Reset conversation dégradée
/batch               # Refacto à l'échelle codebase
/simplify            # 3 agents revue code
/loop 5m /check-ci   # CI babysitting toutes 5min
```

## Patterns réutilisables pour Ivan
1. **CLAUDE.md audit** : auditer son CLAUDE.md avec les 3 questions → performances + économies de coût
2. **Skills pour tâches répétitives** : fiche produit, posts social, SAV → dossiers skills dans .claude/skills/
3. **Hooks post-deploy** : déclencher vérification Shopify après update fichiers
4. **/loop pour monitoring** : surveiller résultats pub Meta/Google, alerter si CPA monte
5. **/btw pour multi-tâche** : question sur analytics pendant que Claude travaille sur une description
6. **/remote-control** : commencer session ordinateur, continuer sur mobile depuis Shopify dashboard
7. **Screenshots → révisions UI** : partager screenshot store pour demander corrections CSS/layout

## Skill_potential
**`/shopify-ops-monitor`** : Hook + loop combiné pour surveiller les métriques Shopify (stock critique, commandes bloquées, CPA pub) et envoyer alertes ntfy. Utilise `/loop` pour polling périodique via API Shopify MCP.

**`/claude-md-auditor`** : Skill qui analyse le CLAUDE.md du projet avec les 3 questions de l'audit, identifie ce qui peut être déplacé en skills ou supprimé, génère un rapport d'optimisation + CLAUDE.md nettoyé.

## Score utilité 0-10 pour Ivan
**9/10** — Conférence dense avec techniques avancées directement applicables. Le trio CLAUDE.md audit + hooks + /loop est un game-changer pour un solo founder qui veut automatiser sans recruter.
