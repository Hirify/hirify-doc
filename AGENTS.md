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

Ce que Hirify ne fait **jamais** : envoyer un message à un candidat, chercher des profils hors du vivier, décider à la place du recruteur.

**Écritures vers le logiciel de recrutement — la distinction est à faire, toujours.** Ne jamais écrire « Hirify n'écrit rien sans votre validation » : c'est faux.

- **Le compte rendu et l'évaluation ne partent jamais sans un geste du recruteur.** L'envoi passe par le panneau ATS de l'entretien et une confirmation explicite.
- **Deux automatismes écrivent d'eux-mêmes, si un administrateur les a activés** : les tags de synthèse posés sur la fiche du candidat, et le remplissage des champs personnalisés restés vides — réversible depuis le panneau ATS, avec une notification. Les deux sont désactivés par défaut ; l'envoi automatique de l'assistant de réunion, lui, est actif par défaut.

## Style

### Ce qui trahit l'écriture automatique

Trois défauts relevés en relecture, à ne pas réintroduire.

**Le point-virgule est proscrit.** Aucun, nulle part. S'il sépare les éléments d'une énumération, passer en liste à puces. Sinon, couper en deux phrases.

**Les virgules superflues.** Pas de virgule avant « et » ou « ou » quand les deux membres partagent le sujet : « il lit vos postes et les remonte », pas « il lit vos postes, et les remonte ». Pas de virgule devant une subordonnée courte : « il capte l'entretien quel que soit le canal ». La virgule reste nécessaire devant « et » quand les propositions ont des sujets différents, et dans une énumération de trois éléments ou plus.

**Les options s'énumèrent en puces**, jamais en prose enchaînée. Nom en gras, deux-points, explication :

```
Vous avez le choix entre plusieurs fonctionnalités :

- **Coller un lien de réunion** : ajoutez simplement le lien de votre réunion pour lancer l'assistant.
- **Planifier par email** : invitez l'assistant de réunion directement depuis votre agenda.
```

Plus largement : pas de triplets rythmés (« court, clair et vérifiable »), pas d'incise entre virgules qui n'apporte rien, pas de « en effet » ni « par ailleurs » décoratifs.

### Le reste

- Vouvoiement, voix active, phrases courtes, une idée par phrase.
- Titres en minuscule de phrase.
- Gras pour les éléments d'interface : cliquez sur **Ajouter le bot**.
- Une page = une tâche. Elle ouvre sur ce à quoi elle sert, enchaîne sur la procédure en `<Steps>`, se termine par « Bon à savoir ».
- Pas de mise en scène de l'IA, pas de langage marketing, pas de calcul de retour sur investissement.

## Périmètre

Documentation destinée à l'utilisateur final. **Ne rien documenter** du back-office d'administration Hirify (`/admin/**`), des pages de développement, de l'architecture interne ou des outils de démonstration.
