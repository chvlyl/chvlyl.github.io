---
layout: post
title: "GitHub basics"
date: 2015-03-08
---


#### Basic workflow
1. Create a branch: anything in the master branch is always deployable. when working on a feature or a fix, create a new branch with descriptive names.
2. Add commits: This keeps track of the progress as you work on a feature branch.
3. Open a pull request
4. Deploy
5. Merge to master branch



### [Pro Git](https://progit.org/)
1. Git has three main states that your files can reside in: committed, modified, and staged. If a particular version of a file is in the Git directory, it’s considered committed. If it has been modified and was added to the staging area, it is staged. And if it was changed since it was checked out but has not been staged, it is modified.
- Committed means that the data is safely stored in your local database. 
- Modified means that you have changed the file but have not committed it to your database yet. 
- Staged means that you have marked a modified file in its current version to go into your next commit snapshot.

2. The first thing you should do when you install Git is to set your user name and e-mail address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com

3. Setup SSH keys
- Check for SSH keys: ls -al ~/.ssh
- Generate SSH kyes with GitHub email: ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
- Add the key to the ssh-agent (skipped): ssh-add ~/.ssh/id_rsa
- Add SSH key to GitHub account: more ~/.ssh/id_rsa.pub and copy the content to GitHub SSH key setting
- Test the connection: ssh -T git@github.com

4. Push the local files to GitHub
- Clone remote repository
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
- 
git remote add origin remote repository URL
git remote -v
- Commit files
git init
git add .
git commit -m 'initial project version'
git push origin master
# Pushes the changes in your local repository up to the remote repository you specified as the origin

5


