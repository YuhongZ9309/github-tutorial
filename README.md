c9 c# GitHub Tutorial

_by Yuhong Zhao_

---
## Git vs. GitHub
Git is a version control system where we can use to keep track of the work. Github is a website service where we can host our code and we can also collaborate with other users. Generally, Git is a command-line tool that can be used independently. While Github is a code hosting service that requires Git for version control.

---
## Initial Setup



---
## Repository Setup
To initialize Git, you would need to create a directory that will contain your project. A directory is a file system folder where we put our files, such as documents, images, and videos. Once you have created a directory, navigate to your directory by using `cd <filename>`. Then, using `git init` to get git started. This means that your directory will be converted to a repository.  A repository is a version control system where developers and software engineers stores their code. You can also see the `(master)` next to the command prompt.  
>  In other words, a directory is just a folder that may or may not contain files, while a repository is basically a directory that has git running.



---
## Workflow & Commands
**Congratulation! You now have git running!**    
As you work on your projects — making and modifying files, it is important to take a *snapshot* of your code. Taking a *snapshot* or committing in git means saving the changes you’ve made till now. Before committing your files, it’s important to use `git status` to tell you which files are ready to commit. Files in red means they have been modified but have not yet added to the staging area. Files in green means they have been modified but is currently in the staging area and ready to be committed.  
To take a *snapshot* of your code, you must first add the files you want to commit to the staging area by using `git add <filename>`. You can add more than one file to the staging area by adding a space between each file name. You can also use `git add .` to add all the files in red.  
It’s recommended to use `git status` again to see if you have added the files properly. The files that were in red before should be in green. Once all your desired files have been added to the staging area, you can use the command `git commit -m “<message>”` to commit.   
You can attach messages to each commit you do, so you keep a note of what does each commit did. Commit messages should be meaningful and in the present tense, Below are examples of good and bad examples.  




---
## Rolling Back Changes


---
