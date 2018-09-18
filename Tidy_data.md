# Tidy data

Tidy data is a foundation of data processing using Pandas. Having your dataset in a tidy structure will make your work easier, quicker and more error-prone.

From [Hadley Wickham's Tidy Data Paper](http://vita.had.co.nz/papers/tidy-data.html)

>A huge amount of effort is spent cleaning data to get it ready for analysis, but there has been little research on how to make data cleaning as easy and effective as possible. This paper tackles a small, but important, component of data cleaning: data tidying.
Tidy datasets are easy to manipulate, model and visualize, and have a specific structure: each variable is a column, each observation is a row, and each type of observational unit is a table.

>It is often said that 80% of data analysis is spent on the process of cleaning and preparing the data (Dasu and Johnson 2003). Data preparation is not just a first step, but must be repeated many times over the course of analysis as new problems come to light or new data is collected. 

>The principles of tidy data provide a standard way to organize data values within a dataset. A standard makes initial data cleaning easier because you do not need to start from scratch and reinvent the wheel every time. The tidy data standard has been designed to facilitate initial exploration and analysis of the data, and to simplify the development of data analysis tools that work well together.

## Defining Tidy Data.

From [Hadley Wickham's Tidy Data Paper](http://vita.had.co.nz/papers/tidy-data.html)

> Like families, tidy datasets are all alike but every messy dataset is messy in its own way. Tidy datasets provide a standardized way to link the structure of a dataset (its physical layout) with its semantics (its meaning).

Let's imagine we have weekly sales data for 2 products (Basic and Premium).

Weeks down the side and products across the top.

| Week  | Basic | Premium |
| ------------- | ------------- | ------------- |
| Week 1  | 167  | 42  |
| Week 2  | 225  | 51  |
| Week 3  | 180  | 44  |

Products down the side and weeks across the top.

| Product  | Week 1 | Week 2 | Week 3 |
| ------------- | ------------- | ------------- | ------------- |
| Basic  | 167  | 225  | 180  |
| Premium  | 42  | 51  | 44  |

There are multiple ways to represent the same dataset. Both tables contain exactly the same data, though they are structured in a different way. You may already expect that keeping data in a variety of structures will cause problems with joining tables as well as will force you to adjust your data processes to the specific structure of your data i.e. your ability to use codes built in the past will be limited.

## Principles of Tidy data.

From [Hadley Wickham's Tidy Data Paper](http://vita.had.co.nz/papers/tidy-data.html)

> A dataset is a collection of values, usually either numbers (if quantitative) or strings (if qualitative). Values are organized in two ways. Every value belongs to a variable and an observation. A variable contains all values that measure the same underlying attribute (like height, temperature, duration) across units. An observation contains all values measured on the same unit (like a person, or a day, or a race) across attributes.

We can summarize the charasteristics of tidy data into the following points. Try to follow them whenever you come to work with data in Python and Pandas.

<b><i>1. Each variable you measure should be in one column.</i></b><p>
<b><i>2. Each different observation of that variable should be in a different row.</i></b><p>
<b><i>3. There should be one table for each "kind" of variable.</i></b><p>
<b><i>4. If you have multiple tables, they should include a column in the table that allows them to be linked.</i></b><p>

Now that we know what structure we should form whenever working with data, let's try to reshape the sales data into a tidy format.

Tidy data format - weeks and product down the side, sales data in one separate column

| Week  | Product | Sales |
| ------------- | ------------- | ------------- |
| Week 1  | Basic  | 167  |
| Week 2  | Basic  | 225  |
| Week 3  | Basic  | 180  |
| Week 1  | Premium  | 42  |
| Week 2  | Premium  | 51  |
| Week 3  | Premium  | 44  |

## Tidying messy datasets.

You will surely come across many data untidy. In that case you will have to transform them so that they are in a nice and neat shape. Let's go through an example.

| Quarter  | TV Spends | Radio Spends | Press Spends | Outdoor Spends | Digital Spends |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Q1  | 228000  | 50000  | 65000  | 28000  | 12000  |
| Q2  | 110000  | 40000  | 60000  | 30000  | 22000  |
| Q3  | 150000  | 45000  | 80000  | 20000  | 24000  |
| Q4  | 140000  | 30000  | 70000  | 10000  | 25000  |

We need to melt the table so that we hav additional column representing the channel and only one column with spends. Also it will be worth removing the "Spends" element from channel name, since this will be the exact name of our new column. The new, dity structure will therefore look as follows.

| Quarter  | Channel | Spends |
| ------------- | ------------- | ------------- |
| Q1  | TV  | 228000  |
| Q2  | TV  | 110000  |
| Q3  | TV  | 150000  |
| Q4  | TV  | 140000  |
| Q1  | Radio  | 50000  |
| Q2  | Radio  | 40000  |
| Q3  | Radio  | 45000  |
| Q4  | Radio  | 30000  |
| Q1  | Press  | 65000  |
| Q2  | Press  | 60000  |
| Q3  | Press  | 80000  |
| Q4  | Press  | 70000  |
| Q1  | Outdoor  | 28000  |
| Q2  | Outdoor  | 30000  |
| Q3  | Outdoor  | 20000  |
| Q4  | Outdoor  | 10000  |
| Q1  | Digital  | 12000  |
| Q2  | Digital  | 22000  |
| Q3  | Digital  | 24000  |
| Q4  | Digital  | 25000  |

## Exercises

1) Exercise 1
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

2) Exercise 2
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

3) Exercise 3
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

4) Exercise 4
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

5) Exercise 5
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

6) Exercise 6
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

7) Exercise 7
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

8) Exercise 8
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

9) Exercise 9
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

10) Exercise 10
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

11) Exercise 11
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

12) Exercise 12
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

13) Exercise 13
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

14) Exercise 14
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

15) Exercise 15
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

16) Exercise 16
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

17) Exercise 17
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

18) Exercise 18
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

19) Exercise 19
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

20) Exercise 20
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>
