# LEARNINGS 
# GIT & GITHUB 

# SOME CMD COMMANDS 
- cd     (to change directory)
- mkdir   (to make directory)
- touch > filename with extension     (for creating files)
          [*.md --- for vs code]
          [*.txt --- for simple text file]
- more <filename with extension>    (for viewing file content in cmd)
- cls     (to clear screen)
- dir     (to display all files)
- rmdir <name of directory>    (to remove/delete directory)
- del <filename with extension>    (to delete a specific file)
- del /f <filename with extension>   (to delete readme file)
- del* .extension   (to delete all file with same exension)
- del* name         (to delete all file with same name)



# GIT COMMANDS 

- git init   (to make hidden .git folder inside any directory)
- dir .git   (to see what .git folder contains)
- git status  (to see the status of the file or to see whether the files are staged or non staged)
- git add .   [To put files on staging area]
- git add <filename with extension>    " " " " "  
- git restore --staged <filename with extension>     (to remove file from staging area)
- git commit -m "some random text"    [To create history or picture of the files in log]
- git log       [To view log history]
- git reset <hashid>  [to reset the recent commit , here you have to paste the previous commit hashid]
- git config --global user.name "username"   [To set your username]
- git config --global user.email "email"     [To set your email]
- git --help    [for seeking help]
- git stash    [stashing changes or saving changes somewhere else other than in log history]
- git stash pop   [Bringing back all the changes from the stash area]
- git stash clear    [To remove all the changes form stash area and now you can't get it back]



# STARTING GITHUB 
[we will use basically git commands]

- git remote add origin <url>  [connecting your git repository to your project]
     [remote --- working with url]
            [ add -- you are going to add new url]
                [origin --- it's basically name of the url]
                       [ url --- you have to paste the url of your repository]

- git remote -v   [To view the attached url]
- git push origin master  [To push local changes to remote repository]
- git branch -d <branchname>    [To delete a branch]

 # ** PRO TIP **
 [NEVER COMMIT ON MAIN BRANCH CREATE OTHER BRANCHES AND THEN COMMIT]

- git branch <branch name>    [To create a new branch]
- git checkout <branch name>   [To align your head to that branch and all the commits you will perform will be done will don't interfere with the main branch]

- git merge <branch name>     [For merging branches]


# WORKING WITH EXISTING PROJECT ON GITHUB 

[You have to fork someone else project to make changes in it untill and unless you don't have access to that project too]
[ fork option will be available there]
- After forking you have to clone that project into your local .... now lets see how it's done. 

- git clone <url>  [For cloninig other project into your local ]
            [url --- url of the forked project you can get it in code section]

- git remote add upstream <url>   [To sync original project with your local]
                [upstream<url> -- from where you have forked this project is known as upstream url]

- git remote -v   [to see the url synced]
- git push origin <branch name>   [ for making pull req ]
        [Never make pull req with main branch untill you don't have your project checked]



# REMOVING A COMMIT FROM THE PULL REQ BY THE FORCE 

Let's assume that you have made some file and have commited it and then pushed it to your repository from specific branch. after that you want to delete a commit follow these :-

- git staus 
- git log
- git reset <hashid>
- git add.
- git stash 
- git push origin <branchname> -f   [for force pushing pull req]

[ <hashid> -- of the previous commit and which you don't want to remove which will be the bellow one of the hashid of the commit you want to remove.]

# MAKING FORK PROJECT EVEN WITH YOUR MAIN PROJECT 
[ keeping your project updated as the original project main branch]

steps to be follow :-

- git checkout main 
- git status 
- git log 
- git fetch --all --prune   [it will fetch even the deleted commits and update it to your project]
- git reset --hard upstream/main 

   ** or you can simply use ** 

- git pull upstream main
- git push origin main 
{ simple be done by this method 2 }

# Squashing commits / merging commits 

first of all make a new branch and align your head to that branch 
now make seprate commit of all the file 

( Using the rebase command to squashing commits)

- git rebase -i <hashid>
                [ <hashid> --- it's that hashid above which commits you want to merge ]

- after that you will have to change "pick" into "s" of those commit who you want to merge into that "pick" commit. 
- after that you can edit the commit message if you wish to

[ In this way commits are merged]

