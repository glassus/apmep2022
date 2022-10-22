
    
[TOC]

----

:pencil: Ce document est conçu pour vous apprendre les bases du travail avec le contrôle de version git et le site Web GitHub.

Objectifs d'apprentissage:

* Comprendre le concept de contrôle de version.
* Comprendre la différence entre le logiciel git et le site Web GitHub.
* Comprendre la terminologie : branche, fourche, fusion, pull, push, distant
* Effectuez votre première demande d'extraction vers un référentiel git sur GitHub.

Il s'inspire des vidéos suivantes 
[Ressource pour ce document](https://www.youtube.com/watch?v=BCQHnlnPusY&list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV)
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_40ae4ab2d2d2c2cd21d9dd28c2e86e02.PNG)

----
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_b2b976faf464402fdcb4e79473543a33.png)
[La Tech avec Bertrand](https://www.youtube.com/watch?v=225wkShIcc8)


---
Quelques vidéos pour comprendre les concepts


- [Démystifions Git, Github, Gitlab (1/3) : Notion d’historique](https://youtu.be/iub0_uVWGmg)


- [Démystifions Git, Github, Gitlab (2/3) : Travailler à plusieurs](https://youtu.be/4xsd8jHyVpk)


- [Démystifions Git, Github, Gitlab (3/3) : L’écosystème Git](https://youtu.be/5EFyKBF1wWw)


----

## A. Introduction Git Github 



Pourquoi Git et GitHub ?

- La gestion de versions (en anglais : version control ou revision control) consiste à gérer l'ensemble des versions d'un ou plusieurs fichiers (généralement en texte).
- Collaboration

Git est un logiciel de controle de version

GitHub est un service web


Première activité rapide :tada:

**Repository**

- Créer un compte sur Github
- Créer un dépot (repository) nommé ```rainbow```
- Créer un nouveau fichier nommer ```poemes.txt```

**Commit new file** 

- ```Commit directly to the main branch```
- Le poeme est dans le dépot

**Commmit change**

- Cliquer sur poeme.txt
- Il manque la couleur verte.
- Cliquer sur le crayon --> Edit this file
- Remplir en bas ```Commit change``` par "j'ai ajouté la couleur verte" puis cliquer sur ```Commit changes```
- Il manque la couleur jaune. Cliquer sur le crayon --> ```Edit this file```
- Remplir en bas ```Commit change``` par "j'ai ajouté la couleur jaune" puis cliquer sur ```Commit changes```

**History** 

- Cliquer sur ```History``` pour voir l'historique.
- En cliquant sur un des commit, on peut voir ce qui a été modifié (souligné, biffer)
- On voit aussi ```commit d8f911b0c32226239ff7bb95e40306014b6386be" commit hash meaning```
- La suite de caractères ```d8f911b0c32226239ff7bb95e40306014b6386be``` est l'identifiant unique du commit
- On le voit aussi dans l'URL ```https://github.com/Charles-depot/rainbow/commit/d8f911b0c32226239ff7bb95e40306014b6386be```


**Bilan :**

- Création d'un dépot.
- Plusieurs commit
- Historique


## B. Branches 

Nous avons effectué des ```commit``` de façon linéaire en apportant des modifications. Chaque commit possède un identifiant unique.
C'est la branche ```master ou main```. C'est la racine de notre arbre.

Je souhaite maintenant faire des modifications mais je ne sais pas si 
je vais les garder. Je souhaite faire une expérience sur mon poème qui va
parler de licornes.
Je souhaite bifurquer (```branch```) à partir d'un commit en créant une nouvelle branche.

On peut toujours continuer à travailler sur la branche master.
On peut aussi faire des commit sur la nouvelle branche.
 On peut faire aussi une autre branche nommée *fées* à partir d'un autre commit.
Etc...

Et comment peut-on fusionner (```merge```) tout ce travail ?

 :pencil: 

- Créer la nouvelle branche *licorne*
- Vérifier que vous êtes bien sur la branche *licorne*
- Modifier le poème en ajoutant des mots.

Ensuite on a le choix :

```Commit directly to the licorne branch```

```Create a new branch for this commit and start a pull request```
 
On choisit ```Commit directly to the licorne branch```. Et on sauvegarde.
 
Si on switch sur la branche ```main```, on voit  l'ancienne version du poème.
On aurait pu faire un commit à partir de la branche main mais on a choisit de faire un chemin différent. On a deux chemins maintenant que l'on peut travailler séparément.
 
Maintenant si je trouve que le chemin licorne est valable et je souhaite que ce travail aille dans la branche ```main```

- Revenir dans le dépot ```rainbow``` puis Insights puis Network. Cela permet de visualiser les différents branches.

![graph_network](https://minio.apps.education.fr/codimd-prod/uploads/upload_5483d2887de27b34ca1ddb0f9fea315b.PNG)

push : pousser (envoyer) quelque chose à quelqu'un 
pull : tirer quelque chose	à quelqu'un
pull request : prendre les changements et les tirer vers la branche master

- retourner sur la branche ```main``` pour voir :
 ![pull_request](https://minio.apps.education.fr/codimd-prod/uploads/upload_33cebc988e3d8db05f94071b664e744a.PNG)
 
- Cliquer sur le bouton : ```Compare & pull request```. Je suis en train de faire un ```pull request``` c'est à dire une requète pour fusionner les changements faits de ```licorne``` à ```main```.
On peut voir les changements en bas de page.
- Cliquer sur le bouton ```create pull request```
- Cliquer sur le bouton ```Merge pull request``` pour finaliser. Puis ```Confirm merge```

- Revenir dans le dépot ```rainbow``` puis ```Insights``` puis ```Network```.
Cela permet de visualiser ce qui s'est passé. On peut voir que la branche licorne a fusionné avec la branche```main```.

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_d59f2cdebfbd61ae8515f244da67ed83.PNG)
 
- Créer une nouvelle branche ```poneys``` à partir de ```main```.
- Modifier le poème.
- Faire un ```commit```

- Revenir à la branche ```main```
- Modifier le poème.
- Faire un ```commit```

- Revenir dans le dépot ```rainbow``` puis ```Insights``` puis ```Network```.


On peut voir les différents actions.

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_3444f77f17abe7b83f96af4c9e86a6dd.PNG)

Commnent fusionner le tout ?

Branche ```main```
Cliquer sur le bouton : ```Compare & pull request```
Cliquer sur le bouton ```Merge pull request``` pour finaliser. Puis ```Confirm merge```

Revenir dans le dépot ```rainbow``` puis ```Insights``` puis ```Network```.
On peut voir le résultat.

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_a9f7b2c83ebbcaacfe1e2dbf4f36658b.PNG)


##  C. Forks and Pull Requests 

Nous allons voir comment contribuer/collaborer avec une autre personne 
dans le dépot.

Deux concepts à ajouter.

- Fork
une instance compléte de mon dépot sur un autre compte
On aura une exacte réplication du dépot avec les commit et les branches.
On peut travailler sur le fork (commit, branches) sans modifier le dépot original.

- Pull request
Cela signifie que par exemple si une branche de mon travail sur le fork est superbe et que je souhaite contribuer dans le dépot original. Je vais envoyer ce travail dans le dépot original.
Et c'est au dépot original d'accepter ou rejeter d'où le pull request.


:pencil:
```charlestuteur``` est au autre compte.
- Aller sur ```charlestuteur```, chercher le dépot ```charles-depot``` puis ```fork```.
- On peut le voir sur ce compte d'où provient le fork :

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_cc8ce67163687f8601e3f6d12cf37c64.png)

- Modifier le poeme
- Faire un commit en choisissant ```Create a new branch for this commit and start a pull request.```
On peut aussi faire juste un commit
- Ensuite faire un pull request pour ajouter à la brancher master du fork
- Verifier sur Insights/Network

- Créer un ```pull request``` vers charles-depot.
Et attendre la réponse.

- Aller sur charles-depot et cliquer sur ```Pull requests```

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_53b19a32151bac85e9e1ea2766d47464.png)

- En cliquant sur la demande on peut voir les changements
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_006a6dfde9c7b28aeed8a9b08e53b8eb.png)

- Remplir le commentaire
- Cliquer sur ```Merge pull requests```

- Aller sur charlestuteur pour voir la péponse.

## D. Issues 

Vous pouvez utiliser ```GitHub Issues``` pour planifier, suivre les idées, les commentaires, les tâches ou les bogues. En un mot suivre votre travail.

:pencil:
- Cliquer sur ```New Issue``` pour créer un nouveau problème.

- Remplir les informations

- Donner à votre problème un titre descriptif. Le titre doit indiquer en un coup d'œil de quoi il s'agit.

- Ajoutez une description qui explique le but du problème, y compris tous les détails qui pourraient aider à résoudre le problème. 

- Vous pouvez utiliser Markdown pour ajouter une mise en forme, des liens, des emojis, etc. 
Pour plus d'informations, consultez [Écrire sur GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

- Ajouter une liste de tâches.
  - [] #50
  - [] faire les modifications

- Ajouter des étiquettes (labels)**
Ajouter une étiquette pour catégoriser votre problème. GitHub fournit des étiquettes par défaut. 

- Vous pouvez utiliser ces libellés par défaut ou créer les votres.
Cliquer sur ```issues``` puis ```Labels``` puis ```New label```.
Donner un nom, une description et une couleur.
[Etiquettes](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels)

:pencil: Associer les issues au commit ou au pull request ?

- Créer un commit et associer dans le titre le numéro de l'issue comme  ... per #8 
On crée un commit particulier à cette issue.
En revenant sur les issues :
``` Charles-depot added a commit that referenced this issue 1 minute ago```

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_85cb3c670c0797bcc124eca97d833d73.PNG)

On peut cliquer sur commit lié ```per #8``` pour suivre les changements.

- Clore l'issue si besoin ou directement dans le commit en écrivant dans le titre fixes #8

- On peut faire une issue à partir d'un commit.

```commit 21f9ba806f57fd947586de3517a469fe41af2157```

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_98d67fbedcbcf7b8df91ee539849e138.PNG)

**Bilan**

- Référence au numéro de l'issue
- Référence à l'identifiant d'un commit ou description de l'issue.



## E. Cloner un dépot et Push-Pull 

Pour l'instant nous avons travaillé directement sur Github website.

Nous allons travaillé maintenant sur l'ordinateur.

Il faut installer **[Git](https://git-scm.com/)** sur l'ordinateur 
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_19146e29058c062510d52a7147bd07dd.png)


Une alternative est d'utiliser un client comme GitHub Desktop
Client git : https://desktop.github.com/
aide  : https://docs.github.com/en/desktop


### Partie 1

:pencil:

- Vérifier que l'installation a bien fonctionné en ouvrant un cmd.
- Taper git. On obtient une aide.
- Faire un dépot Git local. Il faut un dossier dans l'ordinateur qui soit un dépot Git.

On va saisir le dépot sur GitHub et le mettre en local.

:pencil:

- Créer un nouveau dépot : rainbow-song avec un readme.md

On peut ensuite voir :
![adresse](clone1.png)
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_d29e0db1349fc33c5e5ae52c7ece490f.png)


C'est une  URL spécial qui correspond à ce dépot. Nécéssaire pour cloner
le dépot créé sur un ordinateur local.
```https://github.com/Charles-depot/Rainbow-song.git```

NB : Git associe une URL distante à un nom, et votre dépot par défaut est généralement appelée origin.

https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories

### Partie 2
Dans le dossier local

- Soit cmd ou clique droit Git Bash Here
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_6014752be79574f8eeb9682d8814b942.png)


```
git clone https://github.com/Charles-depot/Rainbow-song.git
```
 

- On obtient :
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_d9f32c12e6be4f602748754de9e1301b.png)

- Dans le dossier local :
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_5f745267dddb2285af90c8ac423edb6c.png)

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_3e0ab3fd240c3fa53cd3416a0591a274.png)

- Vous pouvez ouvrir le fichier README.md local pour voir qu'il correspond
à celui de GitHub. Et le modifier. Le sauvegarder.


```
git status
```


![](https://minio.apps.education.fr/codimd-prod/uploads/upload_068f7f639bf1150e6188ee1184b0af31.png)

:warning:  Ce n'est donc pas le dépot Git. Je ne suis pas dans le bon dossier.

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_214f06ea105de4cc2cdc52a759fe1a5a.png)

On voit que l'on est dans la branch ```master```.
On peut voir qu'un fichier a été modifié. 


Pour l'instant, le fichier est modifié localement.



```
$ git commit -a -m "Ajout de la cle C"
```

-a tous les fichiers
-m commentaire

On obtient :
![](https://minio.apps.education.fr/codimd-prod/uploads/upload_c43e2d522a38faa8e767a5e45116047a.png)


```
git config --list 
```


Cela permet d'avoir des renseignements sur la configuration locale.
:warning:  Il y a problème avec le ```user.name```. Il faut le modifier. Et prendre le ```user.name``` du dépot GitHub. 

```
git config global user.name = "Charles-depot" 
```

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_7cdb64370bcb2fa71809247a8c7434dd.png)

Cependant rien n'a changé dans le GitHub.


```
git remote

>> origin 
```



```
$ git remote -v
origin  https://github.com/Charles-depot/Rainbow-song.git (fetch)
origin  https://github.com/Charles-depot/Rainbow-song.git (push)
```



donc 

inf
```
git push origin master
```


:warning: Cela ne fonction pas.

```
git push origin main
```
*main* est nom de la branche dans le dépot.

On obtient : 

![](https://minio.apps.education.fr/codimd-prod/uploads/upload_57bc45ad0f11d66054f764cac8fb8238.png)

On peut voir le changementsur le dépot GitHub.

## F. Git init and git add 

Dans les parties précédentes, nous avons créé un dépot puis on l'a 
mis dans l'ordinateur.

Nous allons lier un dossier local à un dépot Git

### 1. Création d'un dossier local test_depot 
un fichier dance.md

Dans ce dossier: 


```
$ git status
fatal: not a git repository (or any of the parent directories): .git
```


Nous allons en faire un dépot git.


```
$ git init
Initialized empty Git repository in E:/Git Mkdocs Markdown/Test_depot/.git/
```



```
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        dance.md

nothing added to commit but untracked files present (use "git add" to track)
```


### 2. Ajouter un nouveau fichier 

Création de dance-2.md


```
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        dance-2.md
        dance.md

nothing added to commit but untracked files present (use "git add" to track)
```


On ajoute le suivi sur le fichier dance.md

```
$ git add dance.md
```



```
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   dance.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        dance-2.md
```


On peut lire qu'il y a un fichier suivi *dance.md* et un fichier non suivi *dance-2.md*


Un petit *commit*

```
$ git commit -m "Ajout d'une danse"
[master (root-commit) 1c0d430] Ajout d'une danse
 1 file changed, 3 insertions(+)
 create mode 100644 dance.md
```



```
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        dance-2.md

nothing added to commit but untracked files present (use "git add" to track)
```


Si on souhaite tout suivre, on utilise la commande *git add .*


```
$ git add .

$ git commit -m "Ajout de la deuxième dance"
[master 8953913] Ajout de la deuxième dance
 1 file changed, 3 insertions(+)
 create mode 100644 dance-2.md
 
$ git status
On branch master
nothing to commit, working tree clean
```


### 3. Mettre tout dans un dépot


```
$ git push master
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream master master

$ git remote -v
```


Le dépot Git vide existe mais il n'y a pas d'association avec le dossier local.

![](git1.PNG)

![](git2.PNG)

![](git3.PNG)

On peut voir la ligne
```https://github.com/Charles-depot/test_depot.git```
permettant d'associer le dépot distant avec le dossier local


```
$ git remote add origin https://github.com/Charles-depot/test_depot.git

$ git remote
origin

$ git remote -v
origin  https://github.com/Charles-depot/test_depot.git (fetch)
origin  https://github.com/Charles-depot/test_depot.git (push)
```


Le dépot distant se nomme *origin*



```
$ git push origin master
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 496 bytes | 248.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Charles-depot/test_depot.git
 * [new branch]      master -> master

```


Si on regarde maintenant dans le dépot distant.
![](git4.PNG)

On retrouve nos deux fichiers.

### 4.  Changement dans GitHub

Modification du fichier dance.md dans GitHub
![](git5.PNG)
Un petit commit
![](git6.PNG)

Que s'est-il passé en local ?

```
$ git status
On branch master
nothing to commit, working tree clean
```


**Rien**

La solution avec un **git pull**.


```
$ git pull origin master
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 699 bytes | 2.00 KiB/s, done.
From https://github.com/Charles-depot/test_depot
 * branch            master     -> FETCH_HEAD
   8953913..41b7811  master     -> origin/master
Updating 8953913..41b7811
Fast-forward
 dance.md | 1 +
 1 file changed, 1 insertion(+)

```


On ouvre le fichier en local. :tada:


![](https://minio.apps.education.fr/codimd-prod/uploads/upload_5bc0157687c21a06281e610bbb0c0f84.PNG)




