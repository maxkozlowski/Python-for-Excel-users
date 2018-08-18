# Data types and operators

## Basic data types

Alike Excel, you have various data types that you can use in Python. In Excel there are types such as floats, integers, booleans (True/False), texts, date and currency.

Python has 7 basic data types: integers, floats, booleans, strings, lists, tuples, dictionaries. Most of them are quite analogical to Excel, though some of them are more advanced.

| Data Type  | Example | Applications |
| ------------- | ------------- | ------------- |
| integer  | 61  | indexing, counting, very simple calculations  |
| float  | 3.14  | calculations  |
| boolean  | True (False)  | comparisons, 'if' statements  |
| string  | 'Sky Sports', 'Apple'  | working with text  |
| list  | [2, 5, -10, 100]  | storing sequences of data  |
| tuple  | (1, 2, 5, -8)  | storing sequences of data provided you don't want to change them, returning values  |
| dictionary  | {'Kane': 48, 'Messi': 45, 'Ronaldo': 44, 'Lewandowski':48}  | Looking up on data  |

## Operators

Python features a range of operators. They can be split into arithmetic, assignment, comparison, logical, identity, membership and bitwise operators.

You will have seen operators in Excel already. When doing calculations in Excel, you surely employed operators such as +, -, * and /. If you have some experience with VBA you will be familiar with assignment and comparison operators too. 

| Category  | Operator  | Example | Description |
| ------------- | ------------- | ------------- | ------------- |
| arithmetic  | +  | 3 + 2 (outcome: 5) | addition |
| arithmetic  | -  | 3 - 1 (outcome: 2) | subtraction |
| arithmetic  | *  | 3 * 2 (outcome: 6) | multiplication |
| arithmetic  | /  | 9 / 3 (outcome: 3) | division |
| arithmetic  | **  | 2 ** 3 (outcome: 8) | power calculation |
| arithmetic  | //  | 9 // 2 (outcome: 4) | floor division |
| arithmetic  | %  | 9 % 2 (outcome: 1) | modulus |
| assignment  | =  | x = 10 | x = 10 |
| assignment  | +=  | x += 10 | x = x + 10 |
| assignment  | -=  | x-=10 | x = x - 10 |
| assignment  | * =  | x * = 10 | x = x * 10 |
| assignment  | /=  | x /= 10 | x = x / 10 |
| assignment  | ** =  | x ** = 10 | x = x ** 10 |
| assignment  | //=  | x //= 10 | x = x // 10 |
| assignment  | %=  | x %= 10 | x = x % 10 |
| comparison  | ==  | x == y | check if equal |
| comparison  | !=  | x != y | check if not equal |
| comparison  | >  | x > y | check if greater than |
| comparison  | <  | x < y | check if less than |
| comparison  | >=  | x >= y | check if greater than or equal to |
| comparison  | <=  | x <= y | check if less than or equal to |
| logical  | and  | x == y and x < z | check if both statements are true |
| logical  | or  | x == y or x < z | check if at least one of the statements is true |
| logical  | not  | not x == y | return the reverse result |
| identity  | is  | x is y | check if the viables are the same objects |
| identity  | is not  | x is not y | check if the variables are different objects |
| membership  | in  | x in y | check if the variable can be found in the specified sequence |
| membership  | not in  | x not in y | check if the variable can not be found in the specified sequence |

## Working with non-numeric data types

While working with numbers and strings in Python for an Excel user is rather intuitive, lists, tuples and dictionaries do not have a direct analogy in Excel. 

#### List

Lists store arrays of data written within square brackets []. In order to create a new list, simply type in a few numbers delimited by commas and wrap it in square brackets.

Lists elements are easy to access thanks to indexes (either starting from left or right). The first value on the left has index 0 and the first value on the right has index -1.

```python
new_list = [5,10,15,20,25]
# index:    0  1  2  3  4
# index:   -5 -4 -3 -2 -1
```

To get an element from a list, you can simply type the name of the list and the index of the value you are after, wrapped in square brackets.

```python
new_list[3]
new_list[-2]
```

Another way of pulling out values from lists is slicing. Type in the name, and in square brackets the first and the range of observations you want to pull out. Note that Python will return all the values in between the indexes you passed, including the first observation but excluding the last one.

```python
new_list[0:3]
new_list[1:5]
new_list[2:]
new_list[2:]
new_list[:-1]
new_list[:]
```

#### Tuple

Tuples are quite similar to lists and store arrays of data written within brackets (). In order to create a new list, simply type in a few numbers delimited by commas and wrap it in square brackets. The main difference is that tuples, unlike lists, are immutable i.e. once created you cannot change its values.

Tuple elements are easy to access thanks to indexes (either starting from left or right). The first value on the left has index 0 and the first value on the right has index -1.

```python
new_tuple = (5,10,15,20,25)
# index:     0  1  2  3  4
# index:    -5 -4 -3 -2 -1
```

To get an element from a tuple, you can simply type the name of the list and the index of the value you are after, wrapped in square brackets.

```python
new_tuple[3]
new_tuple[-2]
```

Another way of pulling out values from tuples is slicing. Type in the name, and in square brackets the first and the range of observations you want to pull out. Note that Python will return all the values in between the indexes you passed, including the first observation but excluding the last one.

```python
new_tuple[0:3]
new_tuple[1:5]
new_tuple[2:]
new_tuple[2:]
new_tuple[:-1]
new_tuple[:]
```

#### Dictionary

Dictionary is a set of key:value pairs. It is very useful for storing pairs of values and extracting values by providing its key. It can be very often used to perform tasks analogical to vlookup or index/match in Excel.

| Name (Key)  | World Cup Goals (Value)  |
| ------------- | ------------- |
| 'Kane' | 6 |
| 'Griezmann' | 4 |
| 'Lukaku' | 4 |
| 'Cheryshev' | 4 |
| 'Mbappe' | 4 |

You can represent the table above in a dictionary.

```python
new_dictionary = {'Kane':6, 'Griezmann':4, 'Lukaku':4, 'Cheryshev':4, 'Mbappe':4}
```

You can extract the number of goals scored by each player just by calling his name (the key in this dictionary).

```python
new_dictionary['Kane']
new_dictionary['Lukaku']
```


## Exercises

1) Create a variable 'height' and assign your height (in feet).
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
height = 6.1
```

</p>
</details>
<p>&nbsp;</p>

2) Create a new variable 'height_m' that will be a function of 'height' that transforms feet into meters. There are 3.28 feet in a meter.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
height_m = height/3.28
```

</p>
</details>
<p>&nbsp;</p>

3) Create a variable 'birth_year'.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
birth_year = 1991
```

</p>
</details>
<p>&nbsp;</p>

4) Create a variable 'age'. Assign 2018 minus 'birth_year' to it.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
age = 2018 - birth_year
```

</p>
</details>
<p>&nbsp;</p>

5) Subtract 5 years from the 'age' variable. Try using only the number 5 on the right hand side.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
age -=5
```

</p>
</details>
<p>&nbsp;</p>

6) Check if your age 5 years ago was even.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
age%2 == 0
```

</p>
</details>
<p>&nbsp;</p>

7) Create another variable that contains age of one of your friends or siblings. Compare if this variable is bigger or equal to the variable 'age' (you can add back the 5 years you subtracted earlier).
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
age_sibling = 29
age += 5
age_sibling >= age
```

</p>
</details>
<p>&nbsp;</p>

8) Create a list that contains one integer, one float, one string and a bollean. A single list can contain different data types. Name it 'new_list'.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
new_list = [5, 7.13, 'Erika', True]
```

</p>
</details>
<p>&nbsp;</p>

9) Get the first element from the list.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
new_list[0]
```

</p>
</details>
<p>&nbsp;</p>

10) Get the last element from the list.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
new_list[-1]
```

</p>
</details>
<p>&nbsp;</p>

11) Get the first 2 elements from the list.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

12) Get the last 2 elements from the list.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

13) Create a tuple that contains one integer, one float, one string and a bollean. A single tuple can contain different data types. Name it 'new_tuple'.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

14) Get the first element from the tuple.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

15) Get the last element from the tuple.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

16) Get the first 2 elements from the tuple.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

17) Get the last 2 elements from the tuple.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

18) Assign a new number into the first element of your list. Could this be done with the tuple?
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

19) Create a dictionary with at least 3 pairs of fruits and their colours.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>

20) Get the colour of one of the fruits you used.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
code
```

</p>
</details>
<p>&nbsp;</p>
