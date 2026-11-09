# Skill: Shopify Inventory Sync

**Source vidéo :** Agent Skills or MCP in the era of Claude Code? (pvxNcQTcIy4)
**Proposé le :** 2026-11-09
**Status :** À REVIEWER PAR IVAN — non déployé auto

## Ce que fait ce skill

Aide à synchroniser l'inventaire produits Shopify avec un fichier CSV local ou une source de données externe (fournisseur dropship). Vérifie les écarts et propose des ajustements.

## Structure proposée

```
shopify-inventory-sync/
├── SKILL.md           (ce fichier)
├── resources/
│   └── inventory_mapping.json   # SKUs Shopify ↔ codes fournisseur
└── scripts/
    └── sync_inventory.py        # Appelle API Shopify + lit le mapping
```

## Instructions pour Claude

Lorsque ce skill est invoqué :
1. Lire le fichier `resources/inventory_mapping.json` pour connaître les SKUs
2. Proposer un appel à l'API Shopify Admin pour vérifier les stocks actuels
3. Comparer avec les données fournisseur (CSV importé ou passé en argument)
4. Générer un rapport d'écarts : produits en rupture, sur-stock, synchronisés
5. Proposer les commandes de mise à jour ou les emails fournisseurs à envoyer

## Prérequis techniques
- Token API Shopify Admin (stocker dans env var SHOPIFY_API_TOKEN)
- Python 3 avec `shopify` SDK installé
- Format CSV fournisseur documenté dans inventory_mapping.json

## Cas d'usage prioritaire
- PURESOLE : fournisseurs dropship avec catalogue CSV hebdomadaire
- TempleTwins : vérification stock avant campagne marketing

## Score utilité estimé : 8/10
