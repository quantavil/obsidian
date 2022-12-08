-   ls : The ls command lists the current directory contents and by default will not show hidden files. If you pass it the -a flag, it will display hidden files.
-   ls -la : list all the files in current directory
-   ls - l . *git*/ : This is Git directory. You can think of it as a database for your Git projects that store the changes and change history.
-   cd : change directory
-   touch : The touch command is the easiest way to create new, empty files.
-   touch .*git*ignore : Specifies intentionally untracked files to ignore
-    rm -rf : command is one of the fastest way to delete a folder and its contents.
-   rm -r : command deletes the folder recursively, even the empty folder.
-   rm -f : command removes 'Read only File' without asking.
-   rm -rf / : Force deletion of everything in root directory
-   $ *git* help <verb>
-   $ *git* <verb> --help
-   $ *git* init : Create an empty Git repository or reinitialize an existing one
-   $ *git* clone <url> <where to clone> : Clone a repository into a new directory
-   $ *git*-fetch : This command copies the commits done in the remote repository to the remote branches, so we can see what other people have committed.
-   $ *git* pull origin master : Fetch from and integrate with another repository or a local branch
-   $ *git* mv : Move or rename a file, a directory, or a symlink.
-   $ *git* rm <filename> : Remove files from the working tree and from the index.
-   $ *git* status : Show the working tree status

---

**Terminal commands:**

- ls - lists all of the folders

- ls -la - lists all of the files

- cd .. - returns one dir back

- cd - enters a directory

- . - just install in the current directory

---

**On initial install:**

- *git* --version - checks the version of the installed locally *git*

- *git* config --global user.name "Your Name" - sets up the name of the user

- *git* config --global user.email "yourname@somemail.eu" - sets up the mail of the user

- *git* config --list - lists all the *git* configurations

---

**For help on commands:**

- *git* help <verb> (e.g. *git* help config) OR

- *git* <verb> --help

---

**For initializing the project:**

- *git* init - initializes the *git* repo in the current folder

- touch .*git*ignore - creates a *git* ignore file

- *git* status - check working tree - both on the *git* and on local

- *git* add -A - adds all of the files for commiting

---

**Remove files:**

- *git* reset - removes files to be commited

- *git* reset somefile.js - removes somefile.js from the commit preparation

---

**Committing:**

- *git* commit -m "This is the commit message" - -m is used to add message

---

**View info about the repo:**

*git* remote -v - lists info about the repo

*git* branch -a - lists all of the branches

**View changes:**

*git* diff - shows the difference made in the files

**Pull before push ALWAYS:**

- *git* pull origin master

**THEN PUSH:**

*git* push origin master - <origin> name of remote repo <master> the branch that we push to

First time push of the branch:

*git* push -u origin <name of the branch> - -u coordinates the two branches (local and on server)

**Merge a branch:**

*git* checkout master

*git* pull origin master

*git* branch --merged - see which branches are merged

*git* merge <name of the branch you want to merge>

*git* push origin master

**Delete a branch:**

*git* branch -d <name of the branch> - this deletes it locally!!!

*git* branch -a - check the repo branches

*git* push origin --delete <name of the branch> - this deletes it from the repo!
---
Difference between Git pull and get fetch ?

*git* fetch fetches remote updates but doesn't merge; *git* pull fetches remote updates and merges.

-   When you use pull, Git tries to automatically merge. It is context sensitive, so Git will merge any pulled commits into the branch you are currently working on. pull automatically merges the commits without letting you review them first. If you don’t carefully manage your branches, you may run into frequent conflicts.

-   When you fetch, Git gathers any commits from the target branch that do not exist in your current branch and stores them in your local repository. However, it does not merge them with your current branch. This is particularly useful if you need to keep your repository up to date, but are working on something that might break if you update your files. To integrate the commits into your current branch, you must use merge afterwards.

---
![[att0.png]]

Merge takes all the changes in one branch and merges them into another branch in one commit.

Rebase says I want the point at which I branched to move to a new starting point

So when do you use either one?

**Merge**

Let's say you have created a branch for the purpose of developing a single feature. When you want to bring those changes back to master, you probably want merge (you don't care about maintaining all of the interim commits.

**Rebase**

A second scenario would be if you started doing some development and then another developer made an unrelated change. You probably want to pull and then rebase to base your changes from the current version from the repository.

Share

*git* remote update will update all of your branches set to track remote ones, but not merge any changes in.

-   *git* fetch will update only the branch you're on, but not merge any changes in.

-   *git* pull will update and merge any remote changes of the current branch you're on. This would be the one you use to update a local branch.

What is Pull request ?

A request sent to the owner and collaborators of the target repository to pull your recent changes.

*git* init

*git* add README.md

*git* commit -m "first commit"

*git* branch -M main

*git* remote add origin [https://*git*hub.com/karanrawat2q/Motion-Detector.*git*](https://*git*hub.com/karanrawat2q/Motion-Detector.*git*)

*git* push -u origin main

So to sum up, we work on modified files in our working tree. When they're ready, we staged these files by adding them to the staging area. Finally, we commit the changes sitting in our staging area, which takes a snapshot of those files and stores them in the database that lives in the Git directory

-   $ *git* add <filename>: The *git* add command adds a file to the Git staging area
-   $ *git* add . : The *git* add command adds all file to the Git staging area
-   $ *git* add -A : The *git* add command adds all file to the Git staging area
-   $ *git* add * : The *git* add command adds all file to the Git staging area
-   $ *git* add -p : *git* will show us the change being added and ask us if we want to stage it or not.
-   This way we can detect if there's any changes that we don't want to commit.

-   $ *git* branch : List, create, or delete branches
-   $ *git* branch <name> : Create a branch
-   $ *git* branch --merged : Tell us which branch has been merged
-   $ *git* branch -d <branch name> : Delete the merged branch.
-   $ *git* branch -D <branch name> : Forcefully delete the merged or unmerged branch.(if not merged its content will deleted)
-    *git* branch -r : We could have a look at the remote branches that our Git repo is currently tracking.

These branches are read only. We can look at the commit history, like we would with local branches, but we can't make any changes to them directly. To modify their contents, we'll have to go through the workflow we called out before.

-   $ *git* checkout <name of file> : *git* checkout restores files to the latest stored snapshot, reverting any changes before staging.
-   $ *git* checkout <name of file> -p : This will ask you change by change if you want to go back to the previous snapshot or not.
-   $ *git* checkout <branch name> : switch to the given branch. The working tree is updated to match the selected branch including both the files and the *git* history.
-    $ *git* checkout -b <branch name> : Creating a branch and switching to it immediately .
-   $ *git* checkout HEAD <filename> : To revert to last committed version.

-   $ *git* config --global user.name "John Doe"
-   $ *git* config --global user.email johndoe@example.com
-   $ *git* config --list : list all config
-   $ *git* config --global credential.helper wincred :If you use wincred for credential.helper, *git* is using the standard windows Credential Manager to store your credentials.
-   $ *git* config --global credential.helper cache :

-   $ *git* commit -m "Any message" : Record changes to the repository
-   $ *git* commit -a -m "The Commit message" : *git* commit -a is a shortcut to stage any changes to tracked files and commit them in one step. If the modified file has never been committed to the repo, we'll still need to use *git* add to track it first.
-   $ *git* commit --amend : allows us to modify and add changes to the most recent commit. IMP :You should avoid amending commits that have already been made public. This is because using --amend rewrites the *git* history removing the previous commit and replacing it with the amended one

-   $ *git* diff : Show changes between commits, commit and working tree, etc
-   $ *git* diff -- staged : to see the changes that are staged but not committed.

-   $ *git* merge <name of branch> : Merge that branch to the master
-   $ *git* merge --abort : This will stop the merge and reset the files in your working tree back to the previous commit before the merge ever happened.
-   $ *git* merge origin/master : merges the origin/master branch into our local master branch

-   $ *git* log : Show commit logs
-   $ *git* log -p : The p comes from patch, because using this flag gives us the patch that was created
-   $ *git* log --stat : This will cause *git* log to show some stats about the changes in the commit, like which files were changed and how many lines were added or removed.
-   $ *git* log --graph --oneline : This shows a summarized view of the commit history for a repo.
-   $ *git* log -- graph --oneline --all : This shows a summarized view of the commit history for a repo and show branches also.
-   $ *git* log origin/master : look at the current commits in the remote repo

-   $ *git* push -u origin <branch name> : Update remote refs along with associated objects in branch .It doesn't affect master branch
-   $ *git* push -d <remote name> <branch name> : This deletes the branch remotely.

Note that in most cases the remote name is origin. In such a case you'll have to use the command like so ; $ *git* push -d origin <branch name>

-   $ *git* push -f :It forcibly replaces the old commits with the new one and forces Git to push the current snapshot to the repo as it is. This can be dangerous as it can lead to remote changes being permanently lost and is not recommended unless you're pushing fixes to your own fork (nobody else is using it) such as in the case after doing interactive rebasing to squash multiple commits into one as demonstrated.

-   $ *git* rebase <branch name>: Reapply commits on top of another base tip
-   $ *git* rebase -i <branch name> : Interactive rebase

-   $ *git* revert HEAD : Git revert doesn't just mean undo. Instead, it creates a commit that contains the inverse of all the changes made in the bad commit in order to cancel them out.

-   $ *git* reset HEAD <filename> :file is once again untracked in our working tree and no longer staged. You can think of reset as the counterpart to add.
-   $ *git* reset HEAD <filename> -p: You can get *git* to ask you which specific changes you want to reset.

-   $ *git* remote : Manage set of tracked repositories (Whenever we're operating with remotes, Git uses remote branches to keep copies of the data that's stored in the remote repository. )
-   $ *git* remote add origin <repository url> : adds a repo to your project
-   $ *git* remote -v :If you have more than one remote, the command lists them all.
-   $ *git* remote show origin : If you want to see more information about a particular remote, you can use the *git* remote show <remote> command.

(To change remote branch :Pull the remote branch, merge it with the local branch, then push it back to its origin.)

-   $ *git* remote update : If we want to get the contents of remote branches without automatically merging any contents into the local branches, we can call *git* remote update. This will fetch the contents of all remote branches, so that we can just call checkout or merge as needed.

-   $ *git* show : This command takes a commit ID as a parameter, and will display the information about the commit and the associated patch