---
layout: post
title: "Book: Python for Data Analysis"
date: 2015-11-21
---

Here is my reading note for the book "Python for Data Analysis" by Wes McKinney.

### Chapter 4: NumPy Basics:Arrays and Vectorized Computation

1. The NumPy ndarray is homogeneous, that is, all the elements must be the same type.

2. Every ndarray has **shape** and **dtype** attributes. data.shape and data.dtype.

3. Create ndarray by **np.array(data)**. Use **np.zeros(3,5)** to create a 3x5 matrix with zeros and np.ones() to create a matrix with ones. Use **np.eye(10)** to create an identify matrix.

4. Create a sequence of numbers (0 to 10) by np.arange(10).

5. The slicing of the ndarray will not copy the original array. Thus any modifications on the sliced array will be reflected in the source array. 
  
```
arr_slice = arr[5:8]
arr_slice[:] = 1
```

The change on arr_slice will also change arr.

6. Use comma-separated list of indices to select element from two-dimensional array, arr2d[0,2].

7. Reshape an array: arr.reshape((3,5)). Transpose: arr.T

#### Chapter 5: Getting Started with Pandas

1. Series: one-dimentional array with index. ser.values and ser.index to get its values and index.

2. Compared to the NumPy array, one can use values in the index to select the values in the series. ser['a'].

3. One can create a series from Python dict. The keys (in the sorted order) will be the index. Series(dict).

4. Create the DataFrame with dict of equal-length lists or NumPy arrays.

5. Select a column in DataFrame by frame['col'] or frame.col.  Select a row by frame.ix['row'] 

6. Use reindex to change the order of the data.

### Chapter 6: Data Loading, Storage, and File Formats

1. Read a file into DataFrame: pd.read_csv or pd.read_table

2. Write DataFrame into a file:data.to_csv

### Chapter 7: Data Wrangling: Clean, Transform, Merge, Reshape.

1. Merge DataFrame by pd.merge(df1,df2).
