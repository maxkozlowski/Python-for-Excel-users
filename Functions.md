# Functions

Do you rember print() and range() we used in the previous chapters? These are Python functions. A function is a block of organised and reusable code that can be called by typing its name and providing the arguments. Similarly to functions in Excel they are used to perform a specific action.

## Useful functions

Python ducomantation provides you with a list of built in functions. You are likely to work with some functions more often than with the others. There are a few commonly used Python functions. To get a full view of Python built in functions, go to the [official Python website](https://docs.python.org/3/library/functions.html).

```python
len()
```

Return the length (the number of items) of an object. The argument may be a sequence (such as a string, bytes, tuple, list, or range) or a collection (such as a dictionary, set, or frozen set).

```python
print()
```

Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if present, must be given as keyword arguments.

```python
range()
```

Return a sequence based on the arguments provided.

```python
abs()
```

Return the absolute value of a number. The argument may be an integer or a floating point number. If the argument is a complex number, its magnitude is returned.

```python
min()
```

Return the smallest item in an iterable or the smallest of two or more arguments.

```python
max()
```

Return the largest item in an iterable or the largest of two or more arguments.

```python
round()
```

Return number rounded to ndigits precision after the decimal point. If ndigits is omitted or is None, it returns the nearest integer to its input.

```python
type()
```

With one argument, return the type of an object

```python
str()
```

Return a string version of object.

```python
int()
```

Return an integer object constructed from a number or string x, or return 0 if no arguments are given.

```python
float()
```

Return a floating point number constructed from a number or string x.

```python
bool()
```

Return a Boolean value, i.e. one of True or False.

## Defining functions

Just like in Excel, you can define custom functions. You will find it useful when you have to do a repetetive task that takes a few lines of code. It also makes your code more readable and organised if you wrap it into just one function.

In order to declare your function, type def followed by the name of your fonction with brackets at the end. Inside the brackets you can put the arguments you will require.

To call your function, type its name and the brackets.

```python
# Functions with no arguments

# First function
def new_function():
  print('My function')
  
# Function returning this year
def this_year():
  return 2018
  
# Call the functions
new_function()
this_year()
```

## Function arguments

Most often you will want to input some values to get processed by the function. Just like in Excel, you typically want to calculate some results based on arguments provided. To create a function that takes arguments, just type in the arguments in brackets and separate them by commas.

```python
# Functions with arguments

# Sum 2 arguments
def sum_2_arguments(a,b):
  return a+b
  

# Check if the number is even
def is_even(a):
  return not bool(a%2)
```

Some arguments in your function can be optional and can assume some default values for them. This is useful when you expect that most of the times users will want an argument to be equal to a certain number but you want to provide the flexibility to change it.

```python
# Functions with arguments

# Return family size
def family_size(kids, siblings, spouses=1, parents=2):
    return sum([kids, siblings, spouses, parents])
```

Additionally, you can use * args or ** kwargs in your function definition. Using * args is useful when you are not sure how many arguments might be passed to your function. Using * kwargs allows you to handle named arguments that you have not defined in advance.

```python
# Sum all numbers
def sum_all_arguments(*args):
  x = 0
  for i in args:
    x+=i
  return x
  
# Print kwargs
def print_kwargs(**kwargs):
  print(kwargs)
```

## Lambda expressions

When writing short and quick functions you may want to use lambda expression. The only thing it does is that it enables you to write a function in a more concise way.

```python
# Check if the number is even
def is_even(a):
  return not bool(a%2)
  
# Check if the number is even - the same function as the one above but expressed with lambda
lambda a: not bool(a%2)
# You can also assigna name to the function so that you can call it and check if it returns the same values
is_even_lambda = lambda a: not bool(a%2)
```


## Exercises

1) Use len() to measure the length a string, a list a tuple and a dictionary.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
len('wall')
len([1,2,3])
len((1,2,3))
len({'x':1, 'y':2})
```

</p>
</details>
<p>&nbsp;</p>

2) Create a variable and assign a negative variable to it (it can be either float or int). Convert the variable into a positive number using abs().
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x = -3
x = abs(x)
y = -5.14
y = abs(y)
```

</p>
</details>
<p>&nbsp;</p>

3) Get the minimum value of a string, a list, a tuple and a dictionary.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
min('wall')
min([1,2,3,4,5])
min((1,2,3,4,5))
min({1:0.5, 2:1, 4:2, 8:4})
```

</p>
</details>
<p>&nbsp;</p>

4) Get the maximum value of a string, a list, a tuple and a dictionary.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
max('wall')
max([1,2,3,4,5])
max((1,2,3,4,5))
max({1:0.5, 2:1, 4:2, 8:4})
```

</p>
</details>
<p>&nbsp;</p>

5) Create a float number and round it using the round() function.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x = 3.1416
x = round(x)
```

</p>
</details>
<p>&nbsp;</p>

6) You can also tell Python how many decimal numbers you want to round your float to. It is a second argument in the round function, which is 0 by default. Create another float and round it to the second decimal number.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x = 3.1416
x = round(x, 2)
```

</p>
</details>
<p>&nbsp;</p>

7) Create 3 new variables of different types: integer, string and a dictionary. Check their types.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x = 5
type(x)

y = 'Sky'
type(y)

z = {'a':1, 'b':2, 'c':3}
type(z)
```

</p>
</details>
<p>&nbsp;</p>

8) Use the integer you created in the previous exercise and transform it to a string. Could you do the same in case of a dictionary or list?
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x = str(x)
x
```

</p>
</details>
<p>&nbsp;</p>

9) Convert the variable you used in the previous exercise back to numeric types. Create 2 variables: x_int and x_float. Do you think this transformation could be done with a string that contains non-numeric characters or with other data types?
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x_int = int(x)
x_float = float(x)
```

</p>
</details>
<p>&nbsp;</p>

10) Define a function that will return your age.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
def return_age():
  return 27
```

</p>
</details>
<p>&nbsp;</p>

11) Define a function that will take year as an argument and return your age in the year provided.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
def return_age(year):
  return year-1991
```

</p>
</details>
<p>&nbsp;</p>

12) Define a function that will take year as an argument and return your age in the year provided. Use 2018 as the default argument.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
def return_age(year=2018):
  return year-1991
```

</p>
</details>
<p>&nbsp;</p>

13) Create a function that will take an unknown number of values (it can be 1 value or more) and return product of all numbers.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
def sum_all_arguments(*args):
  x = 0
  for i in args:
    x*=i
  return x
```

</p>
</details>
<p>&nbsp;</p>

14) Replicate the function from the exercise 11 using lambda.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
return_age_lambda = lambda year: year-1991
```

</p>
</details>
<p>&nbsp;</p>
