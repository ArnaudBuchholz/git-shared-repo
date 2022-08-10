# git-shared-repo

This is the repo that is shared with several git projects, using subtree.

Beforehand, the linked repository must be added to the container repository :

`git remote add <name> https://github.com/ArnaudBuchholz/git-shared-repo.git`

Then, depending on the container project state :

* To **create** the link (folder must not exist): `git subtree add --prefix=<folder> <name> <branch> --squash`
* To **update** the link : `git subtree pull --prefix=<folder> <name> <branch> --squash`

## Preventing changes in the subtree
