# Analyse Gemini — Claude Code Subagents are Absolutely Insane

**URL :** https://www.youtube.com/watch?v=sNI18nzwgn8  
**Modèle :** gemini-2.5-flash  
**Date analyse :** 2026-07-27  

## Résumé exécutif
La vidéo démontre l'utilisation des sub-agents dans Claude Code CLI pour maintenir la fenêtre de contexte du thread principal courte et lancer des recherches/implémentations en parallèle. Les sub-agents travaillent dans leur propre contexte isolé, permettant de lancer 5-10 agents simultanément pour des tâches spécifiques sans polluer le thread principal.

## Concepts clés avec timestamps
- [00:00] Introduction sub-agents : outil puissant pour "mini-agents" spécialisés, contexte court = meilleurs résultats
- [00:19] Limites thread principal : saturation rapide de la fenêtre contexte dégrade la qualité LLM
- [00:55] /agents : lancer sub-agents sur tâches finies avec contexte isolé
- [02:39] Création agents personnalisés : /agents → create → nom, objectif, outils, modèle, prompt système
- [04:35] Exécution concurrente : 5 ou 10 agents lancés simultanément sur différentes parties du codebase
- [05:19] Isolation contexte : travail sub-agents ne pollue pas le thread principal
- [07:03] Amélioration performances : contexte principal 30% → 16%, meilleurs outputs

## Code/prompts/commandes verbatim
```
# Recherche auth/authorization
Return me a list of all the places where we are doing authentication or authorization. I just want a concise list of files.

# Lancer 5 file-finder agents
Can you please kick off five File Finder agents to return me a list of all the places where we are doing authentication or authorization in this application.

# Lancer 10 security scanners
Please kick off 10 Security Vulnerability Scanner Agents to review these files and return us a list of concise things that we could potentially fix.

# Lancer 10 clean-code-architects
Kick off 10 Clean Code Architect agents to try to address and implement all of these security vulnerabilities.
```

**Config agent "file-finder" :**
- Modèle : Haiku (rapide)
- Description : "Help me find files that are related to a particular task or a research objective."

**Config agent "security-vulnerability-scanner" :**
- Modèle : Opus
- Description : "Help me research code and find any security vulnerabilities and then just return me a concise list of things that we could fix."

**Config agent "clean-code-architect" :**
- Modèle : Opus
- Description : "Help me implement code. Make it clean, reusable, DRY, well maintainable."

## Patterns réutilisables pour Ivan
- **Shopify-Theme-Explorer (Haiku, x5)** : Parcourir thème TempleTwins en parallèle → trouver tous les fichiers liés à [fonctionnalité] sans saturer le contexte
- **App-Security-Auditor (Opus, x5)** : Scanner différentes sections de son app PURESOLE pour vulnérabilités OWASP
- **Shopify-Code-Craftsman (Opus, x5)** : Implémenter nouvelle fonctionnalité avec agents dédiés propreté/maintenabilité
- **Bug-Hunter distribué** : Chaque agent explore une hypothèse de cause pour un bug difficile

## Skill_potential
1. **`shopify-parallel-audit`** — Lance N agents pour auditer différentes sections d'un thème Shopify (products, checkout, collections) et consolide les findings. Modèle Haiku pour recherche, Opus pour implémentation.
2. **`ecommerce-feature-architect`** — Prend une description de fonctionnalité e-commerce, lance agents: 1 recherche code existant + N implémentation code propre, output code Shopify-ready (Liquid, JS, API).

## Score utilité 0-10 pour Ivan
**9/10** — La gestion du contexte par sub-agents est fondamentale pour un solo founder qui gère code + contenu + analytics. Gain de temps massif sur audits et implémentations complexes.
