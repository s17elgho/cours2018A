# éléments pour réaliser du contenu

## Récupérer le source du Site Web et améliorez le

* [Github](https://github.com/) sera notre outil commun de gestion de code.
* Ce site est proposé en tant que [dépôt sur Github](https://github.com/explorweb/cours2018A)
* Commencez par trouver et suivre un tutorial de prise en main de git et de Github
  * Pour travailler dans le cadre du cours, il vous faudra :
    * savoir travailler sur des dépôts sur l'espace local d'un ordinateur. Vous pouvez utiliser le mode ligne ou un outil comme Github Desktop ;
    * savoir créer des branches ( fork ) du dépôt principal du cours, et proposer vos ajouts (Pull request) ;
* Créer une branche ou une copie personnelle pour travailler
* Pour l'instant, vous ne pouvez pas directement modifier la branche principale, Vous devez donc effectuer des `Pull request` qui seront analysées par l'enseignant.

***Un mode d'emploi simplifié sera le bienvenu.***

# Comprendre les principes de publication retenus

Le site web du cours est ce qu'on appelle un site statique. Une arborescence de documents sources et de documents de forme est développée et "compilée" par un outil de traduction en une arborescence de fichiers html, css et autres directement consultable par un navigateur.

Les [Github pages](https://pages.github.com/) proposent à la fois :

   * un outil de génération par défaut [Jekyll] (https://jekyllrb.com/)
   * la publication sur le web au travers d'une url correspondant à votre projet
Et bien plus encore, mais cela suffit dans un premier temps.

Dans notre cas, nous utilisons un outil de génération différent [mkdocs.org](http://mkdocs.org) mais nous utiliserons le même mécanisme de publication en mettant à disposition le résultat de la génération sur  une branche dédié `https://github.com/explorweb/cours2018A/tree/gh-pages`

Vous pouvez tester localement la mise en page de vos écrits en installant mkdocs sur votre PC. Le tutorial proposé est simple et efficace.

Les commandes principales de mkdocs sont :

* pour l'initialisation d'un répertoire  `mkdocs new [dir-name]`. Faire cela avant de récupérer un dépôt local de votre branche dans le répertoire choisi.
* aller dans le répertoire en question `cd [dir-name]`
* `mkdocs serve` démarre un serveur 'live' local sur votre machine qui se mettra à jour au fur et à mesure que vous modifierez le contenu

Si vous ajoutez une page sur le site :

* Créer un document dans le bon répertoire (*a priori* `docs/cours`)  et le compléter.    
* Mettre à jour le fichier de configuration à la racine `mkdocs.yml` pour positionner votre page sur le site.


Lorsque les modifications seront acceptées sur la branche principale, la personne qui acceptera vos modifications effectuera les commandes suivantes pour déployer le site :

* `mkdocs build` - Build the documentation site.
* `mkdocs gh-deploy` - Deploy the site
