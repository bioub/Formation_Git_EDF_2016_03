## Intégrer les changements

Se replacer sur la branch dans laquelle on souhaite intégrer les changements, ex : `git checkout master`

### git merge

3 options :
  * jamais eu de changements sur la branche d'origine, par défaut on applatit le graphe d'historique `git merge master doc-merge --ff-only`
  * jamais eu de changements sur la branche d'origine, et on souhaite conserver un nouveau chemin dans l'historique  `git merge master doc-merge --no-ff`
  * déjà eu des changements, par défaut git merge va créer un nouveau chemin

### git rebase

S'il y a eu des changements sur la branche d'origine, évite un nouveau chemin, utile si le changement n'est pas important pour l'historique (correction de bug minime)
