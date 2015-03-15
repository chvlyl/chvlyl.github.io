---
layout: post
title: "GitHub website setup"
date: 2015-03-09
---

Keep track all the problems I have:  
1. In the YAML header of the .md file, there must be a space after semicolon.  
Wrong:  
 `layout:default`  
Correct:  
 `layout: default`   
2. Emphasis: either \*emphasis\* or \_emphasis\_

Markdown:  
1.Create a new line: just type two or more spaces after the line.

Setup the cutom domain with GoDaddy:  
1. Go to [GoDaddy](www.godaddy.com) and buy my own domain name statchen.com.  
2. Go to GoDaddy *Zone File Editor*:  
3. At *A(Host)* section add Host:@ Points to: 192.30.252.153  and Host:@ Points to: 192.30.252.154  
4. At *CNAME (Alias)* section add Host:www to: chvlyl.github.io
5. Go to GitHub, add a file called CNAME with content statchen.com  
6. I set the link in the layout to my GiHub website link chvlyl.github.io and this caused some problems. I changed the link to statchen.com and then problem was solved.     





Resouces:  
- Markdown:  
[Markdown syntax by John Gruber](http://daringfireball.net/projects/markdown)  
