# ChatGPT General Protocol 

**Un protocole gratuit et généraliste pour travailler avec ChatGPT de manière plus structurée : étapes utiles, suivi du contexte, vérifications explicites et continuation avec remarques.**

> **Testé avec ChatGPT Plus.** Ce projet est indépendant et non officiel ; il n'est pas développé par OpenAI. Il ne s'agit pas d'une extension à installer : ce sont des fichiers d'instructions que vous donnez à ChatGPT.

## Démonstration vidéo : installation et exemple d’utilisation

Cette vidéo montre **comment installer le protocole dans ChatGPT**, puis **un exemple d’utilisation sur une tâche du quotidien**. C’est le moyen le plus simple de découvrir le fonctionnement avant de suivre le guide écrit ci-dessous.

[![Voir la démonstration du protocole ChatGPT sur YouTube](https://img.youtube.com/vi/68u8D3C0kHA/hqdefault.jpg)](https://www.youtube.com/watch?v=68u8D3C0kHA)

**[Regarder la vidéo complète sur YouTube](https://www.youtube.com/watch?v=68u8D3C0kHA)**

> GitHub ne permet pas de lire une vidéo YouTube directement dans un README. Cliquez sur la miniature ou le lien pour ouvrir la vidéo sur YouTube.

---

## À quoi ça sert ?

Sans protocole, vous devez souvent rappeler ce qui a été décidé et rédiger vous-même la demande suivante. Avec celui-ci, ChatGPT doit :

- **Faire le travail immédiatement** lorsqu'il dispose des éléments nécessaires, sans multiplier inutilement les plans.
- **Découper les travaux longs en phases** avec des résultats, décisions et critères de fin identifiables.
- **Conserver un état de reprise explicite** : objectifs, contraintes, décisions, éléments réalisés et reste à faire.
- Afficher **`VÉRIFICATION HUMAINE : REQUIRED` ou `NOT REQUIRED` à chaque phase** et fournir un guide précis si un contrôle manuel est nécessaire.
- Distinguer un **test humain** d'une **autorisation d'agir**. Cliquer sur « Continuer » ne valide jamais un test.
- Proposer, lorsqu'une suite est utile et que l'interface le permet, un **champ de remarques**, un **aperçu du prochain prompt**, **« Continuer — prochaine étape »** et **« Copier le prochain prompt »**. Les deux boutons utilisent exactement le même texte, remarques comprises.
- Utiliser au besoin une **organisation modulaire inspirée de MVC**, sans imposer cette méthode à une simple question.
- **S'arrêter quand la tâche est finie** plutôt que d'inventer une étape supplémentaire.

**Il n'est pas nécessaire de savoir programmer.** Le protocole s'applique à la rédaction, aux recherches, à l'apprentissage, à l'organisation personnelle, à la création de contenus et aux projets techniques.

---

## Installation recommandée : créer un Projet ChatGPT

C'est la méthode à privilégier pour réutiliser le protocole dans **plusieurs conversations d'un même projet**, sans avoir à joindre les fichiers à chaque nouveau chat.

### Étape 1 — Télécharger les fichiers

1. Sur cette page GitHub, cliquez sur **Code → Download ZIP**.
2. Décompressez l'archive sur votre ordinateur.
3. Vous trouverez notamment `RULES.md`, `WORKFLOW.md`, `CONTINUATION_UI.md`, `QUALITE_ET_VERIFICATION.md` et `PROMPT_DE_DEMARRAGE.md`.

### Étape 2 — Créer un projet

1. Ouvrez [ChatGPT](https://chatgpt.com/).
2. Dans la barre latérale, cliquez sur **Nouveau projet** (*New project*).
3. Donnez-lui un nom, par exemple **« ChatGPT — Protocole généraliste »**.
4. Vous pouvez choisir une couleur ou une icône.

> Un **Projet ChatGPT** est un espace regroupant conversations, fichiers et instructions. Ce n'est **pas** la même chose qu'un « GPT personnalisé » créé avec l'éditeur de GPTs.

### Étape 3 — Ajouter le protocole aux sources du projet

1. Ouvrez le projet créé.
2. Repérez la zone **Sources du projet** ou l'option **Ajouter des fichiers / Ajouter des sources** (le libellé peut varier).
3. Importez les fichiers `.md` extraits du ZIP. Si votre interface ne prend pas en charge certains fichiers ou si votre abonnement limite leur nombre, commencez par les documents essentiels ci-dessous.

**Fichiers essentiels :**

| Fichier | Rôle |
| --- | --- |
| [`RULES.md`](RULES.md) | Règles à appliquer pendant le travail |
| [`WORKFLOW.md`](WORKFLOW.md) | Étapes, reprise et achèvement |
| [`CONTINUATION_UI.md`](CONTINUATION_UI.md) | Remarques, aperçu, Continuer et Copier |
| [`QUALITE_ET_VERIFICATION.md`](QUALITE_ET_VERIFICATION.md) | Vérifications humaines et autorisations |
| [`ARCHITECTURE_MODULAIRE.md`](ARCHITECTURE_MODULAIRE.md) | Modularité facultative pour les travaux complexes |

**Recommandé :** ajoutez également `START_HERE.md`, `PROMPT_DE_DEMARRAGE.md`, `EXEMPLES.md` et les modèles du dossier `Templates/`. Les limites d'importation dépendent de votre offre ChatGPT. Importer les fichiers séparément est plus fiable que de supposer que ChatGPT pourra lire un ZIP dans tous les environnements.

### Étape 4 — Configurer les instructions du projet (important)

1. Dans le projet, cliquez sur le menu **•••**.
2. Ouvrez **Paramètres du projet** (*Project settings*).
3. Dans **Instructions du projet**, copiez-collez le texte ci-dessous :

```text
Dans toutes les conversations de CE projet, applique le protocole généraliste ChatGPT v3 FINAL présent dans les fichiers sources du projet.

Au début d'une tâche, consulte les fichiers utiles du protocole, en priorité RULES.md, WORKFLOW.md, CONTINUATION_UI.md et QUALITE_ET_VERIFICATION.md. Consulte ARCHITECTURE_MODULAIRE.md pour les projets complexes, et les modèles si nécessaire. Si une source manque ou n'est pas accessible, signale-le ; n'invente pas son contenu.

Exécute immédiatement les demandes simples. Pour les tâches longues, travaille par phases utiles en conservant objectifs, contraintes, décisions, résultats et état de reprise.

À la fin de CHAQUE phase, y compris la dernière, écris : VÉRIFICATION HUMAINE : REQUIRED ou VÉRIFICATION HUMAINE : NOT REQUIRED. Si REQUIRED, explique exactement comment vérifier et comment communiquer le résultat. Ne considère jamais le bouton Continuer comme une validation de test ou une autorisation.

S'il existe une prochaine étape pertinente et si l'interface le permet, affiche un champ facultatif de remarques, un aperçu dynamique du prochain prompt et deux actions fonctionnelles : « Continuer — prochaine étape » et « Copier le prochain prompt ». Ces actions doivent transmettre/copier exactement le même prompt, avec les remarques originales à reformuler fidèlement au tour suivant. Si ces contrôles ne sont pas disponibles, fournis un prompt complet prêt à copier manuellement.

Ne crée pas de phase inutile ; si la tâche est achevée, conclus normalement.
```

**Pourquoi les deux ?** Les **fichiers sources** contiennent les règles détaillées ; les **instructions du projet** demandent explicitement à ChatGPT de les appliquer. Mettre simplement les fichiers en source ne garantit pas que chaque règle sera systématiquement suivie. Les instructions du projet s'appliquent aux conversations du projet, **pas** à l'ensemble de votre compte.

### Étape 5 — Commencer une conversation dans le projet

Cliquez sur **Nouvelle conversation** à l'intérieur de ce projet, puis écrivez normalement votre demande, par exemple :

> Aide-moi à préparer un déménagement, avec un budget et une liste de priorités. Tu peux avancer par étapes si c'est utile.

Vous n'avez normalement **plus besoin de joindre le protocole dans chaque conversation du projet** : les sources et instructions lui sont associées. Vous pouvez ouvrir une autre conversation dans ce même projet pour une autre tâche.

### Étape 6 — Mémoire et continuité dans le projet

Les projets peuvent utiliser leurs conversations et fichiers comme contexte, selon les réglages de mémoire et le forfait. Dans **Paramètres du projet → Mémoire**, lorsque cette option est proposée, vous pouvez choisir le mode adapté :

- **Mémoire limitée au projet (*Project-only*)** : le contexte reste cantonné aux conversations du projet. Utile pour éviter de mélanger des projets distincts.
- **Mémoire par défaut (*Default*)** : le comportement dépend de votre abonnement et de vos paramètres de mémoire personnels.

**Attention :** ce n'est pas une « mémoire permanente » qui conserve mot pour mot l'ensemble du protocole et de toutes vos décisions. Gardez les documents dans les **sources du projet** et utilisez les modèles [`Templates/ETAT_ET_REPRISE.md`](Templates/ETAT_ET_REPRISE.md) et [`Templates/JOURNAL_DECISIONS.md`](Templates/JOURNAL_DECISIONS.md) pour des reprises importantes. Si la mémoire n'est pas disponible ou désactivée, les instructions et les fichiers du projet restent la base explicite de travail, dans la limite de leur accessibilité.

**Conversation existante :** si ChatGPT propose **Déplacer vers le projet** dans le menu d'un chat, vous pouvez l'utiliser. Le chat hérite alors des instructions et sources du projet. Certaines conversations ne peuvent pas être déplacées.

---

## Alternative : utiliser le protocole dans une seule conversation

Vous ne voulez pas créer de Projet ChatGPT ?

1. Ouvrez une conversation normale.
2. Joignez les fichiers du protocole, ou le ZIP si votre interface sait réellement en consulter le contenu.
3. Copiez le texte de [`PROMPT_DE_DEMARRAGE.md`](PROMPT_DE_DEMARRAGE.md), remplacez `[MA DEMANDE]` par votre objectif et envoyez-le.
4. Pour une nouvelle conversation indépendante, redonnez-lui les règles nécessaires. **Un message dans un chat n'active pas automatiquement le protocole dans tous les autres chats.**

### Peut-on demander à ChatGPT de mémoriser le protocole pour toutes les conversations ?

**Pas de façon fiable en écrivant simplement « retiens ce protocole pour toujours » dans une conversation.** La mémoire peut retenir des préférences utiles, mais elle n'est pas un espace d'installation garantissant que chaque fichier et chaque règle seront appliqués intégralement partout.

Pour avoir un comportement **global** dans les chats ordinaires, utilisez plutôt les **Instructions personnalisées** :

1. Ouvrez **Paramètres → Personnalisation → Instructions personnalisées** (le nom exact peut varier).
2. Activez la personnalisation si nécessaire.
3. Collez la version condensée suivante :

```text
Adopte par défaut un travail structuré : exécute directement les demandes simples ; pour les travaux complexes, découpe en phases utiles, garde les contraintes et décisions importantes et propose la prochaine action. À la fin de chaque phase, indique « VÉRIFICATION HUMAINE : REQUIRED » ou « NOT REQUIRED » ; si REQUIRED, fournis un guide de test précis et attends le résultat avant de déclarer l'étape validée. Si une suite est utile et que l'interface le permet, propose des remarques facultatives, un aperçu et deux actions synchronisées « Continuer — prochaine étape » / « Copier le prochain prompt ». Sinon, donne un prompt prêt à copier. N'invente ni tests ni validations et ne crée pas d'étapes inutiles. Pour les tâches complexes, privilégie une organisation modulaire lorsque pertinente.
```

**Limite importante :** ces instructions **résument** la méthode ; elles ne chargent pas automatiquement les fichiers Markdown du dépôt dans toutes vos conversations. Les instructions d'un Projet ChatGPT prévalent sur les instructions personnalisées globales **dans ce projet**. Pour appliquer le **protocole complet**, préférez donc la méthode Projet ci-dessus.

### Et si je crée mon propre GPT personnalisé ?

C'est une **troisième solution**, distincte des projets : dans l'éditeur de GPTs, vous pouvez placer les règles de comportement dans les instructions et utiliser les documents du protocole comme connaissances, selon les fonctionnalités et limites proposées. Ce GPT suivra alors ces consignes lorsque vous **discuterez avec lui** ; cela ne modifie pas automatiquement vos conversations avec ChatGPT standard.

---

## Comment fonctionne « Continuer » ?

Lorsque le travail comporte une prochaine étape utile, l'expérience attendue est :

1. **Remarques facultatives** : écrivez « ajoute un exemple », « corrige le budget », etc.
2. **Aperçu dynamique** : affiche le prochain prompt avec vos remarques.
3. **Continuer — prochaine étape** : envoie ce prompt dans le chat.
4. **Copier le prochain prompt** : copie exactement le même texte pour le réutiliser.

Les remarques sont conservées dans leur formulation d'origine puis reformulées fidèlement en consignes d'exécution au tour suivant. Un clic ne constitue **jamais** la preuve qu'une vérification manuelle est réussie.

**Les boutons ne sont pas garantis.** Leur présence dépend de l'interface ChatGPT et de ses capacités à afficher des contrôles interactifs réels. Si elle ne les prend pas en charge, ChatGPT doit proposer du texte à copier et ne pas simuler de boutons décoratifs. Voir [`CONTINUATION_UI.md`](CONTINUATION_UI.md).

## Vérification humaine : obligatoire à chaque phase

- `VÉRIFICATION HUMAINE : REQUIRED` — une intervention est indispensable ; ChatGPT explique quoi vérifier, le résultat attendu et comment répondre. Une phase bloquée ne peut pas être déclarée validée sans retour.
- `VÉRIFICATION HUMAINE : NOT REQUIRED` — aucune intervention manuelle indispensable n'est requise pour terminer ou poursuivre.

Une autorisation de modifier, d'envoyer ou de publier quelque chose est distincte de la vérification d'un résultat. Voir [`QUALITE_ET_VERIFICATION.md`](QUALITE_ET_VERIFICATION.md).

## Structure du dépôt

| Fichier | Contenu |
| --- | --- |
| [`README.md`](README.md) | Présentation et installation détaillée |
| [`START_HERE.md`](START_HERE.md) | Prise en main rapide |
| [`PROMPT_DE_DEMARRAGE.md`](PROMPT_DE_DEMARRAGE.md) | Prompt universel à copier |
| [`RULES.md`](RULES.md) | Règles générales |
| [`WORKFLOW.md`](WORKFLOW.md) | Phases, état, reprise, clôture |
| [`CONTINUATION_UI.md`](CONTINUATION_UI.md) | Continuation, remarques, boutons et fallback |
| [`QUALITE_ET_VERIFICATION.md`](QUALITE_ET_VERIFICATION.md) | Vérifications, permissions et blocages |
| [`ARCHITECTURE_MODULAIRE.md`](ARCHITECTURE_MODULAIRE.md) | Organisation modulaire facultative |
| [`EXEMPLES.md`](EXEMPLES.md) | Exemples d'utilisation |
| [`Templates/ETAT_ET_REPRISE.md`](Templates/ETAT_ET_REPRISE.md) | État de reprise |
| [`Templates/JOURNAL_DECISIONS.md`](Templates/JOURNAL_DECISIONS.md) | Suivi des décisions |
| [`CHANGELOG.md`](CHANGELOG.md) | Historique des versions |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contributions et signalements |
| [`LICENCE_A_CHOISIR.md`](LICENCE_A_CHOISIR.md) | Informations sur le choix d'une licence |

## Limites et remarques

- Le protocole **ne débloque pas** d'outils, de capacités, d'accès ou d'exécution en arrière-plan.
- L'application des consignes dépend du modèle, du contexte disponible, de l'interface et des règles prioritaires de ChatGPT.
- Le stockage de fichiers dans un projet et la mémoire conversationnelle sont deux choses différentes.
- Les instructions personnalisées globales ne garantissent pas l'accès au contenu des fichiers joints ailleurs.
- Le dépôt ne constitue pas un produit officiel OpenAI.

## Sources officielles (pour vérifier les étapes d'installation)

- [Projets dans ChatGPT — OpenAI Help Center](https://help.openai.com/fr-fr/articles/10169521-projects-in-chatgpt)
- [Instructions personnalisées — OpenAI Help Center](https://help.openai.com/en/articles/8096356-custom-instructions-for-chatgpt)
- [Créer et modifier un GPT personnalisé — OpenAI Help Center](https://help.openai.com/en/articles/8770868-creating-a-gpt)

## Version

Version du protocole : **v3 FINAL**. Voir [`CHANGELOG.md`](CHANGELOG.md).

---

*Projet indépendant, non officiel et non affilié à OpenAI.*
