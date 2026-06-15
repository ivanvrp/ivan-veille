# Méta-digest juin 2026

> Consolidation de 12 digests (9 × veille-360 + 3 × claude-weekly) — 01 au 15 juin 2026.
> Doublons fusionnés. 1 ligne par item. Source datée entre parenthèses.

---

## (a) Top 5 signaux à action immédiate

1. **⚠️ Shopify Scripts meurent le 30 juin 2026 — J-15** : arrêt total, aucune extension, pas d'édition depuis le 15/04 — auditer l'admin TT/veravie maintenant, migrer vers Functions avant le 23 juin (buffer hotfixes). (cf. 2026-06-01-veille.md, rappelé jusqu'au 2026-06-13-veille.md)
2. **Billing split Claude 15 juin — déjà actif** : usage programmatique (`claude -p`, crons, GitHub Actions) bascule sur budget séparé ($20/mois Pro, $100 Max 5x) — activer le crédit via l'email claim Anthropic, budgéter les routines veille-360. (cf. 2026-06-03-veille.md)
3. **Claude Fable 5 / Mythos 5 — fenêtre gratuite jusqu'au 22 juin** : modèle dépassant Opus 4.8 sur tous les benchmarks, 1M tokens, 128k output — inclus gratuitement Pro/Max/Team jusqu'au 22 juin puis usage credits ; ⚠️ directive US suspend l'accès depuis le 12/06, vérifier disponibilité avant de tester. (cf. 2026-06-11-veille.md, 2026-06-15-veille.md)
4. **Meta Andromeda : creative = 56 % de la perf, broad targeting only** : 1 campagne ASC broad + 15-30 créas distinctes/mois → +65 % ROAS, -17 % CPA vs campagnes segmentées — restructurer immédiatement les campagnes TT/veravie si audiences manuelles actives. (cf. 2026-06-13-veille.md)
5. **Claude Code fallbackModel + /reload-skills** : `fallbackModel` (jusqu'à 3 modèles en cascade) évite les interruptions overnight ; `/reload-skills` supprime le cycle redémarrage sur les 41+ skills TT/veravie/Tora — ajouter `"fallbackModel": "claude-sonnet-4-6"` dans `.claude/settings.json`. (cf. 2026-06-07-veille.md, 2026-06-15-veille.md)

---

## (b) Par axe — 2-3 nouveautés qui comptent

### E-com / Ads
- **Meta Andromeda** : moteur computer-vision qui lit le contenu créatif pour cibler → audiences étroites/lookalikes réduisent les données, le créatif est le nouveau ciblage. (2026-06-13-veille.md)
- **TikTok Video Shopping Ads (VSA) + GMV Max** : VSA = conversion in-app 10 %+ vs 1,9 % standard ; GMV Max remplace VSA/PSA séparées en Q2 2026, ML sélectionne les créatifs gagnants auto. (2026-06-09-veille.md, 2026-06-13-veille.md)
- **Volume créa Meta : sweet spot 6-10 créas actives/ad set**, refresh 7-10j — moins de 4 = algo sous-alimenté, plus de 12 = apprentissage fragmenté. (2026-06-09-veille.md)

### Claude & Code
- **Claude Fable 5** : nouveau flagship Anthropic (9 juin), dépasse Opus 4.8 sur tous les benchmarks, 1M context, adaptive thinking. ID API : `claude-fable-5`. (2026-06-11-veille.md)
- **Dynamic Workflows (research preview)** : orchestration de dizaines à centaines de subagents en parallèle en arrière-plan, imbrication 5 niveaux, commande `/workflows` — disponible Max/Team/Enterprise. (2026-06-01-claude-weekly.md, 2026-06-13-veille.md)
- **Claude Managed Agents cron natif + credential vaults (public beta)** : agents qui tournent sur schedule cron sans GitHub Actions ni serveur, secrets chiffrés en vault. (2026-06-11-veille.md)

### Knowledge stack
- **NotebookLM passe à Gemini 3.5** : 11 formats export (PDF, Excel, PPT, CSV, JSON…), exécution de code cloud, discovery Google Search intégrée dans les notebooks. (2026-06-11-veille.md)
- **Agent Teams** : nouvelle couche au-dessus des subagents — plusieurs sessions se parlent entre elles via task list partagée (vs subagents isolés qui ne reportent qu'au main). Expérimental. (2026-06-15-claude-weekly.md)

### Shopify / CRO
- **Shopify Rollouts natif** : A/B test themes/checkout intégré à l'admin (5 juin), graduation par % trafic, swap BFCM programmable — sans app tierce. (2026-06-09-veille.md)
- **Shopify Summer '26 Editions (150+ updates)** : Checkout Components GA (+8-22 % conversion mesurés), AI Collection Sort natif, Section Nesting dans Theme Editor. (2026-06-13-veille.md)
- **`/llms.txt`, `/llms-full.txt`, `/agents.md` personnalisables** : les devs de thème contrôlent ce que les agents IA lisent d'une boutique — levier AEO montant. (2026-06-15-veille.md)

### MCPs
- **Shopify AI Toolkit MCP officiel** (open-source MIT, depuis avril 2026) : Claude Code se connecte directement à l'Admin API Shopify (GraphQL, 7 outils, inventaire, descriptions, analytics) en 1 commande. (2026-06-01-claude-weekly.md)
- **Heimdall MCP** : mémoire long-terme cross-sessions pour patterns architecturaux et solutions spécifiques — overhead minimal sur MCP standard. (2026-06-07-veille.md)
- **MCP spec stateless (Release Candidate juillet 2026)** : protocole sans état, sessions resumables/migrables, OAuth 2.1 standard — breaking changes potentiels sur serveurs existants à surveiller avant update. (2026-06-02-veille.md, 2026-06-15-veille.md)

---

## (c) Mort / déprécié ce mois

- **`claude-sonnet-4-20250514` et `claude-opus-4-20250514`** : dépréciés API le 15 juin 2026 — migrer vers `claude-sonnet-4-6` / `claude-opus-4-8` dans tous les scripts/crons. (2026-06-01-veille.md, 2026-06-05-veille.md)
- **Shopify Scripts** : arrêt total le 30 juin 2026, impossible d'éditer depuis le 15 avril — remplacés par Shopify Functions (WebAssembly). (couvert dans chaque digest depuis 2026-06-01)
- **Audiences ciblées / lookalikes Meta** : stratégie obsolète avec Andromeda — la segmentation manuelle réduit le pool de données ; seul le broad targeting + volume créa est efficace en 2026. (2026-06-13-veille.md)
- **HTTP+SSE transport MCP** : remplacé par Streamable HTTP comme standard déployé. (2026-06-13-veille.md)

---

## (d) Opportunités concrètes par projet

### TempleTwins (streetwear Shopify)
- **Installer le Shopify AI Toolkit MCP** (`npx -y @shopify/dev-mcp@latest`) : contrôle direct de TT via Claude Code en langage naturel (descriptions, collections, analytics) — 1 commande, 0 code GraphQL à écrire. (2026-06-01-claude-weekly.md)
- **Créer `/llms.txt` custom sur le thème Dawn OS 2.0** : cadrer ce que les agents IA lisent de TT (positionnement, produits phares, voix de marque) avant que l'AEO ne s'impose comme le SEO de 2027. (2026-06-15-veille.md)
- **Tester Shopify Rollouts** sur la page produit Compression Shirt : A/B layout checkout 50/50, 7 jours, mesurer la conversion sans app tierce — quick win CRO zero-cost. (2026-06-09-veille.md)

### veravie (supplément ménopause US)
- **Restructurer les campagnes Meta en 1 CBO ASC broad + 15-30 créas distinctes/mois** : Andromeda lit les créatifs, pas les audiences — passer de campagnes segmentées à 1 campagne broad est le levier structurel #1 avant les premiers achats test. (2026-06-13-veille.md)
- **Audit checkout avant trafic payant** : benchmark Baymard — 48 % abandonnent sur coûts surprises, checkout idéal = 12-14 champs vs 39 zones d'amélioration en moyenne ; priorité absolue avant de passer `password off`. (2026-06-15-veille.md)

### Tora (app fitness)
- **Tester Dynamic Workflows** pour des tâches d'audit codebase en parallèle (ex : "audite toutes les constantes d'entraînement dans la codebase et vérifie leur sourcing dans docs/science.md") — ce qui prendrait des heures devient des minutes. (2026-06-13-veille.md)
- **Migrer les Managed Agents cron** (veille-360, reporting Tora) vers la plateforme Claude native : `platform.claude.com` → Managed Agents → cron schedule + vault pour les secrets NTFY — remplace GitHub Actions, aucun serveur à gérer. (2026-06-11-veille.md)

---

*Généré le 2026-06-15 | Sources : 2026-06-01 à 2026-06-15 (9 × veille-360, 3 × claude-weekly)*
