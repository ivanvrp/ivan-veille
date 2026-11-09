# Skill: Streetwear Trend Analyzer

**Source vidéo :** Agent Skills or MCP in the era of Claude Code? (pvxNcQTcIy4)
**Proposé le :** 2026-11-09
**Status :** À REVIEWER PAR IVAN — non déployé auto

## Ce que fait ce skill

Identifie les tendances émergentes dans le streetwear pour orienter les collections et la communication de TempleTwins. Analyse des sources publiques (hashtags, couleurs, silhouettes dominantes).

## Structure proposée

```
streetwear-trend-analyzer/
├── SKILL.md
├── resources/
│   ├── visual_style_guides/   # Références visuelles (images des dernières collections)
│   └── hashtags.txt           # Hashtags streetwear à surveiller
└── scripts/
    └── analyze_trends.py      # Agrège données publiques, génère rapport tendances
```

## Instructions pour Claude

Lorsque ce skill est invoqué :
1. Lire la liste des hashtags dans `resources/hashtags.txt`
2. Rechercher sur le web (via WebSearch) les tendances récentes associées
3. Consulter les `visual_style_guides/` pour ancrage visuel
4. Générer un rapport de tendances :
   - 3 couleurs dominantes de la saison
   - 3 silhouettes / pièces clés en vogue
   - 3 inspirations culturelles (artistes, films, sports)
   - 2 opportunités produit pour TempleTwins
5. Optionnel : comparer avec la collection actuelle TempleTwins et identifier les gaps

## Fréquence suggérée
Mensuelle ou avant chaque nouveau drop de collection

## Score utilité estimé : 7/10
