---
layout: post
title: "Python tips"
date: 2017-02-10
comments: true
categories: Programming
---


1\.  Iterate over rows in a Pandas DataFrame  
{% highlight python %}
import pandas as pd
for index, row in df.iterrows():
	print index, row
{% endhighlight %}  





2\. Round numbers in a Pandas DataFrame  
* Same decimals to all columns
    {% highlight python %}
df.round(2)
    {% endhighlight %}
* Different decimals to some columns
    {% highlight python %}
df.round({'Column_A': 1, 'Column_B': 2})
    {% endhighlight %}


3\. Add X or Y label in Matplotlib
{% highlight python %}
plt.plot(x, y)
plt.title('Title')
plt.xlim(0, 1)

plt.xlabel('xlab')
plt.ylabel('ylab')

plt.show()
{% endhighlight %}



4\. Add annotation in plots with Matplotlib

We can use `plt.annotation` in Matplotlib to add annotation to the plot. Assume we have a Pandas DataFrame with two columns var_x, var_y. The index of the DataFrame is the label.

{% highlight python %}
for idx,row in df.iterrows():
    x = row.var_x
    y = row.var_y
    plt.annotate(
        idx,
        xy=(x, y), xytext=(-10, 10),
        textcoords='offset points', ha='right', va='bottom',
        bbox=dict(boxstyle='round,pad=0.5', fc='yellow', alpha=0.5),
        arrowprops=dict(arrowstyle = '->', connectionstyle='arc3,rad=0'))
plt.show()
{% endhighlight %}

In the above code, idx is the label. xy=(x,y) are the coordinates of the points and xytext are the relative coordinates of the label. bbox is to add a box around the label and corresponding parameters control the properties of the box. arrowprops is to connect the label and the point with an arrow. Similarly, the parameters control the properties of the arrow. 

See [Matplotlib API](http://matplotlib.org/api/pyplot_api.html#matplotlib.pyplot.annotate) and [examples](http://matplotlib.org/examples/pylab_examples/annotation_demo2.html)