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


