# git-shared-repo

This is the repo that is shared with several git projects, using subtree.

Beforehand, the linked repository must be added to the container repository :

`git remote add <name> https://github.com/ArnaudBuchholz/git-shared-repo.git`

Then, depending on the container project state :

* To **create** the link (folder must not exist): `git subtree add --prefix=<folder> <name> <branch> --squash`
* To **update** the link : `git subtree pull --prefix=<folder> <name> <branch> --squash`

## Preventing changes in the subtree

Adds the `<folder>/` entry to the container `.gitignore`.
This will not prevent modification but an error is raised by git when trying to stage the file.
(Not a perfect solution since it is technically possible to override this behavior).

Another option would be to use a post-checkout hook to set the folder as read-only.

## Providing a message for the commit

The `-m` / `--message` option is supported
