# Git

## First Time Git Setup

1. Initialize local repository

   ~~~bash
   $ git init
   #nevigate to the project folder on which versioning need to be done
   ~~~

2. Add file to index

   [Git add documentation](https://git-scm.com/docs/git-add)

   ~~~bash
   $ git add <file>  # to add one file to index
   $ git add .  #to add all the files to index 
   ~~~

3. Add user client config

   [Git configuration](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)

   ~~~bash
   # to list out all the git config
   $ git config --list
   
   # to find the location of all the configuration
   $ git config --list --show-origin
   
   # add user name
   $ git config --global user.name "User Name"
   
   # add user email
   $ git config --global user.email userEmail@demo.com
   ~~~

   [Writting good commits](https://medium.com/compass-true-north/writing-good-commit-messages-fc33af9d6321)

   [custom git commit template](https://backlog.com/blog/git-commit-messages-bold-daring/)

   Global default commit message

   ~~~bash
   # create the .gitmessage in root directory
   $ nano .gitmessage # to create the file, copy the "template" of this diretory in .gitmessage file
   
   # check whether template set successfully
   $ git config commit.template
   output >> .\.gitmessage  # then commit message template is set correctly
   ~~~

   Repo wise default commit message

   ~~~bash
   # create and edit commitmsg.txt file in local repo
   # add the commitmsg.txt in .gitignore
   
   # set local commitmsg.txt
   $ git config --local commit.template "absolute path name of the commitmsg.txt"
   
   # to check the commitmsg file set correctly 
   $ git config --local commit.template
   >> will return the file path of commitmsg.txt
   ~~~

4. Restored the staged file to unstaged area in index

   ~~~bash
   $ git restore --staged <file>
   ~~~

5. .gitIgnore

   [Git ignore documentation](https://www.atlassian.com/git/tutorials/saving-changes/gitignore)

   When ignoring file is not tracked

   ~~~bash
   # 1 # create .gitignore file
   $ nano .gitignore
   # 2 # edit the .gitignore file [add the file which need to be ignored]
   # 3 # save it, in further commits it will not be tracked
   ~~~

   When ignoring file is being tracked previously

   ~~~bash
   #conside secondIgnore.txt is previously tracked
   
   # 1 # add that file into .gitignore using text editor
   # 2 # remove the secondIgnore.txt file from index with following command
   $ git rm --cached secondIgnore.txt
   
   # 3 # check the index status
   $ git status
   >> modified:   .gitignore
   >> deleted:    secondIgnore.txt
   
   # 4 # update the .gitignore in index
   $ git add .gitignore
   $ git commit  # add the commit msg in text
   ~~~

6. Committing the changes in Index

   [git commit documentation](https://git-scm.com/docs/git-commit)

   ~~~bash
   $ git commit
   ~~~

7. Remote repository commands

   [Git remote documentation](https://git-scm.com/docs/git-remote)

   ~~~bash
   
   $ git push #push the changes to the remote repo
   $ git pull #pull changes from remote repo
   
   $ git remote [-v | --verbose] #list all remote repo [push and pull]
   
   $ git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=<fetch|push>] <name> <url>
   
   $ git remote rename <old> <new>
   
   $ git remote remove <name>
   
   $ git remote set-head <name> (-a | --auto | -d | --delete | <branch>)
   
   $ git remote set-branches [--add] <name> <branch>…​
   
   $ git remote get-url [--push] [--all] <name>
   
   $ git remote set-url [--push] <name> <newurl> [<oldurl>]
   
   $ git remote set-url --add [--push] <name> <newurl>
   
   $ git remote set-url --delete [--push] <name> <url>
   
   $ git remote [-v | --verbose] show [-n] <name>…​
   
   $ git remote prune [-n | --dry-run] <name>…​
   
   $ git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)…​]
   ~~~

8. Cloning the repository from remote server

   [Git clone documentation](https://git-scm.com/docs/git-clone)

   ~~~bash
   $ git clone
   ~~~

## Branching Strategy

1. [Tool to practice branching ](https://git-school.github.io/visualizing-git/#free)

2. When new git repo initialize only master branch present at that moment

3. It good practice to make a branch out of master for further development

   ~~~bash
   $ git init
   $ git add doc1
   $ git commit 
   # HEAD represents on which branch you are now [we are on master]
   ~~~

   ![After initializing the Git in directory](assets/onlyMaster.PNG)

4. Adding branch B1

   ~~~bash
   $ git branch B1
   
   # to check how many branches
   $ git branch  
   >>	B1
   >>  * master		# star represent HEAD which is on master branch
   
   $ git add masterDoc1	 # this doc will be reflected only on master branch
   $ git commit			# this commit will be indexed on master branch
   ~~~

   ![Branch added but changes did not reflect on it](assets/masterDoc1onMasterBranch.png)

5. Change the head to branch B1 and commit changes at branch B1

   ~~~bash
   $ git checkout B1 		# change Head from master to B1
   $ git branch   # to confirm the Head is on B1
   
   $ git add doc2		    # this fill will be inserted on branch B1
   $ git commit			    # file doc2 will not be reflected on master branch
   
   # some changes in file
   $ git commit				# this commite will be apply to branch B1
   
   # add one more file to the branch B1
   $ git add B1doc3
   $ git commit
   ~~~

   ![Above operation](assets/fileaddedAtB1.PNG)

6. Lets add one more branch from master

   ~~~bash
   $ git checkout master		 # changing the head to master from B1
   $ git branch 			  	# check whether head is on itended branch
   
   $ git branch B2			# add B2 branch from master
   $ git checkout B2			# bring the Head to branch B2
   
   $ git add B2doc3 				    # add file name B2doc3 on branch B2
   $ git commit	"5d28802.."			# commit the B2doc3 
   
   # add some more changes at B2
   $ git commit 	"09060a4.."				
   
   # change head to master and add one file at master
   $ git checkout master
   $ git add Mdoc4
   $ git commit	"3f42d0d.."		
   $ git commit 	"a4d2eb2.."			
   
   
   ~~~

   ![Branch B2 added](assets/B2added.PNG)

7. Content of all the branches

   ~~~bash
   Branch : Master
   	doc1  
   	masterDoc1  
   	Mdoc4
   Branch : B1
   	B1doc3  
   	doc1  
   	doc2
   Branch : B3
   	B2doc3
       doc1  
       masterDoc1
   ~~~

8. Merge branch B1 into B2

   ~~~bash
   B2 will be base branch
   
   # bring the head to the branch which need to be merge into base branch
   # in our case Head will be on B1
   
   $ git checkout B1
   merging is already done in the web tool
   ~~~

9. 

10. 

11. 

    ~~~bash
    
    ~~~

    

    









Branching and management commands

what is fork ?

local and remote repo

Strategies