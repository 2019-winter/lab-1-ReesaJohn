---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name: Reesa John
**PUT YOUR FULL NAME(S) HERE**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


1. Is there an easy way to move cells around after we have created them?
2. Can you code in 2 different languages in Jupyter?
3. Does Jupyter notbook allow you to revert to any checkpoint ever made?


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.

```python
#import
import numpy as np
import pandas as pd
```

## Exercise 1

Make an array `a` of size 6x4 where every element is a 2.

```python
# YOUR SOLUTION HERE
a=np.full((6,4),2)
print('this is my answer\n',a) 
```

## Exercise 2
Make an array `b` of size 6x4 that has a 3 on the leading diagonal and 1 everywhere else

```python
# YOUR SOLUTION HERE
b=np.full((6,4),1)
np.fill_diagonal(b,3)
print('this is my answer\n',b) 
```

## Exercise 3
Can you multiply these two matrices together? Why does `a*b` work but not `dot(a,b)`?

```python
print('this is my answer\n',a*b) 
# this will throw an error so I commented it out
#np.dot(a,b)
```

We can do `a*b` because it does elementwise multiplication like `a[r][c]*b[r][c]]`, so it would rely on both matrices possessing the same dimensions which is true of a and b, or one of the variables being a single number. However `dot(a,b)`, which returns the dot product between two arrays, is matrix multiplication in the case of 2d arrays. For the function to work for `a` and `b`, the number of columns of the first matrix needs to be equivalent for the number of rows in the second matrix, which is not true in this case.


## Exercise 4
Compute `dot(a.transpose(),b)` and `dot(a,b.transpose())`. Why are the results different shapes?

```python
print('this is my answer\n',np.dot(a.transpose(),b)) 
print('this is my answer\n',np.dot(a,b.transpose())) 
```

When we do matrix multiplication, the resulting matrix's dimensions contains the same number of rows as the first matrix and the same number of columns as the second matrix. When we transpose `a`, `a` becomes a 4x6 matrix multiplied to a 6x4 matrix, so the resulting matrix will be 4x4. But when we transpose `b`, `b` becomes a 6x4 matrix multiplied to a 4x6 matrix, so the resulting matrix will be a 6x6 matrix.


## Exercise 5
Write a function that prints some output on the screen and make sure you can run it in the programming environment that you are using.

```python
# YOUR SOLUTION HERE
```

## Exercise 6
Now write one that makes some random arrays and prints out their sums, the mean value, etc.

```python
# YOUR SOLUTION HERE
```

## Exercise 7
Write a function that consists of a set of loops that run through an array and count the number of ones in it. Do the same thing using the `where()` function.

```python
# YOUR SOLUTION HERE
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
## YOUR SOLUTION HERE
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
```

```python

```
