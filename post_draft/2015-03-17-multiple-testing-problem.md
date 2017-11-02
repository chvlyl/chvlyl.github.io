---
layout: post
title: "Multiple testing problem and false discovery rate control"
date: 2015-03-09
---

## What is multiple testing problem?
I found one interesting comic from XKCD about [Multiple testing problem](http://imgs.xkcd.com/comics/significant.png)

Basically, the comic says that the scientists want to test the association
between jelly beans and acne with some test. In each test, they control 
the false positive rate at 0.05 level. However, after they repeate the test
20 times, they find one positive but they can not reproduce it in another
experiment. Clearly, this result is actually a false positive.
The reason is that if we control the false postive rate for 
each test at 0.05 level, the overall false positive rate is actually 
$$1-(1-0.05)^{20}=0.64$$ for 20 tests. That is, the overall false positive rate
 is 0.61 even if we control false positive rate for each test at 0.05 level. 

Here are some examples from [Wiki](http://en.wikipedia.org/wiki/Multiple_comparisons_problem):
  
>Suppose the treatment is a new way of teaching writing to students, and the control is the standard way of teaching writing. Students in the two groups can be compared in terms of grammar, spelling, organization, content, and so on. As more attributes are compared, it becomes more likely that the treatment and control groups will appear to differ on at least one attribute by random chance alone.

>Suppose we consider the efficacy of a drug in terms of the reduction of any one of a number of disease symptoms. As more symptoms are considered, it becomes more likely that the drug will appear to be an improvement over existing drugs in terms of at least one symptom.

>Suppose we consider the safety of a drug in terms of the occurrences of different types of side effects. As more types of side effects are considered, it becomes more likely that the new drug will appear to be less safe than existing drugs in terms of at least one side effect.

That is, as the number of comparisons increases, we will eventually find the groups being compared to be different at one attribute. 


## How to control the overall false positive rate?
A natural solution is that we control the false positive rate for each test 
at $$\alpha$$ level so that the overall false postive rate is $$1-(1-\alpha)^n<0.05$$
