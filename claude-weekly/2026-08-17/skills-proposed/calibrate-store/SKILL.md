---
name: calibrate-store
description: Capitalise les apprentissages d'une session Shopify en mettant à jour les fichiers mémoire et CLAUDE.md du store. À appeler en fin de session.
triggers:
  - /calibrate-store
context: fork
---

# Skill : calibrate-store

Adapté du pattern `/calibrate` de Jay (vidéo gQeRjkb_Hlc - Shift 5 des 6 nouvelles règles Anthropic).

## Ce que fait ce skill

En fin de session de travail sur un store Shopify (TempleTwins ou PURESOLE) :

1. **Review** la conversation courante et extrait :
   - Décisions produit/pricing/fournisseur prises
   - Contraintes ou règles business découvertes
   - Préférences de style/contenu confirmées
   - Problèmes rencontrés et solutions trouvées

2. **Met à jour** les fichiers mémoire du store :
   - `memory/store-prefs.md` : préférences et contraintes
   - `memory/suppliers.md` : infos fournisseurs (PURESOLE)
   - `memory/brand-rules.md` : règles de contenu et ton

3. **Met à jour** le CLAUDE.md du store si de nouvelles règles ont émergé :
   - Ajoute seulement si la règle est récurrente et non-évidente
   - Préfère les guidelines au jugement plutôt que les règles strictes (Shift 1)

4. **Log** la session dans `sessions/YYYY-MM-DD.md` :
   - Résumé des actions
   - Décisions clés
   - Prochaines étapes suggérées

## Source

Issu de l'analyse de : https://www.youtube.com/watch?v=gQeRjkb_Hlc
Semaine : 2026-08-17
