# Methods

## Methods vs functions

A Python method is like a function but it is embedded in the object and it works for the object. Methodes are created and used to perform a specific task on a particular, signle object. Working with methods is very similar to working with functions.

```python
# Upper method that works on a string object
my_name = 'Max'
my_name_upper = my_name.upper()
my_name_upper
```

As you can see in the example above, to call a method you first type the object you want to use it on and add the name of the method you want to call after a dot. Sometimes you might want to use more then one methods on an object. You can use it either by using one method in each line of the code or by buiding a chain of methods in the same line.


```python
# Upper method that works on a string object
my_name_spaces = ' Max '
my_name_trimmed_upper = my_name.strip().upper()
my_name_trimmed_upper
```

## Useful methods

Python has a range of useful built in methods. Because methods will work with specific objects it makes sense to group them by data types.

#### Methods for Strings

```python
object.lower()
```

Converts characters to lowercase.

```python
object.proper()
```

Converts characters to propercase.

```python
object.upper()
```

Converts characters to uppercase.

```python
object.strip()
```

Removes leading and trailing whitespaces. Analogical to trim in Excel.

```python
object.replace(old, new)
```

Replaces old substring with a new substring.

```python
object.split(sub)
```

Splits a string based on the substring provided and converts it to a list.

```python
object.endswith(sub)
```

Checks if string ends with substring sub.

```python
object.startswith(sub)
```

Checks if string starts with substring sub.

```python
object.find(sub)
```

Returns the lowest index of the string where substring sub is found. If substring sub can not found -1 is returned.

```python
object.rfind(sub)
```

Returns the highest index of the string where substring sub is found. If substring sub can not found -1 is returned.

```python
object.count(sub)
```

Returns the number of occurrences of substring sub found in the string.

#### Methods for Lists

```python
object.append(x)
```

Add an item x to the end of the list.

```python
object.remove(x)
```

Remove the first item from the list whose value is equal to x.

```python
object.count(x)
```

Return the number of times x appears in the list.

```python
object.reverse()
```

Reverse the elements of the list in place.

#### Methods for Dictionaries

```python
object.keys()
```

Return a view of the dictionary’s keys.

```python
object.values()
```

Return a new view of the dictionary’s values.

## Exercises

1) Create a variable 'my_name' that contains your name. Based on this variable create 2 new variables: 'my_name_lower_case', 'my_name_upper_case'.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
my_name = 'Max'
my_name_lower_case = my_name.lower()
my_name_upper_case = my_name.upper()
```

</p>
</details>
<p>&nbsp;</p>

2) Create a string that will start and end with a space. Create another, trimmed, version of this string.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
some_string = ' Text '
some_string_trimmed = some_string.strip()
```

</p>
</details>
<p>&nbsp;</p>

3) Create a variable that contains a string saying 'My name is ...'. Then replace the 'word' name with the word 'surname' and your name with your surname. Can you think of a way of transforming the string in only one line of code?
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
my_name_sentence = 'My name is Max'

my_surname_sentence = my_name_sentence.replace('name', 'surname')
my_surname_sentence = my_surname_sentence.replace('Max', 'Kozlowski')

my_surname_sentence2 = my_name_sentence.replace('name', 'surname').replace('Max', 'Kozlowski')
```

</p>
</details>
<p>&nbsp;</p>

4) Henry Ford once said <i>Anyone who stops learning is old, whether at twenty or eighty. Anyone who keeps learning stays young. The greatest thing in life is to keep your mind young</i>. Split this sentence by spaces. Call it 'split_sentence'. What is the type of this object?
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
sentence = 'Anyone who stops learning is old, whether at twenty or eighty. Anyone who keeps learning stays young. The greatest thing in life is to keep your mind young.'

split_sentence = sentence.split(' ')
type(split_sentence)
```

</p>
</details>
<p>&nbsp;</p>

5) Try to count the number of occurrences of the word 'learning' in the sentence above. Do it in two ways: using the method count on the split_sentence list and manually looping through the list and counting the occurrences.
<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
split_sentence.count('learning')

x=0
for word in split_sentence:
  if word == 'learning':
    x+=1
```

</p>
</details>
<p>&nbsp;</p>

6) Python often features as one of the most loved languages in the programming community. In the 2018 StackOverflow survey, almost 70% Python developers expressed an interest in continuing working in this language. The top 3 of the survey looks as follows. Translate the table below into a dictionary in Python. Having created the dictionary, get its values and keys using the appropriate methods.

| Language  | Developers intersted in continuing developing in this language (%) |
| ------------- | ------------- |
| Rust  | 78.9  |
| Kotlin  | 75.1 |
| Python  | 68.0  |

<details><summary><i>Click to view the answer.</i></summary>
<p>

```python
loved_programming_languages = {'Rust':78.9, 'Kotlin':75.1, 'Python':68.0}
loved_programming_languages.keys()
loved_programming_languages.values()
```

</p>
</details>
<p>&nbsp;</p>
