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
    pip install mkdocs-material
    pip install mkdocs-macros-plugin
    pip install mkdocs-awesome-pages-plugin
    pip install mkdocs-git-revision-date-localized-plugin
    ```

### 1.2. Hébergement des pages

Dans nos exemples, les pages sont hébergées chez [GitHub](https://github.com/){. target="_blank"}, chez qui la création d'un compte est donc nécessaire. 

Toutefois, une alternative libre existe et propose un service équivalent : [GitLab](https://gitlab.com/gitlab-org/gitlab){. target="_blank"} : 


## 2. Création d'un nouveau dépôt

La méthode présentée ci-dessous va consister à cloner (*forker*) un dépôt déjà existant, contenant la structure minimale d'un site en MkDocs.

Ce site minimal est visible à l'adresse [https://nsi-mauriac.github.io/mkdocs-modele/](https://nsi-mauriac.github.io/mkdocs-modele/){. target="_blank"}

### 2.1 Sur ```GitHub.com``` : fork du site modèle

1. Connectez-vous sur GitHub.
2. Allez à l'adresse [https://github.com/NSI-Mauriac/mkdocs-modele](https://github.com/NSI-Mauriac/mkdocs-modele){. target="_blank"} et cliquer sur le bouton ```Fork``` en haut à droite.
3. Choisissez un nouveau nom pour votre dépôt (votre *repository*).

### 2.2 Sur votre ordinateur : clonage de votre dépôt

1. Sur la page d'accueil de votre dépôt GitHub, cliquez sur le bouton vert ```Code``` et copiez l'adresse affichée, qui doit ressembler à ```https://github.com/<username>/<nomdudépot>.git```. 
2. Sur votre ordinateur, ouvrez un Terminal et tapez la commande 

```git clone https://github.com/<username>/<nomdudépot>.git``` en collant votre adresse par ```Ctrl-Maj-V```

Cette commande va permettre de rapatrier sur votre disque dur votre dépôt, pour l'instant uniquement présent sur les serveurs de GitHub.


## 3. Visualisation du site en local

1. Ouvrez dans VisualStudioCode le dossier de votre dépôt.
2. Dans Terminal, cliquez sur Nouveau terminal pour faire apparaître un nouveau terminal
3. Tapez la commande ```mkdocs serve```.
4. Un serveur se lance et votre page devient normalement disponible dans votre navigateur à l'adresse  ```http://127.0.0.1:8000/```.