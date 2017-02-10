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