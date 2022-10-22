

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_ac334e3b5463dc7cfcebd5927cf9cc6b.PNG)

- [Documentation git](https://git-scm.com/docs)
- [Git Cheat Sheets](https://training.github.com/)
- [Git Cheat Sheets en français](https://training.github.com/downloads/fr/github-git-cheat-sheet/)
- [Git Cheat Sheets en pdf](https://training.github.com/downloads/fr/github-git-cheat-sheet.pdf)
- [Visual Git Cheat Sheet](https://ndpsoftware.com/git-cheatsheet.html#loc=workspace;)

--------

[TOC]

## A. Git premiers pas

### 1. Installation de Git

- Installer [Git](https://git-scm.com/) (installation de raccourci Git Bash)
- Vérifier dans un terminal avec *git version*[^gitversion]


```
$ git version
git version 2.31.1.windows.1
```

Le numéro de la version s'affiche sinon :-1:

- Configurer Git avec *git config*[^gitconfig]

Définit le nom que vous voulez associer à toutes vos opérations de commit

```
$ git config --global user.name "charles"
```


- Définit l’email que vous voulez associer à toutes vos opérations de commit

```
$ git config --global user.email charles.poulmaire@ac-versailles.fr
```

- Voir la configuration avec *git config --list*[^gitlist]

```
$ git config --list
...
...
user.name=Charles
user.email=charles.poulmaire@ac-versailles.fr
...
...
```


[^gitversion]: Complément d'information
Pas trouvé. :smile: 

[^gitconfig]: Complément d'information
https://git-scm.com/docs/git-config

[^gitlist]: Complément d'information
Pas trouvé. :smile:

------------

### 2. Premier pas

- Créer un dossier pour votre site

```
$ mkdir siteWeb
$ cd siteWeb
```

- Démarrer un nouveau dépôt avec *git init*[^gitinit]

[^gitinit]: Complément d'information 
https://git-scm.com/docs/git-init


```
$ git init
```


Création dans le dossier d'un dossier *.git* (bien rempli)

```
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

```


Une *branch* est une ligne de temps sur laquelle nous allons travailler.
Un *commit* est une photo à l'instant t de notre travail.
On peut travailler puis refaire un *commit* pour avoir une photo. Tout en conservant l'ancien *commit*.
On peut aussi avoir plusieurs branch pour tester une solution ou travailler à plusieurs puis fusionner avec la *branch master*.


### 3. Page web

Création d'un page web *index.html*

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Tutoriel Git</title>
  </head>
  <body>
	<h1> Hello world </h1>
  </body>
</html>
```
On affiche le status

```
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
```

Cela nous indique q'un fichier n'est pas suivi. :frowning: On n'a pas encore indiqué qu'il fallait suivre ce fichier.


```
$ git add .
```

Le point *.* permet de tout ajouter pour le suivi.


```
$ git commit -m "Initial commit"

[master (root-commit) 26ee28b] Initial commit
 1 file changed, 11 insertions(+)
 create mode 100644 index.html
```

Le suivi est effectué :smiley: 


```
$ git status
On branch master
nothing to commit, working tree clean
```

Tout se passe bien. :tada: 

### 4. Modification de la page web et des *commit*

- Ajout d'un paragraphe
``` html
<p> Tutoriel sur Git </p>
``` 

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html
```

Git nous indique qu'il y a eu des changements sur le fichier suivi.
Alors ...


```
$ git add .

$ git commit -m "Ajout d'un paragraphe"
[master 7c7b826] Ajout d'un paragraphe
 1 file changed, 1 insertion(+), 1 deletion(-)
```


:tada: une nouvelle photo de notre travail

### 5. Un historique des *commit*

```
$ git log
commit 7c7b826effd3a7989fcba8e339dc6e5e4384d3d0 (HEAD -> master)
Author: Charles Yo <charles.endymion@gmail.com>
Date:   Tue Sep 13 11:41:01 2022 +0200

    Ajout d'un paragraphe

commit 26ee28ba8a62f8bd59e620dc34bfdbfc90bbb434
Author: Charles Yo <charles.endymion@gmail.com>
Date:   Tue Sep 13 11:00:18 2022 +0200

    Initial commit
```


Cette commande *git log* permet de voir tous les *commit*. 
- Auteur; 
- date; 
- message.

## B. Git  Branches

### 1. Les branches


```
$ git status
On branch master
nothing to commit, working tree clean
```
ou 

```
$ git branch
* master
```


Cela nous indique que nous sommes sur la *branch master*.

Le schéma ci-dessous montre en bleu les différents *commit*.
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_3a01cbb6c9e17cc1d2e5218d91fcbbff.png)

On souhaite parfois faire des modifications, développer d'autres fonctionalités. Pour cela on crée une branche en orange puis on fusionne avec la branche *master* si on le souhaite.

### 2. Création d'une branche

- Création d'une branche nommer **Hello** avec *git branch*[^gitbranch]

```
$ git branch Hello
```



```
$ git branch
  Hello
* master
```

On a donc deux branches : Hello et master.  Je suis actuellement sur la branche master indiqué par *.
[^gitbranch]: Complément d'information
https://git-scm.com/docs/git-branch

- Autre solution

```
$ git checkout -b Bye
Switched to a new branch 'Bye'
```



```
$ git branch
* Bye
  Hello
  master
```

Nous avons créé une nouvelle branche et nous sommes actuellement sur la branche Bye indiqué par *.

- Aller sur une autre branche 


```
$ git checkout master
Switched to branch 'master'
```



```
$ git branch
  Bye
  Hello
* master
```



### 3. Travailler sur une branche

- On va travailler sur la branche Hello

```
$ git checkout Hello
```


On effectue quelques modifications sur notre fichier index.html. 

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Tutoriel Git</title>
	<style>
		body{background-color : skyblue;}
		h1,p{color: #ffffff;}
	</style>
  </head>
  <body>
	<h1> Hello world </h1>
	<p> Tutoriel sur Git </p>
	<p> Ceci est une modifiation ! </p>
  </body>
</html>
```
On obtient :

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_6deda52a06f8eec22ce2a701a7ee746e.PNG)

Un suivi et une photo de notre travail


```
$ git add .

$ git commit -m "Ajout de couleur et texte"
[Hello 7d35a64] Ajout de couleur et texte
 1 file changed, 5 insertions(+))
```


:tada: une nouvelle photo de notre travail mais dans la branche **Hello**

Sur n'importe quelle branche **Hello** ou **master** notre travail est suivi.

### 4. Retour sur la branche **master**


```
$ git checkout master
Switched to branch 'master'
```


J'actualise mon site.

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_e4bcea577e4c71aa987a9b28b90bc204.PNG)

Les modifications ont disparues.

- Bascule sur la branche spécifiée et met à jour le répertoire de travail avec *git merge*[^gitmerge]
Il faut donc tirer nos modifications de la branche **Hello** vers la branche **master**


```
$ git merge Hello
Updating 7c7b826..7d35a64
Fast-forward
 index.html | 5 +++++
 1 file changed, 5 insertions(+)

```


On retourne sur le site et :tada: 

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_53ea0f2a3be5d1a7586b633df453dca5.PNG)

Sur la branche **master** et **Hello** on a le même code.

[^gitmerge]: Complément d'information
https://git-scm.com/docs/git-merge


## C. Git partie Push and Pull

Pour l'instant on travaille en local. Sans avoir besoin d'internet.
Mais on souhaite travaille avec des collaborateurs dans un même projet.
Il faut que le code soit en ligne dans un repository (dépot) en ligne.

Listing des clients Git
- Github (Github desktop pas de console)
- GitLab
- Bitbucket

### 1. Utilisation de GitHub

- Création d'un compte
- Création d'un projet

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_e1ffd3855863e27f887994a623f662c1.png)
Puis 

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_08b6107ee0ef88ef3c685ac550fc94f0.png)

Soit on crée un nouveau repository 

```
…or create a new repository on the command line
echo "# tuto-git" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Charles-depot/tuto-git.git
git push -u origin main
```


Soit on pousse un dossier qui existe déjà en local

```
…or push an existing repository from the command line
git remote add origin https://github.com/Charles-depot/tuto-git.git
git branch -M main
git push -u origin main
```


On va utiliser la deuxième solution car on  a notre fichier index.html créé
Dans un terminal et dans le bon dossier.

On va initialiser ce repository


```
$ git remote add origin https://github.com/Charles-depot/tuto-git.git
```


On va pousser notre code dans le repository. Attention la branche c'est master !!! 

```
git push -u origin master 
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (9/9), 926 bytes | 13.00 KiB/s, done.
Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/Charles-depot/tuto-git.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```


Le code est maintenant accessible en ligne en actualisant la page.
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_a3fd8ba8c4627f3f80c2e08ac0f37cc3.png)

On peut le regarder en ligne et il est accessible à tout le monde. Il existe de nombreux repository sur GitHub que l'on peut cloner en local.

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_bd6db3f79effd3e7cfc3b30284ed4622.png)

Petite modification en locale du fichier index.html par
``` html
p> Ceci est une modifiation et un autre ! </p>
``` 

Dans le terminal 


```
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
```



```
$ git add .
$ git commit -m "Modification du paragraphe"
[master 723d493] Modification du paragraphe
 1 file changed, 1 insertion(+), 1 deletion(-)
git 
$ git push origin master
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 311 bytes | 44.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Charles-depot/tuto-git.git
   7d35a64..723d493  master -> master
```


Et sur le repository en actualisant. 

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_2868bc8b3b48962d43785c9cd03df7f1.png)


### 2. Travail avec un collaborateur

Pour la mise à jour d'un dossier sur lequel il y a eu des changements.



```
$ git pull origin master 
```







