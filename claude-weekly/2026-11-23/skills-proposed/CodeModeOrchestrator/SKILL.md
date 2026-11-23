# Skill: CodeModeOrchestrator

**Source** : Code Mode Is The Biggest Claude Code Upgrade In a LONG Time (Nov 19 2026)  
**Vidéo** : https://www.youtube.com/watch?v=ziDQNS3usiA  
**Statut** : Proposé — À valider par Ivan avant déploiement

## Description
Exploite le Code Mode expérimental de Claude Code pour générer des scripts parallèles qui chaînent Bash/Read/Edit en un seul appel. Réduit drastiquement les tokens consommés et les allers-retours pour les tâches multi-fichiers.

## Activation requise
```bash
export CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1
```

## Cas d'usage pour Ivan
- Mettre à jour une fonction dans tous les fichiers .liquid d'un thème Shopify
- Scanner + corriger des erreurs SEO techniques en batch
- Analyser des CSV produits volumieux et transformer les données
- Diagnostic rapide : lancer tests + logs + grep en parallèle

## Pattern core
```javascript
// Script type généré par Claude en Code Mode
const files = await $`rg -l "pattern" src`.text();
const targets = files.trim().split("\n");
await Promise.all(targets.map(f => edit(f, patch)));
const tests = await $`npm test`.text();
return { edited: targets.length, tests: tests.includes("PASS") };
```

## Instructions skill (ébauche)
1. Détecter si Code Mode est activé (CLAUDE_CODE_EXPERIMENTAL_CODE_MODE=1)
2. Transformer la requête en script parallèle optimisé
3. Minimiser les outputs retournés au contexte (uniquement métriques clés)
4. Valider avec tests avant de reporter succès
