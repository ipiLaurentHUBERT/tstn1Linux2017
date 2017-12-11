# Découverte HTML et Javascript

## Exercices


### Utilisation de la console

Prendre le fichier `index-javascript-programme.html`


#### Programme Hello world

C'est le programme le plus simple.

Ajouter l'instruction suivante entre les balises `<script>` et `</script>`:

```javascript
console.log("Hello world !")
```

Ouvrir le fichier `html` dans votre navigateur et afficher les outils du développeur. Aller dans l'onglet **Console**.

Que voyez-vous ?

#### Affectation de variable

A la suite du programme précédent (toujours entre les balises `script`) ajouter l'instruction suivante:

```javascript
texte = "Mon texte"
```

Vous venez d'affecter votre première variable.

Rechargez la page et observez la console, que constatez-vous ?

Ajoutez maintenant l'instruction suivante à la dernière ligne de votre script:

```javascript
console.log(texte)
```

#### Création d'une nouvelle variable

Ajoutez les instructions suivantes:

```javascript
var deuxieme = "second texte"
//Commentaire: la bonne manière de déclarer une variable est de faire précéder son nom par la déclaration `var`

console.log(deuxieme)
console.log(texte)
```

Que constatez-vous ?


#### Affectation de variables entières

Affecter la valeur 2 à une nouvelle variable `a` et la valeur 4 à `b` en écrivant ce programme:

```javascript
a = 2
b = 4
console.log("a=" , a)
console.log("b=" , a)
```

Exécutez le programme en rechargeant le document html

#### Permutations de variables


Tentez maintenant de permuter les valeurs des variables `a` et `b`.

Que constatez-vous ? De quoi avez-vous besoin pour que cela fonctionne correctement ?

#### Opérateurs mathématiques

Cette page donne un résumé des opérations arithmétiques disponibles en javascript :

https://www.w3schools.com/js/js_operators.asp

Vous allez vous intéresser aux opérations suivantes:

| Operator |	Description | Remarque |
|---|---|---|
|+  |	Addition      |   |
|-  |	Subtraction   |   |
|*  |	Multiplication|   |
|/  |	Division      |   |
|%  |	Modulo       | Reste de la division euclidienne  |
|++ | 	Incrémentation unaire    | essayer de placer l'opérateur avant ou après l'opérande pour en constater les effets  |
|-- | 	Décrémententation unaire    | essayer de placer l'opérateur avant ou après l'opérande pour en constater les effets |

Une opération unaire s'applique sur une seule opérande


### Fonctions

Utilisez un nouveau fichier html (en vous basant sur le fichier html précédemment utilisé), que vous nommerez `index-javascript-fonctions.html`

Une fonction est un conteneur qui permet de stocker des suites d'instructions dans un programme.

La déclaration se fait avec

- le mot clé `function`
- suivi du nom de la fonction (qui servira d'identifiant à cette fonction)
- une parenthèse ouvrante
- une liste d'arguments (ou paramètres de la fonction)
- une parenthèse fermante
- une accolade ouvrante
- une suite d'instructions
- une accolade fermante

L'appel de la fonction se fait en écrivant de la fonction suivie d'une parenthèse ouvrante, des valeurs à affecter aux paramètres puis d'une parenthèse fermante.

#### Fonction sans argument


```javascript
function bonjour(){
  console.log("Hello world depuis une fonction")
}
bonjour()
```


#### Multiplication

Voici un exemple de fonction permettant de multiplier deux valeurs:

```javascript
function multiplication(x, y){
  return x * y
}
var resultat = multiplication(3, 4)
console.log(resultat)
```

#### Autres opérations

Ecrire dans votre programme les fonctions pour les autres opérateurs:

- `addition`
- `division`
- `soustraction`
- `modulo`
- `incremente`
- `decremente`

Exécuter ces fonctions dans votre programme

### Stockage de valeur javascript

#### Exercice 1
Prendre le fichier `index-javascript-2-button.html` et le modifier pour qu'un nouvel appui sur le bouton rétablisse la valeur initiale

#### Exercice 2

Faire en sorte que chaque appui sur le bouton permette de boucler sur la valeur du texte affiché :

  - Un appui: "Le bouton a été appuyé"
  - second appui: "Du texte dans le paragraphe"
  - troisième appui: "Le bouton a été appuyé"
  - quatrième appui: "Du texte dans le paragraphe"
  - cinquième appui: "Le bouton a été appuyé"
  - etc

#### Exercice 3

Chaque appui sur le bouton va ajouter un nouveau mot au texte existant.

- Un appui: "Du texte dans le paragraphe"
- second appui: "Du texte dans le paragraphe. Le"
- troisième appui: "Du texte dans le paragraphe. Le bouton"
- quatrième appui: "Du texte dans le paragraphe. Le bouton a"
- cinquième appui: "Du texte dans le paragraphe. Le bouton a été"
- etc

#### Exercice 4

Vous allez rajouter une zone de texte avec un nouvel identifiant (`id="nombre_click"`), en dessous du `paragraph` ayant l'id `texte`

Cette zone de texte affiche le nombre de click sur le bouton qui ont été effectués depuis le chargement de la page.

Lors de l'appui sur le bouton, vous devez incrémenter ce nombre de clicks et l'afficher dans la zone `nombre_click`.

#### Exercice 5

Rajouter une zone de texte avec un nouvel identifiant (`id="parite_nombre_click"`), en dessous du `paragraph` ayant l'id `nombre_click`


A chaque appui sur le bouton, après avoir incrémenté la valeur du nombre de click, indiqué dans cette dernière zone si le nombre de click est pair ou impair.

- Exemple: `Nombre de click est pair`
- Exemple: `Nombre de click est impair`

### Opérations sur les chaînes de caractères

La page https://www.w3schools.com/jsref/jsref_obj_string.asp donne une vision de l'ensemble des fonctions disponibles pour manipuler des chaînes de caractères.

#### Exemples

Pour connaître la longueur d'une chaîne, on utilise son attribut `length`

```javascript
var dixLettres = "abcdefghij"
console.log(dixLettres.length) //10
```

La méthode `charAt()` donne le caractère positionné à l'index donné en paramètre:

```javascript
console.log(dixLettres.charAt(0)) //a
console.log(dixLettres.charAt(1)) //b
console.log(dixLettres.charAt(2)) //c
```

La méthode `substr()` renvoie un sous-ensemble de la chaîne:

```javascript
//A partir du 3ème caractère
console.log(dixLettres.substr(2)) //cdefghij
```

```javascript
//A partir du 3ème caractère, longueur 2
console.log(dixLettres.substr(4,2)) //cd
```

La méthode `substring()` renvoie un sous-ensemble de la chaîne:

```javascript
//A partir du 3ème caractère
console.log(dixLettres.substring(2)) //cdefghij
```

```javascript
//Entre le 5ème et le 3ème caractère
console.log(dixLettres.substring(4,2)) //cd
//Entre le 3ème (inclu) et le 7ème (exclu) caractère
console.log(dixLettres.substring(2,6)) //cde
```

### Boucles

Nous allons maintenant utiliser des boucles pour modifier la page.

Les boucles disponibles en Javascript sont les boucles `for`, `while` et `do . . . while`

La page suivante donne plus d'explications:

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration

#### Exercices

Reprendre le fichier `index-javascript-2-button.html` et le renommer en `index-javascript-2-button-exerciceX.html` ou X sera remplacé par le numéro de l'exercice.

##### Exercice 6

Lors de l'appui sur le bouton, vous devez ajouter autant de paragraphes que de lettres du texte initial dans le document HTML.

Pour cela, vous allez vous appuyer sur cet exemple, qui montre comment ajouter un élément texte dans un autre élément:

```javascript
function nomFonction(){
    var node = document.getElementById("texte");
    node.innerHTML = "Le bouton a été appuyé"

    var contenant = document.getElementById("container");
    var parag = document.createElement("P"); //créer un paragraphe
    parag.innerHTML = "Z"
    contenant.appendChild(parag)
}
```

Au moment de l'appui sur le bouton, on devrait voir apparaître ceci (en dessous du nouveau texte `Le bouton a été appuyé`):

```
D
u

t
e
x
t
e

d
a
n
s

l
e

p
a
r
a
g
r
a
p
h
e
```

#### Exercice 7

Maintenant, on vous demande d'afficher le texte initial en lui enlevant le dernier caractère à chaque nouveau paragraphe jusqu'à ce qu'il n'y ai plus aucun caractère à afficher:

```
Du texte dans le paragraphe
Du texte dans le paragraph
Du texte dans le paragrap
Du texte dans le paragra
Du texte dans le paragr
Du texte dans le parag
...
```

#### Exercice 7

Idem mais cette fois il faut enlever le premier caractère à chaque nouveau paragraphe jusqu'à ce qu'il n'y ai plus aucun caractère à afficher:

```
Du texte dans le paragraphe
u texte dans le paragraphe
 texte dans le paragraphe
texte dans le paragraphe
exte dans le paragraphe
xte dans le paragraphe
...
```

#### Exercice 9

Ici, on vous demande d'afficher le texte initial en l'inversant plutôt que de le remplacer par un nouveau texte:

```
ehpargarap el snad etxte uD
```
 
