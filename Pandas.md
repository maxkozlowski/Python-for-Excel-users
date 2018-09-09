# Pandas

Over the course of this chapter we will be working with the "Telco_Customer_Churn.xlsx" file. You can see more info about this dataset on [Kaggle](https://www.kaggle.com/blastchar/telco-customer-churn).

## Importing Excel files.

Importing Excel files is actually very easy and done with just one line of code.

```python
pd.read_excel(r"file_path/Telco_Customer_Churn.xlsx")
```

Now that you know how to do it, go ahead and load in the "Mobile_Sales_Data.xlsx" file. Let's assign it to an object called "sales_data_table".

```python
churn_data_table = pd.read_excel(r"file_path/Telco_Customer_Churn.xlsx")
```

## Pandas data structures: Series and DataFrame.

Pandas has two main data tructures: Series and DataFrame. A Series is a one-dimensional DataFrame (a DataFrame that contains only one column).

## Viewing data.

When you want to view your table you can either just type in the name of your table, or use head or tail method.

```python
# View the table
churn_data_table

# View the head of the table. By default you will see first 5 rows. If you want to see n rows, type "head(n)"
churn_data_table.head()
churn_data_table.head(10)


# View the tail of the table. By default you will see last 5 rows. If you want to see n rows, type "tail(n)"
churn_data_table.tail()
churn_data_table.tail(10)
```

## Selecting data.

To select a single column (it will yield a Pandas Series), you need to type the name of your table and then in square brackets and quotation marks the name of the column.

```python
churn_data_table["InternetService"]
```

Sometimes you may want to see the unique values in a column. You can do it with the "unique" method.

```python
churn_data_table["InternetService"].unique()
```

You can also select specific rows by calling index of the table.

```python
churn_data_table[3:6]
```

You may also want to select a subtable, based on some filters. Pandas can deal with it in a neat way.

```python
# Create an array with True/False values based on which your filter will work
churn_data_table['customerID'] == '5575-GNVDE'

# In order to actually see the table you need to wrap the above into square brackets and again provide the table of your name
churn_data_table[churn_data_table['customerID'] == '5575-GNVDE']

# Return only customers with Phone Service
churn_data_table[churn_data_table['PhoneService'] == 'Yes']
```

#### iloc

The iloc indexer for Pandas Dataframe is used for integer-location based selection by position. You can just select specific cells from your table with colmns and rows indexes.

```python
### your_table.iloc[row number/selection, column number/selection] ###

# Select the cell tha is in the first row and first column
churn_data_table.iloc[0,0]

# Select the cell that is in the second row and first column
churn_data_table.iloc[1,0]

# Select the cell that is in the first row and second column
churn_data_table.iloc[0,1]

# Select the the first row and all columns
churn_data_table.iloc[0,:]

# Select the first column and all rows
churn_data_table.iloc[:,0]

# Select the the first 3 rows and all columns
churn_data_table.iloc[0:3,:]

# Select the first 3 columns and all rows
churn_data_table.iloc[:,0:3]

# Select the first 3 columns and first 3 rows
churn_data_table.iloc[0:3,0:3]

# By providing just the first argument you are taking all columns and the specified row(s)
churn_data_table.iloc[0]
churn_data_table.iloc[0:5]
```

#### loc

With loc you can select data based on column and index labels.

```python
### your_table.loc[index label, column name] ###

# In the example below the index lables are the same as index row numbers, that's why you will not see the difference in row/index selection versus the iloc selection

# Select the cell tha is in the first row and first column
churn_data_table.loc[0, 'customerID']

# Select the cell that is in the second row and first column
churn_data_table.loc[1,'customerID']

# Select the cell that is in the first row and second column
churn_data_table.loc[0,'gender']

# Select the the first row and all columns
churn_data_table.loc[0,:]

# Select the first column and all rows
churn_data_table.loc[:,'customerID']

# Select the the first 3 rows and all columns
churn_data_table.loc[0:3,:]

# Select the first 3 columns and all rows
churn_data_table.loc[:,['customerID','gender','SeniorCitizen']]

# Select the first 3 columns and first 3 rows
churn_data_table.loc[0:3,['customerID','gender','SeniorCitizen']]

# By providing just the first argument you are taking all columns and the specified row(s)
churn_data_table.loc[0]
churn_data_table.loc[0:5]
```

## Setting values.

If you want to change or update the values in your table, you can use the iloc or loc method and just assign some new value to the cell(s) you indent to update.

```python
churn_data_table.loc[1, 'gender'] = 'Female'

churn_data_table.loc[:,'PhoneService'] = 'Yes'
```

## Working with data - basic operations.

Creating a new column in a Pandas DataFrame is very quick and easy. Just type in the name of your table and of your new column (wrapped in square brackets) and assign some values to it.

```python
churn_data_table['New Column'] = 'New Values'
```

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
