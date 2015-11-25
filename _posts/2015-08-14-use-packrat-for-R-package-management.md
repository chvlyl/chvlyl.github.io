---
layout: post
title: "Use Packrat for R Package Management"
date: 2015-08-14
---

Packrat tracks the version of R and packages used in the project which makes the project completely self-contained. Therefore anyone using Packrat will have the same software environment. With packrat, functions such as install.packages and remove.packages will only modify the private project library, instead of the user library.


1. ### Install Packrat
Install it from GitHub by:  
```
install.packages("devtools")    
devtools::install_github("rstudio/packrat")   
```

2. ### Initialize Packrat
```
packrat::int()
```
Packrat will create a directory called "packrat" and will find packages used by the scripts in the projct and download the source code. It will create a "private library" for package management.
That is, packages installed inside the packrat project are ONLY available to that project. Also packages installed outside the project are NOT available to the project.

3. ### File created by Packrat 
- packrat/packrat.lock: package versions of the packages
- packrat/packrat.opts: project-specific packrat options.
- packrat/lib/: private package library for this project.
- packrat/src/: source packages used in this project.
- .Rprofile: fource R to use the private package library.


4. ### Install other packages
You can install the other packages as you normally do.
```
install.packages("packagename")
```

5. ### Install local source packages
```
packrat::set_opts(local.repos="path")
```

6. ### Track package use
```
packrat::snapshot()
```
Take a snapshot to save the changes in Packrat. When doing this, Packrat will automatically check the priviate package library for packages that have beed added, modified or removed in your code since 
the last snapshot was called.

```
packrat::status()
```
If you change your code and some packages are not needed, Packrat will tell you. 

```
packrat::clean()
```
If you no longer need those packages, you can remove them.

### Restore snapshots
You can install packags from the snapshot into your private library.
```
packrat::restore()
```

7. ### Bundle up the project
If you want to share your project with other people, you can bundle up it with Packrat
```
packrat::bundle()
```

8. ### Reproduce the analysis with the same packages
Copy the original packrat.lock file into the your new packrat folder and run `packrat::status` `packrat::restore`. Packrat will automatic download the same packages
with the same versions.
