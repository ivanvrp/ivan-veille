# Analyse Gemini — Artifacts in Claude Code: share your work as it happens

**Vidéo** : https://www.youtube.com/watch?v=m7TJqx8CYG8
**Source** : Anthropic officiel
**Date** : 18 juin 2026
**Note** : Analyse partiellement capturée (réponse Gemini tronquée + service surchargé au 2ème appel)

---

## Résumé exécutif
Claude Code peut analyser des données d'utilisation pour identifier les points de décrochage dans un tunnel de conversion, proposer des solutions UX concrètes avec maquettes, et générer des rapports HTML interactifs et partageables en temps réel. L'artifact est accessible via un lien `claude.ai/code/artifact/` sans compte Claude requis.

## Concepts clés avec timestamps
- **[00:00] Commande de recherche** : L'utilisateur demande à Claude Code de rechercher les points de décrochage depuis la v4.2 et mettre à jour un tableau de bord.
- **[00:03] Analyse des cohortes** : Claude exécute `Bash(make research-cohorts)`, analyse 90 jours de télémétrie sur 6 cohortes, identifie le processus d'exportation comme étape la plus faible (cohorte "Pro" particulièrement affectée).
- **[00:05] Diagnostic** : Taux d'achèvement export : 27,8%. Problème = l'export est perçu comme un paywall.
- **[00:10] Génération artifact HTML** : `full-pass-data-dropoff.html` — rapport interactif avec tunnel par étape, comparaison Pro vs Free, replays, notes remboursement. URL : `claude.ai/code/artifact/`.
- **[00:14] Visualisation** : 68% d'échec en moins de 3 secondes sur l'étape export.
- **[00:17] Solution UX** : Prompt — "Proposer une solution UX pour corriger le décrochage pendant l'export."
- **[00:20] Proposition** : Revenir au défaut "Standard - gratuit", demander upgrade APRÈS export réussi, tests A/B 14 jours.
- **[00:21] Artifact mis à jour** : `acme-funnel-fix.html` avec maquettes "4.2 Current" vs "4.3.1 Proposed" côte à côte.
- **[00:25] Partage** : Lien partageable, toujours à jour, accessible sans compte.

## Code/prompts/commandes verbatim
```bash
Bash(make research-cohorts)
```
Fichiers : `full-pass-data-dropoff.html`, `acme-funnel-fix.html`, `acme-monitor.json`

## Patterns réutilisables pour Ivan
1. **Funnel Shopify → artifact** : Connecter Shopify analytics, demander à Claude de générer un rapport HTML interactif sur les dropoffs product→cart→checkout→payment pour TempleTwins.
2. **Dashboard dropship PURESOLE** : Artifact de suivi commandes (stocks fournisseurs, délais, retours) mis à jour par scripts.
3. **UX audit express** : Screenshots UI + données session → maquettes avant/après + plan A/B test.
4. **Rapport partageable** : Partager avec prestataires/agences sans accès repo via lien artifact.

## Skill_potential
**Skill proposé : `shopify-funnel-artifact`**
Skill Claude Code qui :
1. Se connecte au MCP Shopify pour extraire données analytics/conversion
2. Analyse les dropoffs par étape (product → cart → checkout → payment)
3. Génère un artifact HTML interactif : visualisations, hypothèses, propositions A/B
4. Produit un lien partageable pour prestataires

## Score utilité 0-10 pour Ivan
**9/10** — Feature directement applicable : rapports de conversion stores Shopify, partage prestataires, itération UX sans outils externes.
