---
layout: post
title: "Kernel and Reproducing Kernel Hilbert Space"
date: 2015-11-20
---


## Feature mapping and kernel function
In many classification problems, the data in the original feature space are not linearly separatable. For example, in a two dimentional feature space $$R^2$$, we have two features $$(X_1,X_2)$$. In this space, one group of data is distributed as a circle and the other group is distributed as a big circle outside the previous one. These two groups are not linearly separatable in the $$(X_1,X_2)$$ space.   

However, we can use feature engineering to map the two dimentional feature space $$R^2$$ into three dimentional feature space $$R^3$$. That is, we can create new features based on the original features. For example, we can map $$(X_1,X_2)$$ into $$(X_1^2,X_2^2,\sqrt2X_1X_2)$$. In other words, we now have a new three dimentional feature space $$R^3$$ as $$(Z_1,Z_2,Z_3)$$. The relation between the original features and new fetures is $$Z_1=X_1^2,Z_2=X_2^2,Z_3=\sqrt2X_1X_2$$. This process is called feature mapping $$\phi: R^2->R^3$$. After feature mapping, the two groups of data are now linearly separatable in the new feature space.  

Let's take a look at the inner product in the orignal feature space (I will call it X hereafter) and new feature space (H). Let's assume that there are two data points $$(X_1,X_2)$$,$$(X_1',X_2')$$ in the original two dimentional feature space $$R^2$$ (Since the original feature space is two dimentional, each data point has two elements such as $$X_1$$ and $$X_2$$ for the first data point. Recall that a point in the space can be considered as a point as well as a vector connecting that point and origin). After feature mapping, the two data points are now $$(Z_1,Z_2,Z_3)$$,$$(Z_1',Z_2',Z_3')$$ in the three dimentional feature space $$R^3$$ (Since the new feature space is three dimentional, each data point has three elements such as $$Z_1$$, $$Z_2$$ and $$Z_3$$ for the first data point). Now let's calculate the inner product in the **new feature space** (use <X,Y> to indicate inner product between X and Y):  
$$
<(Z_1,Z_2,Z_3),(Z'_1,Z'_2,Z'_3)>  \\
= <\phi(X_1,X_2),\phi(X_1',X_2')> \\
= <(X_1^2,X_2^2,\sqrt2X_1X_2),(X_1'^2,X_2'^2,\sqrt2X_1'X_2')>  \\
= X_1^2X_2^2+2X_1X_2X_1'X_2'+ X_1'^2X_2'^2   \\
= (X_1X_1'+X_2X_2')^2 \\
= (<(X_1,X_2),(X_1',X_2')>)^2
$$

As you can see, the inner product of two data points in the new feature space is just the **square** of the inner product of the two corresponding data points in the original feature space. In other words, if we want to map the data points from original space to the new space and calculate the inner product in the new space, we don't need to take all the troubles to do the feature mapping and inner product calculation. Instead, we can calculate the inner product in the original space and take the square without doing the feature mapping at all. Since the inner product in the new space is the function of that in the original space, we can define this as so-called kernel function:  
$$
\kappa(x,x') := <\phi(x),\phi(x')>\\
$$ 

In summary, kernel function is a function to calculate the inner product. But this inner product is not calculated in the original space, it is calculated in another space (but without doing actual feature mapping). That is, a function to calculate the innder product in some inner product space. Therefore, we don't need the inner product to be defined in the orignial space to calculate the kernel. If the original space are apples and oranges, how to calculate the inner product? We can map the apples and organges into their counts and then calculate the inner product.  

## Two fundamental questions
1. Given a feature mapping $$\phi$$, can we find is corresponding kernel function $$\kappa$$?  
2. Given a kernel function $$\kappa$$, can we find its corresponding feature mapping $$\phi$$ and consturct the feature space?  

## Gram matrix or kernel matrix
Given a function $$\kappa: R^d \times R^d->R$$ and data points $$X_1,X_2,\dots,X_m \in R^d$$, the Gram matrix, also called kernel matrix, is just a $$m \times m$$ matrix filled with $$\kappa(X_i,X_j)$$ for its i-th and j-th element.

$$K=
\begin{bmatrix}  
\kappa(X_1,X_1) & \dots & \kappa(X_1,X_m) \\ 
\dots & \ldots & \dots \\ 
\kappa(X_m,X_1) & \dots & \kappa(X_m,X_m)
\end{bmatrix}
$$

Note that the definition is of Gram matrix or kernel matrix for whatever function $$\kappa: R^d->R$$. We will use this definition along with positive semi-definite matrix to check if a funtion is a kernel function or if a kernel function is a valid one.

## Positive semi-definite matrix
A real symmetrix $$m \times m$$ matrix K satifying $$a^TKa \geq 0$$ for all $$a \in R^m$$ is called positive semi-definite matrix. For small matrix, we can use the definition to prove it is positive semi-definite or not. For large matrix, the calculation will be too cumbersome to do. Therefore, usually we use the eigenvalues to check if it is positive semi-definite or not. Note that a real symmetrix is positive semi-definite if and only if all its eigenvalues are non-negative. 

## Kernel function
If a function $$\kappa: R^d \times R^d->R$$ and for any set $$X_1,X_2,\dots,X_m \in R^d$$, its Gram or kernel matrix
$$K=
\begin{bmatrix}  
\kappa(X_1,X_1) & \dots & \kappa(X_1,X_m) \\ 
\dots & \ldots & \dots \\ 
\kappa(X_m,X_1) & \dots & \kappa(X_m,X_m)
\end{bmatrix}
$$

is positive semi-definite, then this functioin is $$\kappa$$ is called positive semi-definite kernel. Sometimes, in short, it is called kernel.  

The kernel function takes two variables as input, $$R^d \times R^d->R$$, and generate a value output in $$R$$. But not every function in this form is kernel function. Therefore, given a function in such form $$\kappa: R^d \times R^d->R$$, we want to know if it is a kernel functioin.  

In summary, in order to check if a function is a kernel, we need to make sure this function is positive semi-definite. We don't do this directly on the function itself. Instead, we transfer the function into its corresponding Gram or kernel matrix. Then we check if the Gram or kernel matrix is positive semi-definite or not.


## Function space
$$R^{R^d}$$ is the set of all functions from $$R^d$$ to $$R$$:   $$R^{R^d} = \{f:R^d->R\}$$. Note that $$R^{R^d}$$ the function maps data points in $$R^d$$ to  $$R$$. The elements in the function space are just all such functions.      

Use kernel function $$\kappa(x,z) = exp(-\frac{(x-z)^2}{2})$$ as an example:  
Let z=0, then $$\Phi_0(x) = \kappa(x,0) = exp(-\frac{x^2}{2}) \in R$$. This means, the kernel function $$\kappa(x,z)$$ maps the data point $$z=1$$ into a function  $$exp(-\frac{x^2}{2})$$.   
Similary, let z=1, then $$\Phi_1(x) = \kappa(x,1) = exp(-\frac{(x-1)^2}{2}) \in R$$.  

If we consider the second variable z in the function $$\kappa(x,z)$$ as the parameter, then for different parameters, we can have different functions. In other words, the kernel function can map each point in one space into a function in another space.  

## The reproducing kernel map
Suppose $$\kappa: R^d \times R^d->R$$ is a kernel. The producing kernel map is a map $$\Phi: R^{R^d}->R^d$$ such that $$\Phi(z)=\phi_z=\kappa(*,z)$$, that is $$\Phi(z)(x)=\phi_z(x)=\kappa(x,z)$$.  

Here, $$\Phi(z)$$ (consider $$\Phi(z)$$ as $$f$$) is a function that depends on z and this function takes x as input. We can write this function as $$\phi_z(x)$$. This is equivalent to kernel function $$\kappa(x,z)$$ with z as fixed.  

Again, this function just maps each point in one space into a function in another space (the new space is a function space because all the elements are functions). This mapping is defined by the kernel function with the second variable replaced by the point in the original space. 

## Fundamental question 2:
Give a kernel function, how to construct a feature space?  
1. Define a vector space based on the image of $$\Phi$$ ($$\Phi$$ can be defined by the kernel function).  
2. Define an inner product based on the vector space.
3. Show that $$\kappa(x,z)=<\Phi(x),\Phi(z)>$$.  

## Define a vector space  
As I mentioned before, given a kernel function, we can define a repdocuing kernel map. This map take points in original space into functions in a new function space. We can then take the linear combinations of those functions to construct a space. We can prove that, this function space is a vector space.  Here is the formal definition:  

Suppose  $$\kappa: R^d \times R^d->R$$ is a kernel and $$\Phi$$ is the corresponding reproducing kernel map. Let  
$$F_{\kappa}= \{f=\sum_i^m\alpha_i\Phi(x_i)|m \ in N, x_i,\dots,x_m \in R^d, \alpha_1,\dots,\alpha_m \ in R\}$$  
Then $$F_{\kappa}$$ is a vector space over R.  

$$\sum_i^m\alpha_i\Phi(x_i)$$ means taking the linear combinations of the functions after reproducing kernel mapping. Note that $$F_{\kappa}$$ depends on $$\kappa$$ because given different kernel functions, the repdocuing kernel maps are different. Therefore the constructed vector spaces are also different. 

## Define an inner product
Next, we want to define inner product in the vector space $$F_{\kappa}$$. Recall that the elements in the $$F_{\kappa}$$ space are functions. How to define inner product for functions?

Given two functions in the function space $$F_{\kappa}$$: $$f=\sum_i^m\alpha_i\Phi(x_i)$$ and $$g=\sum_j^{m'}\beta_j\Phi(x_j')$$,   
recall that $$f=\sum_i^m\alpha_i\kappa(*,x_i)$$ and $$g=\sum_j^{m'}\beta_j\kappa(*,x_j')$$.   

Define  inner product over R as:    
$$
<f,g> := \sum_i^m\sum_j^{m'}\alpha_i\beta_j\kappa(x_i,x_j')
$$

Here, we replace the functions $$\Phi(x_i)$$ and $$\Phi(x_j')$$ with their kernel functions $$\kappa(*,x_i)$$ and $$\kappa(*,x_j')$$. Then we define $$\alpha_i\kappa(*,x_i) \times \beta_j\kappa(*,x_j') = \alpha_i\beta_j\kappa(x_i,x_j')$$

## Reproducing property  
The inner product can be written as:  
$$
<f,g> = \sum_i^m\sum_j^{m'}\alpha_i\beta_j\kappa(x_i,x_j')\\
= \sum_i^m \alpha_i \sum_j^{m'}\beta_j\kappa(x_i,x_j')\\
= \sum_i^m \alpha_i g(x_j')\\
$$   
and  
$$
<f,g> = \sum_i^m\sum_j^{m'}\alpha_i\beta_j\kappa(x_i,x_j')\\
= \sum_j^{m'}\beta_j\sum_i^m\alpha_i\kappa(x_i,x_j')\\
= \sum_j^{m'}\beta_j f(x_i)\\
$$


Then if $$m'=1,\beta_j=1$$, then $$g=\sum_j^{m'}\beta_j\kappa(*,x_j')=\kappa(*,x_j')$$   
$$<\kappa(*,x),f> = f(x)$$  
if $$m=1,\alpha_i=1$$, then $$f=\sum_i^{m}\alpha_i\kappa(*,x_i)=\kappa(*,x_i)$$ 
$$<\kappa(*,x),\kappa(*,z)> = \kappa(z,x) = \kappa(x,z)$$

## Answer to fundamental question 2:
Given a kernel function, we can derive a mapping $$\Phi$$. Based on this mapping, we can define a function space $$F_{\kappa}$$. With inner product definition on the vector space $$F_{\kappa}$$, we can calculate the inner product $$<\Phi(x),\Phi(z)>$$. The inner product is just the value of the kernel function $$\kappa(x,z)$$:  
$$
\kappa(x,z) \\
= <\kappa(*,x),\kappa(*,z)>\\
= <\Phi(x),\Phi(z)>\\
$$



## Fundamental question 1
Given a feature mapping $$\Phi: R^d -> H$$, the corresponding kernel function can be defined as   
$$\kappa(x,z) = <\Phi(x),\Phi(z)>$$. We can prove that this function is positive semi-definite and thus a valid kernel function.  


## Spaces
- Vector space: space with definiton of additioin and scalar product.  
- Inner space: vector space with definition of inner product.  
- Metric space: space with definition of distance. 
- Complete space: space where the every Cauchy sequence is converged within the space.
- Hilbert space: real inner product space that is also a complete metric space with distance function defined by the inner product.  $$d(x,y)=\|x-y\|$$ where $$\|x\|=\sqrt{<x,x>}$$. 


## Reference
1. [Youtube: Reproducing Kernel Hilbert Space I: Basic Definitions](https://www.youtube.com/watch?v=MahJ9iwReAM)  

2. [Youtube: Reproducing Kernel Hilbert Space II: Theorems and Proofs](https://youtu.be/JqsfFi41VTQ)