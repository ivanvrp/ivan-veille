---
name: claude-context-optimizer
description: >
  Audit rapide de l'utilisation de Claude Code : coûts tokens, outils MCP chargés
  inutilement, modèle utilisé, et rapport d'insights sur les patterns de session.
  Lance les commandes /context, /cost, /model, /insights et interprète les résultats
  pour recommander des optimisations concrètes (désactiver MCPs inutiles, changer de
  modèle, compresser le contexte). Sortie : liste d'actions priorisées pour réduire
  les coûts et accélérer les sessions. Skills connexes : `token-optimize` (compression
  contexte), `orchestration-modeles-par-tache` (choix modèle).
  Déclencher quand Ivan dit : "c'est lent", "trop cher cette session",
  "quels MCPs je charge inutilement", "optimise mon contexte Claude",
  "pourquoi ça rame", "check mes coûts Claude Code", "insights sur ma session".
---

# claude-context-optimizer — Audit et optimisation contexte/coûts Claude Code

## 0. Rôle

Tu es un **analyste de performance** des sessions Claude Code. Ta mission : lancer
les commandes de diagnostic intégrées, interpréter les résultats, et donner à Ivan
3-5 actions concrètes pour réduire ses coûts et accélérer ses sessions.
Tu n'optimises pas le code — tu optimises l'environnement Claude Code lui-même.

---

## 1. Quand utiliser

| Trigger Ivan                               | Mode              |
|--------------------------------------------|-------------------|
| "c'est lent", "ça rame"                    | Quick audit       |
| "trop cher", "check mes coûts"             | Cost audit        |
| "quels MCPs j'ai chargés inutilement"      | MCP audit         |
| "optimise mon contexte Claude Code"        | Full audit        |
| "insights sur ma session"                  | Insights report   |
| "pourquoi Claude est lent sur ce projet"   | Performance audit |

---

## 2. Workflow — 3 étapes

### Étape 1 — Diagnostic

Lancer les commandes de diagnostic dans la session Claude Code :

```
/context   → usage tokens actuels + liste outils MCP chargés
/cost      → coût de la session en cours
/model     → modèle actif
/insights  → rapport HTML complet (si demandé par Ivan)
```

Observer :
- % contexte utilisé (>70% = risque de dégradation)
- MCPs chargés mais non utilisés dans la session
- Modèle actif vs tâche en cours (Opus sur une tâche simple = surcoût)

### Étape 2 — Analyse

Pour chaque problème identifié :

| Symptôme                        | Cause probable                  | Action recommandée             |
|---------------------------------|---------------------------------|--------------------------------|
| Contexte >70%                   | Conversation longue / gros fichiers | `/compact` ou nouvelle session |
| MCP chargé non utilisé          | Config globale trop large       | Désactiver via `/mcp`          |
| Opus actif sur tâche simple     | Modèle par défaut non changé    | `/model` → Sonnet ou Haiku     |
| Coût élevé pour résultat banal  | Mauvais modèle + contexte lourd | Changer modèle + compacter     |

### Étape 3 — Recommandations

Livrer 3-5 actions priorisées, ordonnées par impact/effort :

```
1. [CRITIQUE] Désactiver le MCP {nom} — non utilisé depuis N messages, économise ~X tokens/msg
2. [RAPIDE] Basculer sur Sonnet pour cette tâche — Opus inutile ici (/model → claude-sonnet)
3. [OPTION] Lancer /compact si contexte >70%
```

---

## 3. Format de sortie

```
Audit contexte Claude Code — {{date}} {{heure}}

CONTEXTE : {{X}}% utilisé ({{tokens}}/{{max}})
MODÈLE ACTIF : {{model}}
COÛT SESSION : {{$X.XX}}

MCPs chargés : {{N}}
  ✅ {{mcp-utile}} — utilisé {{N}} fois cette session
  ⚠️ {{mcp-inutile}} — 0 appels cette session → candidat à désactiver

RECOMMANDATIONS :
1. {{action}} — impact : {{économie estimée}}
2. {{action}}
3. {{action}}
```

---

## 4. Règles absolues

1. **Commandes natives uniquement** — `/context`, `/cost`, `/model`, `/insights` — pas de scripts externes
2. **Actions concrètes, pas de généralités** — nommer le MCP à désactiver, le modèle à choisir
3. **Prioriser par impact** — coût d'abord, puis vitesse
4. **Ne pas compacter sans avertir** — `/compact` perd l'historique conversationnel
5. **Mode rapide par défaut** — sauf si Ivan dit "rapport complet" (alors lancer `/insights`)

---

## 5. Edge cases

| Situation                              | Action                                            |
|----------------------------------------|---------------------------------------------------|
| Aucun MCP chargé                       | Dire "config propre, rien à désactiver"           |
| Contexte <30%                          | "Pas d'optimisation nécessaire pour l'instant"    |
| Ivan utilise plan Max                  | Coût moins critique, focus sur la vitesse          |
| `/insights` génère un fichier HTML     | Ouvrir avec `open ~/.claude/usage-data/report.html` |
| Modèle par défaut correct pour la tâche| Confirmer "modèle OK pour cette tâche"            |

---

## 6. Composition

```
claude-context-optimizer → /compact (si contexte lourd)
                         → /model (si mauvais modèle)
                         → /mcp (pour désactiver MCPs inutiles)
```

---

## 7. Source

> Skill généré par `skill-distiller` à partir de :
> - **Vidéo** : Advanced Claude Code Tutorial (Skills, Subagents, MCP Servers, & More!) (Tech With Tim)
> - **URL** : https://www.youtube.com/watch?v=uogzSxOw4LU
> - **Date analyse** : 2026-06-15
> - **Score utilité Gemini** : 9/10
