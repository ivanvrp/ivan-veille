# Analyse Gemini — "How Complete Beginners Master Claude Code MCP in 19 minutes"
**URL:** https://www.youtube.com/watch?v=dhsyihMpqZQ
**Upload:** 22 octobre 2026 (11 jours avant cette veille)
**Score scoring:** 9/10 (récent, 19 min sweet spot, MCP débutants, workflow fan-out e-com)

## Résumé exécutif
Guide débutant complet pour configurer Claude MCP en 19 min. Couvre les 2 types (local via JSON / hébergé via connecteurs), workflow "fan-out" multi-MCP, et les 4 erreurs courantes avec diagnostic. Connecteurs clés : filesystem local + Notion hébergé combinés dans un seul prompt.

## Concepts clés avec timestamps
- [0:17] MCP = élimine transfert manuel de fichiers vers Claude, accès live
- [0:40] 2 types : serveurs locaux (JSON config) vs serveurs hébergés (Connecteurs avec auth)
- [1:05] Démo : filesystem local — Claude lit/crée fichiers dans un dossier autorisé
- [1:13] Démo : Notion MCP hébergé — Claude accède aux docs Notion en temps réel
- [4:29] Structure JSON mcp_servers : server_name, command, args, env (pour clés API)
- [7:10] RÈGLE : après config JSON → sauvegarder + quitter entièrement + rouvrir Claude
- [10:17] Notion hébergé : paramètres → Connecteurs → Ajouter connecteur → auth OAuth
- [11:03] Plan payant requis pour connecteurs personnalisés (Pro/Max/Team/Enterprise)
- [14:20] "Fan-out" : une seule instruction → Claude distribue vers filesystem + Notion simultanément
- [16:14] Erreur 1 : commande cassée (cmd /c npx sur Windows)
- [16:53] Erreur 2 : syntaxe JSON invalide (virgule manquante) — fait reset config
- [17:40] Erreur 3 : serveur hébergé mis dans config locale = échec silencieux
- [19:02] Erreur 4 : connexion Notion expirée → reconnect dans Connecteurs

## Code/prompts/commandes verbatim
```json
// Structure JSON locale (Windows)
{
  "mcp_servers": [{
    "server_name": "filesystem",
    "command": "cmd",
    "args": ["/c", "npx", "@anthropic-internal/server-filesystem", "--folder", "C:\\Users\\<user>\\Documents\\projects"]
  }]
}
```

URL connecteur Notion : `https://mcp.notion.com/mcp`

Prompt workflow fan-out :
> "Research the current best practices for password security, then save your findings as a file called 'password-security.md' in my projects folder, and also create a Notion page called 'Password Security Research' with the same findings."

## Patterns réutilisables pour Ivan
- MCP filesystem → pointer sur dossier dropship PURESOLE (fiches fournisseurs, pricing) pour accès direct Claude
- MCP Notion → synchronisation automatique base de connaissances TempleTwins (lookbooks, briefs, guidelines)
- Fan-out : 1 prompt → Claude recherche tendance streetwear + sauvegarde rapport local + crée page Notion éditoriale
- Workflow : "Analyse les ventes Shopify de cette semaine, sauvegarde CSV en local et crée résumé Notion pour Ivan"

## Skill_potential
**Skill proposé : `notion-shopify-sync`**
Skill qui orchestre un workflow fan-out : analyse données Shopify (ventes, stock, best-sellers) → crée rapport structuré en local + synchronise résumé vers Notion page dédiée. Parfait pour review hebdomadaire solo founder.

## Score utilité 0-10 pour Ivan
**9/10** — MCP filesystem + Notion = combo parfait pour solo founder qui jongle entre Shopify, fichiers locaux et docs. Fan-out pattern directement applicable.
