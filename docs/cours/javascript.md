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

# Utilisation du DOM

La variable la plus important quand on veut utiliser le DOM,  c'est `document`. Elle designe la balise `<html>` qui est la racine du document. Voyons dans un premier temps des méthodes utiles, puis ensuite leur utilisation.

L'accès aux balises `<head>`et `<body>` depuis le DOM est un peu à part. Il suffit simplement de taper `document.head` et `document.body`.

Prenons comme exmple le code HTML suivant :

    <!doctype html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>Ma page web</title>
        </head>
        <body>
            <h1>Ma page web</h1>
            <p>Bonjour, je m'appelle Baptiste.</p>
            <p>J'habite dans la belle ville de <a href="http://www.lyon.fr">Lyon</a>.</p>
        </body>
    </html>
    
Le DOM de ce code peut être représenté de façon hiérarchisé sous la forme d'un arbre.

![Représentation sous forme d'arbre de la page WEB d'exemple](https://s3-eu-west-1.amazonaws.com/sdz-upload/prod/upload/DOM1.DOM "Représentation sous forme d'arbre de la page WEB d'exemple")

## Parcours initial

Il est possible d'accéder à tous les noeuds avec les méthodes `childNodes` et `parentNode` qui renvoient, respectivement, un tableau contenant les noeuds fils et le noeud parent d'un noeud choisi. Il est donc théoriquement possible d'accèder à n'importe quel élément de la page depuis la racine avec ces deux méthodes.

Ainsi, si on reprends l'exemple vu plus haut, pour accèder à la balise `<a>`contenue dans le dernier noeud `<p>`, il faudrait écrire `document.body.childNodes[5].childNodes[1]`. Il y a cependant quelque chose à bien noter. Pour accéder au noeud `<p>`, on a accedé au 6ème élement de la liste des enfants de `body` (`document.body.childNodes[5]`, la numérotation commencant à 0) et non le troisième comme on aurait pu le supposer avec la vue du document sous forme d'arbre. Ceci est dû aux retours à la ligne présent dans le document HTML. En effet ils sont considérés par le DOM comme des noeuds textuels, et donc rentrent en compte dans la liste des noeuds fils.

Cette méthode d'accès a cependant des gros défauts. En effet elle est sensible à la structure de la page HTML, ce qui veut dire que si on rajoute un élément, on va devoir modifier les index utilisés pour récupérer tel ou tel élément. Ensuite elle manque de lisibilité. En effet, avec `document.body.childNodes[5]` on a accedé à une balise `<p>`, mais ce n'est pas forcément évident de savoir ce qu'on récupère. Et puis supposons que l'on souhaite récupérer toutes les balises `<p>`, c'est pas très évident à faire avec cette méthode.

Pour ce faire, d'autres méthodes de sélection d'élements existent.

## Parcours plus précis

Plusieurs méthodes existent pour permettre de sélectionner de manière plus fine et plus précise :
- `getElementsByTagName` permet de selectionner tous les éléments d'un même tag, par exemple tous les titres de niveau 2 avec `document.getElementsByTagName("h2")`,
- `getElementsByClassName` permet de selectionner tous les éléments d'un possèdant la même classe CSS, par exemple tous les éléments possédant la classe `gras` avec `document.getElementsByClassName("gras")`,
- `getElementById` permet de selectionner le premier élément qui possède l'identifiant CSS, par exemple l'élément identifié par `photoProfil` avec `document.getElementById("photoProfil")`,
- `querySelectorAll` permet de sélectionner tous les éléments qui suivent un sélecteur CSS, par exemple tous les éléments de paragraphe qui ont la classe italique avec `document.querySelectorAll("p.italique")`,
- `querySelector` fonctionne de la même manière que `querySelectorAll` à ceci près qu'il renvoie uniquement le premier élément correspondant au selecteur CSS

Considérons maintenant un exemple un peu plus complet.

    <!doctype html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>Les sept merveilles du monde</title>
        </head>
        <body>
            <h1>Les sept merveilles du monde</h1>
            <p>Connaissez-vous les merveilles du monde ?</p>
            <div id="contenu">
                <h2>Merveilles du monde antique</h2>
                <p>Cette liste nous vient de l'Antiquité.</p>
                <ul class="merveilles" id="antiques">
                    <li class="existe">La pyramide de Khéops</li>
                    <li>Les jardins suspendus de Babylone</li>
                    <li>La statue de Zeus</li>
                    <li>Le temple d'Artémis</li>
                    <li>Le mausolée d'Halicarnasse</li>
                    <li>Le Colosse de Rhodes</li>
                    <li>Le phare d'Alexandrie</li>
                </ul>
                <h2>Nouvelles merveilles du monde</h2>
                <p>Cette liste a été établie en 2009 à la suite d'un vote par Internet.</p>
                <ul class="merveilles" id="nouvelles">
                    <li class="existe">La Grande Muraille de Chine</li>
                    <li class="existe">Pétra</li>
                    <Li class="existe">Le Christ du Corcovado</Li>
                    <Li class="existe">Machu Picchu</Li>
                    <li class="existe">Chichén Itzá</li>
                    <li class="existe">Le Colisée</li>
                    <li class="existe">Le Taj Mahal</li>
                </ul>
                <h2>Références</h2>
                <ul>
                    <li><a href="https://fr.wikipedia.org/wiki/Sept_merveilles_du_monde">Merveilles antiques</a></li>
                    <li><a href="https://fr.wikipedia.org/wiki/Sept_nouvelles_merveilles_du_monde">Nouvelles merveilles</a></li>
                </ul>
            </div>
            <script src="../js/cours.js"></script>
        </body>
    </html>