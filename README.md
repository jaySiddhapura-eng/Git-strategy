# Git

## Basic git commands

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

3. Committing the changes in Index

   [git commit documentation](https://git-scm.com/docs/git-commit)

   ~~~powershell
   git commit
   ~~~

4. Remote repository commands

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

5. Cloning the repository from remote server

   [Git clone documentation](https://git-scm.com/docs/git-clone)

   ~~~powershell
   git clone
   ~~~

6. .gitIgnore

   [Git ignore documentation](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)

   Creating Gitignore file in windows

   ~~~powershell
   # 1 # create gitignore.txt file
   # 2 # edit this file
   # 3 # open this file in CMD
   # 4 # rename it to .gitignore
   ~~~

   

7. 

   

   



Branching and management commands

local and remote repo

Strategies