---
layout: post
title: "Multiple testing problem and false discovery rate control"
date: 2015-03-09
---

## What is multiple testing problem?
I found this interesting comic from XKCD:

![Multiple testing problem](http://imgs.xkcd.com/comics/significant.png)

Basically, the comic says that the scientists want to test the association
between jelly beans and acne with some test. In each test, they control 
the false positive rate at 0.05 level. However, after they repeate the test
20 times, they find one positive but they can not reproduce it in another
repeated experiment. Clearly, this one positive is actually a false positive.
The reason is that if we control the false postive rate for 
each test at 0.05 level, the overall false positive rate is actually 
$$1-(1-0.05)^20=0.64$$ for 20 tests. That is, the overall false positive rate
 is 0.61 even if we control false positive rate for each test at 0.05 level. 

Here is another example to illustrate this multiple testing problem. 
Suppose that  

## How to control the overall false positive rate?
A natural solution is that we control the false positive rate for each test 
at $$\alpha$$ level so that the overall false postive rate is $$1-(1-\alpha)^n<0.05$$
