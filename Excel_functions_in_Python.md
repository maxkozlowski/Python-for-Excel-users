# Excel functions demonstrated in Python

As always, before starting your work with Python, import the needed modules.

```python
import pandas as pd
import numpy as np
```

Load the Customer Churn data we used in the Pandas chapter. Name it "churn_data_table".

```python
churn_data_table = pd.read_excel(r"file_path/Telco Customer Churn.xlsx")
```

#### vlookup

Before we start, load one more table into your memory: "Telco Customer Churn - Customer name lookup.xlsx" and name it "lookup_table_customer_names". This table will contain customers' id's and their names.

```python
lookup_table_customer_names = pd.read_excel(r"file_path/Telco Customer Churn - Customer name lookup.xlsx")
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

- Summing vertically

```python
churn_data_table['New Sum'].sum()
```

- Summing horizontally (you shouldn't have to do it ofetn, provided you keep your data tidy)

```python
churn_data_table['New Sum'] = churn_data_table['MonthlyCharges'] + churn_data_table['TotalCharges'] 
```

#### max, min

- Max, min vertically

```python
churn_data_table['New Sum'].max()
churn_data_table['New Sum'].min()
```

- Max, min horizontally (you shouldn't have to do it ofetn, provided you keep your data tidy)

```python
def return_max(a, b):
    return max(a,b)
    
churn_data_table.apply(lambda row: return_max(row['New Sum'], row['TotalCharges']), axis=1)
```

#### if

Very often when working with Excel you would use the 'if' function. This will make your function conditional based on some other value. Mirroring this logic in Python will be usually done using a bespoke function and the apply function.

```python
# Based on monthly charge, add a column "Package" that will tell wether a customer is on Basic or Premium Package
def return_package(charge):
  if charge <=60:
    return "Basic"
  else:
    return "Premium"

churn_data_table['Package'] = churn_data_table['MonthlyCharges'].apply(return_package)

# We can also do it in one line using lambda
churn_data_table['Package'] = churn_data_table['MonthlyCharges'].apply(lambda charge: "Basic" if charge<=60 else "Premium")
```

Using the same logic you can create much more complicated and powerful functions that will help you processing your data in the way you need.

#### sumif

When performing sumifs, you should only be doing them vertically. Provided you keep your data structure tidy, you will not have to do a horizontal sumif.

```python
# Sum all monthly charges if 'PaymentMethod' is 'Electronic check'
churn_data_table.loc[churn_data_table['PaymentMethod']=='Electronic check','MonthlyCharges'].sum()
```

#### countif

Countif will be very similar to sumif - you only need to change the method you use to count.

```python
# Count rows if 'PaymentMethod' is 'Electronic check'
churn_data_table.loc[churn_data_table['PaymentMethod']=='Electronic check','MonthlyCharges'].count()
```

#### and

#### or

#### left, right

#### concatenate

If you want to concatenate two or more columns that are of string type, you can just add them together.

```python
churn_data_table['customerID'] = churn_data_table['customerID'] + churn_data_table['customerID']
```

#### trim

```python
# strip
churn_data_table['customerID']=churn_data_table['customerID'].apply(lambda x: x.strip())
```

#### lower, upper, proper

Use apply and one of the methods you need to amend the data.

```python
# lower
churn_data_table['customerID']=churn_data_table['customerID'].apply(lambda x: x.lower())

# upper
churn_data_table['customerID']=churn_data_table['customerID'].apply(lambda x: x.upper())

# proper/title
churn_data_table['customerID']=churn_data_table['customerID'].apply(lambda x: x.title())
```

#### round


