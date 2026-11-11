# Processus de travail généraliste

## 1. Comprendre, puis réaliser

Identifier le résultat attendu, les exigences explicites et les informations disponibles. Consulter les documents si nécessaires et accessibles. Pour les ambiguïtés non bloquantes, choisir une hypothèse raisonnable en la signalant. Pour une information indispensable manquante, poser uniquement la question utile. Exécuter immédiatement ce qui peut l'être.

## 2. Choisir la bonne échelle

- **Simple :** livrer directement, vérifier, conclure (pas de phase factice).
- **Complexe :** regrouper les activités dépendantes en phases productives, chacune avec un résultat exploitable.
- **Long :** tenir à jour les états et décisions à l'aide des modèles facultatifs ; ne pas créer des documents administratifs pour le plaisir.
- **Modulaire :** si le projet possède plusieurs composantes réutilisables, appliquer `ARCHITECTURE_MODULAIRE.md` seulement au niveau de détail qui sert le résultat.

## 3. Bilan obligatoire à la fin de CHAQUE phase (y compris finale)

1. **Phase et statut :** TERMINÉE / PARTIELLE / BLOQUÉE / EN ATTENTE DE VÉRIFICATION / EN ATTENTE D'AUTORISATION.
2. **Livré :** ce qui existe vraiment, avec fichiers ou liens vérifiés lorsqu'ils existent.
3. **Contrôles :** ce qui a été vérifié, ce qui reste incertain.
4. **VÉRIFICATION HUMAINE : REQUIRED / NOT REQUIRED** — cette ligne est obligatoire sans exception. Si REQUIRED, donner actions, résultat attendu, retour demandé et conséquences du test.
5. **AUTORISATION HUMAINE : REQUIRED / NOT REQUIRED** lorsque pertinent ; elle ne remplace jamais la ligne de vérification.
6. **Suite :** prochaine action concrète uniquement s'il reste un travail utile ou un blocage à résoudre.

`NOT REQUIRED` signifie qu'aucune vérification manuelle indispensable n'est attendue pour progresser ; cela ne signifie **pas** « qualité parfaite » ou « tous les tests effectués ».

## 4. Gestion des validations bloquantes

- Si REQUIRED et non confirmée : marquer EN ATTENTE DE VÉRIFICATION ; ne pas déclarer la phase validée.
- Lorsque l'utilisateur appuie sur Continuer sans fournir de résultat de test : le prompt suivant demande ou vérifie ce retour, ou avance uniquement sur des tâches indépendantes, mais **ne suppose jamais la réussite**.
- Si l'utilisateur indique un échec : enregistrer le défaut, diagnostiquer/corriger les éléments accessibles, puis demander une nouvelle vérification si indispensable.
- Si l'utilisateur confirme un test réussi : enregistrer la confirmation et la portée exacte ; ne pas extrapoler à d'autres fonctions.
- Une autorisation requise est un blocage différent : obtenir la permission explicite avant l'action concernée.

## 5. Préserver et arbitrer les décisions

Utiliser `Templates/JOURNAL_DECISIONS.md` si plusieurs décisions risquent de se contredire. Les nouvelles remarques de l'utilisateur peuvent modifier d'anciennes décisions de même niveau ; signaler clairement les conséquences et chercher un arbitrage uniquement lorsque le conflit bloque l'exécution ou rendrait le résultat trompeur.

## 6. Reprise et continuité

Le prompt suivant décrit objectif, état confirmé, résultats vérifiés, décisions actives, fichiers réellement disponibles, obstacles, vérification en attente, prochaine action, remarques originales et instruction de reformulation. Un prompt de reprise ne remplace pas les pièces jointes indispensables. Voir `Templates/ETAT_ET_REPRISE.md`.

## 7. Clôture et critère d'arrêt

Terminer lorsque toutes les exigences explicites réalisables ont un résultat, que les contrôles disponibles sont achevés, que les limites ou réserves sont déclarées et qu'aucune action réellement utile n'est en attente. Montrer le statut de vérification humaine final. **Ne pas proposer de bouton Continuer pour inventer une phase**. Si des travaux optionnels subsistent, les décrire sans les imposer.
