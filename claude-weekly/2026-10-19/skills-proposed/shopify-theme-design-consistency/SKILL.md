# Skill : shopify-theme-design-consistency

> ⚠️ PROPOSÉ — À valider manuellement par Ivan avant déploiement

## Description
Analyse le thème Shopify existant (CSS, Liquid, JS) pour extraire les patterns de design (couleurs, typo, espacements, styles composants), puis garantit que tout nouveau code généré respecte strictement ces conventions visuelles. Élimine les incohérences UI.

## Source
Extrait de l'analyse vidéo `0hdFJA-ho3c` — "Claude Code is all you need in 2026"

## Entrée requise
- Accès aux fichiers du thème Shopify (via MCP Shopify ou copie locale)
- Description de la modification UI à effectuer
- Screenshots de l'état actuel (optionnel mais recommandé)

## Instructions Claude

Quand on te demande de modifier ou créer du code frontend pour une boutique Shopify :

1. **Avant de coder**, examine les fichiers existants :
   - `assets/theme.css` ou équivalent : relève couleurs primaires, secondaires, polices, border-radius
   - Sections Liquid existantes : identifie les patterns de structure (grilles, cartes produits, headers)
   - `layout/theme.liquid` : comprends la structure globale de la page
2. Documente les conventions trouvées :
   - Couleurs : `--color-primary`, `--color-text`, `--color-background`
   - Border radius : valeur utilisée pour les cartes/boutons
   - Spacing system : multiples de 4px ou 8px ?
   - Typographie : famille, tailles, poids
3. Génère le nouveau code en respectant STRICTEMENT ces conventions
4. Si incohérence demandée par l'utilisateur, signale-la et propose l'alternative cohérente
5. Après génération, liste explicitement quelles conventions tu as appliquées

## Format de sortie
```markdown
## Conventions détectées
- Couleur primaire : #...
- Border radius cartes : ...px
- Spacing : multiples de ...px
- Police : ...

## Code généré
[code Liquid/CSS respectant les conventions]

## Conventions appliquées
- [convention 1 appliquée]
- [convention 2 appliquée]
```

## Cas d'usage Ivan
- Ajout nouvelles sections sur TempleTwins sans casser le design
- Personnalisation pages produits PURESOLE avec cohérence visuelle
- Refonte partielle sans refonte complète du thème
