---
name: ecom-qa-manager
description: Orchestre des processus de QA automatisés pour boutiques e-commerce — explore toutes les pages via BFS, détecte les bugs, gère l'état dans un tableau Kanban GitHub Projects. Utilise des instances Claude headless (claude -p) pour éviter le context rot.
triggers:
  - "Fais un audit qualité complet sur mon Shopify TempleTwins en explorant toutes les pages"
  - "Trouve tous les bugs sur les pages produits et de paiement de PURESOLE"
  - "Vérifie la conformité mobile de toutes les routes après la mise à jour"
  - "Génère un rapport des pages non testées ou des bugs restants dans notre projet GitHub"
  - "Lance un test de non-régression sur toutes les fonctionnalités principales de ma boutique"
source_video: https://www.youtube.com/watch?v=XzlSn1M6WKw
source_analysis: ../analyses/XzlSn1M6WKw-stop-using-goal.md
proposed: 2026-05-25
status: À VALIDER — copier vers ~/.claude/skills/ pour activer
---

# Skill : ecom-qa-manager

## Pourquoi ce skill existe

Déduit de la vidéo "Stop Using Claude's /goal Feature | Here's What Works" (Eric Tech, mai 2026).
Le pattern Orchestrator → Claude Headless résout le "context rot" : chaque instance `claude -p` s'exécute
et se termine proprement, sans polluer le contexte de l'orchestrateur.

## Architecture

```
super-orchestrator
    --> super-qa  (BFS exploration des routes)  --> GitHub Projects [Queue/Testing/Bugs/Done/Skip]
    --> super-build (fixe les issues détectées)
    --> boucle jusqu'à : bugs == 0 ET toutes routes testées
```

## Workflow détaillé

### 1. Initialisation
- Charger la liste des routes du store (sitemap Shopify ou liste manuelle)
- Créer les colonnes GitHub Project : Queue / Testing / Done / Bug / Flaky / Skip
- Initialiser : Queue = [/products, /collections, /pages/about, /cart, /checkout, ...]

### 2. Boucle QA (BFS)
```bash
while [ $(gh project item-list --status Queue | wc -l) -gt 0 ] || [ bugs_count -gt 0 ]; do
  route=$(gh project item-list --status Queue | head -1)
  claude -p "Teste la page ${STORE_URL}${route} : vérifie le chargement, les images, les boutons CTA, la responsivité mobile. Rapporte les bugs avec screenshots. Termine avec DONE ou BUG." \
    --allowedTools "Bash,WebFetch"
  # Mise à jour GitHub Project selon résultat
done
```

### 3. Délégation de fix (super-build)
```bash
claude -p "Consulte les issues GitHub du projet avec label 'bug'. Fix chacun. Utilise TDD : écris d'abord le test qui échoue, puis le code qui le passe. Committes. DONE quand github issues count == 0."
```

### 4. Rapport final
- Résumé : N pages testées, N bugs trouvés, N bugs fixés
- Liste des pages Flaky à surveiller

## Configuration requise

```bash
# Dans .claude/settings.json — ajouter les permissions :
{
  "permissions": {
    "allow": ["Bash(gh *)", "Bash(claude -p *)", "WebFetch"]
  }
}
```

## Variables à personnaliser

- `STORE_URL` : https://templatetwins.com ou https://puresole.fr
- `GITHUB_PROJECT_ID` : ID du projet GitHub Kanban
- Routes initiales selon le store

## Validation requise

**Ivan doit :**
1. Lire ce fichier et vérifier que le workflow correspond à ses besoins
2. Tester sur un petit subset (3-5 pages) avant de lancer sur l'ensemble
3. Copier vers `~/.claude/skills/ecom-qa-manager.md` pour activer
4. Déclencher avec : "Fais un audit de qualité complet sur TempleTwins"
