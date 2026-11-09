# Skill: Dropship Order Automation

**Source vidéo :** Agent Skills or MCP in the era of Claude Code? (pvxNcQTcIy4)
**Proposé le :** 2026-11-09
**Status :** À REVIEWER PAR IVAN — non déployé auto

## Ce que fait ce skill

Automatise l'envoi des commandes dropship aux fournisseurs de PURESOLE. Génère des bons de commande basés sur les nouvelles commandes Shopify et les envoie selon le format de chaque fournisseur.

## Structure proposée

```
dropship-order-automation/
├── SKILL.md
├── resources/
│   └── supplier_config.json   # Formats commande + contacts par fournisseur
└── scripts/
    └── process_dropship_order.py  # Parse commandes Shopify → formate → envoie
```

## Instructions pour Claude

Lorsque ce skill est invoqué avec des IDs de commandes Shopify :
1. Récupérer les détails des commandes via l'API Shopify
2. Lire `supplier_config.json` pour identifier le fournisseur par SKU
3. Formater le bon de commande selon les spécifications du fournisseur
4. Proposer l'envoi (email ou API fournisseur) — CONFIRMER avec Ivan avant envoi réel
5. Logger la commande dans un fichier orders_log.csv local

## Règles importantes
- NE JAMAIS envoyer une commande sans confirmation explicite d'Ivan
- Alerter si un SKU n'est pas mappé dans supplier_config.json
- Alerter si le stock fournisseur indique rupture

## Score utilité estimé : 9/10
