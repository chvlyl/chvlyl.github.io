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

4\. The input data need to pass to placeholder by feed_dict. A placeholder is essentially a variable, which will take values later. Use dictionary to pass the values into the placeholder.

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
s = tf.log(16)
{% endhighlight python %}

6\. The weights can be stored in tf.Variable, which can be modified during training. 

{% highlight python %}
W = tf.Variable([1], tf.float32)
b = tf.Variable([0], tf.float32)
x = tf.placeholder(tf.float32)
linear_model = W * x + b
{% endhighlight python %}

However, unlike tf.constant, the variables are not initialized when tf.Variable is called. Therefore, one must explicitly initialize all the tf.Variable as following. 
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


### Lesson 17 Deep Neural Networks

1\. A simple one hidden layer neural network in Tensforflow. Use ReLU as the activation function.

{% highlight python %}
import tensorflow as tf

output = None
hidden_layer_weights = [
    [0.1, 0.2, 0.4],
    [0.4, 0.6, 0.6],
    [0.5, 0.9, 0.1],
    [0.8, 0.2, 0.8]]
out_weights = [
    [0.1, 0.6],
    [0.2, 0.1],
    [0.7, 0.9]]

weights = [
    tf.Variable(hidden_layer_weights),
    tf.Variable(out_weights)]
biases = [
    tf.Variable(tf.zeros(3)),
    tf.Variable(tf.zeros(2))]

features = tf.Variable([[1.0, 2.0, 3.0, 4.0], [-1.0, -2.0, -3.0, -4.0], [11.0, 12.0, 13.0, 14.0]])

hidden_layer = tf.add(tf.matmul(features, weights[0]), biases[0])
hidden_layer = tf.nn.relu(hidden_layer)

output = tf.add(tf.matmul(hidden_layer, weights[1]), biases[1])

with tf.Session() as sess:
    init = tf.global_variables_initializer()
    sess.run(init)
    pout = sess.run(output)
    print(pout)
{% endhighlight python %}


<br />

### Lesson 18 Deep Neural Networks in TensorFlow

1\. A simple example of neural network for MNIST data

{% highlight python %}
import tensorflow as tf

tf.reset_default_graph()

from tensorflow.examples.tutorials.mnist import input_data
mnist = input_data.read_data_sets(".", one_hot=True, reshape=False)


learning_rate = 0.001
training_epochs = 20
batch_size = 128
display_step = 1
n_input = 784  
n_classes = 10  
n_hidden_layer = 256

weights = {
    'hidden_layer': tf.Variable(tf.random_normal([n_input, n_hidden_layer])),
    'out': tf.Variable(tf.random_normal([n_hidden_layer, n_classes]))
}
biases = {
    'hidden_layer': tf.Variable(tf.random_normal([n_hidden_layer])),
    'out': tf.Variable(tf.random_normal([n_classes]))
}


x = tf.placeholder("float", [None, 28, 28, 1])
y = tf.placeholder("float", [None, n_classes])
x_flat = tf.reshape(x, [-1, n_input])


layer_1 = tf.add(tf.matmul(x_flat, weights['hidden_layer']),biases['hidden_layer'])
layer_1 = tf.nn.relu(layer_1)
logits = tf.add(tf.matmul(layer_1, weights['out']), biases['out'])

cost = tf.reduce_mean(tf.nn.softmax_cross_entropy_with_logits(logits=logits, labels=y))
optimizer = tf.train.GradientDescentOptimizer(learning_rate=learning_rate).minimize(cost)

correct_prediction = tf.equal(tf.argmax(logits, 1), tf.argmax(y, 1))
accuracy = tf.reduce_mean(tf.cast(correct_prediction, tf.float32))

### must be after the variables
save_file = './train_model.ckpt'
saver = tf.train.Saver()

init = tf.global_variables_initializer()
with tf.Session() as sess:
    ## saver.restore(sess, save_file)

    sess.run(init)
    for epoch in range(training_epochs):
        total_batch = int(mnist.train.num_examples/batch_size)
        for i in range(total_batch):
            batch_x, batch_y = mnist.train.next_batch(batch_size)
            sess.run(optimizer, feed_dict={x: batch_x, y: batch_y})
        if epoch % 2 == 0:
            valid_accuracy = sess.run(accuracy,
                feed_dict={
                    x: mnist.validation.images,
                    y: mnist.validation.labels})
            print('Epoch {:<3} - Validation Accuracy: {}'.format(epoch,valid_accuracy))

    saver.save(sess, save_file)
    print('Trained Model Saved.')
{% endhighlight python %}



2\. When save and load a trained model, it's better to explicitly name the tensorflow variables. Otherwise, tensorflow will automatically name each variable as variable_num and causes errors when load the model. 

{% highlight python %}
import tensorflow as tf

tf.reset_default_graph()

save_file = './train_model.ckpt'

# Two Tensor Variables: weights and bias
weights = tf.Variable(tf.truncated_normal([2, 3]), name='weights_0')
bias = tf.Variable(tf.truncated_normal([3]), name='bias_0')

saver = tf.train.Saver()

# Print the name of Weights and Bias
print('Save Weights: {}'.format(weights.name))
print('Save Bias: {}'.format(bias.name))

with tf.Session() as sess:
    sess.run(tf.global_variables_initializer())
    saver.save(sess, save_file)

# Remove the previous weights and bias
tf.reset_default_graph()

# Two Variables: weights and bias
bias = tf.Variable(tf.truncated_normal([3]), name='bias_0')
weights = tf.Variable(tf.truncated_normal([2, 3]) ,name='weights_0')

saver = tf.train.Saver()

# Print the name of Weights and Bias
print('Load Weights: {}'.format(weights.name))
print('Load Bias: {}'.format(bias.name))

with tf.Session() as sess:
    # Load the weights and bias - No Error
    saver.restore(sess, save_file)

print('Loaded Weights and Bias successfully.')
{% endhighlight python %}



3\. Deeper is better than wider:   
  * parameter efficiency
  * hierarchical structure



4\. Regulization:   
  * early termination by validation dataset performace
  * L2 penalty
  * Dropout: randomly set half of the activation to zero and scale the rest by 2. Only apply dropout during training but no in validation step.



5\. An example of dropout layer in tensorflow. Remember to set keep_prob = 1.0 during testing to use all units in the network.

{% highlight python %}
import tensorflow as tf

hidden_layer_weights = [
    [0.1, 0.2, 0.4],
    [0.4, 0.6, 0.6],
    [0.5, 0.9, 0.1],
    [0.8, 0.2, 0.8]]
out_weights = [
    [0.1, 0.6],
    [0.2, 0.1],
    [0.7, 0.9]]

weights = [
    tf.Variable(hidden_layer_weights),
    tf.Variable(out_weights)]
biases = [
    tf.Variable(tf.zeros(3)),
    tf.Variable(tf.zeros(2))]

features = tf.Variable([[0.0, 2.0, 3.0, 4.0], [0.1, 0.2, 0.3, 0.4], [11.0, 12.0, 13.0, 14.0]])

keep_prob = tf.placeholder(tf.float32) 
nn_l1 = tf.add(tf.matmul(features,weights[0]),biases[0])
nn_l1 = tf.nn.relu(nn_l1)
nn_l1 = tf.nn.dropout(nn_l1, keep_prob)
logits = tf.add(tf.matmul(nn_l1,weights[1]),biases[1])

init = tf.global_variables_initializer()
with tf.Session() as sess:
    sess.run(init)
    print(sess.run(logits,feed_dict={keep_prob: 0.5}))
{% endhighlight python %}

6\. Ignore colors in the color image by transforming color image into gray scale image (R+G+B)/3

7\. Weight shareing in neural network: set the same weight for two inputs if the two inputs contain the same subject.

8\. Convolution: 
    * A filter that scans the whole image. The weights are the same across different regions.  
    * Graduately increase the depth of the filter in the stack of the neural network. The depth should be roughtly the dimention of the internal structure of the problem.

9\. Stride: how much the filter slides. Larger stride will results in fewer patches and lower accuracy. 

10\. Filter depth: number of filters. Each filter will look for different features in the image. Filter depth is the number of neurons in the next layer.

11\. Padding: same padding is to add zeros to the outside regions of the image so that the output of the filter has the same size as the input. valid padding is to move filters without padding and drop the extra last columns in the image.

12\. Translation invariance: the weights in each filter are shared across patches. That is, the same filter is used to detect the same feature across different areas of the image. That is, it doesn't matter where the cat is in the image.

13\. Convolution layer in TensorFlow 

{% highlight python %}
import tensorflow as tf


k_output = 64

image_width = 10
image_height = 10
color_channels = 3

filter_size_width = 5
filter_size_height = 5

input = tf.placeholder(
    tf.float32,
    shape=[None, image_height, image_width, color_channels])

weight = tf.Variable(tf.truncated_normal(
    [filter_size_height, filter_size_width, color_channels, k_output]))
bias = tf.Variable(tf.zeros(k_output))
## TensorFlow uses a stride for each input dimension, [batch, input_height, input_width, input_channels]
conv_layer = tf.nn.conv2d(input, weight, strides=[1, 2, 2, 1], padding='SAME')
conv_layer = tf.nn.bias_add(conv_layer, bias)
conv_layer = tf.nn.relu(conv_layer)
{% endhighlight python %}


14\. Improvements of convolution 
  * Pooling: convolution lay +  pooling layer. It can decrease the output size of the output and thus reduces the number of parameters in following layers, which in turn prevents overfitting. Pooling causes information loss and is replaced by dropout.
  * 1x1 convolution
  * inception: combine different filters with 1x1 convolution.


15\. Example of CNN in Tensorflow 

{% highlight python %}
from tensorflow.examples.tutorials.mnist import input_data
mnist = input_data.read_data_sets(".", one_hot=True, reshape=False)

import tensorflow as tf

# Parameters
learning_rate = 0.00001
epochs = 10
batch_size = 128

# Number of samples to calculate validation and accuracy
# Decrease this if you're running out of memory to calculate accuracy
test_valid_size = 256

# Network Parameters
n_classes = 10  # MNIST total classes (0-9 digits)
dropout = 0.75  # Dropout, probability to keep units

# Store layers weight & bias
weights = {
    'wc1': tf.Variable(tf.random_normal([5, 5, 1, 32])),
    'wc2': tf.Variable(tf.random_normal([5, 5, 32, 64])),
    'wd1': tf.Variable(tf.random_normal([7*7*64, 1024])),
    'out': tf.Variable(tf.random_normal([1024, n_classes]))}

biases = {
    'bc1': tf.Variable(tf.random_normal([32])),
    'bc2': tf.Variable(tf.random_normal([64])),
    'bd1': tf.Variable(tf.random_normal([1024])),
    'out': tf.Variable(tf.random_normal([n_classes]))}

def conv2d(x, W, b, strides=1):
    x = tf.nn.conv2d(x, W, strides=[1, strides, strides, 1], padding='SAME')
    x = tf.nn.bias_add(x, b)
    return tf.nn.relu(x)

def maxpool2d(x, k=2):
    return tf.nn.max_pool(
        x,
        ksize=[1, k, k, 1],
        strides=[1, k, k, 1],
        padding='SAME')

def conv_net(x, weights, biases, dropout):
    # Layer 1 - 28*28*1 to 14*14*32
    conv1 = conv2d(x, weights['wc1'], biases['bc1'])
    conv1 = maxpool2d(conv1, k=2)

    # Layer 2 - 14*14*32 to 7*7*64
    conv2 = conv2d(conv1, weights['wc2'], biases['bc2'])
    conv2 = maxpool2d(conv2, k=2)

    # Fully connected layer - 7*7*64 to 1024
    fc1 = tf.reshape(conv2, [-1, weights['wd1'].get_shape().as_list()[0]])
    fc1 = tf.add(tf.matmul(fc1, weights['wd1']), biases['bd1'])
    fc1 = tf.nn.relu(fc1)
    fc1 = tf.nn.dropout(fc1, dropout)

    # Output Layer - class prediction - 1024 to 10
    out = tf.add(tf.matmul(fc1, weights['out']), biases['out'])
    return out

# tf Graph input
x = tf.placeholder(tf.float32, [None, 28, 28, 1])
y = tf.placeholder(tf.float32, [None, n_classes])
keep_prob = tf.placeholder(tf.float32)

# Model
logits = conv_net(x, weights, biases, keep_prob)

# Define loss and optimizer
cost = tf.reduce_mean(\
    tf.nn.softmax_cross_entropy_with_logits(logits=logits, labels=y))
optimizer = tf.train.GradientDescentOptimizer(learning_rate=learning_rate)\
    .minimize(cost)

# Accuracy
correct_pred = tf.equal(tf.argmax(logits, 1), tf.argmax(y, 1))
accuracy = tf.reduce_mean(tf.cast(correct_pred, tf.float32))

# Initializing the variables
init = tf. global_variables_initializer()

# Launch the graph
with tf.Session() as sess:
    sess.run(init)

    for epoch in range(epochs):
        for batch in range(mnist.train.num_examples//batch_size):
            batch_x, batch_y = mnist.train.next_batch(batch_size)
            sess.run(optimizer, feed_dict={
                x: batch_x,
                y: batch_y,
                keep_prob: dropout})

            # Calculate batch loss and accuracy
            loss = sess.run(cost, feed_dict={
                x: batch_x,
                y: batch_y,
                keep_prob: 1.})
            valid_acc = sess.run(accuracy, feed_dict={
                x: mnist.validation.images[:test_valid_size],
                y: mnist.validation.labels[:test_valid_size],
                keep_prob: 1.})

            print('Epoch {:>2}, Batch {:>3} -'
                  'Loss: {:>10.4f} Validation Accuracy: {:.6f}'.format(
                epoch + 1,
                batch + 1,
                loss,
                valid_acc))

    # Calculate Test Accuracy
    test_acc = sess.run(accuracy, feed_dict={
        x: mnist.test.images[:test_valid_size],
        y: mnist.test.labels[:test_valid_size],
        keep_prob: 1.})
    print('Testing Accuracy: {}'.format(test_acc))
{% endhighlight python %}



15\. 