make this directory.
you can right-click in the dir and click 'git bash here' or use git from powershell.
type `git init` to start a git here.
show hidden files to see the .git directory.
delete these files to remove your git.

make the file readme.txt.
type `git status` and see that readme.txt is not tracked.
type `git add readme.txt` to add it to staging.
type `git status` to see what is staged.
type `git rm --cached readme.txt` to unstage it.
type `git status` to see that it is not tracked, again.
type `git add readme.txt` to re-stage it.
change readme.txt and save it.
type `git status` to see that it is staged-unstaged (a pre-edit version is staged, the latest version is not).
PS `git config --global user.email your-email@wherever.com` (part of initial git setup).
PS `git config --global user.name "Your-Username"` "".
type `git commit` and type a commit message to commit.
type `git commit -m "this is my first bash commit." to commit without using a text editor.
type `git status` to see your success.

PS `echo "making a file from commandline" > just_a_file.txt` to make a second file to work with.
PS `echo "This file is not to be shared!" > secret_file.txt` to make a third file that will be "ignored" via git.ignore.
.m PS `Set-Content "secret_file.txt" .gitignore -Encoding utf8` to make a utf8 .gitignore file that ignores secret_file.txt (if it's not utf8, you're screwed).
.Tb .gitignore should ignore things prior to its being staged/uploaded.

use `git add .` to add everything (secret_file.txt should not appear in tracked nor untracked).
use `git rm --cached secret_file.txt` if it had already been added and needs to be ignored.

type `git branch mybranch` to make a personal branch.
use `git checkout mybranch` to select it.
PS `Set-Content "merge file" merge_me.txt` to make a merge file.
`git add .`
`git commit -m 'new updates'`
`git checkout master` this is the main branch.
be sure you're using the destination merge: `git checkout master` or `git status`.
`git merge mybranch` to bring its changes into this branch.

Causing a Conflict:
change just_a_file.txt.
`git commit -a -m 'change 6'`
`git checkout mybranch`.
change just_a_file.txt
`git commit -a -m 'change 7'`
`git merge master`
`git status`
you can see the issue directly in just_a_file.txt.
`git mergetool` can help.  You should install winmerge or tortisemerge.

Leaving a branch dirty:
git add .
git stash
when you come back to the branch, type git stash apply.

`git remote` shows remote repositories.
`git clone <url>` pulls down the entire repo.
`git remote` shows the origin.
`git remote -v` shows the urls.
`git fetch origin` gets any changes since you last cloned or fetched.
fetching will pull but not merge.
`git pull origin` will fetch and merge into your current branch.
change just_a_file.txt
`git commit -a -m 'just_a_file changes'`. 
login. `git push origin master` will as for CREDENTIALS.

Add additional remote repos:
git remote add MyRepo <url>.
git remote 
git remote -v
git fetch myrepo...

PUSHING BY FORCE!
git checkout origin/master LICENSE
git commit
git push --force --set-upstream origin master
git status
edit some files.
git add .
git commit
git push -u origin master
	this should work without errors!

UNDOING STUFF:
	RE-SUBMIT A COMMIT WITHOUT NEW MESSAGES:
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
You end up with a single commit — the second commit replaces the results of the first.

	UNSTAGE A FILE:
$ git reset HEAD CONTRIBUTING.md
The command is a bit strange, but it works. The CONTRIBUTING.md file is modified but once again unstaged.

	GET THE PRE-MODIFIED VERSION OF A FILE:
modified:   CONTRIBUTING.md
It tells you pretty explicitly how to discard the changes you’ve made. Let’s do what it says:
$ git checkout -- CONTRIBUTING.md

REMOTE STUFF:
	
	WHAT IS FETCH:
fetch all the information in Pauls but not your repository, you can run:
`git fetch pb`.
Paul’s master branch is now accessible locally as pb/master.
git fetch command only downloads the data to your local repository — it doesn’t automatically merge it with any of your work or modify what you’re currently working on. You have to merge it manually into your work when you’re ready.
`git pull` does fetch and merge on tracked branches: remote branches are tracked by default.

	INSPECTING A REMOTE:
$ git remote show origin
Tells you which branches you don't have yet and which are automatically pushed to.

	RENAME A REMOTE:
$ git remote rename pb paul

	REMOVE A REMOTE:
$ git remote remove paul

	IGNORE THESE ERROR MESSAGES:
"warning: LF will be replaced by CRLF in .gitignore."

	FULL SESSION FOR CREATING A PROJECT THAT YOU OWN
 cargo new yiden > cd yiden > git remote add origin https://github.com/Fohsap/yiden > git pull -OR- git pull git checkout origin/master then git checkout master > git add . > git commit > git push
 