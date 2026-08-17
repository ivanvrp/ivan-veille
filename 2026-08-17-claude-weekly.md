# Claude Weekly — 2026-08-17

> Veille deep-dive Claude / Claude Code / Skills / MCP — solo founder e-commerce (TempleTwins + PURESOLE)

---

## MUST-WATCH (3)

### 1. 🥇 "Claude Code Just Changed Forever (6 NEW Rules by Anthropic Engineers)"
**URL :** https://www.youtube.com/watch?v=gQeRjkb_Hlc
**Date :** ~Aug 3-10, 2026 | **Score :** 9/10 (Gemini confirmé)
**TL;DR :** Ingénieur Anthropic Thariq publie les "nouvelles règles d'ingénierie de contexte" pour Claude 5. Anthropic a supprimé >80% du prompt système de Claude Code sans perte de perf. 6 shifts majeurs à intégrer immédiatement.

**Les 6 shifts (résumé) :**
1. **Règles strictes → Jugement** : "Write code that reads like the surrounding code" remplace 20 règles NEVER/ALWAYS
2. **Exemples → Interfaces** : créer un Brand Book HTML plutôt que donner des exemples figés
3. **Tout upfront → Divulgation progressive** : CLAUDE.md = routeur vers fichiers département (économie tokens ++)
4. **Répétition → Descriptions simples** : Claude 5 comprend au premier coup, supprimer les doublons
5. **Mémoire manuelle → Mémoire auto** : skill `/calibrate` pour capitaliser en fin de session
6. **Specs Markdown → Références riches** : HTML > MD pour les brand guidelines visuelles

**Micro-action Ivan :** Auditer ses SKILL.md et supprimer tous les NEVER/ALWAYS → les remplacer par des guidelines ouvertes. Créer `references/brand-templetwins.html`.

---

### 2. 🥈 "NEW Claude Code Update is INSANE!" (cross-session messaging v2.1.232)
**URL :** https://www.youtube.com/watch?v=6L6qG_safRY
**Date :** ~Aug 10, 2026 | **Score :** 8/10 (Gemini confirmé)
**TL;DR :** Claude Code v2.1.232 permet aux sessions de se parler directement via SendMessage/ListAgents. Fini le copier-coller entre agents. Pipeline SEO/e-com entièrement automatisable.

**Feature clé :** Taper `@nom-session` dans un prompt pour envoyer un message à une autre session active. La session destinataire reçoit un résumé synthétisé (pas l'historique complet).

**Workflow Ivan concret :**
- Session `tt-research` analyse mots-clés streetwear → SendMessage `tt-content` qui rédige → SendMessage `tt-ops` qui update Shopify → tout en automatique
- Configurer `crossSessionInbound: hold` pour les sessions critiques (validation manuelle des messages entrants)

**Micro-action Ivan :** Nommer ses sessions avec des conventions stables (`tt-research`, `ps-sourcing`, etc.) pour faciliter le routing inter-agents.

---

### 3. 🥉 "The Creator of Claude Code on The Hottest Piece of Software" (Odd Lots / Bloomberg)
**URL :** https://www.youtube.com/watch?v=7C_IHWkHKmU
**Date :** récente | **Score estimé :** 8/10
**TL;DR :** Interview longue forme du créateur de Claude Code sur Bloomberg Odd Lots. Vision insider sur pourquoi Claude Code domine, prochaines directions.
**⚠️ Analyse Gemini :** ÉCHEC (vidéo trop longue pour le free tier). À regarder manuellement, ~1h.

---

## NICE (7)

| # | Titre | URL | Raison de garder |
|---|-------|-----|------------------|
| 1 | "Anthropic Engineers Just Fixed Claude Code..." | https://www.youtube.com/watch?v=UBFHTHUs1wA | Security fixes v2.1.232 expliqués |
| 2 | "Anthropic Just Replaced Claude Code With New Claude Tag" | https://www.youtube.com/watch?v=hDsZMb_8FYo | Claude Tag (Slack) — angle pertinent pour ops |
| 3 | "New Claude Code Update Changes AI Agents Forever!" | https://www.youtube.com/watch?v=J1c_V1Euebs | Subagent forking ON by default (v2.1.232) |
| 4 | "AI Summer 2026 — Claude Code & Choosing the Right Model" | https://www.youtube.com/watch?v=Thylf8WVuK8 | Model selection Opus 5 vs Fable 5 vs Sonnet 5 |
| 5 | "Why Claude Opus 5 Changes Everything" (AI Explained) | https://www.youtube.com/watch?v=SI0_DlS59Mg | Tier S, benchmark complet Opus 5 |
| 6 | "Claude Just Got a Big Update (Opus 4.1)" (Matthew Berman) | https://www.youtube.com/watch?v=3vXBVLJusrc | Tier S, update modèle intermédiaire |
| 7 | "Claude Code Is My Technical Cofounder" (Medium) | https://medium.com/activated-thinker/claude-code-is-my-technical-cofounder-64782393ac01 | Essay solo founder — cas proche Ivan |

---

## SKIP

- "Watch This If You're Just Learning Claude Code in 2026" — trop débutant
- "Anthropic is coming for EVERYTHING" — clickbait
- "Claude Code Is Losing Its Crown" — daté (juillet), non pertinent cette semaine

---

## Annonces Anthropic clés (Aug 4-17, 2026)

### 🔑 Claude Code Changelog (highlights)

**v2.1.233 (Aug 14)** — Mémoire cgroup Bash (plus de builds runaway), WebFetch cache TTL configurable, GitLab MR support, fix CPU 100% idle Linux, fix aliases `/checkup`/`/review`, 2 security fixes Windows (NT device prefix bypass).

**v2.1.232 (Aug 13)** — **MAJEUR** :
- Subagent forking ON par défaut (`subagent_type: "fork"` hérite conversation + prompt cache)
- Cross-session `@mention` + `SendMessage` entre sessions
- Sessions aux noms uniques sur une machine
- Security : PowerShell bypass fix, Git Bash symlinks Cygwin fix, nested git trust fix
- Fable 5 de retour dans `/advisor`

**v2.1.229 (Aug 12)** — `claude remote-control --continue`, SSE keepalive streaming, `ListAgents` marque les sessions Remote Control offline/cloud.

**v2.1.228 (Aug 11)** — **Write tool** : les nouveaux modèles peuvent overwriter un fichier non-lu (= comportement Edit), Todo/task tools retirés de Claude 5+ (restaurer avec `CLAUDE_CODE_ENABLE_TODO_TOOLS=1`).

**v2.1.224 (Aug 7)** — **Self-hosted runner** : `claude self-hosted-runner` sur vos propres machines (Team + Enterprise).

### 🌊 Big news Anthropic

**Watermarking (Aug 11-13) :** Tous les modèles Claude post-Aug 2 embedent des watermarks invisibles dans le texte généré (SynthID-Text de Google DeepMind). EU AI Act Article 50. Voyage avec le copier-coller. Pas d'info utilisateur. Impact SEO à surveiller (détection IA).

**IPO (Aug 13) :** Investisseurs ciblent valorisation ~$2T pour octobre 2026 (plus grand IPO de l'histoire). Revenu annualisé $100-120B prévu fin 2026.

**Compute deals :** $10B cloud startup (Aug 4) + $9B Riot Platforms (Aug 6). Capacité en expansion massive.

### 🔌 MCP officiel

Commits récents (jusqu'au 29 juil) : principalement maintenance (dependabot, fix filesystem openWorldHint). Pas de nouveau serveur majeur cette semaine.

---

## Skills proposés (3)

> ⚠️ Ces skills ne sont PAS déployés automatiquement. Ivan review manuellement avant toute activation.

### 1. `/calibrate-store`
**Source :** Analyse vidéo gQeRjkb_Hlc (Shift 5 - mémoire automatique)
**Concept :** En fin de session Shopify, le skill review la conversation et met à jour automatiquement les fichiers mémoire du store (prefs, fournisseurs, règles brand) + log `sessions/YYYY-MM-DD.md`.
**Fichier :** `claude-weekly/2026-08-17/skills-proposed/calibrate-store/SKILL.md`

### 2. `/doctor-context`
**Source :** Analyse vidéo gQeRjkb_Hlc (dérivé de `/doctor-plus` de Jay)
**Concept :** Audit santé du système agentique d'Ivan selon les 6 shifts. Génère rapport avec tableau shifts OK/FLAG + pire offenseur + fix suggéré.
**Fichier :** `claude-weekly/2026-08-17/skills-proposed/doctor-context/SKILL.md`

### 3. `/shopify-pipeline`
**Source :** Analyse vidéo 6L6qG_safRY (cross-session messaging v2.1.232)
**Concept :** Coordonne un pipeline multi-agent (research → content → ops → report) avec des noms de sessions standardisés pour TempleTwins et PURESOLE. Utilise SendMessage/ListAgents.
**Fichier :** `claude-weekly/2026-08-17/skills-proposed/shopify-pipeline/SKILL.md`

---

## Insight cross-vidéos

**Pattern récurrent cette semaine :** Claude 5 change fondamentalement la relation humain-IA de "donneur d'ordres avec règles strictes" à "partenaire avec lignes directrices" — moins de prompts rigides, plus de jugement délégué et de mémoire automatique, sessions multiples qui se coordonnent en autonomie.

---

## Contexte Shopify e-com (bonus)

- **get-ryze.ai** a publié 4 articles pratiques post-juil 2026 sur Claude + Shopify (skills, workflows, automatisation opérations). Bon référentiel tutoriels.
- **Shopify AI Toolkit** (avril 2026) : légitimise les agents comme Claude Code comme opérateurs directs du store (lecture Liquid, bulk metafield updates, rapports custom via MCP + terminal).
- Gain de temps moyen rapporté : 4.1h/semaine pour les utilisateurs quotidiens de Claude Code.

---

## Sources collectées

```
Anthropic changelog: https://code.claude.com/docs/en/changelog
Claude Code releases: https://releasebot.io/updates/anthropic/claude-code
Gradually changelog: https://www.gradually.ai/en/changelogs/claude-code/
MCP servers: https://github.com/modelcontextprotocol/servers/commits/main.atom
Watermarking: https://techcrunch.com/2026/08/11/anthropic-says-it-will-watermark-text-generated-by-its-ai-models/
IPO: https://fortune.com/2026/08/13/anthropic-ipo-2-trillion-october-largest-ever-spacex/
Self-hosted runner: https://claude.com/blog/run-claude-code-sessions-on-your-own-compute
Shopify skills guide: https://www.get-ryze.ai/blog/claude-shopify-skills
Solo founder playbook: https://stormy.ai/blog/solo-founder-playbook-claude-code-startup
```

---

*Généré par veille-claude-weekly · 2026-08-17*
