# Commandes de bases Git

## Configuration

`git --version` indique la version de git installée

`git config --list` affiche toute la configuration (globale + locale au projet courant)

Une fois après l'installation de git penser à configurer le nom d'utilisateur et l'email (global à la machine) :

	git config --global user.user "Romain Bohdanowicz"
	git config --global user.email "romain.bohdanowicz@gmail.com"
	
## Créer un Repository / Dépôt

`git init` pour créer un dépôt vide

`git clone` pour dupliquer un repository (d'un dossier ou machine à une autre)

## Obtenir des informations sur le dépôt

`git status` pour voir les fichiers untracked (non surveillés), cached (prévu pour la prochaine version), indexed (déjà versionné).

`git status -u` pour voir le contenu des répertoires

`git log` pour voir l'historique

## Ajouter un fichier à la staging area (changement à prendre en compte pour la prochaine version)

`git add unFichier.ext` ou `git stage unFichier.ext` (alias)

`git add *.ext` tous les fichiers qui ont l'extension ext

`git add *` tous les fichiers

Pour ajouter qu'un partie d'un fichier utiliser `git add -p unfichier.txt`, un mode interactif s'affiche, vous devrez choisir morceau par morceau (hunk), `y` pour ajouter le morceau, `n` pour ne pas l'ajouter `?` pour afficher la doc des autres options

## Retirer un fichier de la staging area

`git rm --cached fichier.txt` ou `git reset HEAD fichier.txt` si le fichier est déjà indexé (déjà versionné)

## Versionner

`git commit -m "Message le plus précis possible"` pour versionner les changements surveillés (ajouté) dans la staging area

## Revenir à une ancienne version

`git log` pour afficher les versions

`git checkout ab34b25` pour revenir à la version dont l'identifiant commencer par ab34b25

`git checkout master` pour revenir à la dernière version (important faire ses modifs sur la dernière version)

`git checkout HEAD^` revenir à la version précédente

`git checkout HEAD^^` revenir 2 versions en arrière ou  `git checkout HEAD~2`

## Voir les différences

`git diff` différence entre working directory et le dernier commit

`git diff --cached` différence entre la staging area et le dernier commit

`git diff --word-diff` pour voir les changements mot par mot

`git diff --color-words=.` pour voir les changements lettre par lettre

`git diff HEAD HEAD^` pour voir les différence entre le dernier commit et le précédent

## Mettre de côté des modification (sans les placer dans l'historique)

`git stash list` pour voir les changements déjà mis de côté

`git stash save -u "Description des changements"` pour mettre de côté des modifications en dehors de l'historique (`-u` pour garder les fichiers non surveillés -- untracked --)

`git stash pop` pour rappatrier le dernier stash sauvegardé

`git stash pop stash@{1}` pour rappatrier le stash stash@{1} (voir git stash list)

** Attention : ** si conflit il faut éditer manuellement le fichier et retirer les lignes <<<<<<, ======, >>>>>>>> puis faire un commit.

`git stash drop` pour supprimer (à faire manuellement en cas de conflit sur `git stash pop`)

## Indiquer les fichiers à ne pas versionner

Créer un fichier .gitignore à la racine ou dans un sous répertoire (si on souhaite ignorer que pour ce sous répertoire)

Et indiquer sur chaque le nom ou les chemins de fichiers/dossiers à ignorer.

Ex :

	password.txt
	dependencies/
	*.tmp
	
