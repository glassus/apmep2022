# Créer son propre site


## 1. Préparation de l'installation

### 1.1. Les pré-requis

!!! tip "Pré-requis logiciels et packages Python"
    Les logiciels suivants sont nécessaires :

    - [Git](https://git-scm.com/){. target="_blank"}
    - [VisualStudioCode](https://code.visualstudio.com/){. target="_blank"} (ou son équivalent libre [VSCodium](https://vscodium.com/){. target="_blank"})
    - Une version récente de [Python](https://www.python.org/downloads/){. target="_blank"} doit également être installée.

    Les packages Python ```mkdocs-material```, ```mkdocs-macros-plugin```, ```mkdocs-awesome-pages-plugin```, ```mkdocs-git-revision-date-localized-plugin``` doivent ensuite être installés, par exemple par les commandes :

    ```python
    pip install mkdocs-material mkdocs-macros-plugin mkdocs-awesome-pages-plugin mkdocs-git-revision-date-localized-plugin
    ```

### 1.2. Hébergement des pages

Dans nos exemples, les pages sont hébergées chez [GitHub](https://github.com/){. target="_blank"}, chez qui la création d'un compte est donc nécessaire. 

Toutefois, une alternative libre existe et propose un service équivalent : [GitLab](https://gitlab.com/gitlab-org/gitlab){. target="_blank"} : 


## 2. Création d'un nouveau dépôt

La méthode présentée ci-dessous va consister à cloner (*forker*) un dépôt déjà existant, contenant la structure minimale d'un site en MkDocs.

Ce site minimal est visible à l'adresse [https://nsi-mauriac.github.io/mkdocs-modele/](https://nsi-mauriac.github.io/mkdocs-modele/){. target="_blank"}.

### 2.1 Sur ```GitHub.com``` : fork du site modèle

1. Connectez-vous sur [GitHub](https://github.com/){. target="_blank"}.
2. Allez à l'adresse [https://github.com/NSI-Mauriac/mkdocs-modele](https://github.com/NSI-Mauriac/mkdocs-modele){. target="_blank"} et cliquer sur le bouton ```Fork``` en haut à droite.
3. Choisissez un nouveau nom pour votre dépôt (votre *repository*).

### 2.2 Sur votre ordinateur : clonage de votre dépôt

1. Sur la page d'accueil de votre dépôt GitHub, cliquez sur le bouton vert ```Code``` et copiez l'adresse affichée, qui doit ressembler à ```https://github.com/<username>/<nomdudépot>.git```. 
2. Sur votre ordinateur, ouvrez un Terminal et tapez la commande 

```git clone https://github.com/<username>/<nomdudépot>.git```  (vous pouvez y coller votre adresse par ```Ctrl-Maj-V```).

Cette commande va permettre de rapatrier sur votre disque dur votre dépôt, pour l'instant uniquement présent sur les serveurs de GitHub.


## 3. Visualisation du site en local

1. Ouvrez dans VisualStudioCode le dossier de votre dépôt.
2. Dans Terminal, cliquez sur Nouveau terminal pour faire apparaître un nouveau terminal
3. Dans ce terminal, placez vous dans le répertoire de votre dépôt.
4. Tapez la commande ```mkdocs serve```.
5. Un serveur se lance et votre page devient normalement visible dans votre navigateur à l'adresse ```http://127.0.0.1:8000/```.


## 4. Hébergement du site sur les serveurs de ```GitHub```: activation des ```GitHub Pages``` 

1. Toujours en local, dans un Terminal de VSC, tapez la commande ```mkdocs gh-deploy```. Cette commande, qui ne sera réalisée qu'une seule fois, permet de générer toute l'architecture de votre site pour son déploiement sur les pages de ```GitHub```. Elle sera faite automatiquement par la suite sur les serveurs de ```GitHub``` à chaque modification de vos pages.
2. Connectez-vous sur [GitHub](https://github.com/){. target="_blank"} et allez sur la page d'accuil de votre dépôt.
3. Cliquez sur ```Settings```, puis dans la colonne de gauche sur ```Pages```.
4. Dans la partie ```Build and deployment```, choisir la branche ```gh-pages``` puis cliquer sur ```Save```.
5. Quelques instants plus tard, votre site est visible à la page ```https://<username>.github.io/<nomdudepot>``` 


## 5. Fonctionnement quotidien : routines de modification du site

1. Ouvrir VSC, lancer ```mkdocs serve```.
2. Ouvrir la page ```127.0.0.1:8000``` dans son navigateur.
3. Dans VSC, rédiger ses documents en Markdown, faire un ```Ctrl-S``` pour vérifier en local les changements sur le site.
4. Pour valider les changements et les rendre visibles sur ```GitHub```, aller dans la partie ```Contrôle du code-source``` de VSC, sur le bandeau latéral gauche. 
5. Les fichiers modifiés apparaissent. Écrire quelques mots pour décrire les changements puis cliquer sur ```Validation```. 
6. Cliquer ensuite sur ```Synchroniser les modifications```. 