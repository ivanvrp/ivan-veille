# Skill proposé : loop-library-shopify

**Source** : Loop Library Matthew Berman (https://www.youtube.com/watch?v=9QaD8Avfu2Q + https://forwardfuture.com/)
**Statut** : À REVIEW par Ivan (jamais déployé auto)
**Priorité estimée** : Moyenne

---

## Problème résolu

Adapter les loops génériques de Matthew Berman au contexte spécifique e-commerce Shopify d'Ivan. Les templates originaux sont conçus pour dev — ce skill les "shopifie" pour TempleTwins et PURESOLE.

## Ce que fait ce skill

Bibliothèque de loops Shopify prêts à l'emploi :

### Loop 1 : Weekly Analytics Report
```
Analyse les 7 derniers jours Shopify (ShopifyQL):
- CA par canal (organic, direct, social)
- Top 5 produits vendus
- Taux conversion par collection
- Comparaison semaine précédente
Génère un rapport markdown envoyé par mail (via MCP email si configuré)
```

### Loop 2 : Competitor Spy Loop
```
Pour chaque concurrent listé dans CLAUDE.md :
- Vérifie s'il y a de nouveaux produits (via WebSearch)
- Compare prix avec catalogue TempleTwins
- Identifie les gaps d'opportunité
- Log dans competitors-log.md
```

### Loop 3 : Content Calendar Loop
```
Génère 30 jours de contenu social pour TempleTwins/PURESOLE :
- 3 posts Instagram/TikTok par semaine
- Copy court (< 150 mots) + hashtags + visuel suggestion
- Cohérent avec drops planifiés (depuis CLAUDE.md)
```

## Usage type

```
/loop-library-shopify weekly-report
/loop-library-shopify competitor-spy
/loop-library-shopify content-calendar mois=juillet
```

## Prérequis

- MCP Shopify configuré
- CLAUDE.md avec : liste concurrents, calendrier drops, ton de marque
- Optionnel : MCP email pour envoi rapport

## Note

Vérifier la Loop Library sur https://forwardfuture.com/ pour voir si des templates encore plus pertinents ont été ajoutés depuis le 18 juin 2026.
