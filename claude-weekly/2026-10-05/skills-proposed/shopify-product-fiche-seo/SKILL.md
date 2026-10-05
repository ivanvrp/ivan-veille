# Skill: shopify-product-fiche-seo

> **Proposé par**: veille-claude weekly 2026-10-05
> **Source**: Analyse Gemini — vidéo xTRZhPLhQ5E (Claude Code Mods)
> **Statut**: À reviewer par Ivan avant tout déploiement

## Description

Génère des fiches produit Shopify optimisées SEO à partir des caractéristiques brutes d'un produit. Prend en entrée : nom, caractéristiques, prix, images disponibles (paths locaux). Produit : titre SEO, description longue, bullet points bénéfices, balises meta, variantes de titres pour A/B test.

## Trigger

Utilise ce skill quand tu veux créer ou améliorer une fiche produit Shopify pour TempleTwins ou PURESOLE.

Invocation : `/shopify-product-fiche-seo`

## Comportement attendu

1. Demande les inputs : nom produit, caractéristiques (bullet list), prix, audience cible, mots-clés principaux (optionnel)
2. Génère une fiche structurée :
   - **Titre SEO** (max 60 chars, inclut mot-clé principal)
   - **Description longue** (300-500 mots, storytelling streetwear/lifestyle)
   - **Bullet points** (5 bénéfices concis, format Shopify)
   - **Meta description** (max 155 chars)
   - **3 variantes de titre** pour A/B test
   - **Tags Shopify** (10-15 tags pertinents)
3. Sort en format Shopify-ready (markdown + JSON optionnel)

## Pourquoi ce skill

Répétitif, chronophage, et toujours le même format → parfait pour automation. Ivan crée régulièrement de nouvelles références pour TempleTwins + dropship PURESOLE.

## Implémentation suggérée

Peut être implémenté comme :
- Skill Claude simple (SKILL.md dans `.claude/skills/`)
- Claude Code Mod (hook UserPromptSubmit) pour version plus avancée avec accès fichiers locaux

## Risques

- Ton générique si mal prompté → ajouter exemples TempleTwins dans le skill
- SEO trop générique → envisager base de mots-clés locale
