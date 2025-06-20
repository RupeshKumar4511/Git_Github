# Git Commands 
```bash 
To check hidden file :
ls -a  


To check what is inside hidden file :
ls .git


To create a file inside a folder :
touch file_name

To check what is written in the file : 
cat file_name



```


<br>
<br>


# How to set username and password :
```bash 
git config --global user.name "abc"

git cofig --global user.password "abc123"

```


<br>
<br>

```bash

If we want to unstage a file from stagged :
git restore --staged file_name


How we can delete a file or directory from folder :
git rm -rf file_name 

Here 'rm' for remove 

'-r' means Recursive option to remove directories and their contents. If the target is a directory, this flag is necessary.

'f' means Forces the removal of files, even if they are not staged or modified.


We can check the logs of all commits by using:

git log


To see all the commit graphically use: 
git log --oneline --all --graph

```

<br>
<br>

```bash 
If we write some code in a file and we add it(to staged area) but did not commit it and
now I want to clean that code and write some another code. But when we need the previous
code then we can access it for this we can use  :

Note : without making commit we cannot checkout to another branch. In this case, we use stash. 



git stash 
This saves both staged and unstaged changes and resets your working directory to the last commit.

git stash apply 
Reapplies the most recent stash but did not remove it from the stash list.


To apply specific stash : 
git stash apply stash@{1}


git stash pop 
Reapplies the most recent stash and removes it from the stash list.


If we want to clear all the uncommit changes in the stash: 

git stash clear
This command completely removes all entries from the stash.


To delete a specific stash : 
git stash drop stash@{0}


To check stash list :
git stash list 

```



# Some Basic Vim (in line terminal) commands :
```bash 

Save and Exit
Press Esc to ensure you are in normal mode.
Type :wq and press Enter.
:w writes (saves) the file.
:q quits Vim.


Save Without Exiting
Press Esc to ensure you are in normal mode.
Type :w and press Enter.

Exit Without Saving
Press Esc to ensure you are in normal mode.
Type :q! and press Enter.
! forces the quit without saving.

Save to a Specific File
Press Esc to enter normal mode.
Type :w filename and press Enter.
This saves the current buffer to the specified filename.

```


<br>
<br>

```bash 
By convention all the files that are attached to personal account repostories in a github url belongs to origin.

git remote -v  
This commands give us all the url that belongs to a folder.
```
# Branch :
A branch in Git is a lightweight, movable pointer to a commit. It is used to isolate work in a version-controlled project, allowing you to develop features, fix bugs, or experiment without affecting the main codebase.
A branch is just a name (e.g., main) pointing to a specific commit (node).
When you make a new commit, the branch pointer moves forward automatically.

<br>
<br>

<b>Note : 
We should never make commit in main branch while contributing to a open source project because code may have some bugs. In this case we should make a separate branch to add each features to a project.

</b>
<br>

```bash 
To check whether connected with remote repository then use:

git remote show origin
```

# HEAD in Git file : 
Head is just pointing to the last commit made to a current branch.
<br>

```bash 
// We can move/detached head to particular commit in local repo: 

git checkout "hash_of_that_particular_commit"

// we can move/detached head to particular branch in local repo: 

git checkout "branch_name"

```

# Upstream :
It refers to the repository or branch from which your local repository or branch is pulling or push changes.
<br>
```bash 
git push -u origin my-branch

Here -u sets the my-branch branch to track origin/my-branch.
```

# Upstream Url : 
Url from where we have forked a project to our own account is called Upstream url.


# How to reset commits in local repo : 

```bash 
// If we want to reset our project to a particular commit :

git reset --hard "hash_of_that_particular_commit"

// here reset can be :

--soft : It moves HEAD to "hash_of_that_particular_commit" only and Keeps changes in staging area (index) and working directory intact. 


--mixed(Bydefault) : It moves HEAD to "hash_of_that_particular_commit" and resets staging area and Leaves working directory unchanged. 

--hard : It moves HEAD to "hash_of_that_particular_commit" and resets staging and working directory or we can say All changes are lost from disk and staging.


git reset --hard head~1
// move head to previous commit. 

// If we want to revert any commit then we need hash of previous commit and 
// we can access that hash by using ; 

git reflog 

```

# How to revert commit in remote repo : 
If we have pushed an undesired code to remote repo then we can revert it by using : 
<br>

```bash 
git revert "hash_of_that_particular_commit"

// "hash_of_that_particular_commit" will be the hash of that commit which have done by mistake. 


// revert : It creates a new commit that undoes the changes made by the specified commit. But history of that commit is preserved.  


// once we have revert in local repo we need to push
// to remote repo. 


// we can revert multiple commits 

git revert head~3..head~0 

// it will revert last three commits. 




```

# Cherry picking in git : 
Cherry-picking in Git means selecting a specific commit from one branch and merge it to another.
<br>
```bash 

git cherry-pick <commit-hash>
This applies the changes introduced by the commit with the given hash to your current branch.

```

# Remove cache of tracking of file/folder by git: 
git rm --cache <file-name>

git rm --cache <folder-name>



# How to Work on open source project :
```bash 

1. Make a fork of that project to your account .

2. clone the project to your system folder.

3. Make separate branch to add new features there and then commit it.

4. git remote add upstream "https://github.com/RupeshKumar4511/Git_Github.git" 

Here it can be any upstream url.

5. git push origin main

6. make a pull request to main branch of open source project.

```
<br>
<br>
```bash 
when other collaborators make changes in any branch of remote git repository which is not available on local repository then to add it into the local repository we can use: 

git fetch  // fetch the latest commit 

//and then merge the code after verifying it : 
git merge <branch_name>


// We can also use 
git pull  // it fetch and merge operation simultaneously. 



```
# Important Point :
If your local repository does not contains the commit which are on online repository and you want to push some changes to online repo.
then it does not work. Then in this case you need to push it forcefully .
<br>
```bash 
git push origin main -f 

Here f means forcefully.

```
<br>
```bash 
Other way: we can resolve unrelated-history manually. 

git pull origin main --allow-unrelated-histories

//and then accept or denied the changes and then

git add . 

git commit -m "message"

git push origin main 

```

# Pull Request :
A pull request (PR) is a feature in version control systems like Git, used primarily in collaborative development workflows. It allows developers to propose changes to a codebase and request that these changes be reviewed and merged into a target branch (usually the main or development branch).

<br>
<br>

<b>
    Note : One branch is associated with only one pull request so while working on fork of open source project makes separate branch for each features or debugs the bugs and create pull request to main branch of open source project to merge it. Then they sees your code and run some test and give you some suggestion if needed and then you may need to made some changes in your code and finally they merge it if your code feature is useful. 
</b>




<br>
<br>

While working on fork of open source project when your pull request is merged to main branch of upstream(original open source project repo url) but you did not find that changes in your main branch then 
there are two ways to fetch those changes :
<br>
Ist Way : By clicking on the Fetch Upstream button on the github repos.
<br>
<br>
IInd way : 
<br>
```bash 
1. First go to your main branch :
git checkout main 

2. fetch all the commits and changes :
git fetch --all --prune

Here prune means once which are deleted will also fetched.

3. git reset --hard upstream origin/main

This action will:
Point your branch's HEAD to the same commit as upstream/main.
Replace your working directory and index with the upstream branch's state.

or 

we can also pull request of upstream main . 
git pull upstream main 



4. push your changes to main branch.
git push origin main 

```

# Squash Commits : 
It means merging multiple commits in single commits.

<br>
<b>How to pick and squash commits :</b>
<br>

```bash 
1. copy the hash of last commit above which you want merge the commits . 

2. git rebase -i  "hash of last commit"
Here i means interactive environment.
```
<br>

<img src="squash_commits.jpg" alt="squash_commits">
<br>

```bash
All the commits below "pick d9dd724 1"
will be squashed to "pick d9dd724"


3. Exit out of it.
Enter Esc and then type ":x" and press enter.
This will allow you to create a message for new commit.



4. Add message and exit using step3.
```



# Merge Conflicts :
A merge conflict in Git occurs when Git is unable to automatically merge changes from two branches. This typically happens when the same part of a file has been modified in both branches, and Git cannot decide which changes to keep. Merge conflicts require manual intervention to resolve.


 






