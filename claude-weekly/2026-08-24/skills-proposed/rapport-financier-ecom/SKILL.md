---
name: rapport-financier-ecom
description: >
  Version Cowork (Claude in Chrome side panel) du month-end close démo
  Anthropic : Claude lit les onglets ouverts (Shopify orders, Meta Ads
  Manager, TikTok Ads, factures fournisseurs, DHL/UPS, apps Shopify SaaS)
  puis génère un rapport mensuel + Google Sheet. Trigger : "Génère mon
  rapport financier mensuel e-com" ou `/rapport-financier-ecom`.
source: Claude Cowork Chrome side panel demo (YouTube C-5wF6tkQ2Q)
status: DRAFT — dépend de Cowork actif dans Chrome (Max/Team ; Pro en rollout).
---

# rapport-financier-ecom — DRAFT

## Pré-requis
- Extension Claude in Chrome installée
- Side panel Cowork actif (Max/Team plans, rollout Pro en cours août 2026)
- Onglets ouverts : Shopify Admin (TempleTwins + PURESOLE), Meta Ads Manager,
  TikTok Ads Manager, portail transporteur, factures apps Shopify

## Prompt de base (verbatim, inspiré démo Anthropic)
> Run my month-end close on these tabs. Pull each invoice, calculate
> COGS, ad spend, Shopify fees, shipping cost per brand, then push
> everything into the monthly report sheet on Google Drive.

## Sortie attendue
1. **Rapport texte** structuré :
   - Revenus bruts M vs M-1 (par marque)
   - COGS + ad spend + Shopify fees + shipping
   - Marge brute par produit / par marque
   - Anomalies : factures en retard, hausse CPA, hausse coût unitaire
2. **Google Sheet** peuplée (modèle pré-existant)
3. **Alertes** : renouvellements annuels d'apps, litiges transporteurs

## Adaptation Ivan
- 2 brands = 2 onglets templates séparés (`M-close-templeTwins`, `M-close-puresole`)
- Marges variables dropship PURESOLE : forcer Claude à distinguer prix
  fournisseur AliExpress/CJ vs prix Shopify vendu
- Ajouter tab "TikTok organic" (post views vs paid) pour signal de fond

## Skill_potential v2 (auto)
Une fois validé, ce skill devient un CRON hebdo Monday-morning au lieu
de mensuel — signal plus précoce sur les anomalies.
