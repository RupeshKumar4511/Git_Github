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

```bash 
If we want to unstage a file from stagged :
git restore --staged file_name


How we can delete a file or directory from folder :
git rm -rf file_name 

Here 'rm' for remove 

'-r' means Recursive option to remove directories and their contents. If the target is a directory, this flag is necessary.

'f' means Forces the removal of files, even if they are not staged or modified.


If we want to reset our project to a particular commit :
git reset --hard "hash_of_that_particular_commit"


```

<br>
<br>

```bash 
If we make a file and write some code in it and we add it but did not commit it and now I want to clean the code and write some another code But when we need the previous code then we can access it for this :

git stash 
This will clean our directory.

git stash pop 
This will put all the previous code into staged area


If we want to clear that previous code permanently 
git stash clear

This command completely removes all entries from the stash.


To check stash list :
git stash list 

```



# Some Basic Vi (in line terminal) commands :
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
We should never make commit in main branch initially because code may have bugs. In this case we make a new separate branch to add features to a project.

