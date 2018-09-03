# Pandas

Over the course of this chapter we will be working with the "Mobile_Sales_Data.xlsx" file. The first five rows of the file look as follows.

| Date  | iPhone | Samsung | Huawei |
| ------------- | ------------- | ------------- | ------------- |
| x  | x  | x  | x  |
| x  | x  | x  | x  |
| x  | x  | x  | x  |
| x  | x  | x  | x  |
| x  | x  | x  | x  |

## Importing Excel files.

Importing Excel files is actually very easy and done with just one line of code.

```python
pd.read_excel("file_path/ExcelFile.xlsx")
```

Now that you know how to do it, go ahead and load in the "Mobile_Sales_Data.xlsx" file. Let's assign it to an object called "sales_data_table".

```python
sales_data_table = pd.read_excel("file_path/Mobile_Sales_Data.xlsx")
```

## Pandas data structures: Series and DataFrame.

Pandas has two main data tructures: Series and DataFrame. A Series is a one-dimensional DataFrame (a DataFrame that contains only one column).

## Viewing data.

When you want to view your table you can either just type in the name of your table, or use head or tail method.

```python
# View the table
sales_data_table

# View the head of the table. By default you will see first 5 rows. If you want to see n rows, type "head(n)"
sales_data_table.head()
sales_data_table.head(10)


# View the tail of the table. By default you will see last 5 rows. If you want to see n rows, type "tail(n)"
sales_data_table.tail()
sales_data_table.tail(10)
```

## Selecting data.

To select a single column (it will yield a Pandas Series), you need to type the name of your table and then in square brackets and quotation marks the name of the column.

```python
sales_data_table["iPhone"]
```
You can also select specific rows by calling index of the table.

```python
sales_data_table[3:6]
```

#### loc

#### iloc

## Setting values.

## Working with data - basic operations.

## Aggregating and melting DataFrames.

## Merging and joining DataFrames.

## Exporting Pandas DataFrames into Excel formats.

```python
pd.to_excel("file_path/ExcelFileFromPandas.xlsx")
```

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
