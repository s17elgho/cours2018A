# Initiation au Javascript


**Prérequis**

Avant d'entamer ce module, vous n'avez besoin d'aucune connaissance préalable en JavaScript, mais vous devriez être familier avec HTML et CSS. Nous vous conseillons de lire les modules concernant HTML et CSS avant d'aller plus loin.

# Une définition générale de JavaScript

JavaScript (« JS » en abrégé) est un langage de programmation dynamique complet qui, appliqué à un document HTML, peut fournir une interactivité dynamique sur les sites Web.

# Rôles du HTML / CSS / JavaScript
![](https://i.imgur.com/njTtKgC.png)

- HTML est un langage de balisage utilisé pour structurer et donner sens au contenu web. Par exemple : définir des paragraphes, en-têtes et tables de données ou encore intégrer des images ou des vidéos dans une page.
- CSS est un langage de règles de style utilisé pour appliquer un style au contenu HTML. Par exemple : en modifiant la couleur d’arrière-plan ou les polices, ou en disposant le contenu en plusieurs colonnes.
- JavaScript est un langage de programmation qui permet de créer du contenu mis à jour de façon dynamique, de contrôler le contenu multimédia, d’animer des images, à peu près tout. Bon, peut-être pas tout, mais vous pouvez faire bien des choses avec quelques lignes de JavaScript.
- Attention: Le JavaScript est exécuté par le moteur JavaScript du navigateur, après que le HTML et le CSS aient été assemblés et combinés en une page web. Cet enchaînement est nécessaire pour être sûr que la structure et le style de la page seront déjà en place quand le JavaScript commencera son exécution.

# Notion de DOM
## Présentation du DOM

Le Document Object Model (DOM) est une interface de programmation pour les documents HTML et XML. Il fournit une page dont des programmes peuvent modifier la structure, son style et son contenu. Cette représentation du document permet de le voir comme un groupe structuré de nœuds et d'objets possédant différentes propriétés et méthodes. Fondamentalement, il relie les pages Web aux scripts ou langages de programmation.

Une page Web est un document. Celui-ci peut être affiché soit dans la fenêtre du navigateur, soit sous la forme de son code source HTML. Mais il s'agit du même document dans les deux cas. Le modèle objet de document proposé par le DOM fournit une autre manière de représenter, stocker et manipuler ce même document. Le DOM est une représentation entièrement orientée objet de la page Web, et peut être manipulé à l'aide d'un langage de script comme JavaScript.

## DOM et JavaScript

Les codes qui sont écrit en JavaScript peuvent utiliser le DOM pour accéder au document et à ses éléments. Le DOM n'est pas un langage de programmation, mais sans lui le langage JavaScript n'aurait aucun modèle ni aucune notion des pages Web, des documents XML, et des éléments pour lesquels il est généralement utilisé. Chaque élément d'un document, que ce soit le document lui-même, ses en-têtes, les tableaux internes au document, les en-têtes de colonnes et le texte contenu dans les cellules de ces tableaux, fait partie du modèle objet de document (DOM) de ce document. Tous ces éléments sont donc accessibles et peuvent être manipulés à l'aide du DOM et d'un langage de script comme JavaScript.

À l'origine, JavaScript et le DOM étaient fortement liés, mais ils ont fini par évoluer en deux entités distinctes. Le contenu de la page est stocké dans le DOM et on peut y accéder et le manipuler via JavaScript, de la sorte qu'on pourrait écrire cette équation approximative :

API (page Web ou XML) = DOM + JS (langage de script)

Le DOM a été conçu pour être indépendant de tout langage de programmation, ce qui rend la représentation structurelle du document disponible à l'aide d'une API simple et cohérente.

# Premiers pas en JavaScript

## Ajouter des variables pour stocker les données

Une variable est un conteneur pour une valeur, tel un nombre à utiliser pour une addition, ou une chaîne devant faire partie d'une phrase. Mais un aspect spécial des variables est que les valeurs contenues peuvent changer. Voyons un exemple simple :

```
<button>Pressez moi</button>
```

```
var button = document.querySelector('button');

button.onclick = function() {
  var name = prompt('Quel est votre nom ?');
  alert('Salut ' + name + ', sympa de vous voir !');
}
```
Dans cet exemple, presser le bouton déclenche l'exécution de quelques lignes de code. La première ligne affiche à l'écran une boîte priant le lecteur de saisir son nom et stocke la valeur entrée dans une variable. La deuxième affiche un message de bienvenue qui contient le nom, pris dans la valeur de la variable.

## Les Fonctions

- Fonctions personnalisées
```
function draw() {
  ctx.clearRect(0,0,WIDTH,HEIGHT);
  for (var i = 0; i < 100; i++) {
    ctx.beginPath();
    ctx.fillStyle = 'rgba(255,0,0,0.5)';
    ctx.arc(random(WIDTH), random(HEIGHT), random(50), 0, 2 * Math.PI);
    ctx.fill();
  }
}
```
Cette fonction dessine 100 cercles aléatoires dans un élément canvas. À chaque fois que nous voulons faire cela, il suffit d'invoquer la fonction comme suit :

```
draw();
```
- Fonctions anonymes
 vous pouvez également créer une fonction qui n'a pas de nom :
```
function() {
  alert('hello');
}
```
Ceci est une fonction anonyme— elle n'a pas de nom ! De plus, elle ne produira pas d'effet par elle-même. Les fonctions anonymes sont généralement utilisées en association avec un gestionnaire d'évènement, comme dans l'exemple suivant qui lance le code inscrit dans la fonction lorsque le bouton associé est cliqué :
```
var myButton = document.querySelector('button');

myButton.onclick = function() {
  alert('hello');
}
```
## Objet et héritage

- Les bases de l'objet

Un objet est une collection de données relatives entre elles et/ou de fonctionnalités (qui, souvent, se composent de plusieurs variables et fonctions, appelées propriétés et méthodes quand elles sont dans des objets). Prenons un exemple pour voir à quoi elles ressemblent.

Comme souvent dans JavaScript, pour créer un objet, on commence avec la définition et l'initialisation d'une variable. Essayez de mettre le code ci-dessous sous le code déjà écrit de votre fichier JavaScript, puis sauvegardez et rafraichissez la page :

```
var personne = {};
```

Félicitations, vous avez créé votre premier objet ! Mais c'est un objet vide, on ne peut pas faire grand-chose avec. Modifions notre objet pour qu'il ressemble à ceci :

```
var personne = {
  nom: ['Jean', 'Martin'],
  age: 32,
  sexe: 'masculin',
  interets: ['musique', 'skier'],
  bio: function() {
    alert(this.nom[0] + ' ' + this.nom[1] + ' a ' + this.age + ' ans. Il aime ' + this.interets[0] + ' et ' + this.interets[1] + '.');
  },
  salutation: function() {
    alert('Bonjour ! Je suis ' + this.nom[0] + '.');
  }
};
```
Vous avez désormais des données et des fonctionnalités dans votre objet, et vous pouvez y accéder avec une une syntaxe simple et claire !

```
personne.nom[0]
personne.age
personne.interets[1]
personne.bio()
personne.salutation()
```

- Héritage

Ci-dessus vous trouverez le constructeur Personne ():
```
function Personne(prenom, nom, age, genre, interets) {
  this.nom = {
    prenom,
    nom
  };
  this.age = age;
  this.genre = genre;
  this.interets = interets;
};
```
L'ensemble des méthodes est défini dans le prototype :
```
Personne.prototype.saluer = function() {
  alert('Salut! Je suis ' + this.nom.prenom + '.');
};
```
Essayons de créer une classe Professeur similaire à celle que nous avons utilisée jusqu'ici dans les autres modules d'initiations à l'approche objet. Ainsi, cette classe hérite de Personne mais possède aussi :

Un nouvel attribut matière — qui contiendra la matière que le professeur enseigne.
Une méthode saluer un peu plus élaborée, qui sera un peu plus formelle que la méthode de base, cela sera plus approprié, lorsque le professeur s'adrressera à des étudiants, par exemple.

La première chose à faire est de créer le constructeur Professeur() via l'ajout du code suivant :

```
function Professeur(prenom, nom, age, genre, interets, matiere) {
  Personne.call(this, prenom, nom, age, genre, interets);

  this.matiere = matiere;
}
```
Cela ressemble beaucoup au constructeur Personne mais il y a quelque chose que nous n'avons pas encore vu : la fonction call(). Cette fonction permet d'appeler une fonction définie ailleurs dans le contexte actuel. Le premier paramètre spécifie la valeur de this que l'on souhaite utiliser lors que l'on utilisera la fonction, les paramètres suivants seront les paramètres qui pourront être passés en arguments lorsqu'elle sera appelée.

Nous voulons que le constructeur Professeur() aie les mêmes attributs que Personne(), nous les spécifions donc dans l'appel fait via la fonction call().

La dernière ligne au sein du constructeur sert simplement à définir l'attribut matière que les professeurs enseignent, ce qui n'est pas valable pour les personnes génériques.