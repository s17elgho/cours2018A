## Tutorial pour contribuer

`git clone https://github.com/explorweb/cours2018A.git ` ou `git checkout` pour créer une branche

mkdocs new cours2018A/
cd cours2018A

mkdocs serve

* ajouter son contenu
* mettre à jour le fichier de configuration à la racine : mkdocs.yml
### et plus bas



# Welcome to MkDocs

For full documentation visit [mkdocs.org](http://mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
  * set the site on `http:\\localhost:8000` or evenly on `http:\\127.0.0.1:8000`
* `mkdocs build` - Build the documentation site.
* `mkdocs gh-deploy` - Deploy the site
* `mkdocs help` - Print this help message.
## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
