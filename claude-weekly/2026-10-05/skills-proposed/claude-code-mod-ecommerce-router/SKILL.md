# Skill Proposal: claude-code-mod-ecommerce-router

> **Proposé par**: veille-claude weekly 2026-10-05
> **Source**: Analyse Gemini — vidéo xTRZhPLhQ5E + u1dW4z5Ye90 (Claude Code Mods)
> **Statut**: À reviewer par Ivan — implémentation technique requise (TypeScript)

## Description

Un Claude Code Mod (TypeScript) qui route automatiquement les prompts d'Ivan selon leur nature :
- **Prompts e-commerce** (fiches produit, ads, email) → contexte e-commerce injecté
- **Prompts code Shopify** (Liquid, API) → contexte technique Shopify injecté
- **Prompts généraux** → pas d'injection, prompt direct

Évite la "context creep" des hooks réguliers et réduit les coûts en tokens.

## Fonctionnement technique (mod)

```typescript
// hooks/ecommerce-router.ts (mod Claude Code)
export default {
  name: 'ecommerce-router',
  hooks: {
    userPromptSubmit: async (event) => {
      const prompt = event.prompt.toLowerCase();
      
      if (prompt.includes('fiche produit') || prompt.includes('shopify') || prompt.includes('dropship')) {
        event.systemPrompt += '\n\n[CONTEXTE: TempleTwins = streetwear premium Paris. PURESOLE = dropship sneakers. Tone: direct, lifestyle, Gen-Z.]';
      }
      
      if (prompt.includes('liquid') || prompt.includes('api shopify') || prompt.includes('thème')) {
        event.systemPrompt += '\n\n[CONTEXTE TECH: Shopify 2.0, Dawn theme base, pnpm, Polaris 2.0 RC]';
      }
      
      return event;
    }
  }
}
```

## Valeur pour Ivan

- Réduit la répétition de contexte dans chaque prompt
- Coût tokens optimisé (injection conditionnelle, pas systématique)
- Moins de prompts longs = sessions plus rapides

## Prérequis

- Claude Code ≥ 2.1.287 (Mods disponibles)
- Connaissances TypeScript basiques (ou demander à Claude de l'écrire)

## Étapes d'implémentation

1. Créer le fichier mod TypeScript ci-dessus
2. `claude plugin install ./ecommerce-router`
3. Tester avec un prompt fiche produit
4. Ajuster les conditions de routage selon retours
