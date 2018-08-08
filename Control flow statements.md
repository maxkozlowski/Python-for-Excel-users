# Control flow statements

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
