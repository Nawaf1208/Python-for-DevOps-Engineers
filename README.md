# Python-for-DevOps-Engineers

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

![](Python.png)  

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

## OOP

**_13.Explain inheritance and how to use it in Python_**

- Inheritance is a fundamental concept in Object-Oriented Programming (OOP) where a new class, called the child class (or subclass/derived class), derives properties and methods from an existing class, called the parent class (or superclass/base class).

- This allows for:
  - 1.**Code Reusability**: Properties and methods defined in the parent class are available in the child class.
  - 2.**Creating a hierarchy**: Modeling an "is-a" relationship (e.g., a "Dog" is a "Mammal").

- To create a child class that inherits from a parent class, you specify the parent class name inside parentheses when defining the child class:
- `class Animal:`
-   `def __init__(self, name):`
-     `self.name = name`
-   `def speak(self):`
-     `return f"{self.name} makes a sound."

-   `class Dog(Animal):`
-     `def speak(self):
-       `parent_sound = super().speak()
-       `retun f"{self.name} barks! ({parent_sound})"

-    `my_dog = Dog("Buddy")`
-    `print(my_dog.speak())`
     
**_14.Explain and demonstrate class attributes & instance attributes_**

- In the following block of code `x` is a class attribute while `self.y` is a instance attribute

- `class MyClass(object):`
-    `x = 1`
-
-    `def __init__(self, y):`
-        `self.y = y`

## Exceptions

**_15.What is an error? What is an exception? What types of exceptions are you familiar with?_**

- Note that you generally don't need to know the compiling process but knowing where everything comes from and giving complete answers shows that you truly know what you are talking about.

- Generally, every compiling process have a two steps.
  - Analysis
  - Code Generation.

- Analysis can be broken into:
  - 1. Lexical analysis   (Tokenizes source code)
  - 2. Syntactic analysis (Check whether the tokens are legal or not, tldr, if syntax is correct)

               for i in 'foo'
                          `^`
             SyntaxError: invalid syntax

        We missed ':'


  - 3. Semantic analysis  (Contextual analysis, legal syntax can still trigger errors, did you try to divide by 0, hash a mutable object or use an undeclared function?)

                 1/0
                ZeroDivisionError: division by zero

- These three analysis steps are the responsible for error handlings.

- The second step would be responsible for errors, mostly syntax errors, the most common error.

- The third step would be responsible for Exceptions.

- As we have seen, Exceptions are semantic errors, there are many builtin Exceptions:

        ImportError
        ValueError
        KeyError
        FileNotFoundError
        IndentationError
        IndexError
        ...

- You can also have user defined Exceptions that have to inherit from the `Exception` class, directly or indirectly.

    Basic example:

      class DividedBy2Error(Exception):
        def __init__(self, message):
            self.message = message


      def division(dividend,divisor):
          if divisor == 2:
              raise DividedBy2Error('I dont want you to divide by 2!')
          return dividend / divisor

      division(100, 2)

      >>> __main__.DividedBy2Error: I dont want you to divide by 2!

**_16.Explain Exception Handling and how to use it in Python_**

- Exceptions: Errors detected during execution are called Exceptions.

- Handling Exception: When an error occurs, or exception as we call it, Python will normally stop and generate an error message.

- Exceptions can be handled using `try` and `except` statement in python.

- Example: Following example asks the user for input until a valid integer has been entered.

- If user enter a non-integer value it will raise exception and using except it will catch that exception and ask the user to enter valid integer again.

- `while True:`
-    `try:`
-        `a = int(input("please enter an integer value: "))`
-        `break`
-    `except ValueError:`
-        `print("Ops! Please enter a valid integer value.")`

**_17.What is the result of running the following function?_**

- `def true_or_false():`
-    `try:`
-        `return True`
-    `finally:`
-        `return False`

- False

## Built-in Functions

**_19.Explain the following built-in functions (their purpose + use case example):_**
- **_repr_**
- **_any_**
- **_all_**

- 1.`repr()`
  - Returns a "printable" string representation of an object that should look like a valid Python expression (used for debugging/logging).
  - Seeing the "true" value of a variable (e.g., distinguishing between a string and its content).
    - `s = "Hello"`
    - `print(repr(s))`
    - `# Output: 'Hello'`
   
- 2.`any()`
  - Returns `True` if at least one element in an iterable is true. If the iterable is empty, it returns `False`.
  - Checking if any item in a list meets a condition.
    - `results = [False, 0, "Exists", False]`
    - `print(any(results))`
    - `# Output: True`
   
- 3.`all()`
  - Returns `True` if all elements in an iterable are true (or if the iterable is empty). 
  - Ensuring every requirement in a checklist is completed.
    - `scores = [100, 95, 88, 92]`
    - `print(all(s > 80 for s in scores))`
    - `# Output: True`

**_20.What is the difference between repr function and str?_**

- **Reconstruction**: Ideally, `repr()` should return a string that looks like the code used to create the object (so `eval(repr(obj)) == obj`).

- **Fallback Behavior**: If you don't define `__str__` in a class, Python will use `__repr__` as a backup. However, it does not work the other way around.

- **Containers**: When you print a list or dictionary, Python uses `repr()` for the items inside, even if you called `str()` on the container itself.

**_21.What is the __call__ method?_**

- It is used to emulate callable objects. It allows a class instance to be called as a function.

  - Example code
    - `class Foo:`
    -   `def __init__(self: object) ->  None:`
    -     `pass`
    -   `def __call__(self: object) -> None:`
    -     `print("Called!")`

    - `f = Foo()`
    - `f()`
  - Result:
    - `Called!`

**_22.Do classes has the __call__ method as well? What for?_**

- Yes, classes can have a `__call__` method. Defining `__call__` allows an instance of a class to be called like a regular function (using parentheses). It essentially turns an object into a callable.

- **Maintaining State**: To create "functions" that remember data between calls without using global variables.
- **Functional Programming**: When you need an object to behave like a function (e.g., for decorators or callbacks) but still need the structure of a class.

**_23.What _ is used for in Python?_**

- 1.Translation lookup in i18n
- 2.Hold the result of the last executed expression or statement in the interactive interpreter.
- 3.As a general purpose "throwaway" variable name. For example: x, y, _ = get_data() (x and y are used but since we don't care about third variable, we "threw it away").

**_24.Explain what is GIL_**

- Python Global Interpreter Lock (GIL) is a type of process lock which is used by python whenever it deals with processes. Generally, Python only uses only one thread to execute the set of written statements. This means that in python only one thread will be executed at a time.

**_25.What is Lambda? How is it used?_**

- A lambda expression is an 'anonymous' function, the difference from a normal defined function using the keyword `def` is the syntax and usage.

- The syntax is:

- `lambda[parameters]: [expresion]`

- Examples:
  - A lambda function add 10 with any argument passed.
    - `x = lambda a: a + 10`
    - `print(x(10))`

  - An addition function
    - `addition = lambda x, y: x + y`
    - `print(addition(10, 20))`

  - Squaring function
    - `square = lambda x : x ** 2`
    - `print(square(5))`

- Generally it is considered a bad practice under PEP 8 to assign a lambda expresion, they are meant to be used as parameters and inside of other defined functions.

## Properties

**_26.Are there private variables in Python? How would you make an attribute of a class, private?_**

- Technically, no. Python does not have strict "private" variables like Java or C++. All attributes are technically accessible.

- However, Python uses naming conventions to signal intent:
  - 1.**Protected (Internal Use)**: Prefix an attribute with a single underscore `_`
    - `self._value = 10`
  - 2.**Private (Name Mangling)**: Prefix an attribute with a double underscore `__`
    - `self.__secret = 42`
   
**_27.Explain the following:_**
- 1.**_getter_** -> The Getter retrieves the value of a private attribute.
  - `@property`
  - Allows read-access and data formatting before returning.
- 2.**_setter_** -> The Setter updates the value of an attribute.
  - `@<attribute_name>.setter`
  - Enables validation (e.g., ensuring a price isn't negative) before saving data.
- 3.**_deleter_** -> The Deleter handles the cleanup when an attribute is deleted using `del`
  - `@<attribute_name>.deleter`
  - Useful for logging deletions or resetting related values.

**_28.Explain what is @property_**

- The `@property` decorator is a built-in tool that turns a class method into a "virtual" attribute. It allows you to access a method's return value using simple dot notation (e.g., `obj.price`) instead of calling it like a function (`obj.price()`). This is primarily used to implement encapsulation: you can start with a simple public attribute and later wrap it in logic (like validation or logging) without changing the external API of your class.

**_29.How do you swap values between two variables?_**

- `x, y = y, x`

**_30.Explain the following object's magic variables:_**
- **_dict_** - A magic attribute that stores an object's writable attributes in a dictionary format.
  - It maps attribute names (keys) to their current values (values).
 
**_31.Write a function to return the sum of one or more numbers. The user will decide how many numbers to use_**

- First you ask the user for the amount of numbers that will be use. Use a while loop that runs until amount_of_numbers becomes 0 through subtracting amount_of_numbers by one each loop. In the while loop you want ask the user for a number which will be added a variable each time the loop runs.

- `def return_sum():`
-   `amount_of_numbers = int(input("How many numbers? "))`
-   `total_sum = 0`
-   `while amount_of_numbers != 0:`
-     `numm = int(input("Input a number. "))`
-     `total_sum += num`
-     `amount_of_numbers -= 1`
-   `return total_sum`

**_32.Print the average of [2, 5, 6]. It should be rounded to 3 decimal places_**

- `li = [2, 5, 6]`
- `print("{0:.3f}".format(sum(li)/len(li)))`

## Lists

**_33.What is a tuple in Python? What is it used for?_**

- A tuple is a built-in data type in Python. It's used for storing multiple items in a single variable.

**_34.List, like a tuple, is also used for storing multiple items. What is then, the difference between a tuple and a list?_**

- List, as opposed to a tuple, is a mutable data type. It means we can modify it and at items to it.

**_35.How to add the number 2 to the list `x = [1, 2, 3]`_**

- `x.append(2)`

**_36.How to get the last element of a list?_**

- `some_list[-1]`

**_37.How to add the items of `[1, 2, 3]` to the list `[4, 5, 6]`?_**

- `x = [4, 5, 6]` `x.extend([1, 2, 3])`
- Don't use append unless you would like the list as one item.

**_38.How to remove the first 3 items from a list?_**

- `my_list[0:3] = []`

**_39.How to insert an item to the beginning of a list? What about two items?_**

- One item:
  - `numbers = [1, 2, 3, 4, 5]`
  - `numbers.insert(0, 0)`
  - `print(numbers)`

- Multiple items or list:
  - `numbers_1 = [2, 3, 4, 5]`
  - `numbers_2 = [0, 1]`
  - `numbers_1 = numbers_2 + numbers_1`
  - `print(numbers_1)`
 
**_40.How to sort list by the length of items?_**

- `sorted_li = sorted(li, key=len)`

- Or without creating a new list:
  - `li.sort(key=len)`
 
**_41.Do you know what is the difference between list.sort() and sorted(list)?_**

- `sorted(list)` will return a new list (original list doesn't change)
- `list.sort()` will return None but the list is change in-place
- `sorted()` works on any iterable (Dictionaries, Strings, ...)
- `list.sort()` is faster than sorted(list) in case of Lists

**_42.Convert every string to an integer: `[['1', '2', '3'], ['4', '5', '6']]`_**

- `nested_li = [['1', '2', '3'], ['4', '5', '6']]`
- `[[int(x) for x in li] for li in nested_li]`

**_43.How to merge two sorted lists into one sorted list?_**

- `sorted(li1 + li2)`

- Another way:

- `i, j = 0`
- `merged_li = []`

- `while i < len(li1) and j < len(li2):`
-   `if li1[i] < li2[j]:`
-     `merged_li.append(li1[i])`
-     `i += 1`
-   `else:`
-     `merged_li.append(li2[j])`
-     `j += 1`

**_44.How to check if all the elements in a given lists are unique? so [1, 2, 3] is unique but [1, 1, 2, 3] is not unique because 1 exists twice_**

- There are many ways of solving this problem:
- `# Note: :list and -> bool are just python typings, they are not needed for the correct execution of the algorithm.`

- Taking advantage of sets and len:
  - `def is_unique(l:list) -> bool:`
  - `return len(set(l)) == len(l)`

- This one is can be seen used in other programming languages.
  - `def is_unique2(l:list) -> bool:`
    - `seen = []`

    - `for i in l:`
      - `if i in seen:`
        - `return False`
      - `seen.append(i)`
    - `return True`

- Here we just count and make sure every element is just repeated once.
  - `def is_unique3(l:list) -> bool:`
  -   `for i in l:`
  -     `if l.count(i) > 1:`
  -       `return False`
  -   `return True`

- This one might look more convulated but hey, one liners.

  - `def is_unique4(l:list) -> bool:`
  -   `return all(map(lambda x: l.count(x) < 2, l))`

**_45.You have the following function_**
- **_def my_func(li = []):_**
- **_li.append("hmm")_**
- **_print(li)_**

- If we call it 3 times, what would be the result each call?
  - ['hmm']
  - ['hmm', 'hmm']
  - ['hmm', 'hmm', 'hmm']
 
**_46.How to iterate over a list?_**

- `for item in some_list:`
-   `print(item)`

**_47.How to iterate over a list with indexes?_**

- `for i, item in enumerate(some_list):`
-   `print(i)`

**_48.How to start list iteration from 2nd index?_**

- Using range like this

  - `for i in range(1, len(some_list)):`
  -   `some_list[i]`

- Another way is using slicing
  - `for i in some_list[1:]:`
 
**_49.How to iterate over a list in reverse order?_**

- Method 1
  - `for i in reversed(li):`
  -   `...`

- Method 2
  - `n = len(li) - 1`
  - `while n > 0:`
    - `...`
    - `n -= 1`
   
**_50.Sort a list of lists by the second item of each nested list_**

- `li = [[1, 4], [2, 1], [3, 9], [4, 2], [4, 5]]`
- `sorted(li, key=lambda l: l[1])`

- or

- `li.sort(key=lambda l: l[1)`

**_51.Combine [1, 2, 3] and ['x', 'y', 'z'] so the result is [(1, 'x'), (2, 'y'), (3, 'z')]_**

- `nums = [1, 2, 3]`
- `letters = ['x', 'y', 'z']`

- `list(zip(nums, letters))`

**_52.What is List Comprehension? Is it better than a typical loop? Why? Can you demonstrate how to use it?_**

- List comprehensions provide a concise way to create lists. Common applications are to make new lists where each element is the result of some operations applied to each member of another sequence or iterable, or to create a subsequence of those elements that satisfy a certain condition.

- It's better because they're compact, faster and have better readability.

  - For loop:
    - `number_lists = [[1, 7, 3, 1], [13, 93, 23, 12], [123, 423, 456, 653, 124]]`
    - `odd_numbers = []`
    - `for number_list in number_lists:`
    -   `for number in number_list:`
    -     `ifnumber % 2 == 0:`
    -       `odd_numbers.append(number)`
    - `print(odd_numbers)`

  - List comprehesion:
    - `number_lists = [[1, 7, 3, 1], [13, 93, 23, 12], [123, 423, 456, 653, 124]]`
    - `odd_numbers = [number for number_list in number_lists for number in number_list if number % 2 == 0]`
    - `print(odd_numbers)`
   
**_53.You have the following list: [{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}] Extract all type of foods. Final output should be: {'mushrooms', 'goombas', 'turtles'}_**

- `brothers_menu =  \`
- `[{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}]`

- `# "Classic" Way`
- `def get_food(brothers_menu) -> set:`
-   `temp = []`

-   `for brother in brothers_menu:`
-     `for food in brother['food']:`
-       `temp.append(food)`
-   `return set(temp)`

- `# One liner way (Using list comprehension)`
- `set([food for bro in x for food in bro['food']])`

## Dictionaries

**_54.How to create a dictionary?_**

- `my_dict = dict(x=1, y=2) OR my_dict = {'x': 1, 'y': 2} OR my_dict = dict([('x', 1), ('y', 2)])`

**_55.How to remove a key from a dictionary?_**

- `del my_dict['some_key'] you can also use `my_dict.pop('some_key')` which returns the value of the key.`

**_56.How to sort a dictionary by values?_**

- `{k: v for k, v in sorted(x.items(), key=lambda item: item[1])}`

**_57.How to sort a dictionary by keys?_**

- `dict(sorted(some_dictionary.items()))`

**_58.How to merge two dictionaries?_**

- `some_dict1.update(some_dict2)`

**_59.Convert the string "a.b.c" to the dictionary {'a': {'b': {'c': 1}}}_**

- `output = {}`
- `string = "a.b.c"`
- `path = string.split('.')`
- `target = reduce(lambda d, k: d.setdefault(k, {}), path[:-1], output)`
- `target[path[-1]] = 1`
- `print(output)`

## Common Algorithms Implementation

**_60.Can you implement "binary search" in Python?_**

- `def binary_search(arr, target):`
-   `low, high = 0, len(arr) - 1`

-   `while low <= high:`
-     `mid= (low + high) // 2`
-     `if arr[mid] == target:`
-       `return mid`
-     `elif arr[mid] < target:`
-       `low = mid + 1`
-     `else:`
-       `high = mid - 1`
-     `return -1`

## Files

**_61.How to write to a file?_**

- `with open('file.txt', 'w') as file:`
-   `file.write("My insightful comment")`

**_62.Sum all the integers in a given file_**

- `def sum_file_integers(filename):`
  - `with open(filename, 'r') as f:`
    - `return sum(int(w) for line in f for w in line.split() if w.isdigit())`

**_63.Print a random line of a given file_**

- `import random`
- `with open('file.txt', 'r') as f:`
  - `lines = f.readlines()`
  - `print(random.choice(lines).strip())`
 
**_64.Print every 3rd line of a given file_**

- `from itertools import islice`
- `with open('file.txt', 'r') as f:`
  - `for line in islice(f, 2, None, 3):`
    - `print(line.strip())`
   
**_65.Print the number of lines in a given file_**

- `with open('file.txt', 'r') as f:`
  - `print(len(f.readlines()))`
 
**_66.Print the number of of words in a given file_**

- `print(len(open('file.txt').read().split()))`

**_67.Can you write a function which will print all the file in a given directory? including sub-directories_**

- `from pathlib import Path`
- `def print_files(directory):`
  - `for path in Path(directory).rglob('*'):`
    - `if path.is_file():`
      - `print(path)`

- `print_files('your_directory_path')`

**_68.Write a dictionary (variable) to a file_**

- `import json`
- `with open('file.json', 'w') as f:`
  - `f.write(json.dumps(dict_var))`

## OS

**_69.How to print current working directory?_**

- `import os`
- `print(os.getcwd())`

**_70.Given the path `/dir1/dir2/file1` print the file name (file1)_**

- `import os`

- `print(os.path.basename('/dir1/dir2/file1'))`

# Another way
- `print(os.path.split('/dir1/dir2/file1')[1])`

**_71.Given the path `/dir1/dir2/file1`_**
- **_1. Print the path without the file name (/dir1/dir2)_**
- **_2. Print the name of the directory where the file resides (dir2)_**

- `import os`
- ## Part 1.
- # os.path.dirname gives path removing the end component
- `dirpath = os.path.dirname('/dir1/dir2/file1')`
- `print(dirpath)`

- ## Part 2.
- `print(os.path.basename(dirpath))`

**_72.How do you execute shell commands using Python?_**

- `import subprocess`

- # Simple command
- `subprocess.run(["ls", "-l"])`

- # Capture output to a variable
- `result = subprocess.run(["echo", "Hello World"], capture_output=True, text=True)`
- `print(result.stdout)`

**_73.How do you join path components? for example `/home` and `/luig` will result in `/home/luigi`_**

- `from pathlib import Path`

- `path = Path("/home") / "luigi"`
- `print(path)`

**_74.How do you remove non-empty directory?_**

- `import shutil`

- `shutil.rmtree('/path/to/directory')`

## Regex

**_75.How do you perform regular expressions related operations in Python? (match patterns, substitute strings, etc.)_**

- Using the re module

**_76.How to find all the IP addresses in a variable? How to find them in a file?_**

- `import re`

- `ip_pattern = r'\b(?:\d{1,3}\.){3}\d{1,3}\b'`
- `found_ips = []`

- `with open('server.log', 'r') as file:`
  - `for line in file:`
    - `found_ips.extend(re.findall(ip_pattern, line))`

## Strings

**_77.Find the first repeated character in a string_**

- While you iterate through the characters, store them in a dictionary and check for every character whether it's already in the dictionary.

- `def firstRepeatedCharacter(str):`
  - `chars = {}`
  - `for ch in str:`
    - `if ch in chars:`
      - `return ch`
    - `else:`
      - `chars[ch] = 0`
     
**_78.How to extract the unique characters from a string? for example given the input "itssssssameeeemarioooooo" the output will be "mrtisaoe"_**

- `x = "itssssssameeeemarioooooo"`
- `y = ''.join(set(x))`

**_79.Find all the permutations of a given string_**

- `def permute_string(string):`

  - `if len(string) == 1:`
    - `return [string]`

  - `permutations = []`
  - `for i in range(len(string)):`
    - `swaps = permute_string(string[:i] + string[(i+1):])`
    - `for swap in swaps:`
      - `permutations.append(string[i] + swap)`

  - `return permutations`

- `print(permute_string("abc"))`

**_80.How to check if a string contains a sub string?_**

- `text = "Hello, Luigi!"`

- `if "Luigi" in text:`
  - `print("Found it!")`
 
**_81.Find the frequency of each character in string_**

- `from collections import Counter`

- `text = "banana"`
- `frequency = Counter(text)`

- `print(frequency)`

**_82.Count the number of spaces in a string_**

- You can use the "count" method like this:
  - `ImAString.count(" ")`
 
**_83.Given a string, find the N most repeated words_**

- `import re`
- `from collections import Counter`

- `text = "apple banana apple cherry banana apple"`
- `n = 2`

- `words = re.findall(r'\w+', text.lower())`

- `most_common = Counter(words).most_common(n)`

- `print(most_common)`

**_84.Given the string (which represents a matrix) "1 2 3\n4 5 6\n7 8 9" create rows and colums variables (should contain integers, not strings)_**

- `matrix_str = "1 2 3\n4 5 6\n7 8 9"`

- `rows = [[int(x) for x in line.split()] for line in matrix_str.split('\n')]`

- `cols = list(zip(*rows))`

- `print(f"Rows: {rows}")`
- `print(f"Cols: {cols}")`

**_85.What is the result of each of the following?_**
- **_`', '.join(["One", "Two", "Three"])`_**
- **_`" ".join("welladsadgadoneadsadga".split("adsadga")[:2])`_**
- **_`"".join(["c", "t", "o", "a", "o", "q", "l"])[0::2]`_**

- `'One, Two, Three'`
- `'well done'`
- `'cool'`

**_86.If `x = "pizza"`, what would be the result of `x[::-1]`?_**

- It will reverse the string, so x would be equal to `azzip`.

**_87.Reverse each word in a string (while keeping the order)_**

- `text = "Hello Luigi"`

- `result = " ".join(word[::-1] for word in text.split())`

- `print(result)`

**_88.What is the output of the following code: `"".join(["a", "h", "m", "a", "h", "a", "n", "q", "r", "l", "o", "i", "f", "o", "o"])[2::3]`_**

- mario

## Iterators

**_89.What is an iterator?_**

- An iterator is an object that allows you to traverse through a collection (like a list) one element at a time. In Python, it is any object that implements the Iterator Protocol.

- The Iterator Protocol
- An object is an iterator if it has these two methods:
  - `__iter__()`: Returns the iterator object itself.
  - `__next__()`: Returns the next value. Raises StopIteration when no items are left.

## Misc

**_90.Explain data serialization and how do you perform it with Python_**

- Data serialization is the process of converting complex objects (like lists, dictionaries, or classes) into a byte stream or string format that can be easily stored in a file or transmitted over a network. Deserialization is the reverse process.

- JSON
  - `import json`
  - `data = {"id": 1, "name": "Luigi"}`
  - `serialized = json.dumps(data)`

- Pickle
  - `import pickle`
  - `serialized = pickle.dumps(data)`
 
**_91.How do you handle argument parsing in Python?_**

- `import argparse`

- `parser = argparse.ArgumentParser(description="A simple script")`

- `parser.add_argument("name", help="Your name")`  
- `parser.add_argument("-a", "--age", type=int, help="Age")`

- `args = parser.parse_args()`

- `print(f"Hello {args.name}, you are {args.age}")`

**_92.What is a generator? Why using generators?_**

- A generator is a special type of iterator defined by a function that uses the `yield` keyword instead of `return`. When called, it doesn't execute the code immediately; instead, it returns a generator object that produces values one at a time on demand. Each time `yield` is reached, the function's state is "frozen," allowing it to resume exactly where it left off during the next iteration.

- The primary reason to use generators is memory efficiency. Unlike lists, which store all elements in RAM simultaneously, generators use lazy evaluation, calculating each item only when requested. This makes them ideal for processing massive datasets, reading large files, or representing infinite sequences where storing the entire collection would be impossible.

**_93.What would be the output of the following block?_**
**_- `for i in range(3, 3):`_**
  **_- `print(i)`_**

- No output
