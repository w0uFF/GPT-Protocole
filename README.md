# ChatGPT General Protocol
No more Drunkgpt, Only GigaChadGPT

Testé avec ChatGPT Plus.

**Un protocole de travail généraliste pour utiliser ChatGPT de manière plus structurée, sans compétences techniques.**

Il aide à passer d'une simple réponse à un travail suivi : exécution immédiate des tâches réalisables, progression par étapes lorsque nécessaire, décisions conservées, contrôles explicites et reprise facilitée.

> **Ce n'est pas une extension de ChatGPT.** Le projet fournit des instructions et des modèles Markdown. Les interfaces interactives dépendent des fonctionnalités réellement disponibles dans votre version de ChatGPT.

## Ce qu'il apporte

| Fonction | Comportement demandé au protocole |
| --- | --- |
| **Exécution d'abord** | Produire un résultat concret plutôt que multiplier les plans. |
| **Phases adaptées** | Aller droit au but pour une tâche simple ; structurer les travaux complexes. |
| **Continuer** | Si une vraie prochaine étape existe, proposer un bouton qui envoie le prochain prompt. |
| **Copier le prochain prompt** | Copier exactement le même prompt que celui envoyé par Continuer. |
| **Remarques facultatives** | Ajouter des modifications sans réécrire toute la consigne. |
| **Aperçu dynamique** | Visualiser le prompt actualisé avant envoi ou copie. |
| **Vérification humaine** | Afficher **REQUIRED** ou **NOT REQUIRED** en fin de **chaque** phase, même finale. |
| **Tests et autorisations** | Distinguer les vérifications manuelles des permissions d'agir ; ne jamais supposer qu'un clic valide un test. |
| **Suivi et reprise** | Préserver l'objectif, les contraintes, les décisions, les résultats et les blocages. |
| **Architecture modulaire** | Proposer, quand c'est pertinent, une séparation inspirée de MVC applicable aussi aux projets non techniques. |
| **Fin réelle** | Ne pas inventer d'étape supplémentaire une fois le travail achevé. |

## Démarrage rapide

**Option A — télécharger le dépôt**

1. Cliquez sur **Code → Download ZIP** sur GitHub
2. Ouvrez [`PROMPT_DE_DEMARRAGE.md`](PROMPT_DE_DEMARRAGE.md), copiez le prompt qu'il contient, remplacez `[MA DEMANDE]` par votre objectif.
3. Dans ChatGPT, joignez l'archive ZIP.


**Option B — copier les fichiers**

Récupérez les documents de ce dépôt et mettez-les à disposition de la conversation. Le protocole ne peut être appliqué complètement que si ChatGPT peut effectivement lire les règles concernées.

### Exemple de demande

> Organise mon déménagement : calendrier, budget, tâches prioritaires et points à vérifier. Avance étape par étape si nécessaire, tout en me laissant ajouter mes remarques.

Consultez [`START_HERE.md`](START_HERE.md) pour les explications détaillées et [`EXEMPLES.md`](EXEMPLES.md) pour d'autres cas.

## Continuer + Copier + remarques : comment ça fonctionne ?

Quand une étape utile reste à effectuer, l'expérience cible comporte :

1. Un champ facultatif **« Remarques pour la prochaine étape »**.
2. Un **aperçu du prochain prompt** qui reflète les remarques saisies.
3. **« Continuer — prochaine étape »**, qui envoie le prompt.
4. **« Copier le prochain prompt »**, qui copie **le même texte** pour le réutiliser ailleurs.

Les remarques sont transmises telles qu'écrites ; ChatGPT doit les reformuler fidèlement en instructions opérationnelles au tour suivant. **Le clic sur Continuer n'est jamais une preuve qu'un test a réussi ni une autorisation implicite.**

Si les contrôles interactifs ne sont pas disponibles, le protocole prévoit **un prompt textuel à copier manuellement**. Il ne peut pas ajouter des boutons à une interface qui ne les prend pas en charge.

Voir [`CONTINUATION_UI.md`](CONTINUATION_UI.md) pour le contrat complet.

## Vérification humaine : obligatoire à chaque phase

Chaque phase doit se terminer par l'un des deux statuts suivants :

- **`VÉRIFICATION HUMAINE : REQUIRED`** — un contrôle de l'utilisateur est indispensable ; ChatGPT doit fournir des étapes de test, les critères de réussite et le retour attendu.
- **`VÉRIFICATION HUMAINE : NOT REQUIRED`** — aucune vérification manuelle indispensable n'est attendue pour continuer ou clôturer.

Une **autorisation d'effectuer une action** est distincte de la **vérification d'un résultat**. Une étape bloquée reste bloquée jusqu'au retour pertinent.

Voir [`QUALITE_ET_VERIFICATION.md`](QUALITE_ET_VERIFICATION.md).

## Architecture facultative inspirée de MVC

Pour un travail important, le protocole peut séparer :

- **Modèle** : faits, données, contenu et contraintes.
- **Vue** : formats de restitution (rapport, planning, supports, etc.).
- **Contrôleur** : enchaînement des actions, décisions et règles de progression.

Il s'agit d'une **méthode d'organisation**, et non d'une obligation de développement logiciel. Pour une demande simple, elle n'est pas nécessaire. Détails : [`ARCHITECTURE_MODULAIRE.md`](ARCHITECTURE_MODULAIRE.md).

## Structure du dépôt

| Fichier | Fonction |
| --- | --- |
| [`PROMPT_DE_DEMARRAGE.md`](PROMPT_DE_DEMARRAGE.md) | Prompt universel à copier |
| [`START_HERE.md`](START_HERE.md) | Prise en main |
| [`RULES.md`](RULES.md) | Règles permanentes |
| [`WORKFLOW.md`](WORKFLOW.md) | Phases, suivi et clôture |
| [`CONTINUATION_UI.md`](CONTINUATION_UI.md) | Boutons, remarques, aperçu, mode de repli |
| [`QUALITE_ET_VERIFICATION.md`](QUALITE_ET_VERIFICATION.md) | Contrôles, blocages et autorisations |
| [`ARCHITECTURE_MODULAIRE.md`](ARCHITECTURE_MODULAIRE.md) | Modularité facultative |
| [`EXEMPLES.md`](EXEMPLES.md) | Cas d'utilisation |
| [`Templates/ETAT_ET_REPRISE.md`](Templates/ETAT_ET_REPRISE.md) | État de reprise |
| [`Templates/JOURNAL_DECISIONS.md`](Templates/JOURNAL_DECISIONS.md) | Journal des décisions |

## Ce que ce projet ne garantit pas

- L'affichage de boutons interactifs dans tous les clients ChatGPT.
- La conservation automatique des fichiers et de la mémoire entre conversations.
- L'accès à des applications ou documents non connectés.
- L'exécution en arrière-plan sans fonctionnalité prévue à cet effet.
- Des résultats infaillibles ou des validations humaines automatiques.

Il s'agit d'un **protocole de comportement**, pas d'un logiciel installé, ni d'un moyen de contourner les limitations du modèle ou de l'interface.

## Contribuer et signaler un problème

Les signalements documentés et les propositions d'amélioration sont les bienvenus. Voir [`CONTRIBUTING.md`](CONTRIBUTING.md). Pour un signalement, précisez la version de ChatGPT et si le problème touche l'affichage des contrôles ou l'application des règles.

## Version et licence

Version documentée : **v3 FINAL**. Historique : [`CHANGELOG.md`](CHANGELOG.md).

**Licence à définir par le propriétaire du dépôt avant publication.** Aucun droit de réutilisation n'est accordé automatiquement en l'absence de licence explicite. Le fichier [`LICENCE_A_CHOISIR.md`](LICENCE_A_CHOISIR.md) explique les choix possibles.

---

*Projet indépendant, non officiel et non affilié à OpenAI.*
