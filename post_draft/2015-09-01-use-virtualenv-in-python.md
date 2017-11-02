---
layout: post
title: "Use virtualenv in Python"
date: 2015-09-01
---



Virtualenv is a package to create isolated Python environments. So you can use different python environments for each project.  

> The basic problem being addressed is one of dependencies and versions, and indirectly permissions. Imagine you have an application that needs version 1 of LibFoo, but another application requires version 2. How can you use both these applications? If you install everything into /usr/lib/python2.7/site-packages (or whatever your platform's standard location is), it's easy to end up in a situation where you unintentionally upgrade an application that shouldn't be upgraded.

### -- Install virtualent
```python
sudo pip install virtualenv
```

### -- Create a Python environment
```python
mkdir new_project
virtualenv --distribute new_project
```

The --distribute is to use distribute package system instead of setuptools. It will install pip in the new virtual environment.  The new_project folder has its own Python and pip in it. All the packages installed globally are also available to the virtualenv environment.


### -- Activate the virtualenv
```python
cd new_project
source bin/activate
```

Use deactivate to exit the environment.

### -- Python style guide
[PEP 0008 Python coding style](https://www.python.org/dev/peps/pep-0008/)



### -- Reference
1. The above content was summarized from http://mirnazim.org/writings/python-ecosystem-introduction/