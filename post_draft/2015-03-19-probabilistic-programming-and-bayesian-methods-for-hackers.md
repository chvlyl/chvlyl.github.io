---
layout: post
title: "Book: Probabilistic Programming and Bayesian Methods for Hackers"
date: 2015-03-19
---

I found [this book](https://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/). It covers the Bayesian methods
 and very easy to understand without math background. I like the examples in this book.  

#### Chapter 1: Basics about Bayesian methods.  
- Bayesian methods = prior knowledge + data (evidence). The data can wash away the prior knowledge.
- Use PyMC for Bayesian analysis in Python.  
- It is OK if the posterior distribution does not look like the prior distribution for the parameter
 (if we use MCMC rather than analytical distribution).  
- Find the change point for count data: assume two poisson distribution with different means before and after time point t. 

#### Chapter 2: PyMC  
- A good starting point to modeling is to think about `how you generate the data`.  
  - What is the best distribution to describe the data? Poisson? Normal?  
  - What are the parameters in the distribution and do we know the values?  
  - Give priors to the unknown parameters.  
- Godness of fit: compare observed data with model prediction. If the data is statistically different from the model prediction, then
the model does not accurately fit the data. 

#### Chapter 3: MCMC  
- N unknowns parameters will define an N dimensional space for the probability distribution. The surface or curve that on top of the space 
is the probability of a specific point.   
  - For example, if there are two unknown parameters, p_1 and p_2 ~ U(0,5), then the space is a square of length 5 and the surface is just
a plane on the top of the square. The volumn of the whole space is 1.  
- After we incorporate the data, the space of prior distribution on unknowns does not change, but the surface of the space is changed. 
The resulting surface is the posterior distribution.  
- The curse of dimensionality: it is very difficult to search the high dimensional space.   
- MCMC: sample the posterior distribution. It explores the nearby positions and moves into areas with higher probability.  
- Algorithms for MCMC: most of them are as follows:
1. Start at current position.  
2. Propose moving to a new positoin.  
3. Accept/Rejct the new position.  
4. If accept, move to the new position. If rejct, do not move.
5. Iterate and return all accepted posisions (trace).  
- Covergence in MCMC algorithm: the traces converge, not to a single point, but to a distribution of possible points.     
- The traces appear as a random walk in the apce.  
- Autocorrelation: correlation of two time points. If I know the position of the series at time s, can it help me know where I cam at time t.
- MCMC algoritm regurns samples that exhibit autocorrelation.  
- If a prior distribution assigns 0 probability to the unknown parameter, the posterior will also assign 0 probability. Therefore the prior must 
contain the true parameter.  

#### Chapter 4: Theorem
- The law of large numbers: the average of a sequence of random variable from the same distribution coverges to the expected value of that distribution.  


#### Chapter 5: Loss function  
- Squared-error loss function: put too much weight on large outliers. 
- Absolute-error loss function
- Asymmetric squared-error loss function.  
- Loss functions are objective.  
- Bayesian loss function: E[L(theta,theta.hat)]. Use Law of Large Numbers to approciate the expectation.  


#### Chapter 6: How to choose a prior
- Bayesian methods: prior distribution with hyperparameters
- Empirical Bayes: use data to get the prior
- Wishart distribution: is a distribution over all positive semi-definite matrices.


 
