# Analyse Gemini — Claude Skills Just Fixed MCP's Biggest Problem

**URL :** https://www.youtube.com/watch?v=A-ZScvLMd-U  
**Modèle :** gemini-2.5-flash  
**Date analyse :** 2026-07-27

## Résumé exécutif
Les Agent Skills d'Anthropic pour Claude offrent une approche "progressive disclosure" pour la gestion du contexte, réduisant drastiquement l'utilisation de tokens. Ces "Skills" sont des dossiers contenant des instructions, des scripts et des ressources que Claude charge uniquement quand c'est pertinent, améliorant la flexibilité, la scalabilité et les performances pour des tâches spécialisées. Cette solution semble corriger les inefficacités du Model Context Protocol (MCP) traditionnel.

## Concepts clés avec timestamps
- [00:00] Introduction aux Agent Skills : Skills comme solution majeure au problème MCP, réduction tokens
- [00:19] Définition des Skills : Instructions personnalisées dans dossiers avec SKILL.md, exemples, scripts
- [00:40] Progressive disclosure : Claude charge ~100 tokens (nom+desc) → <5k tokens (SKILL.md) → illimité (fichiers)
- [01:09] Problème MCP traditionnel : descriptions longues remplissent le contexte avant même de commencer
- [01:22] Fonctionnement Skills : Claude scanne, charge minimum pertinent, accède expertise spécialisée
- [01:54] Gestion Skills : Onglet "Capabilities" > "Skills" pour Pro/Max, upload via .zip
- [02:17] Skills vs MCP 2.0 : Plus faciles à construire, meilleure gestion contexte
- [02:34] Architecture Agent + Skills + VM : Claude interagit avec Skills via système fichiers virtuel, exécute Bash/Python/Node.js
- [03:00] Structure SKILL.md : YAML frontmatter (nom, description) + Markdown instructions
- [04:35] Meilleures pratiques : Commencer simple, être précis, tester, organiser par objectif
- [04:54] Risques : Tool poisoning et prompt injection possibles dans skills tiers
- [05:09] Ressources : GitHub public `anthropic/skills` avec exemples

## Code/prompts/commandes verbatim
```yaml
# pdf/SKILL.md frontmatter
name: pdf
description: Comprehensive PDF toolkit for extracting text and tables,
  merging/splitting documents, and filling-out forms.
```

```python
from pypdf import PdfReader, PdfWriter
reader = PdfReader("document.pdf")
print("Pages:", len(reader.pages))
text = ""
for page in reader.pages:
    text += page.extract_text()
```

## Patterns réutilisables pour Ivan
- **Modularisation** : Décomposer e-commerce complexe (fiches produits, campagnes) en skills spécialisés
- **Gestion contexte** : Skills brand guidelines, politiques livraison, FAQ → accès contextuel sans surcharge
- **Scripts exécutables** : Python pour interroger Shopify (stocks/ventes), générer rapports Excel
- **Skill-creator** : Claude l'aide à construire ses propres tools rapidement
- **Partage workflows** : Encapsuler étapes dropshipping PURESOLE ou directives design TempleTwins

## Skill_potential
1. **product-description-writer** : Génère descriptions produit SEO depuis caractéristiques + ton de marque (streetwear/dropship). Fichiers: brand_tones/, product_data_schema.md, scripts/generate_description.py
2. **marketing-campaign-creator** : Plans campagnes social + email pour nouveaux lancements. Fichiers: brand_guidelines/, content_templates/, scripts/campaign_planner.py
3. **customer-query-resolver** : Réponses support précises depuis politiques PURESOLE/TempleTwins. Fichiers: faqs/, policies/, scripts/search_knowledge_base.py
4. **inventory-forecaster** : Prédiction besoins stock depuis historique ventes + tendances saisonnières. Scripts: analyze_sales.py, predict_stock.py

## Score utilité 0-10 pour Ivan
**9/10** — Progressive disclosure = moins de tokens = coûts réduits. Skills spécialisables pour ses deux boutiques. Exécution scripts = automatisation profonde. Skill-creator inclus.
