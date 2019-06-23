### How To Use Git with GitHub

###### Install Git Package on Ubuntu/Debian

    sudo apt-get install git-core


###### Add a SSH Key
Run the following commands to add a SSH Key to your SSH-agent so you can use git without logging in again and again.
It is important that you stand in your home directory

Generates a new set of SSH-keys both private and public, it will ask you to create a password.

    cd .ssh && ssh-keygen -t rsa -b 4096 -C "your_email@example.com"


Add your private SSH-Key to your computers ssh-mannager

    ssh-add


Add your public SSH-key to GitHub

    cat id_rsa.pub

    
Now copy the latest output and go to GitHub to add the public SSH Key to your account

Source: https://help.github.com/articles/generating-ssh-keys/

Also you can copy the local public key to remote server using this command:

    ssh-copy-id -i id_ed25519.pub user@hostname

###### Download repository from github

    git clone git@github.com:Username/Repo.git

###### Add new files to the tracking list

    git add filename.sh             // Adds everything to next push
    git status            // shows changes you are about to commit
    git commit -m "Some Comment"  // Prepare for push
    git push            // You are sending all chosen changes to your repository

###### If you are ahead in branches use

    git push origin master

###### Remove files from repository

    git rm filemane         // Removes file from repo on next push
    git status            // Shows changes you are about to commit
    git commit -m "Removed some files"  // Prepare for push
    git push            // you are sending all chosen changes to your repository

###### Download changes

    git pull

##### View unpushed changes (compare your local HEAD with master remote)

    git diff origin/master..HEAD

##### Branching

###### Create and start working on new branch

    git checkout -b branchname

###### Deletion of Branch

    git branch -d branchname

###### Merge branch into master branch

    git checkout master
    git merge branchname

###### To remove the last commit (Might be dangerous for others working on project)
    git rebase -i HEAD~2
    git push -f origin branchName

###### If you have commited and pushed file changes to remote and would like to revert the changes to this specifik file

    git checkout HEAD~ -- path/to/file
    git commit --amend -CHEAD
    git push --force-with-lease origin <branchname>

###### If you would like to change the lastest commit message(given no one pulled the recent changes)
    git commit --amend -m "New commit message"
    git push --force origin <branchname>





###### Having trouble with keeping up with git? Try this
* http://pcottle.github.io/learnGitBranching/
