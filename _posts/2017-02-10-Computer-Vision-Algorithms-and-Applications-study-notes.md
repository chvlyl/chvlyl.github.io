---
layout: post
title: "Computer Vision: Algorithms and Applications"
date: 2017-02-10
comments: true
categories: Machine-Learning
---

Here is my study notes for Computer Vision: Algorithms and Applications by Richard Szeliski. This book is freely avaiable at [the author's website](http://szeliski.org/Book/).


### Chapter 2: Image formation

<br /> 

1\. Pixel: it's a 2D point in an image and represented with a pair of values (x,y).

<br /> 

2\. 2D planar transformations   

  * Translation:   
  x' = x + t 

  * Rotation + translation: It is also known as 2D rigid body motion or 2D Euclidean transformation.  The Euclidean distances are preserved in this transformation.  
  x' = Rx + t

  * Scale rotation: It is also known as similarity transformation. The angles between lines are preserved.  
  x' = sRx + t,  
  Where s is the scale factor

  * Affine: This transformation keeps parallel lines as parallel.

  * Projective: This transformation keeps straight lines as straight.

<br /> 

### Chapter 3: Image processing

<br /> 

1\. Image compositing  
  
  * To composite a foreground image on a background image, one can use:   
  C = (1-a) Background + a Forground

<br /> 

2\. Histogram equalization  

  * This methond tries to adjust the gray level of each pixel so that the gray levels are uniformly distributed across all picels. That is, the histogram is flat.

<br /> 
### Chapter 5: Segmentation

<br /> 

1\. Active contours: the basical idea is to identify curves corresponding to object bundaries.

   * Three approaches to identify boundary curves: snakes, intelligent scissors and level set.

   * snakes: user rougly specifies a boundary and the algorithm evolves towards strong edges.

   * intelligent scissors: user rougly specifies a boundary and the algorithm computes a more accurate curve in real time.

   * level sets: the curve is defined by zero-crossing funtion 

<br /> 

2\. Split and merge: the basical idea is to split the image into pieces and then merge some pieces together.

   * Watershed: this algorithm identifies basins, which are the local minima. The boundaries are just the ridges where different regions meet. 

   * This algorithm can cause over-segmentation and therefore is often used with manually marked seed locations. The seed can be a simple line and it marks the centers of basins.  

<br /> 

3\. Mean shift and mode finding: use k-means or Gaussian mixture model to model the pixel intensity in order to find clusters in the distribution. The model can be parametric or non-parametric.

   * K-means clustering: need to pre-specify the clusters in the data.

   * Gaussian mixture model: need to pre-specify the number of components in the model. The cluster is softly assigned.

   * Mean shift: a non-parametric approach to identify peaks in the high-dimentional data without specifying the function explicitly. 
   This method uses kernel density estimation to find the modes or peaks of the distribution. The regions that climb to the same peak is then assigned to the same region. 

   * This is the inverse of watershed algorithm, which identify regions that belong to the same basin. 
   Usually, the method is applied to the joint domain of color and location, that is, combine the color values and locations.

<br /> 

4\. Sobel filter: it calculates an approximation of the gradient of the image intensity in order to detect the edges. The filter has one positive column, zero column and negative column. The ratio of the values in the positive and negative columns is 1:2:1.

+----+----+----+
| -1 |  0 |  1 |
+----+----+----+
| -2 |  0 |  2 |
+----+----+----+
| -1 |  0 |  1 |
+----+----+----+
