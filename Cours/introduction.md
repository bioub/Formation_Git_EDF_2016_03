# Commandes de bases Git

## Configuration

`git --version` indique la version de git installée

`git config --list` affiche toute la configuration (globale + locale au projet courant)

Une fois après l'installation de git penser à configurer le nom d'utilisateur et l'email (global à la machine) :

	git config --global user.user "Romain Bohdanowicz"
	git config --global user.email "romain.bohdanowicz@gmail.com"
	
## Créer un Repository / Dépôt

`git init` pour créer un dépôt vide

`git clone` TODO

## Obtenir des informations sur le dépôt

`git status` pour voir les fichiers untracked (non surveillés), cached (prévu pour la prochaine version), indexed (déjà versionné).

`git status -u` pour voir le contenu des répertoires

`git log` pour voir l'historique

## Ajouter un fichier à la staging area (changement à prendre en compte pour la prochaine version)

`git add unFichier.ext` ou `git stage unFichier.ext` (alias)

`git add *.ext` tous les fichiers qui ont l'extension ext

`git add *` tous les fichiers

