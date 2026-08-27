# Documentation Hirify — instructions

## À propos

- Site de documentation [Mintlify](https://mintlify.com) pour **Hirify**, plateforme d'entretiens de recrutement assistés par IA.
- Les pages sont des fichiers MDX avec frontmatter YAML. La configuration vit dans `docs.json`.
- **Public visé : des recruteurs francophones.** Toute l'application est en français ; la documentation l'est aussi.

## Règles absolues

Ces trois règles ont une raison d'être : les 23 pages générées le 27 août 2026 les violaient toutes, et ont dû être retirées.

1. **Marque blanche stricte.** Ne jamais nommer un fournisseur tiers — captation, transcription, modèle d'IA, téléphonie, hébergement, chat de support, plongements. On nomme la fonction : « la transcription », « l'analyse par IA », « le chat de support ». La liste nominative des sous-traitants est fournie avec le contrat de sous-traitance, jamais publiée ici.
2. **Aucune affirmation invérifiable.** Pas de tarif, de nom d'offre, de quota, de délai, de statistique ou de mécanisme produit qui ne soit pas vérifié dans le code de l'application. En cas de doute, décrire au lieu d'affirmer, ou omettre.
3. **Aucune affirmation de conformité non sourcée.** Hirify est **sous-traitant** ; la conformité RGPD est celle du client responsable de traitement. Ne jamais écrire « GDPR compliant », « ISO 27001 certified » ou « données jamais transférées hors de l'UE » sans source interne à l'appui.

## Vocabulaire

Repris de l'interface, à ne pas traduire ni paraphraser : *entretien*, *compte rendu*, *template*, *vivier*, *intervenant*, *analyse*, *signaux*, *assistant de réunion* (le bouton s'appelle « Ajouter le bot »), *Sourcing*, *Assistant*, *Pilotage*, *Fiabilité*.

Ce que Hirify ne fait **jamais** : envoyer un message à un candidat, écrire dans le logiciel de recrutement sans validation du recruteur, chercher des profils hors du vivier, décider à la place du recruteur. Aucune page ne doit laisser entendre le contraire — en particulier, **le compte rendu n'est jamais poussé automatiquement**.

## Style

- Vouvoiement, voix active, phrases courtes, une idée par phrase.
- Titres en minuscule de phrase.
- Gras pour les éléments d'interface : cliquez sur **Ajouter le bot**.
- Une page = une tâche. Elle ouvre sur ce à quoi elle sert, enchaîne sur la procédure en `<Steps>`, se termine par « Bon à savoir ».
- Pas de mise en scène de l'IA, pas de langage marketing, pas de calcul de retour sur investissement.

## Périmètre

Documentation destinée à l'utilisateur final. **Ne rien documenter** du back-office d'administration Hirify (`/admin/**`), des pages de développement, de l'architecture interne ou des outils de démonstration.
