# Analyse Gemini — jzf7DQa2CAc
**URL:** https://www.youtube.com/watch?v=jzf7DQa2CAc
**Titre:** How I Use Claude Code With Skills, MCP, Agents & Plugins
**Vues estimées:** ~13 426

## Résumé exécutif
Cette vidéo présente les 4 outils principaux de Claude Code (Skills, MCPs, Agents, Commands) pour personnaliser et automatiser le développement, ainsi que les Plugins. Ces outils permettent de définir des standards, d'interagir avec l'extérieur, de paralléliser des tâches et d'automatiser des workflows, offrant ainsi une grande efficacité pour un développeur solo.

## Concepts clés avec timestamps
- **[00:48] Skills** : Fichiers Markdown qui enseignent à Claude comment accomplir des tâches spécifiques en suivant des standards et des patterns prédéfinis. Claude décide quand les utiliser.
- **[02:39] MCP (Model Control Protocol)** : Connecte Claude Code à des outils externes (ex. : automation de navigateur, APIs, bases de données) pour interagir avec le monde réel.
- **[03:59] Agents** : Instances spécialisées de Claude Code, focalisées sur une seule tâche (ex. : UI, SEO, accessibilité), qui peuvent être exécutées en parallèle et orchestrées par un agent principal.
- **[06:23] Commands** : Commandes personnalisées déclenchées manuellement par l'utilisateur (avec `/`) pour automatiser des workflows répétitifs et sur demande.
- **[07:47] Plugins** : Bundles pré-configurés de Skills, MCPs, Hooks et Commands, permettant une installation facile et un partage au sein d'équipes ou de la communauté.
- **[08:23] Cadre de décision** : Guide pour choisir le bon outil : Skill pour les standards, MCP pour les outils externes, Slash Command pour les workflows à la demande, Sub Agent pour le travail parallèle, Plugin pour le regroupement et le partage.

## Code/prompts/commandes verbatim
```
Using the landing copy skill, rewrite the copy for this Evex landing page to make it more professional and meet the standards of a real landing page for a mobile app.
```
```
Make a dedicated about page for this Evex landing page, where it has information about the founders, and what our mission is. Once it is done, use the Chrome DevTools MCP to inspect the page, take screenshots, and verify it is styled appropriately.
```
```
Make me a UI researcher that uses the Chrome DevTools MCP to search similar designs for our app on Dribbble, takes screenshots, assesses the commonality in all of them, and then implements them in our app.
```
```
/tweet
```

## Patterns réutilisables pour Ivan
- **Skill product descriptions** : Définir un skill avec critères de rédaction (longueur, mots-clés, ton) pour générer des fiches produits cohérentes sur TempleTwins/PURESOLE
- **MCP Shopify API** : Connecter Claude Code à l'API Shopify pour lire stock, commandes, automatiser mises à jour
- **Agent "Sourcing Produit"** : Instance spécialisée pour recherche de produits, analyse tendances dropshipping
- **Commande `/seo-audit`** : Audit SEO rapide sur pages produits/collections
- **Commande `/new-product-listing`** : Workflow rapide pour créer ébauche fiche produit
- **Plugin "E-commerce Launchpad"** : Bundle skills rédaction + MCP Shopify + commandes social/email

## Skill_potential
**Proposition : `product-description-generator`**
Génère des descriptions de produits claires, engageantes et optimisées SEO pour Shopify/dropshipping. Entrée : nom, caractéristiques, public cible, ton, mots-clés. Sortie : description Markdown prête à l'emploi avec titre accrocheur + description courte + description détaillée + CTA.

## Score utilité 0-10 pour Ivan
**Score : 9/10** — Puissant pour solo founder e-commerce, automatise contenu et interactions Shopify.
