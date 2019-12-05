c9 c# GitHub Tutorial

_by Yuhong Zhao_

---
## Git vs. GitHub
Git is a version control system where we can use to keep track of the work. Github is a website service where we can host our code and we can also collaborate with other users. Generally, Git is a command-line tool that can be used independently. While Github is a code hosting service that requires Git for version control.


---
## Initial Setup
Before we start using Git, we would have to do some additional one-time steps. We will need a Github account. If you don’t currently have one you can go [here](https://github.com/join?source=header-home) to create a new account).
1. Basic information
    * Enter your desired username, email address, and password
    * Complete the Captcha
2. Plan
    * For beginners, pick the free plans
3. Complete Setup
    * Enter your responses according to the questions and click *Complete Setup*
    * If you don’t want to do this, you can skip this by clicking *Skip this step* at the end
4. Verify your email address
    * GitHub will send you an email to the email address you’ve provided and just open the link in that email to verify your account.

Once you have an account, we will need an IDE (Integrated development environment) to type your codes. Your IDE would be your local IDE and will contain files locally. Local IDE runs off your computer using your computer’s resources. Here we will be using [ide.cs50.io](https://ide.cs50.io)  as our IDE. This is a remote IDE because it runs off a server somewhere else in the world. Each type of IDE have their benefits and drawbacks, but using a remote IDE would be more beneficial, especially if you are a beginner. One of the biggest benefits is you will not be able to mess up and corrupt your system because you are constrained in a *box*. Unlike a local IDE, you have access to your computer’s file; but if you don’t know what you doing and accidentally deleted something, it can cause your system to crash.
#### [Directions to set up your IDE](https://github.com/hstatsep/ide50)


---
## Repository Setup
To initialize Git, you would need to create a directory that will contain your project. A directory is a file system folder where we put our files, such as documents, images, and videos. Once you have created a directory, navigate to your directory by using `cd <filename>`. Then, using `git init` to get git started and running. This means that your directory will be converted to a repository.  A repository is a version control system where developers and software engineers stores their code. You can also see the `(master)` next to the command prompt.
![](screenshots/git-init.png)
>  In other words, a directory is just a folder that does not have git running, while on the other hand, a repository is a folder that has git running. We also call it a **repo** for short.







---
## Workflow & Commands
**Congratulations! You now have git running!**  
As you work on your projects — making and modifying files, it is important to take a *snapshot* of your code. Taking a *snapshot* or committing in git means saving the changes you’ve made till now. Before committing your files, it’s important to use `git status` to tell you which files are ready to commit. Files in red means they have been modified but have not yet added to the staging area. 
![](screenshots/git-status-red.PNG)  

Files in green means they have been modified but is currently in the staging area and ready to be committed.
![](screenshots/git-status-green.PNG)

To take a *snapshot* of your code, you must first add the files you want to commit to the staging area by using `git add <filename>`. You can add more than one file to the staging area by adding a space between each file name. You can also use `git add .` to add all the files in red.
It’s recommended to use `git status` again to see if you have added the files properly. The files that were in red before should be in green. Once all your desired files have been added to the staging area, you can use the command `git commit -m “<message>”` to commit.

You can attach messages to each commit you do, so you keep a note of what does each commit did. Commit messages should be meaningful and in the present tense, Below are examples of good and bad examples.
Bad Examples | Good Examples
------------ | -------------
“DoNe” | “make README.md”
“I hate git” | “make title bold and italicized”
“Ice Cream?” | “add text to README.md”
“Updated repo” | “change dog to fish in README.md”


Once you have made some changes and committed those changes, you will need to put your code live. To do so, you would need to *push* your files to a remote server such as GitHub. Before pushing to GitHub, you will need to head over to the [website](www.github.com) to make a repository with the **same name** as your repository in your IDE. We will *bridge* your local repo and your remote repo. Bridging or connecting your local repo and your remote repo is important because it allows you to push your files to a remote server to be lived after you finish adding and editing codes in your IDE. If you tried to push your files to a remote server without bridging your IDE and your GitHub account, you would receive an error.
![](screenshots/git-push-error.PNG)
##### Directions to bridge your local and remote repo:
1. After you created a repo in GitHub with the same name as the one in your local IDE, scroll down to find the **`…or push an existing repository from the command line`** sections.
    * Here, you will find two commands.
![](screenshots/git-bridge-commands.PNG)
2. Copy the first command and paste it into your IDE and press enter.
3. Copy the second command and paste it into your IDE and press enter.
    * You must have committed at least one or else you will receive an error.
![](screenshots/git-bridge-commands-errors.PNG)
4. Enter the following code into your command line: `git remote -v`
    * If you get similar feedback to the image, then successfully connected your local repo to your remote repo.
![](screenshots/git-bridge-successful.PNG)
    * Whenever you push your repo to a remote repo, you would not need to do these steps. You will just need to do `git push` to push your files. 




---
## Rolling Back Changes
Once you have saved many changes, you can use `git log` to view all the commits you have made. What if you have made some errors and you want to go back to the last commit that you’ve made? It is recommended to use ‘`git diff` to show you any changes you’ve made ever since the last commit. Texts that you have added will be highlighted in green along with a `+`, while texts that you have deleted will be highlighted in red. You can use the command `git checkout -- <filename>` to discard any changes you have made — *texts in green would be deleted and texts in red would come back*.  After discarding any changes you can use `git diff` again to make sure you did it correctly. It should respond with nothing.
* Your files must not be on the stage in order to use `git diff` and `git checkout` correctly.

What if you accidentally added your files to the staging area and you want to remove the files off from the stage so you can use `git diff` and `git checkout`? Well, you can always unstage a file by using `git reset HEAD <filename>`. Just be sure to replace the `<filename>` with the actual name of the file you want to unstage.
>NOTE: If you ever forget the command for unstaging and discarding changes, you can always use `git status` to find the command.

If you were to make a typo and want you change the commit message of your last commit, you can just simply use `git commit --amend -m “<new-message>”` to change the message of the last commit. What if you committed but you forgot to include a file to that commit? You can also fix that by simply adding the files to the stage that you forgot to commit, and then use the command again, `git commit --amend -m “<new-message>”`.
* It is basically the same but with the addition of `--amend`. With it, you can fix the most recent commit message, but does not allow you to change the commit messages of older commits.

What if you don’t want to change the commit message and you just want to delete or *undo* the last commit? You can use the command `git reset --soft HEAD~1` to basically *rewinds* back into the commit before the last commit. `--soft` allows keeping your changes and untouched. But if you just want to undo a commit and have all the changes discard, then you just replace `--soft` with `--hard`— `git reset --hard HEAD~1`.

But if you want to just go back in history and start from an older commit, then you use `git reset --hard <SHA KEY>`. Replace the SHA key with the one attached to the commit you want to revert back to. 
* SHA key are those unique ID provided to each commit. You can view the SHA key when use the `git log` function. It will be something similar: `commit fab7b189c7ed8e5b14d85f50b837709e99b22e70`
>NOTE: You can just use the first 7 characters instead of the whole string.


First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column



---
## Erorr Handling 
Used `git init` in the wrong folder or directory? Don’t worry! You can always remove git or *uninitialize* git by removing a folder called `.git`. Every thing when you use initialize git, it will create that folder where it will store all the commits and necessary files. In your IDE, it will be hidden because it starts with a dot. You can toggle on to show hidden files in the settings. 
To uninitialize git and remove the `.git` folder, use the command `rm -rf .git`
> `rm` is a remove command, while `-rf` basically means “force removal”. 

This command can also be used with any that you want to remove. Just beware that this command is very powerful as you cannot undo this action and there would be no warning. If you are sure, the command is `rm -rf <filename>`. Just replace `<filename>` with the actual name of the file you want to remove. You can also use this command for remove repos within your local IDE. 
But if you want to completely remove a repo, you will need to use the command mentioned above and as well as removing it in GitHub website. 
####How to delete repo from GitHub
1. Head over to your repo’s main page on GitHub website
2. Click on Setting and scroll down all the way to the last section, **DANGER ZONE**.
3. There are four options and click on the last option, **Delete this Repository**.
4. Type in the name of the repo you are deleting to confirm
5. If done correctly, the continue option would be available. Click on it to ***understand the consequences, delete this repository***.

---
## How to Fork and Clone
GitHub is a website server that stores code, made with the intention of collaborating with other users. In GitHub, you must download their repo in order to test or make changes.

If you just want to test someone’s code and play around with it, you can clone their project on GitHub to your local IDE. ***Cloning is copying from a remote to a local.*** This is like basically downloading a copy of the software and play with it. 
#### Directions on how to clone:
1. You will first need the SSH key of the repo you want to clone.
	* Head to the repo’s main page on GitHub and find **Clone and download**
	* Click on it and copy the **SSH key** only. Do not copy the HTTPS key.
2.  Go back to your IDE, and type `git clone`. Then, paste the SSH key after space.
	* Make sure that you are in the right place where you wish your file to be cloned. 
 	* If you cloned it in the wrong place, you can just use `rm -rf` to delete it. Then navigate to the right place and then clone. 
> A good rule of thumb is to `cd` right into the folder you cloned so you will not be making files in the wrong place.

If you do not want to test someone’s project, but instead want to add changes and provide suggestions to the owner, then you will need to fork the project. Forking a project is making a version of their project that resides in your account. ***Forking is copying for a someone’s remote to your remote.***  
#### To fork someone’s project:
1. You will just need to go over to the repo’s main page on GitHub. 
2. There will be an option to fork this project. Click on it and it will start forking.
3. Wait till it is finish forking, then you can just clone the forked repo to your IDE so you can start editing and adding changes. 

If you cloned someone’s repo and then made some changes, you cannot push your changes because you do not have permission to change someone else’s repo. If you forked, all the changes will be a push to your forked repo. Here you have permission to do so because you are basically pushing changes to your own repo. If you clone from your own existing repo such as forked repos, you do not need to setup up the bridge connection again as that bridge will be already established.

---
## How to Pull Request
After you’ve forked, cloned repo, and have pushed all changes to your forked repo, you can now send these changes to the owner as suggestions. These suggestions in GitHub are called Pull Request. To do so, just click on **New Pull Request** and then click on it again. After that, you can add a message to that pull request. Once done, just press “Create pull request”.
> Pull request should be helpful in explaining what changes you’ve or files you’ve deleted/created.

The owner can review your changes and then if approved, your changes will be merged into the master branch of the code (the main code). 

The owner can also copy from the repo with your changes into his IDE. Once the changes are merged, the remote repo on GitHub “is ahead” of your local by *n* commits, or your local “is behind of your remote by *n* commits. The owner can update the local by using `git pull` which fetch the last modified repository.






