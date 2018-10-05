# Excel functions demonstrated in Python

As always, before starting your work with Python, import the needed modules.

```python
import pandas as pd
import numpy as np
```

Load the Customer Churn data we used in the Pandas chapter. Name it "churn_data_table".

```python
churn_data_table = pd.read_excel(r"M:\MMM\Python\Learning\Python Training Aug-Oct 18\Files\Telco Customer Churn.xlsx")
```

#### vlookup

Before we start, load one more table into your memory: "Telco Customer Churn - Customer name lookup.xlsx" and name it "lookup_table_customer_names". This table will contain customers' id's and their names.

```python
lookup_table_customer_names = pd.read_excel(r"M:\MMM\Python\Learning\Python Training Aug-Oct 18\Files\Telco Customer Churn - Customer name lookup.xlsx")
```

There is a few ways to perform a vlookup in Python.

1) Perform a merge on the 2 tables.

You can merge the 2 tables on customerID, so that you add a customer name column.

```python
# Merge the 2 tables
churn_data_table.merge(lookup_table_customer_names, how='left', on='customerID')

# As merge will merge all columns from the tables, it is worth specifying only those that you need from your lookup table-it will be your keys on which you are matching tables as well as the columns you want to add.
churn_data_table.merge(lookup_table_customer_names[['customerID','customers name']], how='left', on='customerID')
```

2) Use replace method using dictionary

```python
# Create a dictionary based on the look up table
dictionary_lookup_table_customer_names = dict(zip(lookup_table_customer_names['customerID'],lookup_table_customer_names['customers name']))

# Create a new column in churn_data_table named 'customer name'. For the moment store customerID there.
churn_data_table['customer name'] = churn_data_table['customerID']

# In the column 'customer name' replace customer ID's with customer names- based on the lookup dictionary.
churn_data_table['customer name'].replace(dictionary_lookup_table_customer_names, inplace=True)
```

It is important to remember that Python, as opposed to Excel is case-sensitive. Also, sometimes you might have spaces at the beginning or at the end which are difficult to spot.
It is a good habit to always lower cases and trim your columns on which you will be looking up.

```python
# Trim customerID column - both in date and lookup table
churn_data_table['customerID']=churn_data_table['customerID'].str.strip()
lookup_table_customer_names['customerID']=lookup_table_customer_names['customerID'].str.strip()

# Lower cases - both in date and lookup table
churn_data_table['customerID']=churn_data_table['customerID'].apply(lambda x: x.lower())
lookup_table_customer_names['customerID']=lookup_table_customer_names['customerID'].apply(lambda x: x.lower())
```

#### sum

Calculating sums in Python is very easy, though you have to approach differently horizontal and vertical sums.

- Summing horizontally

```python
churn_data_table['New Sum'] = churn_data_table['MonthlyCharges'] + churn_data_table['TotalCharges'] 
```

- Summing vertically

```python
churn_data_table['New Sum'].sum()
```

#### max, min

#### if

#### sumif

#### countif

#### and

#### or

#### left, right

#### concatenate

#### trim

#### lower, upper, proper

#### round

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