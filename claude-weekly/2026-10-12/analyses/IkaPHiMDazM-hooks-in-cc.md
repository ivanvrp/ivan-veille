# Analyse Gemini — IkaPHiMDazM
URL: https://www.youtube.com/watch?v=IkaPHiMDazM

## Résumé exécutif
Les hooks Claude Code permettent d'exécuter des commandes déterministes à des moments précis du cycle de vie. Ils garantissent l'exécution de tâches comme le formatage automatique ou le blocage d'opérations dangereuses, assurant la cohérence et le respect des règles du projet.

## Configuration hooks (verbatim)
```json
{
  "hooks": {
    "PreToolUse": [{
      "matcher": "Bash",
      "hooks": [{"type": "command", "command": "$CLAUDE_PROJECT_DIR/.claude/hooks/block-dangerous-commands.sh"}]
    }],
    "PostToolUse": [{
      "matcher": "Edit|MultiEdit|Write",
      "hooks": [{"type": "command", "command": "$CLAUDE_PROJECT_DIR/.claude/hooks/auto-format.sh", "timeout": 20}]
    }]
  }
}
```

## Script block-dangerous-commands.sh
```bash
COMMAND=$(jq -r '.tool_input.command')
if echo "$COMMAND" | grep -qE "rm\s+(-[a-zA-Z]+\s+)?-rf"; then
  echo "Blocked: destructive rm command" >&2; exit 2
fi
if echo "$COMMAND" | grep -qE "git\s+push\s+.*--force"; then
  echo "Blocked: force push" >&2; exit 2
fi
exit 0
```

## Score utilité 0-10 pour Ivan
**9/10** — Déterminisme = filet de sécurité ultime dev Shopify production.

## Skill_potential
1. `EnforceCodeStyle` (PostToolUse + formateurs Prettier/ESLint)
2. **`ProductionSafetyPolicy`** → **IMPLÉMENTÉ comme production-safety-policy**
3. `AutomatedTaskNotifier` (Notification/Stop → Slack/Discord)
