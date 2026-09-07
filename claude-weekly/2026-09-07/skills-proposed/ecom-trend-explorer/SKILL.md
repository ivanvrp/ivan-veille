# Skill : ecom-trend-explorer

> Proposé le 2026-09-07 — Source : Analyse Gemini #yeMhldEJLN4 (Fable 5.1 agents)
> **Statut : PROPOSITION — À reviewer par Ivan avant déploiement**

## Description

Analyse de tendances marché pour identifier des opportunités produits, niches sous-exploitées et changements de préférences consommateurs — spécialisé streetwear et dropshipping.

## Déclencheur

```
/trend-explore [catégorie] [marché]
```

Exemples :
```
/trend-explore streetwear France Q4-2026
/trend-explore sneakers dropshipping EU automne
/trend-explore accessoires mode homme 18-30 ans
```

## Workflow

1. **Scope definition** : catégorie + marché + horizon temporel
2. **Signal collection** : tendances Google, réseaux sociaux (TikTok/Insta), données de recherche, rapports de vente disponibles
3. **Opportunity scoring** : volume potentiel × niveau de concurrence × adéquation catalogue Ivan
4. **Output** : 5 opportunités rangées par priorité avec score et action suggérée

## Output format

```markdown
## Top opportunités — [catégorie] — [marché]

1. **[Produit/niche]** — Score: 8/10
   - Volume estimé : [tendance]
   - Concurrence : [faible/moyenne/forte]
   - Action : [commander X unités / tester campagne / ajouter au catalogue]

2. ...
```

## Estimation valeur Ivan

⭐⭐⭐⭐ — Remplace 2-3h de recherche manuelle par une analyse structurée en < 2 min.
