# Git and GitHub Basics for Beginners.

## Git Intro

**Git** is a free and open source distributed version control system.

A **version control system** is a type of software that helps a team of programmers to manage and track all the changes made to a source code that they are all collaborating towards.
In addition, it contains information like what changes have been made and by whom.

A **distributed version control system** is a type of version control system whereby every developer has a local copy of the complete codebase on their computer. 

Therefore, in simple terms git is a software that allows you to manage and track changes to files.

## Importance of Git

Git is important when creating documents and recording the changes that undergo with a lot of redrafting and revision.

- It helps to identify what changes have been made while allowing the developers to revert and go back to the previous codebase.

- It helps developers coordinate collaboratively while ensuring the code do not conflict.

## Git Beginner Concepts

Start by downloading git from their site here.[Git](https://git-scm.com/downloads)

Open the command prompt and type the following command to verify Git.

`git --version`


## Creating Local Git Repository

On your computer desktop, create a project folder name beginner-git-intro.
```
cd desktop
mkdir beginner-git-intro
```
You will always be required to add a local Git repository to the project folder so that Git can know what to manage and track.

To add a local Git repository you need to go into your project folder and initialise git. Use the following commands:
```
cd beginner-git-intro
git init
```
In the project, the local Git repository has been added using the `git init` command.

## Creating a Document for the Local Git Repository

In the project folder `beginner-git-intro`, create a `gitdemo.txt` and add the following code snipet into it:

```javascript
if (true){
	let message = "Hello World";
	alert(message);		// Hello World
}
```

The code above is just for demo only, but overally it is a javascript `if statement` that declares a variable named `message` and assigns it a "Hello World" value. Hello World will be displayed as the output.

## Staging and Committing the Code

In order to commit a code in git, a two step process needs to be performed: staging the code and the actual commiting.

### Staging

Staging is the process of telling Git what (new untracked, modified, deleted) files you want to be part of the next commit and what changes in the file will occur in the next commit.
Staging is important especially when working on two files, it helps the developer in controlling which files are ready and needed to be committed.

To Stage a file, the following code is used:

`git add gitdemo.txt`

To add multiple files, the following code can be used:

`git add file1 file5 file9`

In order to add all the files inside the project folder to the staging area, use the following command:

`git add .`

It is important to note that the above command adds all the files and folders in your project to the staging area,so be careful when employing it.

### Committing

**Committing** is the process of adding the code in a developers' computer to the **local Git repository**.

In order to commit a file, use the following command:

`git commit -m "Initial Commit"`

"Initial Commit" is the **commit messages** that describes what code changes were done in that specific commit.

## Git Status and Git Log Command

We are going to modify the `gitdemo.txt` file by adding the following code snippet:

```javascript
<script>
	if (true){
		let message = "Hello World";
		alert(message);		// Hello World
	}
</script>
```

### Git Status

`git status` command is used to find out details regarding what files are modified and what files are in the staging area among others.

To check the status of your Git repo, use the following command:

`git status`

The Git repo status reveals that `gitdemo.txt` is modified and has not yet been added to the staging area.

The following steps are for us to add the `gitdemo.txt` to the staging area and commit the file using the following commands:

`git add gitdemo.txt git commit -m "gitdemo.txt file is modified"`

### Git Log

To check all the commits that you have done so far you can use the `git log` command.
The `git log` command shows the commit message, the author of every commit done, and the date of that particular commit.

## Creating Branches

Git branches are a pointer to the latest changes done in the git repo.
Basically, a new branch encapsulates the changes made.

The importance of git branches is that it makes it harder for unstable code to be merged into the main code base.
In turn, this gives the developer a chance to clean up their future's history before merging it into the main branch.

By default, the commits done in git repo goes into the **master** branch.

Therefore, in our current git repo our master branch points to the second `git commit -m "gitdemo.txt file is modified"`.

Multiple branches supports multiple parallel developments.

To create a new branch use the following command:

`git branch betatest`

The output of this command creates a branch called `betatest`.

The above command only creates the `betatest` branch but it does not switch the pointer from the master branch.
To switch to the `betatest` branch, use the following command:

`git checkout betatest`

The above command has now pointed us to the `betatest` branch.

To check all the branches that are present in the local repo, you can list them using the following command:

`git branch`

### Committing data in the New Branch

Modify the `gitdemo.txt` by adding the following snippet:

```javascript
// If statement in JavaScript
<script>
	if (true){
		let message = "Hello World";
		alert(message);		// Hello World
	}
</script>
```

Stage and commit the modification done to the `gitdemo.txt` by using the following command:

`git add gitdemo.txt git commit -m "Commit Betatest Branch"`

Since we committed the snippet in the Betatest Branch, the Betatest Branch is ahead of the master branch by one commit.
This is as a result of having the two commits from the master branch also included in the Betatest Branch.

Let us verify the commit history done in the Betatest Branch using:

`git log`

### Git Merge

So far the Betatest Branch is ahead of the master branch by one commit.

Git merge is very important in the case whereby we would want all the code snippets in the Betatest Branch to combine with the Master Branch.

The following are the steps that are followed when merging the code snippets from the Betatest Branch into the Master Branch.

Step 1: Go back to the Master Branch:

`git checkout master`

Step 2: Execute the merge command:

`git merge Betatest`

The merge should be successful, and no conflicts highlighted, after running these two commands.

However, in real life projects, conflicts will occur when merging branches.
As you continue to work more with Git you will be able to get the hang of resolving these conflicts which comes with experience.

When you execute `git log` you will observe that the master branch now also has three commits.

## Pushing Code into a Remote Git Repository

So far we have been working on the local repository.

Developers work in their local repository but eventually, they will push the code snippet to a remote git repository.
Other developers can view and modify the snippets when the code is in the remote repository.

# GitHub Intro

In the following project, we will use GitHub for the remote repository.

Visit [GitHub](https://github.com/) and create an account.

Click on **Start a Project** after registering in the GitHub homepage; this will create a new Git repository.

Assign the repository a name and click "Create Repository".
Assign the repo name as `Git-and-GitHub-Basics`.
The above process will create a remote repository in GitHub.

## Git Remote

Open the repository and a page like the below image will open up:

![GitHub Repository]()

The highlighted portion in the opened repository page is the repository URL.
For instance, in this situation it is the following snippet:

`https://github.com/njehamigwi/Git-and-GitHub-Basics.git`

So as to point your local Git repository to the remote GitHub repository, use the following command:

`git remote add origin [repository url]`

## Git Push

To push all the code from the local Git repository into the remote GitHub repository, we will use the following command:

`git push -u origin master`

The above command pushes the code from the master branc in the local Git repo to the master branch in the remote GitHub repo.

# Additional Commands

## Git Pull

`git pull` is used to pull the latest changes from the remote GitHub repo into the local Git repo.

`git pull` is important since the remote GitHub repo is constantly updated by various developers.

To pull the latest change we will use the following command:

`git pull origin master`

## Git Clone

`git clone` is used to clone an existing remote GitHub repo into a developer's computer. The command for this is:

`git clone [repository url]`
