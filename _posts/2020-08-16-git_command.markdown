---
layout: post
title:      "Git Command"
date:       2020-08-16 23:44:25 +0000
permalink:  git_command
---


As a web developer when we are working on our code we want to make changes on them. Also we might have wanted to save the old version of our file. Most of the time that become quickly messy, especially when we duplicate the file and then make change to the duplicate.  As we begin working on larger projects we need to store the files somewhere online so that all we can be working on the same files. There are many websites that we can use to store our files  In order to keep track of changes that we make to our code we can use Git Command.

Git is set of command that designed to execute on Linux, Windows and Mac.  Git allows us to: 
* Track changes made to files and easily reference them.
* Save the old version without duplicate the file.
* Synchronize code between different developers.
* Test changes to our code without lose access to the original version. 
* Revert back to the old version of our code. 

Here are some basic Git command: 

**git clone**
After creating a new repository at github, we run git clone to take the repository from the internet and download it into our computer. We run git clone follow by the url for the git repository that we need to download.
```
git clone <url>
```

**git add**:
After we add some code to our file the command git add will add the changes to the staging area. We can run git add follow by the file name if we need to add specific file. If we want to add all the files we run `git add .` 
```
git add <filename>
```

**git commit**:
Git commit keeps track of any changes that we add to our files and creates a snapshot of the change and save the current state of the repository. We run git commit follow by -m follow by a message that describes the changes that we made inside quotation mark. 
```
git commit –m “Message”
```

**git push**:
We run git push to send our commits to the github repository. 
```
git push
```
