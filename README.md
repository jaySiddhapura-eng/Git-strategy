# Git

## First Time Git Setup

1. Initialize local repository

   ~~~powershell
   git init
   #nevigate to the project folder on which versioning need to be done
   ~~~

2. Add file to index

   [Git add documentation](https://git-scm.com/docs/git-add)

   ~~~powershell
   git add <file>  # to add one file to index
   git add .  #to add all the files to index 
   ~~~

3. Add user client config

   [Git configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)

   [Writting good commits](https://medium.com/compass-true-north/writing-good-commit-messages-fc33af9d6321)

   [custom git commit template](https://backlog.com/blog/git-commit-messages-bold-daring/)

   ~~~powershell
   # to list out all the git config
   git config --list
   
   # to find the location of all the configuration
   git config --list --show-origin
   
   # add user name
   git config --global user.name "User Name"
   
   # add user email
   git config --global user.email userEmail@demo.com
   
   # configure default commit message 
   
   ~~~

4. Committing the changes in Index

   [git commit documentation](https://git-scm.com/docs/git-commit)

   ~~~powershell
   git commit
   ~~~

5. Remote repository commands

   [Git remote documentation](https://git-scm.com/docs/git-remote)

   ~~~powershell
   
   git push #push the changes to the remote repo
   git pull #pull changes from remote repo
   
   #list all remote repo [push and pull]
   git remote [-v | --verbose]
   
   git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=<fetch|push>] <name> <url>
   
   git remote rename <old> <new>
   
   git remote remove <name>
   
   git remote set-head <name> (-a | --auto | -d | --delete | <branch>)
   
   git remote set-branches [--add] <name> <branch>…​
   
   git remote get-url [--push] [--all] <name>
   
   git remote set-url [--push] <name> <newurl> [<oldurl>]
   
   git remote set-url --add [--push] <name> <newurl>
   
   git remote set-url --delete [--push] <name> <url>
   
   git remote [-v | --verbose] show [-n] <name>…​
   
   git remote prune [-n | --dry-run] <name>…​
   
   git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)…​]
   ~~~

6. Cloning the repository from remote server

   [Git clone documentation](https://git-scm.com/docs/git-clone)

   ~~~powershell
   git clone
   ~~~

7. .gitIgnore

   [Git ignore documentation](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)

   Creating Gitignore file in windows

   ~~~powershell
   ### When file is already not tracked 
   # 1 # create .gitignore file
   nano .gitignore
   # 2 # edit the .gitignore file [add the file which need to be ignored]
   # 3 # save it, in further commits it will not be tracked
   
   ### Add file in to gitignore which is already tracked
   #conside secondIgnore.txt is previously tracked
   
   # 1 # add that file into .gitignore using text editor
   # 2 # remove the secondIgnore.txt file from index with following command
   git rm --cached secondIgnore.txt
   
   # 3 # check the index status
   git status
   >> modified:   .gitignore
   >> deleted:    secondIgnore.txt
   
   # 4 # update the .gitignore in index
   git add .gitignore
   git commit  # add the commit msg in text
   ~~~

8. Restored the staged file to unstaged area in index

   ~~~powershell
   git restore --staged <file>
   ~~~

9. 

   

   



Branching and management commands

local and remote repo

Strategies