---
layout: post
title: "SIG interview"
date: 2016-02-08
---

### 2015-12
SIG总部在费城，主要做option market making。onsite面了7轮还是8轮，有点记不清了。我觉得比较有意思的题目如下：

第一个面试的是micheal, SIG的head of quantitative research。先问了我一堆关于covariance matrix的问题，如果A，B都是covariance matrices，A+B呢？A^2呢? AB呢？如果AB＝BA呢？然后给四个点（－1，－1），（－1，0），（1，0），（1，1），做regression，在不同的loss下，best fitted line是什么？然后是设计一个方法efficiently generate a random permutation of (1,…,n)。最后一个问题，3 events: A,B,C. A is independent of B, A is independent of C. Is A independent of intersection of B and C? 答案是not independent。

第二个人先打印了一些R code，然后问我这些code在干嘛。然后问了下SQL，各种join什么意思。再然后给了个increasing function f(x):[0,1] -> R，还有一个函数g(p) = E[f(X/N)], X~Binom(N,p)，问g()是不是increasing?怎么证明？之后搞了个covariance matrix，然后分四块，问我左上角那块是不是也是covariance matrix。


第三个。第一个问题是，考虑一个矩阵，取每列最大的，然后在这些数里面取最小的，这是第一个数。第二个数，先取每行最小的，再取这些数里最大的。问第一个数和第二个数哪个大？第二个是考虑一个game，10张牌，5红5黑，洗好，然后从第一张开始猜颜色，全部猜对算赢。求最优策略和赢的概率。

第五个面试官先问了一个问题，一个游戏，两个人猜一个城市的人口数，第一个人先给一个估计，第二个人判断是高了还是低了，然后去查实际数字，如果第二个人判断正确算赢。具体一点说就是第一个人估计假设是X_0+X_1，第二个人的估计是X_0+X_2，X_0是真值，X_1,X_2相互独立，服从uniform[-a,a]。问第二个人赢的概率是多少？答案是3/4。如果，第一个人可以说一个范围[Y-b,Y+b]而不是一个数，为了让这个游戏公平，b的值应该是多少？（b = \sqrt{2}-1）。这个问题实际上跟bid/ask spread有关。

第六轮来了两个人，technology team的。给一个array，怎么找中位数？我回答说，先排序，在找中间的值。问了下sorting algorithms的time complexity。然后接着问，如果这个array非常大，内存读不了，怎么办？下个问题是说估计exchange的数据传到SIG所需的时间，我们知道从exchange出来的时刻接受到数据的时刻。但是后一个时刻精确到minisecond, 前一个时刻只精确到microsecond，怎么估计办？之后在白板上写了python程序，关于binary search tree的find和insert。


还有一个有趣的问题，忘了谁问的了。现在我们有两种游戏，只能选一个而且只能玩一次：A: fixed reward $240; B: win $1,000 with prob 0.25, which one do you prefer? 当然是A啦。现在增加游戏B赢的概率，比如加到0.5，选哪个？游戏B吧。然后，改下条件A: fixed reward $24,000; B: win $100,000 with prob 0.5, which one do you prefer? A吧…现在我们把条件generalize一下，有两种游戏，A: fixed reward with F dollars; B: win R dollars with prob p, how do you make decision?
还有，已知E[X]=0, Var[X]=1,give an upper bound for Pr(|X|>1)? By Chebyshev’s inequality, Pr(|X|>1) <= 1. Construct an example to show this upper bound is tight.


### 2014-12
Interview
Applied through school, got a first round of phone screening, which was just basic question like why do you want to work here. After that there was a round of phone interview with questions on mostly probability and bits of game theory. After that there was another round of phone interview with more statistical questions.

### 2015-11
Interview
Probability, Statistics, Brainteasers. The process was fairly straightforward, I suppose I simply was not fast enough to answer all of the questions. Interviewer was very nice and all, resume overview then some math questions. I did not remember any question in particular. Know your probability brainteasers, for sure. Conditional probability and other sorts of math tricks will help


Interview
Got through to the second round of phone interviews. Standard probability (Baye's Thm, etc.) questions and Game theory stuff, but got tripped up on the last one (Options). First round had the torpedo and coin flipping questions. Second round had the nursery and count to 50 questions. Interviewer was very friendly.

The probability of three people have the birthday on the same day of a week?  

### 2014-03
Drawing a pair of (x, y) from a joint Gaussian distribution with 0 covariance. Knowing the stndard deviations of x and y and knowing z = x + y, what is your best guess for x?

z/2. Think about the 2 dimensional graph of joint density of (x, y). The condition x+y = z (here z is fixed) is a vertical plane. The intersection will be proportional to the conditional density. For any curve of such intersection, the highest point has x coordinate z/2.

Z sigma_x^2/ (sigma_x^2 + sigma_y^2). This is because X and Z are jointly normal and their covariance is equal to the variance of x. Therefore, the correlation coefficient is equal to sigma_x/sigma_z, and as E(X|Z)= rho. (sigma_x/sigma_z). Z, replacing the fact that the variance of the sum is the sum of the variance for independent (normal) R.V.s will give us the answer!

The answer is 0.5 EX - 0.5* EY + 0.5z (EX EY is not equal to zero)

### 2011-03
There is a piece of gold under the ground. It costs $K to dig it out, while the gold price varies. How you price it?  
It is a standard American Call option