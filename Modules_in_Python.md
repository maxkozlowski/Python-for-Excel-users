# Modules

## What are modules?

Modules are sets of codes that you can easily access and reuse. They are simply files containing definitions and statements. The [official Python website](https://docs.python.org/3/tutorial/modules.html) describes modules as follows.
>If you quit from the Python interpreter and enter it again, the definitions you have made (functions and variables) are lost. Therefore, if you want to write a somewhat longer program, you are better off using a text editor to prepare the input for the interpreter and running it with that file as input instead. This is known as creating a script. As your program gets longer, you may want to split it into several files for easier maintenance. You may also want to use a handy function that you’ve written in several programs without copying its definition into each program.

>To support this, Python has a way to put definitions in a file and use them in a script or in an interactive instance of the interpreter. Such a file is called a module; definitions from a module can be imported into other modules or into the main module (the collection of variables that you have access to in a script executed at the top level and in calculator mode).

## Useful modules

Python provides many great modules for dealing with data. Depending on what project you are working on, you are very likely to be using some of the modules below.

| Module type  | Module name |
| ------------- | ------------- |
| Data wrangling  | Pandas  |
| Data wrangling  | NumPy  |
| Data wrangling  | SciPy  |
| Charting  | Matplotlib  |
| Charting  | Seaborn  |
| Charting  | Bokeh  |
| Charting  | Plotly  |
| Machine Learning  | Statsmodels  |
| Machine learning / Deep learning | Scikit-Learn  |
| Deep learning | TensorFlow  |
| Deep learning | Keras  |
| Deep learning | Theano  |

Because in this course we are focusing on data processing, we will not be going through charting or machine learning. For data processing, the most common modules used are Pandas and NumPy. When replacing Excel tasks, particularly Pandas proves to be very useful.

#### Pandas

From [Pandas website](http://pandas.pydata.org/pandas-docs/stable/)
>Pandas is a Python package providing fast, flexible, and expressive data structures designed to make working with “relational” or “labeled” data both easy and intuitive. It aims to be the fundamental high-level building block for doing practical, real world data analysis in Python. Additionally, it has the broader goal of becoming the most powerful and flexible open source data analysis / manipulation tool available in any language. It is already well on its way toward this goal.

>Pandas is well suited for many different kinds of data:
>- Tabular data with heterogeneously-typed columns, as in an SQL table or Excel spreadsheet
>- Ordered and unordered (not necessarily fixed-frequency) time series data.
>- Arbitrary matrix data (homogeneously typed or heterogeneous) with row and column labels
>- Any other form of observational / statistical data sets. The data actually need not be labeled at all to be placed into a pandas data structure

Pandas works very well with Excel data. It can easily import and export data from/to Excel. The logic of tables is also quite analogical to Excel. The only difference is that in Pandas you wil be working with tables rather than spreadsheets. For example, in one Excel spreadsheet you could have 3, 4 or more tabes. In Pandas you will have 3 or 4 different objects, each one containing one table.


#### NumPy

From [Wikipedia](https://en.wikipedia.org/wiki/NumPy)
>NumPy is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

While Pandas provides nice and analogical to Excel logic and structure of data, NumPy will be typically used when you need to create some scientific numbers such as pi or you want to create randomised numbers. Also, NumPy provides numpy arrays which you can used instead of standard Python lists.

## Exercises

1) Import Pandas module (as pd) and NumPy (as np).
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
import pandas as pd
import numpy as np
```

</p>
</details>
<p>&nbsp;</p>
