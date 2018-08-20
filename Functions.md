# Functions

Do you rember print() and range() we used in the previous chapters? These are Python functions. A function is a block of organised and reusable code that can be called by typing its name and providing the arguments. Similarly to functions in Excel they are used to perform a specific action.

## Useful functions

Python ducomantation provides you with a list of built in functions. You are likely to work with some functions more often than with the others. There are a few commonly used Python functions.

```python
len()
```

Return the length (the number of items) of an object. The argument may be a sequence (such as a string, bytes, tuple, list, or range) or a collection (such as a dictionary, set, or frozen set).

```python
print()
```

Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if present, must be given as keyword arguments.

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
  return bool(a%2)
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
  return bool(a%2)
  
# Check if the number is even - the same function as the one above but expressed with lambda
lambda a: a%2
# You can also assigna name to the function so that you can call it and check if it returns the same values
is_even_lambda = lambda a: bool(a%2)
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
