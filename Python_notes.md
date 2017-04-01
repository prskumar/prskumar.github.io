# Python (from http://www.python-course.eu/object_oriented_programming.php)

1.  ## Background:
    * General purpose high level language and Portable

    * Object oriented , imperative and functional style

    * Source code is compiled into byte codes which is an intermediate language that run on virtual machine executing machine code corresponding to each byte

    * Since its interpreted language rather than compiled language – hence might take up more CPU time

    * [link](http://www.python-course.eu/images/py_pyc_overview.gif)
    * link : ![Alt](http://www.python-course.eu/images/py_pyc_overview.gif)


2.  ## Basic Programming constructs:
  *  Programs get structured through indentation, this means that code blocks are defined by their indentation. Okay that's what we expect from any program code, isn't it? Yes, but in the case of Python it's a language requirement not a matter of style. This principle makes it easier to read and understand other people's Python code.
  * [Structure](http://www.python-course.eu/images/blocks.png)

  * Structure: ![Alt](http://www.python-course.eu/images/blocks.png)

  * Python follows the usual order of operation in expression. The standard order of operations is expressed in the following enumeration

      * exponents and roots
      * multiplication and division
      * addition and subtraction


3. ## Data Types in Python:

    ###  Variables
    * a variable is something which can change. A variable is a way of referring to a memory location used by a computer program. A variable is a symbolic name for this physical location
    * One of the main differences between _Python_ and _strongly-typed languages_ like C, C++ or Java is the way it deals with types.Declaration of variables is not required in Python. If there is need of a variable, you think of a name and start using it as a variable which can be changed during program execution(both type and value)
    *  **=** is an assignment operation where **==** is equal to operator
    * Changing Data Types and Storage Locations

        `i = 42			# data type is implicitly set to integer
        i = 42 + 0.11		# data type is changed to float
        i = "fourty"		# and now it will be a string`
    *  What's happening, when we make assignments? Let's look at the following piece of code:

       x = 3

       y = x

       y = 2

       *   Python chooses a memory location for x and saves the integer value 3. The second assignment is more worthwhile: Intuitively, you may assume that Python will find another location for the variable y and will copy the value of 3 in this place. But Python goes his own way, which differs from our intuition and the ways of C and C++. As both variables will have the same value after the assignment, Python lets y point to the memory location of x.
       The critical question arises in the next line of code. Y will be set to the integer value 2. What will happen to the value of x? C programmers will assume that x will be changed to 2 as well, because we said before that y "points" to the location of x. But this is not a C-pointer. Because x and y will not share the same value anymore, y gets his or her own memory location, containing 2 and x sticks to 3, as can be seen in the animated graphics on the right side.

       *  But what we said before can't be determined by typing in those three lines of code. But how can we prove it? The identity function id() can be used for this purpose. Every instance (object or variable) has an identity, i.e. an integer which is unique within the script or program, i.e. other objects have different identities.
       So, let's have a look at our previous example and how the identities will change:
                  `>>> x = 3
                   >>> print id(x)
                   157379912
                   >>> y = x
                   >>> print id(y)
                   157379912
                   >>> y = 2
                   >>> print id(y)
                   157379924
                   >>> print id(x)
                   157379912
                   >>>`

    ### Numbers:
          * integer (eg: 4231)
          * long integer(eg: 42000000**L**)
          * float (eg: 42.11)
          * Complex number(eg: x= 3+4j)

    ### Strings:    
          *  string in Python consists of a series or sequence of characters - letters, numbers, and special characters. Strings can be indexed - often synonymously called subscripted as well. Similar to C, the first character of a string has the index 0

          > character : ![Alt](http://www.python-course.eu/images/string_indices.gif)
          It's possible to start counting the indices from the right. In this case negative numbers are used, starting with -1 for the most right character.

          > index :
          ![Alt](http://www.python-course.eu/images/string_indices_negative.png)

          ![Alt](http://www.python-course.eu/images/string_aufbau.gif)

## Operators

    * These operations (operators) can be applied to all numeric types:

|Operator|	Description|	Example|
|--------:|-------------:|---------:|
|+, |-	Addition, Subtraction	|10 -3
|*, /, %|	Multiplication, Division, Modulo|	27 % 7 Result: 6|
|//  |Truncation Division (also known as floordivision or floor division) The result of this division is the integral part of the result, i.e. the fractional part is truncated, if there is any. If both the divident and the divisor are integers, the result will be also an integer. If either the divident or the divisor is a float, the result will be the truncated result as a float.|>>>10 // 3 is 3 >>> 10.0 // 3 3.0|
|+x, -x|	Unary minus and Unary plus (Algebraic signs)|	-3
|~x	|Bitwise negation	|~3 - 4 Result: -8|
|**	|Exponentiation	|10 ** 3 Result: 1000
|or, and, not|	Boolean Or, Boolean And, Boolean Not	|(a or b) and c
|in	|"Element of"	|1 in [3, 2, 1]
|<, <=, >, >=, !=, ==|The usual comparison operators|	2 <= 3
|&,^|	Bitwise Or, Bitwise And, Bitwise XOR|	6 ^ 3
|<<, >>|	Shift Operators	|6 << 3|

## Conditional Statements:

  The general form of the if statement in Python looks like this:
  `if condition_1:
       statement_block_1
   elif condition_2:
       statement_block_2
   else:
       statement_block_3`

## Loops:
*  WHILE** Lopp:

  >  Similar to the if statement, the while loop of Python has also an optional else part. This is an unfamiliar construct for many programmers of traditional programming languages.The statements in the else part are executed, when the condition is not fulfilled anymore. Some might ask themselves now, where the possible benefit of this extra branch is. If the statements of the additional else part were placed right after the while loop without an else, they would have been executed anyway, wouldn't they. We need to understand a new language construct, i.e. the break statement, to obtain a benefit from the additional else branch of the while loop.

The general syntax of a while loop looks like this:

while condition:

statement_1

...

statement_n

else:

statement_1

...

statement_n

![Alt](http://www.python-course.eu/images/while_loop_with_else_break.png)

Sample code of the **While** loop:

    import random
    n = 20
    to_be_guessed = int(n * random.random()) + 1
    guess = 0
    while guess != to_be_guessed:
        guess = input("New number: ")
        if guess > 0:
            if guess > to_be_guessed:
                print "Number too large"
            else:
                print "Number too small"
        else:
            print "Sorry that you're giving up!"
            break
    else:
        print "Congratulation. You made it!"  

* **FOR** Loop
  >  We often need to go through all the elements of a list or perform an operation over a series of numbers. The Python for statement is the right tool to go easily through various types of lists and ranges.

      for variable in sequence:
      	Statement1
      	Statement2
      	...
      	Statementn
      else:
      	Else-Statement1
      	Else-Statement2
      	...
        Else-Statementm

        Generally, it is assumed that the Pythagorean theorem was discovered by Pythagoras that is why it has its name. But there is a debate whether the Pythagorean theorem might have been discovered earlier or by others independently. For the Pythagoreans, - a mystical movement, based on mathematics, religion and philosophy, - the integer numbers satisfying the theorem were special numbers, which had been sacred to them.

    These days Pythagorean numbers are not mystical anymore. Though to some pupils at school or other people, who are not on good terms with mathematics, they may still appear so.

    So the *definition is very simple:
    Three integers satisfying a2+b2=c2 are called Pythagorean numbers.*

    The following program calculates all Pythagorean numbers less than a maximal number.
    Remark: We have to import the math module to be able to calculate the square root of a number.

      #!/usr/bin/env python
      from math import sqrt
      n = raw_input("Maximal Number? ")
      n = int(n)+1
      for a in range(1,n):
          for b in range(a,n):
              c_square = a**2 + b**2
              c = int(sqrt(c_square))
              if ((c_square - c**2) == 0):
                  print a, b, c
    ![Alt](http://www.python-course.eu/images/pythagoras_proof.png)

### Lists in Python
* The list is a most versatile data type in Python. It can be written as a list of comma-separated items (values) between square brackets.
* Lists can have sublists as elements. These sublists may contain sublists as well, i.e. lists can be recursively constructed by sublist structures.

      >>> person = [["Marc","Mayer"],["17, Oxford Str", "12345","London"],"07876-7876"]
      >>> name = person[0]
      >>> print name
      ['Marc', 'Mayer']
      >>> first_name = person[0][0]
      >>> print first_name
      Marc
      >>> last_name = person[0][1]
      >>> print last_name
      Mayer
      >>> address = person[1]
      >>> street = person[1][0]
      >>> print street
      17, Oxford Str
      The next example shows a more complex list with a deeply structured list:
      >>> complex_list = [["a",["b",["c","x"]]]]
      >>> complex_list = [["a",["b",["c","x"]]],42]
      >>> complex_list[0][1]
      ['b', ['c', 'x']]
      >>> complex_list[0][1][1][0]
      'c'

### Tuples
* A tuple is an immutable list, i.e. a tuple cannot be changed in any way once it has been created.
  * Tuples are faster than lists.
  * If you know that some data doesn't have to be changed, you should use tuples instead of lists, because this protects your data against accidental changes.
  * _Tuples can be used as keys in dictionaries, while lists can't_.

In Python these data types(**list and tuples**) are called "sequence data types" or "sequential data types".

## Operations
### Slicing
  Python makes it very easy with its slice operator. Slicing is often better known as substring or substr
    >>> str = "Python is great"
    >>> first_six = str[0:6]
    >>> first_six
    'Python'
    Slicing works with three arguments as well. If the third argument is for example 3, only every third element of the list, string or tuple from the range of the first two arguments will be taken.

  If s is a sequential data type, it works like this:   _s[begin: end: step]_

### Length
    >>> txt = "Hello World"
    >>> len(txt)
    11
    >>> a = ["Swen", 45, 3.54, "Basel"]
    >>> len(a)
    4

### Concatenation of Sequences
    >>> colours1 = ["red", "green","blue"]
    >>> colours2 = ["black", "white"]
    >>> colours = colours1 + colours2
    >>> print colours
    ['red', 'green', 'blue', 'black', 'white']

### Repetitions
It's a kind of abbreviation for an n-times concatenation, i.e.

    str * 4
    is the same as
    str + str + str + str

## Dictionaries
A dictionary is an associative array (also known as hashes). Any key of the dictionary is associated (or mapped) to a value. The values of a dictionary can be any Python data type. So dictionaries are unordered **key-value-pairs.**
    >>> food = {"ham" : "yes", "egg" : "yes", "spam" : "no" }
    >>> food
    {'egg': 'yes', 'ham': 'yes', 'spam': 'no'}
    >>> food["spam"] = "yes"
    >>> food
    {'egg': 'yes', 'ham': 'yes', 'spam': 'yes'}
    >>>
Lists are ordered sets of objects, whereas dictionaries are unordered sets. But the main difference is that items in dictionaries are accessed via keys and not via their position

### Operators on Dictionaries

|Operator|  Explanation|
|---------:|----------:|
|len(d)|returns the number of stored entries, i.e. the number of (key,value) pairs.
|del d[k]|deletes the key k together with his value
|k in d|True, if a key k exists in the dictionary d
|k not in d|True, if a key k doesn't exist in the dictionary d

### Operations on Dictionaries

1.  Accessing non Existing Keys

If you try to access a key which doesn't exist, you will get an error message:

    >>> words = {"house" : "Haus", "cat":"Katze"}
    >>> words["car"]
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    KeyError: 'car'
    You can prevent this by using the "in" operator:
    >>> if "car" in words: print words["car"]
    ...
    >>> if "cat" in words: print words["cat"]
    ...
    Katze

2.  Copying dictionary

A dictionary can be copied with the method copy():

    >>> w = words.copy()
    >>> words["cat"]="chat"
    >>> print w
    {'house': 'Haus', 'cat': 'Katze'}
    >>> print words
    {'house': 'Haus', 'cat': 'chat'}
    The content of a dictionary can be cleared with the method clear(). The dictionary is not deleted, but set to an empty dictionary:
    >>> w.clear()
    >>> print w
    {}

3.  Update: Merging Dictionaries

What about concatenating dictionaries, like we did with lists? There is something similar for dictionaries: the update method
update() merges the keys and values of one dictionary into another, overwriting values of the same key:

    >>> w={"house":"Haus","cat":"Katze","red":"rot"}
    >>> w1 = {"red":"rouge","blau":"bleu"}
    >>> w.update(w1)
    >>> print w
    {'house': 'Haus', 'blau': 'bleu', 'red': 'rouge', 'cat': 'Katze'}

4.  Iterating over a Dictionary

No method is needed to iterate over a dictionary:

    for key in d:
    	print key

But it's possible to use the method **iterkeys()**:

    for key in d.iterkeys():
    	print key

The method **itervalues()** is a convenient way for iterating directly over the values:

    for val in d.itervalues():
    	print val

The above loop is of course equivalent to the following one:
    for key in d:
    	print d[key]

5.  Lists from Dictionaries

It's possible to create lists from dictionaries by using the methods items(), keys() and values(). As the name implies the method keys() creates a list, which consists solely of the keys of the dictionary. values() produces a list consisting of the values. items() can be used to create a list consisting of 2-tuples of (key,value)-pairs:

    >>> w={"house":"Haus","cat":"Katze","red":"rot"}
    >>> w.items()
    [('house', 'Haus'), ('red', 'rot'), ('cat', 'Katze')]
    >>> w.keys()
    ['house', 'red', 'cat']
    >>> w.values()
    ['Haus', 'rot', 'Katze']

6.  Dictionaries from Lists

We want to show you, how to turn lists into dictionaries, if these lists satisfy certain conditions.
We have two lists, one containing the dishes and the other one the corresponding countries:

    >>> dishes = ["pizza", "sauerkraut", "paella", "Hamburger"]
    >>> countries = ["Italy", "Germany", "Spain", "USA"]

Now we will create a dictionary, which assigns a dish to a country, of course according to the common prejudices. For this purpose we need the function zip(). The name zip was well chosen, because the two lists get combined like a zipper.

    >>> country_specialities = zip(countries, dishes)
    >>> print country_specialities
    [('Italy', 'pizza'), ('Germany', 'sauerkraut'), ('Spain', 'paella'), ('USA', 'Hamburger')]
    >>>
The variable country_specialities contains now the "dictionary" in the 2-tuple list form. This form can be easily transformed into a real dictionary with the function dict().

    >>> country_specialities_dict = dict(country_specialities)
    >>> print country_specialities_dict
    {'Germany': 'sauerkraut', 'Spain': 'paella', 'Italy': 'pizza', 'USA': 'Hamburger'}
    >>>

7.  Sets in Python

![Alt](http://www.python-course.eu/images/sets_with_notations.png)

The data type "set", which is a collection type, has been part of Python since version 2.4. A set contains an unordered collection of unique and immutable objects. The set data type is, as the name implies, a Python implementation of the sets as they are known from mathematics. This explains, why sets unlike lists or tuples can't have multiple occurrences of the same element.
Creating Sets

If we want to create a set, we can call the built-in set function with a sequence or another iterable object.

In the following example, a string is singularized into its characters to build the resulting set x:
    >>> x = set("A Python Tutorial")
    >>> x
    set(['A', ' ', 'i', 'h', 'l', 'o', 'n', 'P', 'r', 'u', 't', 'a', 'y', 'T'])
    >>> type(x)
    <type 'set'>
    >>>

We can pass a list to the built-in set function, as we can see in the following:

    >>> x = set(["Perl", "Python", "Java"])
    >>> x
    set(['Python', 'Java', 'Perl'])
    >>>

8.  Shallow and deep copy
* Copying a list
      >>> colours1 = ["red", "green"]
      >>> colours2 = colours1
      >>> colours2[1] = "blue"
      >>> colours1
      ['red', 'blue']

 * _Using the Method deepcopy from the Module copy_

      `from copy import deepcopy

      lst1 = ['a','b',['ab','ba']]

      lst2 = deepcopy(lst1)

      lst2[2][1] = "d"
      lst2[0] = "c";

      print lst2
      print lst1`

### Functions

* Functions are a construct to structure programs and are used to utilize code in more than one place in a program

The general syntax looks like this:

    def function-name(Parameter list):
        statements, i.e. the function body

        >>> def add(x, y):
...        """Return x plus y"""
...         return x + y
        >>>

The parameter list consists of none or more parameters. Parameters are called arguments, if the function is called. The function body consists of indented statements. The function body gets executed every time the function is called.
Parameter can be mandatory or optional.

* Calling a function
  * Call by value
    * In call-by-value, the argument expression is evaluated, and the result of this evaluation is bound to the corresponding variable in the function. So, if the expression is a variable, a local copy of its value will be used, i.e. the variable in the caller's scope will be unchanged when the function returns.

  * Call by reference
    * In call-by-reference evaluation, which is also known as pass-by-reference, a function gets an implicit reference to the argument, rather than a copy of its value. As a consequence, the function can modify the argument, i.e. the value of the variable in the caller's scope can be changed

  * [`*`]  in Function Calls
    * The following example demonstrates the usage of ** in a function call:
          >>> def f(a,b,x,y):
      ...     print(a,b,x,y)
      ...
              `>>> d = {'a':'append', 'b':'block','x':'extract','y':'yes'}
              >>> f(**d)
              ('append', 'block', 'extract', 'yes')
              and now in combination with *:
              >>> t = (47,11)
              >>> d = {'x':'extract','y':'yes'}
              >>> f(*t, **d)
              (47, 11, 'extract', 'yes')
              >>> `

#### Recursive Functions
* Recursion is a way of programming or coding a problem, in which a function calls itself one or more times in its body. Usually, it is returning the return value of this function call

* Now we come to implement the factorial in Python. It's as easy and elegant as the mathematical definition.
          def factorial(n):
              if n == 1:
                  return 1
              else:
                  return n * factorial(n-1)


*                 Let's have a look at an iterative version of the factorial function.
        `def iterative_factorial(n):
            result = 1
            for i in range(2,n+1):
                result *= i
            return result`

### Memoization and Decorators
* The term **memoization** was introduced by Donald Michie in the year 1968. It's based on the Latin word memorandum, meaning "to be remembered". It's not a misspelling of the word memorization, though in a way it has something in common. Memoisation is a technique used in computing to speed up programs. This is accomplished by memorizing the calculation results of processed input such as the results of function calls. If the same input or a function call with the same parameters is used, the previously stored results can be used again and unnecessary calculation are avoided.

Memoization can be explicitly programmed by the programmer, but some programming languages like Python provide mechanisms to automatically memoize functions


### File Management

* To read a file
  `fobj = open("ad_lesbiam.txt", "r")`
  `poem = open("ad_lesbiam.txt").readlines()` __this will read all the lines__
  `poem = open("ad_lesbiam.txt").read()`  __this will read all the content into string__
* To close a file
  `fobj.close()`
* Python offers for this purpose a module, which is called "pickle". With the algorithms of the pickle module we can serialize and de-serialize Python object structures. "Pickling" denotes the process which converts a Python object hierarchy into a byte stream, and "unpickling" on the other hand is the inverse operation, i.e. the byte stream is converted back into an object hierarchy. What we call pickling (and unpickling) is also known as "serialization" or "flattening" a data structure
      import pickle
      data = (1.4,42)
      output = open('data.pkl', 'w')
      pickle.dump(data, output)
      output.close()

### Modules
* A module in Python is just a file containing Python definitions and statements. The module name is moulded out of the file name by removing the suffix .py. For example, if the file name is fibonacci.py, the module name is fibonacci.
`>>> from fibonacci import fib, ifib`

* If you import a module, let's say "import abc", the interpreter searches for this module in the following locations and in the order given:
  1.  The directory of the top-level file, i.e. the file being executed.
  2.  The directories of PYTHONPATH, if this global variable is set.
  3.  standard installation path Linux/Unix e.g. in /usr/lib/python2.5.

* **Module Packages** - It's possible to put several modules into a Package. A directory of Python code is said to be a package.
A package is imported like a "normal" module.
Each directory named within the path of a package must also contain a file named `__init__.py`, or else your package import will fail.

### Lambda, filter, reduce and map

* **Lambda Operator**
  * The lambda operator or lambda function is a way to create small anonymous functions, i.e. functions without a name. These functions are throw-away functions, i.e. they are just needed where they have been created. Lambda functions are mainly used in combination with the functions filter(), map() and reduce()
  * The general syntax of a lambda function is quite simple:
  `lambda argument_list: expression`

      >>> a = [1,2,3,4]
      >>> b = [17,12,11,10]
      >>> c = [-1,-4,5,9]
      >>> map(lambda x,y:x+y, a,b)
      [18, 14, 14, 14]
      >>> map(lambda x,y,z:x+y+z, a,b,c)
      [17, 10, 19, 23]
      >>> map(lambda x,y,z:x+y-z, a,b,c)
      [19, 18, 9, 5]
  *   **filter()**    
      >>> a = [1,2,3,4]
      >>> b = [17,12,11,10]
      >>> c = [-1,-4,5,9]
      >>> map(lambda x,y:x+y, a,b)
      [18, 14, 14, 14]
      >>> map(lambda x,y,z:x+y+z, a,b,c)
      [17, 10, 19, 23]
      >>> map(lambda x,y,z:x+y-z, a,b,c)
      [19, 18, 9, 5]

  * **reduce()**
      >>> f = lambda a,b: a if (a > b) else b
      >>> reduce(f, [47,11,42,102,13])
      102
      >>>

![Alt](http://www.python-course.eu/images/reduce_diagram.png)
