## Laboratoire sur AJAX

Ce laboratoire commence avec un simple projet MVC (modèle-vue-contrôleur) de base.
La seule chose qui a été ajouté, c'est une vue qui se nomme **Partielle.cshtml**

### Afficher une vue partielle obtenu par un appel AJAX
1. Créer une action dans le contrôleur Home qui retourne la vue partielle qui existe déjà
  - Si l'action a le même nom que la Vue, return View(); est suffisant, sinon il faut faire return View("Partielle");
2. Modifier le fichier index.cshtml et ajouter un id au div pour facilement l'obtenir dans un script
3. Écrire un script en JS qui fait un appel $.get et obtient la vue partielle
4. Utiliser la fonction jQuery .html(x) pour mettre le contenu de la vue partielle à l'intérieur du div
![alt text](image.png)

### Afficher une vue partielle en envoyant des données
#### JS
1. Ajoutez un input de type number et un autre de type texte
2. Ajouter un bouton à la page index et appeler un fonction JS lorsque vous cliquez dessus
![alt text](image-1.png)
3. Créer un objet avec les propriétés qty et texte qui sont les valeurs des 2 inputs
```
let data = {
   qty: x,
   texte: y
};
```
4. Commencer par faire utiliser alert ou console.log dans la fonction pour vérifier que ça fonctionne.
5. Ajoutez un appel $.get qui passe l’objet data et qui appelle l’action Partielle2 (Que vous allez ajouter bientôt)
6. Ajoutez également un id et la méthode de callback qui va mettre le contenu html dans l’autre div. (Exactement comme on a fait dans la partie précédente)

#### C#
- Créer une classe Partielle2DTO avec les propriétés int Qty et string Texte
- Dans votre contrôleur HomeController, ajouter une méthode Partielle2 qui reçoit en paramètres un Partielle2DTO
- Ajouter un point d'arrêt et vérifier que l'objet est bien reçu

![alt text](image-2.png)