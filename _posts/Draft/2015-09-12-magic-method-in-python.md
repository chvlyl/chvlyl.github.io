---
layout: post
title: "Magic methods in Python"
date: 2015-09-12
---

In Python, there are some variables/methods with double underscores, for example, __name__ and __init__. Sometings, they are called magic variables/methods. They are created by the core Python team for their own protocols. So never created these variables and methods for your own use. That is, you can use them in your code, but do not create new ones by yourself. Here are some common magic variables/methods.   

### __name__
- If .py file is executed directly，__name__ will be set as __main__.
- If .py file is imported，then __name__ is the name of the .py file.

So if we write the .py like following:
```
## some functions here
if __name__=='__main__':
    ## run some test
```
Then, if we import this .py file, the code inside the if statement will not be executed, because __name__ is the name of the .py file. But if we run this .py file directly, the test code inside the if statment will run, because __name__ is now "__main__". Therefore, we can put the test code in the if statement with __name__.

### __init__
This is the constructor to initilize an object. 


### __doc__
The documentation for modules, classes and functions. For example:
```
#file.py
"""
file's doc
"""
class someclass(object):
    """
    class's doc
    """
    pass
def somefunction():
    """
    function's doc
    """
    pass
```
If we run
```
print __doc__
print someclass.__doc__
print somefunction.__doc__
```
we will get
```
script's doc
class's doc
function's doc
```

### __call__
If an object has the __call__() function，then this object can be called as a function.
```
class someclass(object):
    def __init__(self):
        pass
    def funcion(self):
        pass
    def __call__(self):
        return self
```
```
test=someclass()
# we can use test as a function
test()
```