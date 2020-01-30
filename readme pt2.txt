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

