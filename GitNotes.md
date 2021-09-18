# What is Git?
- It is a distributed version control system that helps us to track changes made to our application, file and folder overtime.
- It also allows us to do concurrent programming which basically means that multiple people can work on the same files or series of files and seamlessly integrate changes together.

# What are Repositories?
- Repositories are the containers for git. Whenever we want to use git for a project we will need to initialise a repository.

# How to initialise a repository?
- To initialise a git repository will need to to run the command on the terminal.
```
git init
```
# How to check if folder you are working on has an empty Git repository?
- To check this we will need to simply write this command on the terminal.
```
ls -a
```
If you see that there is a .git file, it basically means that your repository is has being setup correctly.

# Checking the status of our repository
- As mentioned above we know that Git helps us to track changes made to our application. To see this we will need to run
```
git status
```
Let's say we would now like to send the application to github or other platforms like github, how do we do that? 
We will need to first add and that commit. The adding is done in the stating section and the commiting can be found in the commit section.

# Staging files
There are various way we can add files. 
## 1. Add all the files found in the folder
```
git add .
```
But in a large project it is not wise to add all the files everytime because it will take sometime. Instead, we could just add the files that we have modified
## 2. Adding selected files
```
git add file.py file1.py style.css
```
## 3. Adding just 1 file
```
git add file.py
```
After add the files, we would have to commit.
# What is commit?
- When we are making a commit, we are just having a snapshot of our code with the timestamp which is then saved in the commit history of our repository.
To commit, the cammand we will need to run is
```
git commit -m "message"
```
*It is a good practice to have a meaningful commit message. For example, if you change the colour of the button, you can write a commit message
that says "Change the colour of the submit button"*

# Commit history

If you wish to see all the commit that were made in the project then the command for that is 
```
git log
```
The logs will show 4 things and they are the commit message, commit hash, author name and the date when the commit is done. For example
```
  add test.py
commit 65t89q1z123458685....
Author: jack <example@gmail.com>
Date: Fri sep 15 01:25:26 2021 -0800
```
If for some reason you wish to rollback to the previous version, you will need to run
```
git checkout <commit-hash>
```
If you wish to go back to the latest version, you can run
```
git checkout master
```
# Ignoring files
- Now, we know that the all the files in our repository are being tracked for changes all the time. But what to do if we have a file that we do not want 
git to track. Well for that we will need to create a file name .gitignore in our project folder and in that file we will need to add the names of files and folders we 
do not want git to track.

# Branching

![git-branches-merge](https://user-images.githubusercontent.com/90772840/133884854-aa7b1031-1aba-4187-b0c5-c5563eb82527.png)
- Branching is a useful feature that git has to offer.Branches allow people to work on separate parts of the codebase and not interfere with one another, or risk breaking a product that is visible to the client. Breaking something on one branch does not have an impact on any other.

## How to create a branch
- To create a branch we need to run the command
```
git branch <branch name>
```
## Switching from our branch to another branch
- Let's say we would want to switch from one branch to another, we will need to need to run
```
git checkout <branch name>
```
## Switching to the master branch
- To switch to the main branch we will need to run
```
git checkout master
```
# Merging branches
- In this previous section, we looked at how we can create a branch to work on it without touching the master branch. Now, we will look at how we can merge our branch to the master branch. To do this we will need to run 
```
git merge <branch name>
```
# Conflicts during merging
- Merge conflict occurs when we have 2 different values in the same line. For example
*Test.txt on our branch*
```
Hi John Wick.
Hi Sam.
```
*Test.txt on the main branch*
```
Hi John Wick.
Hi May.
```
Clearly we can see that there is going to be a conflict when trying to merge "Hi Sam" because there is already a line "Hi May"
When merging git will show the error like this 
```
This line could be merged automatically.
<<<<<<< current:Test.txt

```
