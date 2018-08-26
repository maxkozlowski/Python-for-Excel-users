# Control flow statements

Control flow statements break up the flow of execution of code by employing decision making, looping, and branching, enabling your program to conditionally execute particular blocks of code.

## Indentation

Python uses indentation instead of braces to structure its programs and scripts into blocks. To indicate a block of code in Python, you must indent each line of the block by the same amount (typically four spaces). You will have to use indentation every time you use control flow statements, particularly if, else/elif, for and while. It is worth remembering that the control flow statements also use colons.

```python
# Pseudo-code example of how to use colons and indentation with control flow statements
control_flow_statement_1:
  block of code (it belongs to control_flow_statement_1)
  block of code (it belongs to control_flow_statement_1)
  block of code (it belongs to control_flow_statement_1)
  control_flow_statement_2:
    block of code (it belongs to control_flow_statement_2)
    block of code (it belongs to control_flow_statement_2)
    block of code (it belongs to control_flow_statement_2)
    control_flow_statement_3:
      block of code (it belongs to control_flow_statement_3)
      block of code (it belongs to control_flow_statement_3)
      block of code (it belongs to control_flow_statement_3)
    block of code (it belongs to control_flow_statement_2)
    block of code (it belongs to control_flow_statement_2)
  block of code (it belongs to control_flow_statement_1)
  block of code (it belongs to control_flow_statement_2)
block of code (outside of and intependent from any control_flow_statement)
block of code (outside of and intependent from any control_flow_statement)
```

## if

This statement is both self-explanatory and often used in Excel formulas. It simply checks whether or not the statement following if is True.
```python
# Declare a variable
x = 10
# If statement
if x < 15:
  print('The variable is less than 15')
```

#### elif and else

Very often you will want to check if some other cases are true. You also may need to do something if non of your cases are true. In these cases elif and else come in handy.

```python
# Declare a variable
x = 10
# If statement
if x < 15:
  print('The variable is less than 15')
# if x is not less than 15 check if it is less than 20
elif x < 20:
  print('The variable is between 15 and 19')
# if x is not less than 15 check if it is less than 20
elif x < 30:
  print('The variable is between 20 and 29')
# all other cases (x is not less than 30)
else:
  print('The variable is 30 or more')
```

## for

You can use for statmenet to iterate over some objects. Typically you will use the for statement to iterate over lists, strings or ranges.

```python
# Iterate over a list
for i in [0,1,2,3,4,5]:
  print(i)

# Iterate over a string
for i in 'your_name':
  print(i)
```

#### range

Often you may want to iterate over some range, for example from 0 to 10 or from 5 to 50. In this case, you don't have to declare a long list with all the elements you want to iterate over. You can use range instead.

Do you remember that when you slice a list, the last element will not be included? The range function works in the same way.

```python
# Iterate over a range (0 to 9)
for i in range(11):
  print(i)

# Iterate over a range
for i in range(5,51):
  print(i)
```

## while

Used for iterating as long as the condition following the statement is True. You can use it to iterate over ranges.

```python
# Iterate from 0 to 10
i = 0
while i < 10:
  print(i)
  i += 1
```

## continue

Continue statement tends to be used with for loop. It stops the current iteration and continues with the next iteration of the loop.

```python
# Iterate over a list 1 to 8 and print only even numbers
for i in [1,2,3,4,5,6,7,8]:
    if i%2 == 1:
        continue
    print(i)
# Do you remember that True or False are actually 1 and 0 in value terms?
# Considering this, could we make our if statement shorter?
```

## break

Break statement terminates the loop before it has looped through all the items.

```python
for i in [1,2,3,4,5,6,7,8]:
    if i > 5:
        break
    print(i)
```

## pass

Pass statement does not actually do anything. It is used more as a place-holder for some code to be written. The pass is silently ignored.

```python
for i in [1,2,3,4,5,6,7,8]:
    if i > 5:
        pass
    print(i)
```


## Exercises

1) Create some numeric variable and write an if statement that divides the variable by 3 if it's larger than 10.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
x = 15

if x > 10:
    x = x/3
```

</p>
</details>
<p>&nbsp;</p>

2) Create an if statement that takes 2 predefined variables: 'my_age' and 'my_friends_age'. Depending on the result it will print 'I am older', 'My friend is older' or 'We are the same age'.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
my_age = 27
my_friends_age = 28

if my_age > my_friends_age:
    print("I'm older")
elif my_age == my_friends_age:
    print('We are the same age')
else:
    print('My friend is older')
```

</p>
</details>
<p>&nbsp;</p>

3) Imagine that you are testing a hypothesis and you are using two-tailed test. Create a variable 'test_statistic' and assign some number to it. Write an if statement that prints 'Hypothesis rejected with 5% significance level' if the variable is more than 1.96 or less than -1.96. Then, if it's not the case but your variable is larger or smaller than 1.645 (-1.645), print out 'Hypothesis rejected with 10% significance level'. In all other cases print out 'Hypothesis not rejected'.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
test_statistic = -1.7

if test_statistic > 1.96 or test_statistic < -1.96:
    print('Hypothesis rejected with 5% significance level')
elif test_statistic > 1.645 or test_statistic < -1.645:
    print('Hypothesis rejected with 10% significance level')
else:
    print('Hypothesis not rejected')
```

</p>
</details>
<p>&nbsp;</p>

4) Create a list that contains at least 5 elements. Print out their elements using for loop.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
random_elements = [5, 4.5, True, 'Text', 6.1, 3.3]

for element in random_elements:
    print(element)
```

</p>
</details>
<p>&nbsp;</p>

5) Create a list that contains only numeric data types (5 elements or more). Iterate over the list and print each item multiplied by 2.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
competition_scores = [10.5, 11.1, 9.6, 11.2, 10.2, 12.4, 8.6, 9.0]

for score in competition_scores:
    print(score*2)
```

</p>
</details>
<p>&nbsp;</p>

6) The longest word in english is 'pneumonoultramicroscopicsilicovolcanoconiosis'. Try to calculate how long is this word. Use the for loop that iterates over the string. Create a predefined variable i=0, that will get incremented by 1 every iteration.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
i = 0
longest_word = 'pneumonoultramicroscopicsilicovolcanoconiosis'

for character in longest_word:
    i+=1
print(i)
```

</p>
</details>
<p>&nbsp;</p>

7) Iterate over a range 0 to 20 using for and range. Print out each element.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
for i in range(21):
    print(i)
```

</p>
</details>
<p>&nbsp;</p>

8) Iterate over a range 0 to 20 using while. Print out each element.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
i = 0
while i <= 20:
    print(i)
    i+=1
```

</p>
</details>
<p>&nbsp;</p>

9) Iterate over a range 0 to 20 and print only uneven numbers.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
for i in range(21):
    if i%2 != 0:
        print(i)
    else:
        continue
```

</p>
</details>
<p>&nbsp;</p>

10) Iterate over a range 0 to 20 and print only even numbers.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
for i in range(21):
    if i%2 == 0:
        print(i)
    else:
        continue
```

</p>
</details>
<p>&nbsp;</p>

11) Iterate over a range 0 to 20 and print only numbers that are divisible by 3.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
for i in range(21):
    if i%3 == 0:
        print(i)
    else:
        continue
```

</p>
</details>
<p>&nbsp;</p>

12) Iterate over a range 0 to 40 and print every number. Terminate the loop when the number is larger than 30.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
for i in range(41):
    if i>30:
        break
    else:
        print(i)
```

</p>
</details>
<p>&nbsp;</p>
