---
layout: post
title: "Use Python for machine learing"
date: 2016-01-22
---

1. IPython
2. Pandas
3. Scikit-learn


## Install IPython, Pandas, Scikit-learn
Anaconda includes IPython, Pandas, Scikit-learn as well as other useful python packages. Download it from [here](https://www.continuum.io/downloads) and install it.


## IPython
1. Run "ipython notebook" in the termianl to run IPython Notebook. IPython Notebook is the computing environment using markdown syntax.

2. In IPython Notebook, use tab for auto completion. Use shift+tab to get information about the function. 

## Numpy
1. Create a numpy.array

~~~
import numpy as np
np.array()
~~~

## Pandas
Pandas is very useful Python package for data.

1. Load pandas
```
import pandas as pd
```

2. Read files
```
data = pd.read_csv(filename,index_col=0)
```
Note that the index in python start at 0

3. Head and tail

~~~
data.head()
data.tail()
~~~


4. Summary of the data
```
data.descript()
```

5. Shape
```
data.shape()
```

6. Subset columns

~~~
data['var1']
data[['var1','var2','var3']]
~~~
Note that if you want to subset more than one columns, the column names must be in an list.

7. Filter rows
```
data.loc['labelname']
```

8. Count by values
```
data.value_count
```


## Skikit-learn

1. Load built-in dataset

~~~
from sklearn.datasets import load_iris
iris = load_iris()
type(iris)
~~~

Note the type of iris is "bunch", which is a bundle of data and attributes. 

```iris.data```: the data
```iris.feature_names```: feature names, which are the column names
```iris.target```: target, which are the outcome labels in integers
```iris.target_names```: target, which are the outcome labels in strings

The sciki-learn has serveral requirements on the input data:
-. The features and response variable must be in two separate variables. For example, iris.data and iris.target
-. The features and response variable must be numeric. Therefore, we can only use iris.target but not iris.target_names in sciki-learn
-. The features and response variable must be numpy.ndarray (numpy) or DataFrame (pandas).  Use type() to check the data type
-. The features must have two dimentions and reponse variable must have one dimention. The first dimention of these two must meach. Use data.shape() to check the data dimentions.


2. K-nearest neighbor
All the machine learning methods in scikit-learn have a four-step modeling pattern.

<1>. Import the class that has the machine learning method you want to use 
```
from sklearn.neighbors import KNeighborsClassifier
```

<2>. Create an instance of the class that you just imported. When create the instance, the paramters can be speficied. 
```
knn = KNeighborsClassfier(n_neighbors=10)
```

<3>. Fit the model on the data
```
knn.fit(x,y)
```

<4>. Predict the response variable for the new data set with the model that just trained.
```
knn.predict(new_x)
```

3. Other models

Linear regression

~~~
from skleanr.linear_model import LinearRegression
lnreg = LinearRegression()
lnreg.fit(x,y)

linreg.intercept_
linreg.coef_
~~~
Note that in sciki-learn, the estimated parameters are labelled with the underscore.

Logistic regression

~~~
from sklearn.linear_model import LogisticRegression
logreg = LogisticRegression()
~~~

4. Model evaluation

~~~
from sklearn import metrics
metrics.accuracy_score(y,y_pred)
metrics.mean_absolute_error(y,y_pred)
metrics.mean_squared_error(y,y_pred)
~~~


~~~
metrics.confusion_matrix(y_test,y_pred)
metrics.recall_score(y_test,y_pred)
metrics.precision_score(y_test,y_pred)
~~~



5. Split data into traning and testing set

~~~
from sklearn.cross_validation import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.4,random_state=10)
~~~

6. Cross validation

~~~
from sklearn.cross_validation import cross_val_score
knn = KNeighborsClassifier(n_neighbors=5)
scores = cross_val_score(knn,x,y,cv=10,scoring='accuracy')
scores.mean()
~~~
Note that cross_val_score() returns the prediction score for each split iteration.


7. Grid search
It uses the k-fold cross-validation method to search for the best parameter across a grid of parameters.

~~~
from sklearn.grid_search import GridSearchCV
k_range = range(1,20)
param_grid = dict(n_neighbors=k_range)
grid = GridSearchCV(knn,param_grid,cv=20,scoring='accuracy')
grid.fit(x,y)
grid.grid_scores_
grid.best_score_
grid.best_params_
grid_best_estimator_
grid.predict(x_new,y_new)
~~~

Note that the dict(n_neighbors=k_range) is to map the parameter values range(1,20) to the name n_neighbors. grid.predict() will automatically use the best model for prediction.



## Matplotlib

1. Import matplotlib

~~~
import matplotlib.pyplot as plt
%matplotlib inline
~~~

The last line ```%matplotlib inline``` is to allow the plots to show up in the ipython notebook


2. Simple plot

~~~
plt.plot(x,y)
plt.xlabel('xlabel')
plt.ylabel('ylabel')
~~~

3. Histogram

```
plt.hist(y,bins=10)
```



## Seaborn

1. Import seaborn

~~~
import seaborn as sns
%matplotlib inline
~~~

2. Pairplot
```
sns.pairplot(data,x_vars=['v1','v2','v3'],y_vars='v4',size=7,aspect=0.5)
```
