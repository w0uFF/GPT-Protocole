# Interface de continuation — contrat fonctionnel

## Quand l'afficher

**Seulement** si une prochaine étape utile existe (ou si un retour nécessaire est attendu). Ne pas la rendre obligatoire sur une tâche déjà terminée. Si une validation est bloquante, l'interface doit clairement l'indiquer.

## Contrôles demandés (si la plateforme le permet)

1. **Remarques pour la prochaine étape** — champ multiligne **facultatif**.
2. **Aperçu du prochain prompt** — affiche tout le prompt calculé, actualisé lorsque les remarques changent.
3. **Continuer — prochaine étape** — bouton réel qui transmet ce prompt comme nouveau message utilisateur.
4. **Copier le prochain prompt** — bouton réel qui copie le **même texte exact** que celui transmis par Continuer, en tenant compte des remarques actuelles.

L'aperçu ne doit pas masquer le fait que la reformulation sémantique des remarques se produit au **tour suivant** : avant ce tour, afficher le texte original et l'instruction qui ordonne de le reformuler, sans prétendre qu'il est déjà transformé par IA.

## Construction du prompt (une source de vérité)

Créer **un seul** texte `prochain_prompt` depuis : objectif, état vérifié, décisions/contraintes actives, livrables accessibles, limites, statut de vérification humaine, autorisations éventuellement requises, prochaine action autorisée, remarques originales et instruction de reformulation. Utiliser exactement cette variable pour : aperçu, envoi et copie. Le prompt doit être compréhensible hors de la réponse précédente ; mentionner les pièces à joindre de nouveau si elles ne sont pas accessibles.

### Contrat minimal du texte envoyé/copié

```text
OBJECTIF : [objectif établi]
ÉTAT CONFIRMÉ : [réalisé, résultats, phase, incertitudes]
DÉCISIONS / CONTRAINTES : [consignes en vigueur]
LIVRABLES DISPONIBLES : [références réellement accessibles ou à joindre]
VÉRIFICATION HUMAINE : [REQUIRED ou NOT REQUIRED]
RÉSULTAT DE VÉRIFICATION : [confirmé, échec, non effectué ou sans objet]
AUTORISATION HUMAINE : [requise / non requise ; statut]
PROCHAINE ACTION : [action concrète ; si blocage, demander son retour]
REMARQUES ORIGINALES DE L'UTILISATEUR : [texte exact ou « aucune »]

Au début de ta réponse, reformule les remarques en consignes opérationnelles fidèles.
En cas de contradiction matérielle, expose le conflit et ne tranche pas sans base.
N'assimile pas mon clic à une validation ou une autorisation.
Réalise ensuite les actions permises ; respecte la règle de fin de phase et
propose une nouvelle interface seulement si une suite reste utile.
```

## Mise en œuvre possible dans ChatGPT

Avec les composants interactifs autorisés, conserver les remarques dans un état lié au champ multiligne, dériver `prochain_prompt` de cet état, l'afficher en aperçu, appeler l'action d'envoi de nouveau tour au clic Continuer et l'action de copie au clic Copier. Les deux actions doivent référencer le **même** `prochain_prompt`. Les noms précis des composants et actions dépendent de l'environnement : ne pas afficher de syntaxe technique inutile à l'utilisateur ordinaire. Ne jamais placer un contrôle faux ou non relié à une action réelle.

## Blocage de vérification

Si `VÉRIFICATION HUMAINE : REQUIRED` et aucun résultat confirmé : le prompt doit conserver le statut « non effectué » et demander le résultat, ou ne proposer que des travaux indépendants ; il **ne doit pas** avancer comme si la vérification était réussie. Si le test est réellement indispensable à la suite, indiquer que la continuation est bloquée et présenter les instructions de test avant les contrôles.

## Repli sans interface interactive

Afficher **le prompt intégral prêt à copier** dans un bloc clairement délimité, avec la section `REMARQUES ORIGINALES : [écrivez ici]`. Dire : « Copiez le prompt, ajoutez vos remarques, puis envoyez-le dans le chat. » Ne pas promettre de bouton, de synchronisation automatique ou de champs fonctionnels dans une interface qui ne les prend pas en charge. Dans certains clients, le copier/coller peut être manuel.

## Limites explicites

Le protocole seul ne peut installer des composants, déclencher un traitement autonome, accéder à une autre conversation, transférer des fichiers absents ni maintenir un état persistant garanti. L'état du champ peut être perdu si l'interface est rechargée. Les limites et règles applicables au produit priment.
