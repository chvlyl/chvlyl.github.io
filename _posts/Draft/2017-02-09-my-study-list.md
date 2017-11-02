---
layout: post
title: "My study list"
date: 2017-02-09
comments: true
categories: Other
---

## Python




## Machine Learning

<br /> 
1\. [Machine Learning for Healthcare by David Sontag](http://people.csail.mit.edu/dsontag/courses/mlhc17/)

A MIT course about machine learning for healthcare. The slides can be downloaded from the course website.

<br /> 

2\. [Rules of Machine Learning:Best Practices for ML Engineering](http://martin.zinkevich.org/rules_of_ml/rules_of_ml.pdf)  

The post offers some very proctical suggestions about using machine learning to solve problems.
   
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

<br /> 

3\. [Deep Learning Research Review: Reinforcement Learning by Adit Deshpande](https://adeshpande3.github.io/adeshpande3.github.io/Deep-Learning-Research-Review-Week-2-Reinforcement-Learning)

<br />

4\. [Deep Learning Research Review: Generative Adversarial Nets by Adit Deshpande](http://www.kdnuggets.com/2016/10/deep-learning-research-review-generative-adversarial-networks.html)

<br />  


5\. [Deep learning (Nature 2015) by Yann LeCun, Yoshua Bengio & Geoffrey Hinton](http://www.nature.com/nature/journal/v521/n7553/pdf/nature14539.pdf)

<br />

6\. [Critique of Paper by "Deep Learning Conspiracy" ](http://people.idsia.ch/~juergen/deep-learning-conspiracy.html)

<br />

7\. [Deep Learning Gallery - a curated list of awesome deep learning projects](http://deeplearninggallery.com/)

<br />

8\. [AlphaGo Replication](https://github.com/Rochester-NRT/RocAlphaGo/wiki/01.-Home)

<br />

9\. [Oxford Deep NLP 2017 course](https://github.com/oxford-cs-deepnlp-2017/lectures)

Here is the syllabus from the course web site, quoted as below.
>
> * Introduction/Conclusion: Why neural networks for language and how this course fits into the wider fields of Natural Language Processing, Computational Linguistics, and Machine Learning.
> * Simple Recurrent Neural Networks: model definition; the backpropagation through time optimisation algorithm; small scale language modelling and text embedding.
> * Advanced Recurrent Neural Networks: Long Short Term Memory and Gated Recurrent Units; large scale language modeling, open vocabulary language modelling and morphology.
> * Scale: minibatching and GPU implementation issues.
> * Speech Recognition: Neural Networks for acoustic modelling and end-to-end speech models.
> * Sequence to Sequence Models: Generating from an embedding; attention mechanisms; Machine Translation; Image > * Caption generation.
> * Question Answering: QA tasks and paradigms; neural attention mechanisms and Memory Networks for QA.
> * Advanced Memory: Neural Turing Machine, Stacks and other structures.
> * Linguistic models: syntactic and seminatic parsing with recurrent networks.

<br />

10\. [CS 20SI: Tensorflow for Deep Learning Research](http://web.stanford.edu/class/cs20si/index.html)


<br /><br /> 

## Image Processing


<br /><br />  

## Natural Language Processing 



## Startup