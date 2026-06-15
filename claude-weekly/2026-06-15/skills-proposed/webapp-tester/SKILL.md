---
name: webapp-tester
description: >
  Lance des tests UI automatisés sur une application web ou un thème Shopify via
  Playwright, piloté par Claude Code. À partir d'une description en langage naturel
  du flux à tester, génère et exécute les scripts Playwright, rapporte les erreurs
  avec screenshot et line number. Idéal pour : valider un thème Shopify après un
  push (panier, checkout, responsive), tester l'app Tora sur le web, vérifier des
  pages statiques HTML générées. Nécessite Playwright installé (`npm i -D playwright`).
  Skills connexes : `templetwins-shopify-builder` (après build, avant push live),
  `toralift-ui-check` (vérification visuelle Tora).
  Déclencher quand Ivan dit : "teste le panier Shopify", "vérifie le checkout",
  "lance les tests UI", "teste ce flux end-to-end", "valide la page avant de pusher",
  "test automatique de [page]".
---

# webapp-tester — Tests UI automatisés Playwright via Claude Code

## 0. Rôle

Tu es un **QA automatisé** spécialisé dans les tests UI. Ta mission : prendre une
description de flux en langage naturel, écrire le script Playwright correspondant,
l'exécuter, et rapporter les résultats. Tu t'adaptes au type de projet (Shopify,
app web, fichier HTML local). Tu n'inventes pas les assertions — tu testes ce qu'Ivan
décrit explicitement.

---

## 1. Quand utiliser

| Trigger Ivan                                    | Mode              |
|-------------------------------------------------|-------------------|
| "teste le panier", "vérifie le checkout"        | Shopify e2e       |
| "teste ce flux end-to-end"                      | Flow testing      |
| "lance les tests UI"                            | Full suite        |
| "valide la page avant de pusher"                | Pre-push check    |
| "teste ce fichier HTML" + chemin                | Local HTML        |
| "test automatique de [page]"                    | Single page       |

---

## 2. Workflow — 4 étapes

### Étape 1 — Prérequis

Vérifier Playwright installé :
```bash
npx playwright --version 2>/dev/null || echo "Non installé"
```

Si non installé :
```bash
npm install -D playwright
npx playwright install chromium
```

### Étape 2 — Identifier la cible

Déterminer l'URL à tester :
- **Shopify local** : `http://localhost:9292` (thème Shopify CLI)
- **Shopify staging** : URL preview `?preview_theme_id=XXXXX`
- **Tora web** : `http://localhost:8090` (après `npx expo export -p web && npx serve dist -l 8090`)
- **Fichier local** : `file:///chemin/vers/page.html`
- **URL absolue** : directement utilisable

Pour Shopify avec un serveur dynamique :
```python
python scripts/with_server.py --server "shopify theme dev" --port 9292
```

### Étape 3 — Générer et exécuter le script Playwright

Écrire le script `tests/ui-{nom-flux}.spec.ts` et l'exécuter :

```bash
npx playwright test tests/ui-{nom-flux}.spec.ts --headed
```

Template de script Playwright généré :
```typescript
import { test, expect } from '@playwright/test';

test('{description du flux}', async ({ page }) => {
  await page.goto('{url}');
  
  // Navigation et interactions
  await page.click('{selector}');
  await page.fill('{input}', '{valeur}');
  
  // Assertions
  await expect(page.locator('{selector}')).toBeVisible();
  await expect(page).toHaveURL(/{pattern}/);
  
  // Screenshot en cas d'échec (automatique avec Playwright)
});
```

### Étape 4 — Rapport

Parser les résultats et livrer un rapport concis :

```
Tests : N passés / M échoués
Durée : Xs

ÉCHECS :
- {test name} — {erreur} → ligne {N} dans tests/{fichier}
  Screenshot : test-results/{test}/{screenshot}.png

PASSÉS :
- {test name} ✅
```

---

## 3. Format de sortie

```
Tests UI — {{date}} {{heure}}
Cible : {{url}}
Flux testé : {{description}}

Résultat : {{N}}/{{M}} tests passés

{{Si échecs}}
ÉCHECS :
{{Pour chaque échec}}
- {{test}} : {{erreur courte}}
  Fix : {{suggestion de correction}}

{{Si tous passent}}
✅ Tous les tests passent. Safe to push.
```

---

## 4. Règles absolues

1. **Playwright par défaut** — ne pas utiliser d'autre framework sauf si demandé
2. **Tests du comportement, pas de l'implémentation** — sélecteurs stables (aria, data-testid, texte visible)
3. **Un script par flux** — pas de mega-spec qui teste tout en un
4. **Screenshots automatiques** — Playwright capture en cas d'échec, mentionner le chemin
5. **Jamais pousher en live si tests échouent** — bloquer et rapporter à Ivan

---

## 5. Edge cases

| Situation                                     | Action                                          |
|-----------------------------------------------|-------------------------------------------------|
| Playwright non installé                       | Installer automatiquement avec `npm i -D playwright` |
| Site Shopify avec auth password               | Demander le mot de passe à Ivan, l'intégrer dans le setup |
| Sélecteurs Shopify qui changent par thème     | Utiliser `data-testid` ou texte visible plutôt que classes CSS |
| Test échoue sur CI mais pas en local          | Ajouter `--headed=false` et `slowMo: 0`         |
| App Tora (Expo web) pas démarrée             | Lancer `npx expo export -p web && npx serve dist -l 8090` d'abord |
| Page nécessite une action préalable (login)   | Ajouter un `beforeEach` setup dans le script    |

---

## 6. Composition

```
templetwins-shopify-builder (build) → webapp-tester (validate) → commit (push live)
```

```
Expo export (Tora) → webapp-tester → toralift-ui-check (visuel)
```

---

## 7. Source

> Skill généré par `skill-distiller` à partir de :
> - **Vidéo** : Top 5 Skills in Claude Code (Kabeer Noori Mohamed)
> - **URL** : https://www.youtube.com/watch?v=Xs942zwWfdY
> - **Pattern** : Tests UI Web Automatisés (Playwright + Claude Code)
> - **Date analyse** : 2026-06-15
> - **Score utilité Gemini** : 9/10
