---
layout: post
title: "Do we need to scale the data before calculating the distance?"
date: 2015-03-20
---

I have been confused about this question for quite a long time. Because all the text books I read say that one MUST scale data before calculating the distance for PCA or clustering analysis. Is this true? The short answer is: it depends.

- If the variables or features are not comparable and measured in different units, then it is better to scale the data before calculating the distance.
For example, if we have two variables, height in inches and weight in pounds, we should scale the data before doing PCA or clustering. The reason is that the variable
weight has much larger scale than variable height and thus the distance will be dominated by the weight. That is, a relatively small change in weight will cause a dramatical change in distance, while even a relatively large change in height will not change the distance very much. Since the height and weight are not directly comparable, we can scale them and then compare them.

- It is also faster for gradient descent algorithm to converge if we scale the data.

- However, if the variables or features are comparable and measured in the same units, then we should not scale the data. For example, if we have two variables, arm length and leg length, both in meters, then we should not scale the data. Because arm length and leg length are comparable and scaling the data will distort the meaning of the data. Therefore, for this kind of data, we should not scale them and keep the original scale.
