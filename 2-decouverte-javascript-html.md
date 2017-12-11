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

Recharger la page, que constatez-vous

#### Permutation de variable

Affecter la valeur 2 à a et la valeur 4 à b

#### Opérateurs mathématiques

https://www.w3schools.com/js/js_operators.asp




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
