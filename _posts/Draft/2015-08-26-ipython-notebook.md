---
layout: post
title: "IPython Notebook"
date: 2015-08-26
---


## Install Anaconda  
Anaconda includes a large collection of popular Python packages for scientific computing. It can be download [here](http://continuum.io/downloads). IPython and IPython Notebook have been already included in the Anaconda distribution. So you don't need to install IPython after Anaconda is installed.

You can install packages from Anaconda.org:  

~~~
conda install -c packagename
~~~

If you want to install packages from non-Anaconda, you can use pip, which is also included in Anaconda:

~~~
pip install packagename
~~~

## Use R in IPython Notebook
First, you need to install the R kernel:

~~~
conda install -c r r-irkernel
~~~

Then, run the IPython Notebook server:

~~~
ipython notebook
~~~

In IPython notebook, you can create a R notebook.


