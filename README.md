c9 c# GitHub Tutorial

_by Yuhong Zhao_

---
## Git vs. GitHub
Git is a version control system where we can use to keep track of the work. Github is a website service where we can host our code and we can also collaborate with other users. Generally, Git is a command-line tool that can be used independently. While Github is a code hosting service that requires Git for version control.


---
## Initial Setup



---
## Repository Setup
Before we start using Git, we would have to do some additional one-time steps. We will need a Github account. If you don’t currently have one you can go [here](https://github.com/join?source=header-home) to create a new account.  
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
##### [Directions to set up your IDE](https://github.com/hstatsep/ide50)



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
