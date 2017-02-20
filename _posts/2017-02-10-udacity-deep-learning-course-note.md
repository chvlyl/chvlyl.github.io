---
layout: post
title: "Udacity deep learning course study notes"
date: 2017-02-10
comments: true
categories: Machine-Learning
---





### Lesson 15 MiniFlow

1\. Computation graph: Nodes are mathematical functions and edges are weights. Nodes take input (except input layer) and generate output.

2\. Neural networks can be defined by computation graphs. First, one need to define the nodes and edges in the graph. Then, calculation of the neural network is just to propagate values through the graph.

3\. Topological sort: Flatten and sort the graph so that the dependencies between nodes are known. 

<br />

### Lesson 16 Intro to TensorFlow

1\. Install TensorFlow

{% highlight python %}
conda install -c conda-forge tensorflow
{% endhighlight %}

2\. TensorFlow stores the data in tensors, which can be integers, floats, or strings. The tensor can be multidimensional. 


{% highlight python %}
X = tf.constant(1) 
Y = tf.constant([ [1,2,3] ]) 
Z = tf.constant([ [1,2,3], [4,5,6] ])
{% endhighlight %}

3\. TensorFlow uses sesstion to run the computational graph. For example, the following code creates a TensorFlow session and evaluates it.

{% highlight python %}
hello_constant = tf.constant(1) 
with tf.Session() as sess:
    output = sess.run(hello_constant)
{% endhighlight %}

4\. The input data need to pass to placeholder by feed_dict.

{% highlight python %}
input_data = tf.placeholder(tf.float32)

with tf.Session() as sess:
    output = sess.run(input_data, feed_dict={input_data: 45.67})
{% endhighlight python %}

5\. Math

{% highlight python %}
x = tf.add(1, 2)
y = tf.sub(1, 2) 
z = tf.mul(1, 2)  
p = tf.div(1, 2)
r = tf.reduce_sum([1,2,3,4,5])
s = ()tf.log(16)
{% endhighlight python %}

6\. The weights can be stored in tf.Variable, which can be modified during training. The following code initialize all the tf.Variable.


{% highlight python %}
init = tf.global_variables_initializer()
with tf.Session() as sess:
    sess.run(init)
{% endhighlight python %}

Or one can manually set the initialized values by tf.truncated_normal, which will randomly generate weights from a normal distribution but with max value less than 2 sd.

{% highlight python %}
n_features = 120
n_labels = 5
weights = tf.Variable(tf.truncated_normal((n_features, n_labels)))
{% endhighlight python %}

7\. The softmax function can be calculated with tf.nn.softmax


{% highlight python %}
x = tf.nn.softmax([2.0, 1.0, 0.2])
{% endhighlight python %}

8\. Before training the model, one need to normalize inputs (zero mean and equal variance) and Initialize weights (randomly sample from normal distribution).  

9\. Tricks for SGD: momentum (running average) and learning rate decay. Plot the loss vs. steps and use it to choose better learning rate. Use ADAGRAD, which is less sensitive to initial learning rate, learning rate decay and momentum.

10\. Save the processed data into pickle file

{% highlight python %}
# Save the data for easy access
pickle_file = 'file.pickle'
if not os.path.isfile(pickle_file):
    print('Saving data to pickle file...')
    try:
        with open('file.pickle', 'wb') as pfile:
            pickle.dump(
                {
                    'train_dataset': train_features,
                    'train_labels': train_labels,
                    'valid_dataset': valid_features,
                    'valid_labels': valid_labels,
                    'test_dataset': test_features,
                    'test_labels': test_labels,
                },
                pfile, pickle.HIGHEST_PROTOCOL)
    except Exception as e:
        print('Unable to save data to', pickle_file, ':', e)
        raise

print('Data cached in pickle file.')
{% endhighlight python %}




{% highlight python %}
import pickle

# Reload the data
pickle_file = 'file.pickle'
with open(pickle_file, 'rb') as f:
  pickle_data = pickle.load(f)
  train_features = pickle_data['train_dataset']
  train_labels = pickle_data['train_labels']
  valid_features = pickle_data['valid_dataset']
  valid_labels = pickle_data['valid_labels']
  test_features = pickle_data['test_dataset']
  test_labels = pickle_data['test_labels']
  del pickle_data  # Free up memory

print('Data and modules loaded.')
{% endhighlight python %}

<br />