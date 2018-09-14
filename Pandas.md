# Pandas

Over the course of this chapter we will be working with the "Telco_Customer_Churn.xlsx" file. You can see more info about this dataset on [Kaggle](https://www.kaggle.com/blastchar/telco-customer-churn).

Before starting typing your code, make sure you import both Pandas and NumPy.

```python
import pandas as pd
import numpy as np
```

## Importing Excel files.

Importing Excel files is actually very easy and done with just one line of code.

```python
pd.read_excel(r"file_path/Telco Customer Churn.xlsx")
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

## Selecting and understanding the data.

To select a single column (it will yield a Pandas Series), you need to type the name of your table and then in square brackets and quotation marks the name of the column.

```python
churn_data_table["InternetService"]
```

Sometimes you may want to see the unique values in a column. You can do it with the "unique" method.

```python
churn_data_table["InternetService"].unique()
```

It will also be useful to check what are the data types within your table (each column can be of different data type). The dtypes method comes handy in this case.

```python
churn_data_table.dtypes
```

When you want to get to know some numeric variable, you might want to use sum, mean or count methods.

```python
churn_data_table['MonthlyCharges'].sum()
churn_data_table['MonthlyCharges'].mean()
churn_data_table['MonthlyCharges'].count()
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

You can use loc in another, more useful way. For index label, instead of manually typing the numbers of rows you want choose, you can input an object that will contain the indexes you are after.

```python
# Select all columns, only in cases where gender is Female
churn_data_table.loc[churn_data_table['gender']=='Female',:]

# Select the first four columns, only in cases where InternetService is DSL
churn_data_table.loc[churn_data_table['InternetService']=='DSL',['customerID','gender','SeniorCitizen','Partner']]
```

Using the loc method in this way looks very similar to how we were selecting data at the begginning of this section. However, when you want to overwrite some values, the best way to do it is through using the loc method.

## Setting values.

Changing or updating some values in table is usually done with the loc method.

```python
# Change a specific cell
churn_data_table.loc[1, 'gender'] = 'Female'

# Change a specific cell
churn_data_table.loc[:,'PhoneService'] = 'Yes'

# Change a range of cells in a specific column
churn_data_table.loc[churn_data_table['PaymentMethod']=='Electronic check','MonthlyCharges'] = churn_data_table.loc[churn_data_table['PaymentMethod']=='Electronic check','MonthlyCharges']*1.2
```

## Working with data - basic operations.

Creating a new column in a Pandas DataFrame is very quick and easy. Just type in the name of your table and of your new column (wrapped in square brackets) and assign some values to it.

```python
churn_data_table['New Column'] = 'New Values'
churn_data_table['Count'] = 1
```

You can also create new columns that and based their valus on already existing columns.

```python
churn_data_table['Tenure in years'] = churn_data_table['tenure']/12
```

Let's also use what we have learned about loc and setting the values to modify the Churn column- instead Yes and No, we would rather have True and False or 0 and 1.

```python
# Change Yes and No into 0 and 1
churn_data_table.loc[churn_data_table['Churn']=='Yes','Churn'] = 1
churn_data_table.loc[churn_data_table['Churn']=='No','Churn'] = 0
```

## Aggregating and melting DataFrames.

#### pivot_table

Surely you have used pivot tables in Excel many times. Pandas has the pivot_table function that does the same job.

```python
pd.pivot_table(churn_data_table, values='Churn', index=['gender', 'Contract','PaymentMethod'], columns='InternetService', aggfunc=np.sum)
```

As you can see, you wil get multi-level indexes by default. We can deal with it using the reset_index method.

```python
pd.pivot_table(churn_data_table, values='Churn', index=['gender', 'Contract','PaymentMethod'], columns='InternetService', aggfunc=np.sum).reset_index()

pivot_table_churn = pd.pivot_table(churn_data_table, values='Churn', index=['gender', 'Contract','PaymentMethod'], columns='InternetService', aggfunc=np.sum).reset_index()
```

Multi-levels for indexes are fine, as we can easily deal with them (as shown above). It is not recommended however to use multi-levels for columns- using this table for some further processing will become more difficult.

#### melt

Melt does the opposite to pivot_table, it breaks down and disaggregates the table.

```python
pd.melt(pivot_table_churn, id_vars=['gender', 'Contract','PaymentMethod'], value_name='Churn')

melted table = pd.melt(pivot_table_churn, id_vars=['gender', 'Contract','PaymentMethod'], value_name='Churn')
```

In fact, this (melted) structure of data proves to be a very efficient structure that allows you processing your data in a quick and easy way. We will cover this in more detail in the next chapter.

## Merging and joining DataFrames.

You will usually use either append, merge or concat when merging and joining tables.

#### concat

The method concat comes in handy when you want to join 2 or more tables of the same structure (same columns), one below the other. Imagine you have a few weekly reports that are in the same format and you want to bring them into one object.

```python
# Load in the two tables to concat
table_1 = pd.read_excel(r"file_path/Telco Customer Churn.xlsx")
table_2 = pd.read_excel(r"file_path/Telco Customer Churn_part_2.xlsx")

# Concat the 2 tables - the argument is a list of objects you want to concatenate.
pd.concat([table_1,table_2])
```
Concat will work well as long as the structure of your reports is the same. If the structure differs slightly, use the function append.

#### append

The append function is realy useful when you expect that the sructure of your reports may differ or columns may be in different order. It will however work perfectly fine if the structure is the same too. Therefore you can use this method by default.


```python
# Append together the 2 tables - the argument is a list of objects you want to concatenate
table_1.append(table_2)

# Add a column into table_2
table_2['New Column']='Some Values'

# Append again the 2 tables
table_1.append(table_2)

# Create table 3 based on table 1 and add a column
table_3 = table_1
table_3['New Value'] = 1

# Append 3 tables together
table_1.append([table_2,table_3])
```

#### merge

Merge is used to join together tables that share one or more common column. It can be used analogically to Excel lookups.

```python
code
```

## Exporting Pandas DataFrames into Excel formats.

To export your DataFrame into an Excel file, use the method to_excel.

```python
churn_data_table.to_excel("file_path/ExcelFileFromPandas.xlsx")
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
