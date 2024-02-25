## What is Git?
<p>Git is a tool/software that is used to control the version of a system </p>

## Why do we need git ?
- Version Control System
- Keep track of Changes
- Collaboration on Project

## Other Version Control System
1. GitLab
2. BeanStalk
3. PerForce
4. BitBucket

``` Over 70% Developer use Git !```

## What is Github?
<p>Github is Repository that provides Graphical user inteface.</p>

### Difference between Git and Github:
|Github | Git |  
|-------|------ |  
|Service | Tool/Software |  
|Repository/folder/source code | Change Control, Version Control|  
|Provides GUI Interface | Provides CLI Interface |  
|Maintained on cloud/web | Installed and maintained locally | 

### More about Git and Github:
#### GitHub: 
- More than 56 million users
- Founded in 2008
- Owned by Microsoft

#### Git:
- Released : April 7, 2005
- Python, C, C++, Perl
- Linus Towards  

## Git Setup and Configuration
<p>To download the git in your device click download</p>
[download]('https://git-scm.com/downloads')

__To show git version__  
```git --version```   
__For Git Configuration__:   
UserName:  
```git config --global user.name "UserName"```   
Email:  
```git config --global user.email "Email"```   
To see the UserName what you have set in the terminal:   
```git config user.name```   
To see the Email what you have set in the terminal:   
```git config user.email```  
<p>You can change the username and email if you need to change according to config</p> 
  
__How can we push a file/folder in github from git__   
```working Directory -> staging area -> local repo. -> remote repo.```   
```Test-area -> git add -> git commit-> git push```



## __Git Command__
### To show Which directory we are working:   
```pwd```
### To see all files:   
```ls```
### Create make dictionary/folder
```mkdir folderName```
### To see all files with hidden files
``` ls -a ```
### To initialize the git in your terminal:
``` git init ```
### Create new file  
```touch fileName```
### Open the file in windows
```start fileName```
### Open the file in linux
``` open fileName ```
### To see git status
```git status ```  
### Delete a folder: 
``` rm -rf “folder name” ```
## __To go Stagging area from working Directory__
From Untracked to tracked file:
- git add FolderName
- git add - A (stage all changed file in directory and sub-directories)
- git add . (stage all changed file in directory but not sub-directories)
- git add *. (directory wildcard)

```For restore information -> git restore fileName```

## From Staging to unstaging add:
```git rm --cached fileName```
## To see the difference between unstaging and staging area
```git diff ``` 
## Staging area to local Repository...
### How to make a git commit:
```git commit -m "just write text what about you do or why you want to commit" ```
### To see all history
```git log ```
### Instead of git log, to see id and commits
``` git log --oneline ```
### Combine of Tracking/stagging and create local repository
``` git add . && git commit -m "message" ```
### To open folder in Visual Studio code
```code .```
### Move one commit to another commit 
``` git checkout commitName ```
### To delete all files from local Repository. to working directory
``` git reset HEAD^ ```
### From Local Repository to stagging area
``` git reset --soft HEAD^ ```
## Remote Repository
### To check, the remote repository exist or not
``` git remote ```
### To move from local repo. to remote repo.
``` git remote add origin "link of remote repo." ```
### To push on master branch
``` git push -u origin master ```
### For Pull Request
``` git pull / git pull origin master ```

## __Gitignore File__ 
<p>.gitignore refers to sectret things that we do not want to share.</p>   

### Example
- test.txt
- .env
- *.txt (all txt file)
- !main.txt (not main.txt)
- text?.txt (text1, text2, text3 ....... .txt)
- temp / (will be ignore inside all file in temp folder) 

__if you write above list in .gitignore file, then these file will be hidden in your remote repository__.

## __Branch__
Branch is a new and separate branch of the master repo.   
In a big project,we separate the tasks and features and create branch so editing in the new branch does not affect the master branch.

``` Branch -> Reviews -> Testing  -> Merge ```
### Necessary Commands for Branch
---
### To check, how many branch have your repo. ---
``` git branch ```
### To check remote branch 
``` git branch -r ```
### To check local and remote branch
``` git branch -a ```
### To create New Branch
``` git branch "Branch Name" ```
### Move/switch to new Branch
``` git checkout "Branch Name" ```  
### Asterisk symbol(*)
```* represents current branch ``` 
### Delete new branch 
``` git branch -d "BranchName" ``` 
### Merge with Master Branch
``` git merge "BranchName" ```
### Create and Checkout branch 
``` git checkout -b "branchName" ```
### Push New branch in github
```git push -u origin "BranchName" ```

### Merge in git from github
``` git pull ```



## 2-way merge / First forward Merge
Example - 
```
- git commit
- git commit
- git branch feature1
- git checkout feature1
- git commit
- git commit
- git checkout master
- git merge feature1
```
![First Forward Merge]([data:image/png;base64,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](https://miro.medium.com/v2/resize:fit:1400/1*zEwBR4qwR87766jJOv1a8g.jpeg))

## 3-way Merge
```
- git commit -m “second commit”
- git commit -m “third commit”
- git branch feature
- git checkout feature
- git commit -m “four commit”
- git commit -m “five commit”
- git checkout master
- git commit -m “six commit”
- git commit -m “seven commit”
- git merge feature

```

![3-way Merge](data:image/jpeg;base64,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)


## Merge Conflict
At a time different merge do from different branch -> create conflict
and we can resolve the ultimate conflict

## Fork 
- A Fork is a copy of a repository. This is useful when you want to contribute to someone else’s project or start your own project based on theirs.
- Forking own repo is not possible.
- Fork is not a command, use github and fork.

```Fork -> git clone -> make pull request```

## Clone
``` git clone HTTPs links ```















