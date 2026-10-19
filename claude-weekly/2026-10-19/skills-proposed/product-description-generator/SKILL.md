# Skill : product-description-generator

> ⚠️ PROPOSÉ — À valider manuellement par Ivan avant déploiement

## Description
Génère des descriptions de produits claires, engageantes et optimisées SEO pour des boutiques Shopify (streetwear, dropshipping). Suit les meilleures pratiques de rédaction pour maximiser les conversions et la visibilité organique.

## Source
Extrait de l'analyse vidéo `jzf7DQa2CAc` — "How I Use Claude Code With Skills, MCP, Agents & Plugins"

## Entrée requise
- Nom du produit
- Caractéristiques clés (matière, dimensions, coloris, usage)
- Public cible (ex: streetwear 18-28 ans, acheteur dropship)
- Ton de voix (ex: "jeune et tendance", "premium et épuré")
- Mots-clés SEO (optionnels)

## Instructions Claude

Quand on te demande de générer une description de produit pour TempleTwins ou PURESOLE :

1. Analyse les informations fournies sur le produit
2. Si mots-clés SEO non fournis, identifie les 3-5 termes pertinents pour la niche (streetwear / dropshipping)
3. Rédige :
   - **Titre produit** : accrocheur, 60-80 caractères, mot-clé principal en tête
   - **Description courte** (above the fold) : 1-2 phrases percutantes, bénéfice principal
   - **Description complète** : 100-150 mots, structure bénéfices → caractéristiques → usage → CTA
4. Respecte ces règles de style :
   - Langage actif, pas de superlatifs excessifs
   - Max 2-3 phrases par paragraphe
   - Éviter le jargon non expliqué
5. Intègre un appel à l'action clair et court
6. Format : Markdown prêt pour import Shopify

## Format de sortie
```markdown
# [Titre produit]

[Description courte — 1-2 phrases]

## Détails
[Description complète]

**[CTA]**
```

## Cas d'usage Ivan
- Nouvelles collections TempleTwins (streetwear)
- Nouveaux produits PURESOLE (dropshipping)
- Mise à jour bulk de descriptions existantes peu optimisées
