# Documentation Hirify — instructions

## À propos

- Site de documentation [Mintlify](https://mintlify.com) pour **Hirify**, plateforme d'entretiens de recrutement assistés par IA.
- Les pages sont des fichiers MDX avec frontmatter YAML. La configuration vit dans `docs.json`.
- **Public visé : des recruteurs.** L'application existe en français et en anglais. La documentation aussi : `fr/` est la langue par défaut, `en/` sa version anglaise, régie par la section [English version](#english-version) en fin de fichier.

## Règles absolues

Ces trois règles ont une raison d'être : les 23 pages générées le 27 août 2026 les violaient toutes, et ont dû être retirées.

1. **Marque blanche stricte.** Ne jamais nommer un fournisseur tiers — captation, transcription, modèle d'IA, téléphonie, hébergement, chat de support, plongements. On nomme la fonction : « la transcription », « l'analyse par IA », « le chat de support ». La liste nominative des sous-traitants est fournie avec le contrat de sous-traitance, jamais publiée ici.
2. **Aucune affirmation invérifiable.** Pas de tarif, de nom d'offre, de quota, de délai, de statistique ou de mécanisme produit qui ne soit pas vérifié dans le code de l'application. En cas de doute, décrire au lieu d'affirmer, ou omettre.
3. **Aucune affirmation de conformité non sourcée.** Hirify est **sous-traitant** ; la conformité RGPD est celle du client responsable de traitement. Ne jamais écrire « GDPR compliant », « ISO 27001 certified » ou « données jamais transférées hors de l'UE » sans source interne à l'appui.

## Vocabulaire

Repris de l'interface, à ne pas traduire ni paraphraser : *entretien*, *compte rendu*, *template*, *vivier*, *intervenant*, *analyse*, *signaux*, *assistant de réunion* (le bouton s'appelle « Ajouter le bot »), *Sourcing*, *Assistant*, *Pilotage*, *Fiabilité*.

Ce que Hirify ne fait **jamais** : envoyer un message à un candidat, chercher des profils hors du vivier, décider à la place du recruteur.

**Écritures vers le logiciel de recrutement — la distinction est à faire, toujours.** Ne jamais écrire « Hirify n'écrit rien sans votre validation » : c'est faux.

- **Le compte rendu et l'évaluation ne partent pas sans un geste du recruteur, sauf l'exception Teamtailor ci-dessous.** L'envoi passe par le partage de l'analyse, depuis le panneau ATS de l'entretien, avec un aperçu et une confirmation.
- **Avec la carte Hirify de Teamtailor, un réglage envoie le compte rendu lui-même** : **Publier l'analyse automatiquement** pousse l'analyse et le compte rendu sur la fiche du candidat dès la fin de l'entretien, sans relecture (`push_teamtailor_partner_result_job.ts`). Il est désactivé par défaut et activé par un administrateur ou un admin facturation.
- **Deux automatismes écrivent d'eux-mêmes, si un administrateur ou un admin facturation les a activés** : les tags de synthèse posés sur la fiche du candidat, et le remplissage des champs personnalisés restés vides — réversible depuis le panneau ATS, avec une notification. Les deux sont désactivés par défaut ; l'envoi automatique de l'assistant de réunion, lui, est actif par défaut.

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

## English version

The English pages under `en/` carry the same facts as the French pages under `fr/`, written for an English-speaking recruiter. They are an adaptation, not a translation: keep the meaning, every fact and every limit, and write the sentence an English technical writer would write. The absolute rules above apply unchanged, including the distinction between the interview notes and evaluation (shared by a user action) and the ATS automations written on their own once an administrator or a billing admin turns them on: summary tags, empty custom fields, and, with the Teamtailor Hirify card, the analysis and interview notes themselves.

French stays the default language. When a French page changes, update its English counterpart in the same pull request.

### Page map

The English slugs are English. The language switcher cannot pair pages by path, so this table is the pairing.

| French | English |
| --- | --- |
| `fr/index` | `en/index` |
| `fr/premiers-pas` | `en/quickstart` |
| `fr/glossaire` | `en/glossary` |
| `fr/demarrer/creer-votre-espace` | `en/getting-started/create-your-workspace` |
| `fr/demarrer/rejoindre-une-organisation` | `en/getting-started/join-an-organization` |
| `fr/demarrer/inviter-un-membre` | `en/getting-started/invite-a-member` |
| `fr/demarrer/roles-et-acces` | `en/getting-started/roles-and-access` |
| `fr/demarrer/securiser-votre-compte` | `en/getting-started/secure-your-account` |
| `fr/demarrer/ameliorer-les-transcriptions` | `en/getting-started/improve-transcripts` |
| `fr/entretiens/choisir-son-canal` | `en/interviews/choose-how-to-record` |
| `fr/entretiens/en-visioconference` | `en/interviews/video-meetings` |
| `fr/entretiens/en-presentiel` | `en/interviews/in-person` |
| `fr/entretiens/importer-un-audio` | `en/interviews/upload-audio` |
| `fr/entretiens/automatique-depuis-l-ats` | `en/interviews/automatic-from-your-ats` |
| `fr/entretiens/reunions-hors-recrutement` | `en/interviews/non-recruiting-meetings` |
| `fr/entretiens/retrouver-et-suivre` | `en/interviews/find-and-track` |
| `fr/entretiens/relire-un-entretien` | `en/interviews/review-an-interview` |
| `fr/entretiens/identifier-les-intervenants` | `en/interviews/identify-speakers` |
| `fr/entretiens/ajouter-le-cv-du-candidat` | `en/interviews/add-the-candidate-cv` |
| `fr/entretiens/fusionner-deux-entretiens` | `en/interviews/merge-two-interviews` |
| `fr/comptes-rendus/choisir-un-template` | `en/notes/choose-a-template` |
| `fr/comptes-rendus/creer-un-template` | `en/notes/create-a-template` |
| `fr/comptes-rendus/partager-un-template` | `en/notes/share-a-template` |
| `fr/comptes-rendus/lire-et-modifier` | `en/notes/read-and-edit` |
| `fr/comptes-rendus/analyse-du-candidat` | `en/notes/candidate-analysis` |
| `fr/comptes-rendus/exporter-et-partager` | `en/notes/export-and-share` |
| `fr/integrations/connecter-votre-agenda` | `en/integrations/connect-your-calendar` |
| `fr/integrations/connecter-votre-ats` | `en/integrations/connect-your-ats` |
| `fr/integrations/lier-un-entretien-a-une-candidature` | `en/integrations/link-an-interview-to-an-application` |
| `fr/integrations/renvoyer-une-evaluation` | `en/integrations/send-to-your-ats` |
| `fr/integrations/automatismes-ats` | `en/integrations/ats-automations` |
| `fr/integrations/familles-de-profils` | `en/integrations/job-families` |
| `fr/integrations/extension-chrome` | `en/integrations/chrome-extension` |
| `fr/integrations/personnaliser-l-assistant` | `en/integrations/customize-the-meeting-assistant` |
| `fr/integrations/deconnecter-un-outil` | `en/integrations/disconnect-a-tool` |
| `fr/telephonie/obtenir-un-numero` | `en/calling/get-a-phone-number` |
| `fr/telephonie/passer-un-appel` | `en/calling/make-a-call` |
| `fr/assistant/poser-une-question` | `en/assistant/ask-a-question` |
| `fr/assistant/verifier-une-reponse` | `en/assistant/check-an-answer` |
| `fr/sourcing/lancer-une-recherche` | `en/sourcing/start-a-search` |
| `fr/sourcing/ponderer-les-criteres` | `en/sourcing/weight-the-criteria` |
| `fr/sourcing/lire-et-comparer` | `en/sourcing/read-and-compare` |
| `fr/sourcing/rediger-un-message-d-approche` | `en/sourcing/write-an-outreach-message` |
| `fr/pilotage/composer-un-tableau-de-bord` | `en/analytics/build-a-dashboard` |
| `fr/pilotage/enregistrer-partager-epingler` | `en/analytics/save-share-and-pin` |
| `fr/pilotage/fiabilite-des-donnees` | `en/analytics/data-reliability` |
| `fr/compte/offres-et-acces` | `en/account/plans-and-access` |
| `fr/compte/gerer-les-membres` | `en/account/manage-members` |
| `fr/compte/abonnement-et-facturation` | `en/account/subscription-and-billing` |
| `fr/compte/notifications` | `en/account/notifications` |
| `fr/compte/suivi-du-support` | `en/account/support-requests` |
| `fr/confiance/informer-vos-candidats` | `en/trust/inform-your-candidates` |
| `fr/confiance/vos-donnees` | `en/trust/your-data` |
| `fr/confiance/l-ia-chez-hirify` | `en/trust/ai-at-hirify` |
| `fr/aide/faq` | `en/help/faq` |
| `fr/aide/l-entretien-n-a-pas-ete-enregistre` | `en/help/interview-not-recorded` |
| `fr/aide/la-transcription-est-incomplete` | `en/help/incomplete-transcript` |
| `fr/aide/les-intervenants-sont-melanges` | `en/help/speakers-mixed-up` |
| `fr/aide/mon-ats-ne-se-synchronise-plus` | `en/help/ats-not-syncing` |
| `fr/aide/contacter-le-support` | `en/help/contact-support` |
| `fr/nouveautes` | `en/whats-new` |

Links inside `en/` point to `/en/...`, never to `/fr/...`.

### Interface labels

A bold label in an English page is the exact string the English interface shows. The strings live in the application repository, in `inertia/locales/en/*.json` and `resources/lang/en/*.json`. To find one, search the French label in the `fr` file of the same name and read the value at the same key in the `en` file. When no English string exists, describe the element in plain words, without bold, rather than inventing a label.

| French interface | English interface |
| --- | --- |
| Tableau de bord, Démarrer un entretien | **Dashboard**, **Start an interview** |
| Collez un lien Meet ou Teams, Planifier par email, Présentiel, Importer un audio, Appeler | **Paste a Meet or Teams link**, **Schedule by email**, **In person**, **Upload audio**, **Call** |
| Barre latérale : Mon espace, Entretiens, Données, Talents IA | Sidebar: **My workspace**, **Interviews**, **Data**, **AI talent tools** |
| Transcriptions (entrée de la barre latérale) | **Interviews** |
| Calendrier, Ajouter le bot | **Calendar**, **Add the meeting assistant** |
| Bot connecté, Bot non accepté | **Assistant joined**, **Assistant not admitted** |
| Bots de transcription automatiques | **Automatic meeting assistant** |
| Notes, L'essentiel, Transcription (vues d'une fiche entretien) | **Notes**, **Key takeaways**, **Transcript** |
| Compte-rendu, Nouvelle note | **Interview notes**, **New note** |
| Templates de notes, Sans template | **Notes templates**, **No template** |
| Vôtres, Partagés, Bibliothèque, Personnel, Équipe | **Yours**, **Shared**, **Library**, **Personal**, **Team** |
| Analyse, Analyse candidat, Vigilance légale | **Analysis**, **Candidate analysis**, **Legal watch-outs** |
| Signaux bloquants, Bloquant, Écart CV | **Deal-breakers**, **Deal-breaker**, **CV mismatch** |
| Identifier les intervenants, Qui parle ici ?, Inverser avec..., Fusionner avec..., Non-candidat | **Identify speakers**, **Who's speaking here?**, **Swap with...**, **Merge with...**, **Not the candidate** |
| Assistant, Sourcing, Pilotage, Fiabilité | **Assistant**, **Sourcing**, **Analytics**, **Data reliability** |
| Forte correspondance, À considérer, Réserve | **Strong match**, **Worth considering**, **Weak match** |
| Profil recherché, Rédiger un message, Brouillon de message | **Target profile**, **Write a message**, **Outreach draft** |
| Paramètres : Profil, Sécurité, Intégrations, Téléphonie, Vocabulaire, Familles de profils | **Settings**: **Profile**, **Security**, **Integrations**, **Calling**, **Custom vocabulary**, **Job families** |
| Jetons d'accès, Continuer avec le SSO | **Access tokens**, **Continue with SSO** |
| Numéro affiché, Identifiants secondaires, Vérification entreprise | **Caller ID**, **Secondary caller IDs**, **Business verification** |
| Tags automatiques, Compléter les champs ATS, Historique des envois, Profil ATS | **Automatic tags**, **Fill in ATS fields**, **Push history**, **ATS profile** |
| Gérer l'abonnement, Abonnement, Mon plan, Consommation, Facturation | **Manage subscription**, **Subscription**, **My plan**, **Usage**, **Billing** |
| Membre, Manager, Administrateur, Admin facturation (sélecteur de rôle) | **Member**, **Manager**, **Admin**, **Billing admin**. In prose: member, manager, administrator, billing admin. |
| Suivi du support, Contacter le support, Centre d'aide | **Support requests**, **Contact support**, **Help center** |
| Bientôt disponible, Accès réservé | **Coming soon**, **Restricted access** |

### Vocabulary

| French | English |
| --- | --- |
| entretien | interview |
| compte rendu | interview notes (the document). One occurrence, one per template, is a note. |
| template | template |
| vivier | talent pool |
| intervenant | speaker |
| assistant de réunion | meeting assistant. The English interface never says bot. |
| analyse, signaux, points à examiner | analysis, signals, points to review |
| logiciel de recrutement | ATS. Spell it out once per page where it helps: applicant tracking system (ATS). |
| candidature, poste, fiche candidat | application, job, candidate profile |
| évaluation envoyée dans l'ATS | evaluation. The imported ones are ATS scorecards. |
| tags de synthèse, champs personnalisés | summary tags, custom fields |
| organisation, offre, place ou siège | organization, plan, seat |
| responsable de traitement, sous-traitant | controller, processor |
| RGPD, Code du travail | GDPR, French Labor Code |
| Bon à savoir | Good to know |

The plan names stay Starter, Hub and Volume. Prices stay in euros, excluding VAT, copied from the French page and never converted.

### Style

- US spelling, as in the interface: organization, analyze, customize.
- Second person, active voice, present tense. Short sentences, one idea each. Contractions are fine.
- Sentence case for titles and headings.
- Bold for interface labels. Options are listed as bullets, bold name, colon, explanation: `- **Upload audio**: transcribe an interview you recorded elsewhere.`
- No em dash and no semicolon. Use a period or a comma.
- Serial comma in a list of three or more: "interviews, notes, and templates".
- Sidebar groups and tabs: Welcome, Getting started, Record an interview, Interview notes and analysis, Connect your tools, Calling, Use your talent pool, Your account, Trust. Tabs: Documentation, Help (group Troubleshooting), What's new.
- No marketing words (seamless, powerful, effortless, unlock, streamline, leverage) and no rhetorical triplets.
- The frontmatter `description` says what the page covers, in plain words: "What Hirify does, what it doesn't, and where to start". It never starts with "You will".
- A pending screenshot is an MDX comment, as in the French pages: `{/* SCREENSHOT: ... */}`. The French captures show the French interface and are not reused in English pages.
