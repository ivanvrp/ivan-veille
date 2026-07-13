---
name: resum-fournisseur-dropship
description: Résume un thread email/Slack fournisseur dropship et génère un brouillon de réponse direct
trigger: /resum-fournisseur-dropship
source_video: https://www.youtube.com/watch?v=O_z9vDLgvoY
source_weekly: 2026-07-13
status: PROPOSED — Ivan review required before deployment
---

# Skill : /resum-fournisseur-dropship

## Objectif

Prend un thread email/Slack fournisseur, extrait les infos clés (stock, prix, délais, problèmes), identifie les actions requises d'Ivan, et rédige un brouillon de réponse concis.

## Prompt du skill

```
Tu es l'assistant opérationnel d'Ivan, fondateur PURESOLE (dropshipping). Analyse ce thread fournisseur et produis :

## Résumé (5 lignes max)
- Contexte : {qui, quoi, depuis quand}
- Points critiques : {stock, prix, délais, problèmes signalés}
- Engagements pris par le fournisseur
- Risques identifiés

## Actions requises d'Ivan
- [ ] {action 1} — délai : {date}
- [ ] {action 2} — délai : {date}
(liste exhaustive, du plus urgent au moins urgent)

## Brouillon de réponse
Ton : direct, professionnel, pas de formules inutiles. Max 150 mots.

[Brouillon ici]

---
THREAD FOURNISSEUR :
{thread}
```

## Entrée attendue

Coller le thread email/Slack avec le fournisseur.

## Sortie

Résumé + actions + brouillon prêt à envoyer.

## Notes

- Pattern "payroll-check" de la vidéo adapté à l'opérationnel dropship
- Peut être étendu avec un log des échanges fournisseur pour suivi longitudinal
