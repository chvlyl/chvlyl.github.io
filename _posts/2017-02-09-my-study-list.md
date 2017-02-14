---
layout: post
title: "My study list"
date: 2017-02-09
comments: true
categories: Other
---

## Python




## Machine Learning
   
   
<br /><br />  

## Deep Learning

<br />
   

1\. [Deep Learning, NLP, and Representations by Christopher Olah](http://colah.github.io/posts/2014-07-NLP-RNNs-Representations/)

This is a great post covering deep learning in NLP. 
    
<br />
   
2\. [Deep Learning Research Review: Natural Language Processing by Adit Deshpande](https://adeshpande3.github.io/adeshpande3.github.io/Deep-Learning-Research-Review-Week-3-Natural-Language-Processing)

This is a general introduction aritle about natural language processing and the application of deep learning in this field. 

* Word vector: each word is represented by a vector, which can represent the meaning, context and semantics of the word. The vector can be constructed from co-occurrence matrix. 

* Co-occurrence matrix: this matrix is similar to covariance matrix. Rows and columns are the words in the documents and the values are the counts of how many times two words show up togeter in the sentence. Two words with similar vector values represent similar meaning. However, if the number of unique words in the documents is large, the dimension of co-occurrence matrix would be huge.

* Word2Vec: this method tries to form the problem as following: for a given word (center word), we build a model to predict the next word. This model is naive bayes model, which model the conditional probability. Then Word2Vec essentialy a method to find the vector representations with different words that maximize the conditional probability.

* RNN (Recurrent Neural Networks): each hidden node not only takes the word vector as input but also the hidden state vector from the previous time. i.e, there are recurrent weight matrices, which are the same across all time points. RNN has gradient vanishing problem.

* GRUs (Gated Recurrent Units): this model introduce three different gates, thus three different recurrent weight matrices. They are update gate, reset gate, and new memory container.The update gate controls how much information in the previous hidden state can go through. The reset gate controls if model should drop information if that information is not usefull in the future. 

* LSTMs (Long Short Term Memory Units)

<br /><br />  

3\. [Deep Learning Research Review: Reinforcement Learning by Adit Deshpande](https://adeshpande3.github.io/adeshpande3.github.io/Deep-Learning-Research-Review-Week-2-Reinforcement-Learning)

<br /><br />   

4\. [Deep Learning Research Review: Generative Adversarial Nets by Adit Deshpande](http://www.kdnuggets.com/2016/10/deep-learning-research-review-generative-adversarial-networks.html)

<br /><br />    


5\. [Deep learning (Nature 2015) by Yann LeCun, Yoshua Bengio & Geoffrey Hinton](http://www.nature.com/nature/journal/v521/n7553/pdf/nature14539.pdf)

<br /><br /> 

6\. [Critique of Paper by "Deep Learning Conspiracy" ](http://people.idsia.ch/~juergen/deep-learning-conspiracy.html)

<br /><br /> 


## Image Processing


<br /><br />  

## Natural Language Processing 



## Startup