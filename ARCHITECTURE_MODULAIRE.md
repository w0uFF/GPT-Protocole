# Architecture modulaire facultative (inspirée de MVC)

## Pourquoi

Pour un projet étendu, séparer les **informations**, leur **présentation** et la **logique de coordination** évite qu'un changement local oblige à refaire l'ensemble. Cette approche est inspirée du modèle MVC (Model / View / Controller), **sans exiger de programmation** et sans prétendre être une architecture universelle.

## Trois responsabilités distinctes

| Concept | Rôle dans un projet généraliste | Exemples |
|---|---|---|
| **Modèle** | Connaissances, données, règles, contraintes, contenus sources | Faits d'un rapport, programme pédagogique, liste de tâches |
| **Vue** | Restitution adaptée aux personnes et aux supports | Rapport, tableau, fiche, calendrier, support de formation |
| **Contrôleur** | Processus, décisions, transformations et enchaînement | Validation, priorisation, progression, publication |

### Exemple : formation

- **Modèle :** objectifs pédagogiques, notions, exercices et corrigés.
- **Vue :** pages de cours, fiches et quiz.
- **Contrôleur :** critères de progression et adaptation des prochaines séances.

Modifier la présentation ne doit pas altérer les faits ; changer une règle de progression ne doit pas obliger à réécrire tout le contenu.

### Exemple : organisation d'un événement

- **Modèle :** budget, fournisseurs, invités, contraintes.
- **Vue :** planning, invitations, tableau de suivi.
- **Contrôleur :** calendrier des décisions, responsables, conditions de validation.

## Règles de modularité proportionnée

1. N'utiliser cette séparation que si le projet a plusieurs livrables, des changements attendus ou des dépendances qui la justifient.
2. Chaque module possède une responsabilité claire ; conserver les interfaces ou formats d'échange nécessaires sans ajouter de couches décoratives.
3. Garder une **source de vérité** pour chaque information importante ; éviter plusieurs versions contradictoires.
4. Décrire les dépendances et les conséquences d'un changement majeur.
5. Prévoir des extensions simples si l'utilisateur anticipe de nouvelles catégories, contenus, activités ou modules.
6. Réutiliser les modèles pertinents, pas créer systématiquement des fichiers.
7. Pour les tâches simples, ne pas parler de MVC : livrer directement.

Le protocole **propose** cette méthode d'organisation ; il ne fabrique pas automatiquement un système technique ni une architecture complète sans éléments de projet.
