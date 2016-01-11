---
layout: post
title: "Linear regression y on x and x on y"
date: 2015-11-25
---


For two variables X and Y, is it equivalent to model their relation by either $$Y=\beta_1X+\epsilon_1$$ or $$X=\beta_2Y+\epsilon_2$$?  In the first model, we consider Y as the independent variable and X as the dependent variable. In the second model, we switch X and Y. 

The answer is no. 

For the first model $$Y=\beta_1X+\epsilon_1$$, the least square estimate is (in matrix form) $$\beta_1=(X^TX)^{-1}X^TY$$. However, for second model $$Y=\beta_2X+\epsilon_2$$, the least square estimate is   $$\beta_2=(Y^TY)^{-1}Y^TX$$. Generally, $$\beta_1$$ and $$\beta_2$$ are not the same. Intuitively, in the X-Y plot (Y is on the y-axis and X is on the x-axis), the least square estimate of model $$Y=\beta_1X+\epsilon_1$$ is to minimize the vertical distance (along y-axis) between the data and the fitted line. However, for the second model $$Y=\beta_2X+\epsilon_2$$, it minimizes the horizontal distance (along x-axis). Therfore, the estimates are not the same.

### Reference
1. [What is the difference between linear regression on y with x and x with y? on StackExchange](http://stats.stackexchange.com/questions/22718/what-is-the-difference-between-linear-regression-on-y-with-x-and-x-with-y)
