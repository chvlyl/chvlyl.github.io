---
layout: post
title: "Python tips"
date: 2017-02-10
comments: true
categories: Programming
---

1.  Iterate over rows in a Pandas DataFrame  
{% highlight python %}
import pandas as pd
for index, row in df.iterrows():
	print index, row
{% endhighlight %}
