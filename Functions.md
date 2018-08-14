# Functions

Do you rember print() and range() we used in the previous chapters? These are Python functions. A function is a block of organised and reusable code that can be called by typing its name and providing the arguments. Similarly to functions in Excel they are used to perform a specific action.

## Useful functions

Python ducomantation provides you with a list of built in functions. You are likely to work with some functions more often than with the others. There are a few commonly used Python functions.

- len()

Return the length (the number of items) of an object. The argument may be a sequence (such as a string, bytes, tuple, list, or range) or a collection (such as a dictionary, set, or frozen set).

- print()

Print objects to the text stream file, separated by sep and followed by end. sep, end, file and flush, if present, must be given as keyword arguments.

- abs()

Return the absolute value of a number. The argument may be an integer or a floating point number. If the argument is a complex number, its magnitude is returned.

- min()

Return the smallest item in an iterable or the smallest of two or more arguments.

- max()

Return the largest item in an iterable or the largest of two or more arguments.

- round()

Return number rounded to ndigits precision after the decimal point. If ndigits is omitted or is None, it returns the nearest integer to its input.

- type()

With one argument, return the type of an object

- str()

Return a string version of object.

- int()

Return an integer object constructed from a number or string x, or return 0 if no arguments are given.

- float()

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
  return a%2
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
