//Got of gitbash and move to windows subsystem linux (WSL).
sudo apt update && sudo apt upgrade
sudo apt install curl
sudo apt install git
sudo apt install netcat
//netcat is used for termbin.

//Now, I had to reconfigure git!
git config --global user.email "<myemail>" 
git config --global user.name "<my_github_username>"


git checkout -b firstNewBranch
git push --set-upstream origin firstNewBranch:firstNewBranch
git status ${COMMENT+ This also tells you you're on 

//Some cool stuff to see where you are!
git branch -vv
git remote show origin
//you can type graph after the command below to execute the command on the right-hand side of the expression below.
alias graph="git log --all --decorate --oneline --graph"
graph

//The name is too long: renaming it (locally then remotely).  You can do this from any branch.  Optionally remove <old-branch-name> if you're on the branch you're renaming.
git branch -m <old-branch-name> <new-branch-name>
git status
git branch -m <old-branch-name> <new-branch-name>
git push <remote-repo> -d <old-branch-name>
git push <remote-repo> <new-branch-name>
git checkout <new-branch-name>
git push <remote-repo> -u <new-branch-name>