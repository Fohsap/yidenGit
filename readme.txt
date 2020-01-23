make this directory.
you can right-click in the dir and click 'git bash here' or use git from powershell.
type `git init` to start a git here.
show hidden files to see the .git directory.
delete these files to remove your git.

make the file readme.txt.
type `git status` and see that readme.txt is not tracked.
type `git add readme.txt` to add it to staging.
type `git status` to see what is staged.
type `git rm readme.txt` to unstage it.
type `git status` to see that it is not tracked, again.
type `git add readme.txt` to re-stage it.
change readme.txt and save it.
type `git status` to see that it is staged-unstaged (a pre-edit version is staged, the latest version is not).
`PS W:\prj\yidenGit> git config --global user.email your-email@wherever.com`
`PS W:\prj\yidenGit> git config --global user.name "Your-Username"`
type `git commit` and type a commit message to commit.
type `git commit -m "this is my first bash commit." to commit without using a text editor.