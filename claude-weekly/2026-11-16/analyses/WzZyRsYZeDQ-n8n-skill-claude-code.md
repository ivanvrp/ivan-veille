# Analyse Gemini — NEW n8n Skill for Claude Code!
**Video ID:** WzZyRsYZeDQ  
**URL:** https://www.youtube.com/watch?v=WzZyRsYZeDQ  
**Analysé le:** 2026-11-16

## Résumé exécutif
Cette vidéo démontre comment installer et utiliser les skills n8n pour Claude Code, permettant à un agent AI de créer et gérer des workflows n8n de manière autonome. En connectant Claude Code à l'Instance-level MCP de n8n, Claude peut interpréter des prompts en langage naturel pour construire, valider et tester des automatisations complexes, réduisant considérablement le temps et les coûts liés au développement manuel de workflows.

## Concepts clés avec timestamps
- [00:00] MCP (Multi-Client Protocol) : Protocole de communication permettant à Claude Code d'interagir avec n8n.
- [00:12] Installation des Skills n8n : Ajout du plugin n8n-skills dans Claude Code via marketplace et installation locale.
- [00:52] Activation de l'Instance-level MCP dans n8n : Configuration exposant le serveur MCP avec URL et jeton d'accès.
- [01:10] Connexion de Claude Code au MCP n8n : Configuration avec URL du serveur MCP et jeton d'authentification.
- [02:25] Création de workflow par prompt : Description en langage naturel du workflow à construire.
- [02:47] Utilisation des Skills pour la configuration : Claude charge dynamiquement n8n-agents, n8n-workflow-lifecycle, n8n-node-configuration, n8n-error-handling.
- [03:30] Auto-correction et validation : Claude identifie les anti-patterns, ajuste, configure et valide avant publication.
- [04:22] Test et publication : Publication du workflow + test via cURL automatisé.
- [05:37] Rôle des Skills ("manuel") : Les skills agissent comme manuel d'instructions pour utiliser les outils MCP de n8n efficacement.

## Code/prompts/commandes verbatim
```bash
# Ajouter le marketplace des skills n8n
/plugin marketplace add n8n-io/skills

# Installer les skills n8n
/plugin install n8n-skills@n8n-io

# Ajouter le serveur MCP n8n à Claude Code
claude mcp add --transport http https://<votre-instance-n8n>/mcp-server/http \
  --header "Authorization: Bearer VOTRE_TOKEN"
```

Fichier `.mcp.json` :
```json
{
  "mcpServers": {
    "n8n-mcp": {
      "type": "http",
      "url": "https://<votre-instance-n8n>/mcp-server/http",
      "headers": { "Authorization": "Bearer VOTRE_TOKEN" }
    }
  }
}
```

Prompt exemple :
```
create a new workflow. It should be a webhook trigger that receives a prompt... 
It then goes through an AI agent that is able to use openrouter (gemini 2.5 flash) 
to answer the user's question. they then get the response back from the webhook.
```

## Patterns réutilisables pour Ivan
1. **Création de workflows par langage naturel** : Décrire un besoin d'automatisation Shopify et laisser Claude construire.
2. **Gestion des commandes** : "Crée un workflow qui, quand une commande est 'expédiée' dans Shopify, envoie un e-mail de suivi avec tracking."
3. **Marketing ciblé** : "Identifie les clients ayant dépensé >500€ le mois dernier et ajoute-les à une liste VIP."
4. **Synchronisation de stock** : "Mets à jour le stock fournisseur dans Shopify toutes les 4h."
5. **Gestion des retours** : "Automatise les demandes de retour avec formulaire web + update Shopify + notification équipe."

## Skill_potential
**n8n-shopify-lifecycle** : Skill permettant à Claude Code de gérer le cycle de vie complet des automatisations Shopify dans n8n — commandes, produits, clients, marketing. Ivan peut dire "crée une automatisation pour le lancement d'un nouveau produit" et Claude sait intégrer tous les nœuds Shopify pertinents.

**n8n-supplier-integration** : Skill pour générer des workflows n8n interagissant avec des APIs fournisseurs dropshipping — authentification, requêtes GET/POST pour commandes, mises à jour stock, mapping données Shopify↔fournisseur. Idéal pour PURESOLE.

## Score utilité 0-10 pour Ivan
**9/10** — Automatisation e-commerce par langage naturel = gain de temps considérable pour TempleTwins et PURESOLE. Skills spécialisés Shopify réduisent les itérations et coûts tokens. Manque d'intégrations prêtes-à-l'emploi pour fournisseurs dropshipping spécifiques pour viser 10/10.
