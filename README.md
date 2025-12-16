# Python-for-DevOps-Engineers

## Hello World

**_1.How to print "Hello World"?_**

- `print("Hello World")`

**_2.How to print "Hello Amazing" and then print "World" on the same line? (to clarify, you should use two print statements)_**

- `print("Hello Amazing", end=" ")`
- `print("World")`

**_3.The following program reads two numbers from the user_**
  - **_x = int(input())_**
  - **_y = int(input())_**
- **_Print the sum and the difference between the numbers_**

- `print(x + y)`
- `print(x - y)`

## Conditionals

**_4.Read a number from the user and check whether it's even. If it's even, print "yay". If it's not, print "nay"_**

- `x = int(input())`

- `if x % 2 == 0:`
-   `print("yay")`
- `else:`
-   `print("nay")`

## Loops

**_5.Given an integer (n), print all the numbers between 0 and n (including n)_**

- `for i in range(n + 1):`
-   `print(i)`

**_6.Given an integer (n), print all the numbers between 0 and n (including n) that are even_**

- `for i in range(n + 1):`
-  `if i % 2 == 0:`
-    `print(i)`

## Classes

**_7.Define a class that does nothing_**

- `class SomeClass:`
-    `pass`

**_8.True or False? If `c` is an instance of a class, then in `c.x = 1`, `x` is a variable of the value 1_**

- False. `x` is an attribute in the case `c.x = 1`

**_9.True or False? Every object in Python has attributes_**

- True. You can think on attributes as private dictionaries but instead of accessing them with `[]` or `.get`, they are accessed by using a dot.

**_10.True or False? As opposed to variables, attributes can't contain any Python object, only several selected types_**

- False. Like variables, attributes can contain any Python object.

## Strings

**_11.How to convert `"2 0 1 7"` to the list `[2, 0, 1, 7]`?_**

- `[int(i) for in in "2 0 1 7".split()]`

## Lists

**_12.How to remove duplicates from a given sorted list?_**

- `def remove_duplicates(sorted_list):`
-   `if not sorted_list:`
-      `return []`
-   `unique_elements = [sorted_list[0]]`
-   `for item in sorted_list[1:]:`
-     `if item != unique_elements[-1]:`
-       `unique_elements.append(item)`
-     `return unique_elements`

