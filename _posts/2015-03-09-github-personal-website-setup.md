---
layout: post
title: "GitHub personal website setup"
date: 2015-03-09
---

Step 1: setup an account in GitHub:  
  1. Go to [GitHub](https://github.com/).  
  2. Create an account in GitHub.  
  3. Create a repository username.github.io, replacing username with your GitHub username.  
  4. I used the website templates from [Jonathan Mcglone](http://jmcglone.com/guides/github-pages/) and [Yihui Xie](http://yihui.name/).  
  5. Copy the template into your github repository. You have to learn some github basics about how to push a file into the respository.   


Step 2: setup the custom domain with GoDaddy:  
  1. Go to [GoDaddy](www.godaddy.com) and buy your own domain name (mine is statchen.com).  
  2. Go to GoDaddy **Zone File Editor**:  
  3. At **A(Host)** section add `Host:@ Points to: 192.30.252.153`  and `Host:@ Points to: 192.30.252.154`  
  4. At **CNAME (Alias)** section add `Host:www to: chvlyl.github.io`  
  5. Go to GitHub, add a file called CNAME with content `statchen.com`  
  6. I set the link in the layout to my GiHub website link chvlyl.github.io and this caused some problems. I changed the link to statchen.com and then problem was solved.     


Step 3: modify the index.md files from the template (this is the main website):  
  1. In the YAML header of the .md file, there must be a space after semicolon.  
  Wrong:  
   `layout:default`  
  Correct:  
   `layout: default`   
  2. Create a new line: just type two or more spaces after the line.  
  3. Math equation support:  use \\ begin\{equation\} and \\end\{equation\}


Step 4: update changes: 
git add README.md
git commit -m 'Add README.md'
git push -u origin master

 
Step 5: run Jekyll:  
Run `jekyll serve --detach` in the website home folder to setup the local server. You can use `http://127.0.0.1:4000/` to access the website on the local web browser.

Step 6: add new pages on the main website:  
In the `_layouts` folder, edit the layout html file you use, for example `default.html`. 



