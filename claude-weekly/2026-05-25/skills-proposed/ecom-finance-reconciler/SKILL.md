---
name: ecom-finance-reconciler
description: Automatise le classement, le renommage et la synthèse de documents financiers et opérationnels pour e-commerce — factures fournisseurs PURESOLE, rapports de vente TempleTwins, numéros de suivi dropshipping. Utilise /goal avec "hard cap" pour protéger le budget tokens.
triggers:
  - "Je dois classer toutes les factures de mes fournisseurs dropshipping pour PURESOLE par mois et par catégorie"
  - "J'aimerais que tous mes rapports de ventes mensuels de TempleTwins soient consolidés en un CSV avec les KPIs"
  - "Mes reçus de frais marketing sont éparpillés, renomme-les et organise-les par année pour ma comptabilité"
  - "Vérifie les numéros de suivi de toutes les commandes PURESOLE en attente et génère un rapport d'anomalies"
  - "Standardise les descriptions produits dans mon dossier pour qu'elles aient toutes le bon format SEO"
source_video: https://www.youtube.com/watch?v=2qlZsi8eh3s
source_analysis: ../analyses/2qlZsi8eh3s-goal-command-explained.md
proposed: 2026-05-25
status: À VALIDER — copier vers ~/.claude/skills/ pour activer
---

# Skill : ecom-finance-reconciler

## Pourquoi ce skill existe

Déduit de la vidéo "Claude Goal Command Explained" (mai 2026).
La commande `/goal` avec une "ligne d'arrivée vérifiable" + hard cap permet de déléguer des tâches
administratives longues sans risque de boucles infinies.

## Patterns clés

### Règle d'or du /goal : ligne d'arrivée vérifiable
```text
BAD : "Classe mes fichiers"  → le Boss ne peut pas vérifier
GOOD: "Renomme tous les PDF en YYYY-MM-DD_Fournisseur.pdf ET génère recap.csv.
       DONE quand recap.csv existe ET dossier source est vide.
       Stop after 30 turns or 45 minutes."
```

### Hard cap obligatoire
Toujours inclure : `Stop after N turns or X minutes.`

## Templates /goal prêts à l'emploi

### 1. Classement factures fournisseurs PURESOLE
```text
/goal Renomme tous les fichiers PDF dans ~/Documents/Factures-Fournisseurs/ 
au format YYYY-MM-DD_NomFournisseur.pdf en lisant la date et le nom du fournisseur 
dans chaque fichier. Génère recap_factures_YYYY-MM.csv avec : nom_original, 
nouveau_nom, date, fournisseur, montant_total. 
DONE quand recap_factures.csv existe et contient une ligne par fichier traité.
Stop after 100 turns or 60 minutes.
```

### 2. Consolidation rapports ventes TempleTwins
```text
/goal Agrège les données de vente Shopify depuis les CSV dans ~/Reports/TT-Sales/ 
dans rapport_ventes_consolidé.csv avec colonnes : SKU, nom_produit, qte_vendue, 
CA_total, marge_estimée, mois. Calcule les top 10 produits par CA.
DONE quand rapport_ventes_consolidé.csv existe et contient > 50 lignes.
Stop after 20 turns or 30 minutes.
```

### 3. Vérification numéros de suivi dropshipping
```text
/goal Pour chaque commande dans commandes_en_attente.csv, vérifie le numéro 
de suivi via l'API {transporteur}. Génère commandes_statuts.csv avec colonnes : 
commande_id, tracking, statut, dernière_mise_à_jour, anomalie (oui/non).
DONE quand commandes_statuts.csv contient autant de lignes que commandes_en_attente.csv.
Stop after 100 API calls or 30 minutes.
```

## Workflow du skill

1. **Demande à Ivan** : type de tâche (factures / rapports / suivi), dossier source, format de sortie souhaité
2. **Construit le prompt /goal** : avec ligne d'arrivée vérifiable + hard cap + dossier isolé
3. **Configure les prérequis** : vérifie Auto-Approve activé + permissions terminal
4. **Lance /goal** en arrière-plan
5. **Monitoring** : rappelle d'utiliser `/usage` pour surveiller la consommation tokens
6. **Rapport de complétion** : résumé des fichiers traités + CSV généré

## Validation requise

**Ivan doit :**
1. Tester avec un dossier de 3-5 fichiers avant de lancer sur l'ensemble
2. Vérifier que Auto-Approve est activé dans Claude Code
3. Copier vers `~/.claude/skills/ecom-finance-reconciler.md` pour activer
4. Déclencher avec : "Classe toutes mes factures fournisseurs PURESOLE"
