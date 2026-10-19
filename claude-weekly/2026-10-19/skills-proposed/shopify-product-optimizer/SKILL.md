# Skill : shopify-product-optimizer

> ⚠️ PROPOSÉ — À valider manuellement par Ivan avant déploiement

## Description
Analyse une page produit Shopify existante et génère des titres, descriptions, tags et métadonnées SEO optimisés pour maximiser la visibilité et la conversion. Se base sur les tendances actuelles de la niche.

## Source
Extrait de l'analyse vidéo `9JoIpWgAsZ8` — "I Mapped Every Claude Code Concept So You Don't Have To"

## Entrée requise
- URL produit Shopify OU données produit brutes (titre actuel, description actuelle, tags actuels)
- Mots-clés cibles optionnels
- Brand voice (ex: "jeune et tendance TempleTwins", "neutre et confiant PURESOLE")

## Instructions Claude

Quand on te demande d'optimiser un produit Shopify pour TempleTwins ou PURESOLE :

1. Analyse le produit existant : titre, description, tags, images alt text
2. Identifie les lacunes SEO (mots-clés manquants, titre trop court/long, description trop générique)
3. Propose :
   - **Nouveau titre** : 60-80 caractères, mot-clé principal en tête, différenciateur de marque
   - **Description optimisée** : structure H1 → bénéfices → caractéristiques → CTA, 150-200 mots
   - **Tags optimisés** : 5-8 tags pertinents (niche + produit + style + usage)
   - **Alt text images** : description avec mot-clé principal naturellement intégré
4. Explique pourquoi chaque changement améliore le SEO ou la conversion

## Format de sortie
```markdown
## Analyse actuelle
[Points forts et lacunes identifiées]

## Optimisations proposées

### Titre : [nouveau titre]
### Description :
[nouvelle description]

### Tags : [tag1], [tag2], [tag3]...

### Alt text images : [description alt]

## Justification SEO
[Explication des changements clés]
```

## Cas d'usage Ivan
- Audit produits existants sur PURESOLE (catalogue dropshipping)
- Lancement nouvelle collection TempleTwins
- Amélioration des produits avec peu de trafic organique
