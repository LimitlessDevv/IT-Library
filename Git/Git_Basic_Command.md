# Basic Git Commands
## 1. git init
`git init` command creates a new Git repository or reinitates an existing one.

When you run the command, your current directory becomes a Git repository, allowing you to track its changes. It adds a hidden .git folder in the directory, where Git store all the metadata and history of your project. Without it, your project is just a normal folder, not a Git repository.
![alt text](images/hidden_git.png)

## 2. git clone
`git clone` command copies a Git repository from on location to another. It usually copies an existing repository from remote servers like GitHub or GitLab to your local machine.

`git clone <repository-url> [new-folder-name]
`

## 3. git status
`git status` command shows the current state of your working directory and staging area. 
1. shows staged changes

    :  Files added with  git add that are ready to be committed
2. Shows unstaged changes

    : Files that have been modified but not yet staged
3. Shows untracked files
    
    : New files that Git isn't tracking yet
4. Shows branch info

    : Tells you which branch you are on and if it's ahead/behind the remote branch
    ![alt text](images/git_status.png)