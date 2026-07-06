# Skill : ecommerce-asset-generator

**Source vidéo :** A0bxjZsLo4k — This MCP Builds Entire Branded Websites in Claude Code  
**MCP source :** Higgsfield MCP  
**Statut :** PROPOSÉ — review manuelle Ivan requise avant déploiement

## Description

Prend une URL de produit Shopify ou un brief, un style et un kit de marque (couleurs, logo) pour générer divers assets marketing : images de produit en situation, vidéos UGC (avec script et personnage), sections de site web brandées.

## Déclencheur suggéré

```
/ecommerce-asset-generator {url_produit_ou_brief} [--brand-kit] [--type image|video|web]
```

## Cas d'usage Ivan

- TempleTwins : générer des photos de produits lifestyle sans shooting photo
- PURESOLE : créer des visuels produit depuis les URLs fournisseurs
- Créer des assets pour les publicités Meta/TikTok directement depuis Claude

## MCP à configurer

```bash
claude mcp add higgsfield -- npx -y higgsfield-mcp@latest
```

## Workflow démontré

1. Fournir brief produit + palette de marque
2. Higgsfield MCP génère assets via son API
3. Claude assemble et organise les assets dans le dossier projet
4. Export direct vers le dossier assets Shopify

## Valeur

Remplace un shooting photo (~500-2000€) par une génération IA en quelques minutes pour le dropshipping.
