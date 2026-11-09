# Skill: Analyseur de Campagne Publicitaire

**Source vidéo :** How I Use Claude Code With Skills, MCP, Agents & Plugins (jzf7DQa2CAc)
**Proposé le :** 2026-11-09
**Status :** À REVIEWER PAR IVAN — non déployé auto

## Ce que fait ce skill

Analyse la performance des campagnes publicitaires Meta/Google d'Ivan et propose des optimisations basées sur les métriques clés. Transforme un export CSV de dashboard en recommandations actionnables.

## Instructions pour Claude

Lorsque ce skill est invoqué avec un fichier CSV ou des métriques copiées :

### Métriques analysées
- CTR (Click-Through Rate) — seuil alerte : < 1% pour Meta
- CPA (Coût par Acquisition) — comparer au panier moyen TempleTwins/PURESOLE
- ROAS (Return on Ad Spend) — seuil minimum : 3x
- CPM — benchmark secteur streetwear/dropship
- Fréquence d'exposition — alerte si > 3.5

### Livrables
1. **Score santé global** : Rouge/Orange/Vert par campagne
2. **Top 3 insights** : Ce qui fonctionne vraiment
3. **Top 3 optimisations** : Actions concrètes prioritaires (ex: couper les adsets < 0.5% CTR, tester nouveaux visuels, ajuster budget)
4. **Alerte budget** : Identifier où l'argent est gaspillé
5. **Recommandation de test A/B** : Une hypothesis à valider la semaine suivante

### Format de sortie
Markdown structuré, lisible sur mobile, avec emojis pour les indicateurs (✅🟡🔴)

## Prérequis
- Export CSV Meta Ads Manager ou Google Ads (colonnes standards)
- Ou copier-coller des métriques depuis le dashboard

## Score utilité estimé : 8/10
