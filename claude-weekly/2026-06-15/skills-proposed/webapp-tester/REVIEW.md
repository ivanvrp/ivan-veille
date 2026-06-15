# REVIEW — webapp-tester

## Pourquoi ce skill ?
Issu de la vidéo : Top 5 Skills in Claude Code (Kabeer Noori Mohamed) — https://www.youtube.com/watch?v=Xs942zwWfdY
Pattern extrait : `Tests UI Web Automatisés` via Playwright, piloté par langage naturel
Application pour Ivan : (1) Valider le thème Shopify TempleTwins avant chaque push live — critique car Ivan bosse seul sans filet. (2) Tester les pages export web de Tora.

## Score utilité (hérité de Gemini)
9/10 — Pattern directement applicable pour TempleTwins (Shopify) et Tora (Expo web).

## Comment installer (si validé)
```bash
mv /Users/ivanvasseur/Code/_workspace/ivan-veille/claude-weekly/2026-06-15/skills-proposed/webapp-tester \
   /Users/ivanvasseur/.claude/skills/webapp-tester
```
Puis recharger Claude Code (Cmd+R) ou relancer la session.

## Comment tester
1. "teste le panier Shopify sur le thème dev" → doit générer un script Playwright qui ouvre le thème dev, ajoute un produit au panier, vérifie la quantité et le CTA checkout
2. "valide la page avant de pusher" → doit demander l'URL de preview, écrire le test, l'exécuter
3. "teste ce fichier HTML local : /Users/ivanvasseur/Desktop/pricing-test.html" → test sur fichier local

## Alternatives considérées
- **`toralift-ui-check`** → vérification visuelle/manuelle de Tora, pas automatisée — complémentaire
- **Note Obsidian** → trop répétable et actionnable pour être une simple note

## Risques / limites
- Nécessite Playwright installé localement (`npm i -D playwright` dans le projet)
- Les sélecteurs Shopify (Dawn) peuvent être fragiles si Shopify change le thème
- Pas testé sur thèmes Shopify headless — adapter si besoin

## Si rejet
```bash
rm -rf /Users/ivanvasseur/Code/_workspace/ivan-veille/claude-weekly/2026-06-15/skills-proposed/webapp-tester
```
