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

#### sum

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
