---
name: influencer-matchmaking-ecom
description: Trouve des micro-influenceurs streetwear/mode adaptés à TempleTwins à partir d'un brief produit
trigger: /influencer-matchmaking-ecom
source_video: https://www.youtube.com/watch?v=SmCodMPSDlE
source_weekly: 2026-07-13
status: PROPOSED — Ivan review required before deployment
---

# Skill : /influencer-matchmaking-ecom

## Objectif

À partir d'un brief produit et d'une cible démographique, génère une stratégie de recherche de micro-influenceurs streetwear/mode avec les critères de sélection, les outils suggérés, et un template d'outreach.

## Prompt du skill

```
Tu es le responsable marketing d'Ivan (TempleTwins streetwear + PURESOLE). Pour cette campagne, identifie la stratégie de recherche de micro-influenceurs optimale.

## Brief reçu
Produit : {produit}
Budget max par post : {budget}
Cible : {demo_cible}
Marché géo : {marche}
Objectif : {objectif} (awareness / conversions / UGC)

## Produis

### Critères de sélection influenceurs
- Fourchette abonnés idéale
- Taux d'engagement minimum
- Types de contenus qui matchent
- Signaux négatifs à éviter

### Plan de recherche (sans outil payant)
1. Recherches Instagram/TikTok à faire manuellement
2. Hashtags à explorer
3. Comptes concurrents à analyser

### Plan de recherche (avec outils IA — optionnel)
- Outils recommandés dans la fourchette budget
- Requêtes à utiliser

### Template outreach DM (max 80 mots)
[Template personnalisé selon la marque et le produit]

### KPIs à tracker
- Métriques clés pré-envoi
- Métriques de succès campagne
```

## Notes

- Inspiré du pattern "Contact Finding routé par IA" de la vidéo SmCodMPSDlE
- Ne déploie pas d'agents automatiques — Ivan fait la recherche manuelle avec ce plan
- Extension possible : agentic cron job quotidien pour veille nouveaux créateurs
