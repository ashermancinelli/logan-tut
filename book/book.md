
### Table of Contents

1. Intro
2. Data
3. Example Problem

### Intro

This should read like a short tutorial or intro textbook.
If you have any questions, feel free to let me know and I can clarify.

This tutorial is geared towards python, but most of these concepts will apply broadly.
This text contains lots of 'helpfully untrue' statements: simplifications that will help you understand a concept.
Python reads much like English, so when you don't understand something, think about it like a foreign language: infer meaning from context and try things out yourself.

To get started, you should already have downloaded and installed python.
You can install it from python's website (`https://www.python.org/downloads/`).
This let's you run python programs and installs some helpful stuff for you.
Just make sure to check the box to *add Python to your PATH*.

If you now press the *start* key and run the `cmd` program, you'll be taken to your *command prompt*.
If you then type the word `python` into your prompt, you will enter a python *interpreter*, which means that each line of code you type will be ran immediately.
For example, when I type `python` into my command prompt, I see something like this:
```bash
> python
Python 3.7.6 (default, Dec 30 2019, 19:38:28)
[Clang 11.0.0 (clang-1100.0.33.16)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
Now, anything you type will be ran as python code.
I will use this for many examples.

If you run into problems getting started, you can look up youtube videos on installing python.


### Data

Pretty much all of programming is changing data from one format to another, extracting new data from existing data, or automating something to do with data.

Each line of code will be turned into 1's and 0's and ran by the computer one way or another.
Try to think about this like you would any math concept; there are inputs and outputs.
The words you type into a file will change the 1's and 0's you feed into your computer, and in turn change how your computer behaves.

Let's look at some examples:

The line below is a comment; anything written after a '#' character will not be ran by the computer.
Rather, what you type after a '#' is to be read by humans writing or changing your code.
Good programmers usually write quite a few comments so that any other human reading the program knows what's going on.
```python
>>> # This line is is a comment
>>>
```

You can see that after running the comment, nothing happens.
Because the line starts with a '#', no 1's or 0's are sent to your computer.

Below are some numbers, like you're used to in math. They work as expected.

These are called *floating point numbers*, and they are basically just numbers with decimals.
```python
>>> 4.2
4.2
>>> 3.14159 
3.14159 
>>> 1e3     # Some scientific notation!
1000.0
```

Numbers like these are called *integers*, and they do not have decimals.
```python
>>> 3
3
>>> 1200
1200
```

We also have another data type called a *string*.
This is just a collection of letters and numbers that are treated only as literal text.
```python
>>> 'this is a string'
'this is a string'
>>> 'one string' + 'another string'
'one stringanother string'
>>> "a third string"
'a third string'
```

You can see that what's inside the `'` or `"` characters are treated as literal text, not variables or code.

You can do some basic math too:
```python
>>> 1 + 1
2
>>> 5 - 2
3
>>> 2 * 3       # Multiplecation
6
>>> 3 / 2       # Division
1.5
>>> 2 ** 3      # Exponents
8
>>> 3 // 2      # Rounded division
1
```

Let's extend the math comparison.
In math, as with programming, we have functions and variables.

```python
>>> x = 5   # This is a variable
>>> x
5
>>> x * 3
15
>>> x = 10
>>> x
10
>>> my_name = 'asher'
>>> 'My name is: ' + my_name
'My name is: asher'
>>> age = 22
>>> 'I am ' + age + ' years old'
'I am 22 years old'
>>> # Below are some functions
>>> def my_function():
...     print('You called my_function')
>>> my_function()
You called my_function
>>> def say_hello(name):
...     print('Hello there, ', name)
>>> say_hello('asher')
Hello there, asher
>>> say_hello('logan')
Hello there, logan
```

We've assigned the value `5` to the variable `x`, and then the value `10`, and then we set it to a string.
It should be apparent now that you can add values of different types.
Above I added an integer to some strings, and Python figured out the rest for us.
Note also that you can *call functions* by *passing parameters* into the functions.
Functions have inputs and outputs, just as in math.

Single numbers alone are not used as often as groups of numbers.
We can use a `list` for this:
```python
>>> x = [ 1, 2, 3 ]     # This is a list
>>> x
[1, 2, 3]
>>> x[0]    # Here we grab the first element of our list
1
>>> x[1]
2
>>> x[2]
3
```

You can see that we can use something called an 'index' to get a certain value out of our list.
Note also that the first element of the list has an index of `0`.
This means that the third element of the list has an index of `2`.
Indeces start at 0.
What happens if we try to get an index outside the range of the list?

```python
>>> x
[1, 2, 3]
>>> x[3]    # max index is 2!
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

We tried to get an element out of our list that doesn't exist!
Python gives us some helpful information about what went wrong.
These error messages will be very helpful later on when we try to figure out where we've made a mistake.

Let's extend the math analogy with a function.
As in math, a function takes some input and returns some output.

```python
>>> def double_me(x):
...     return x * 2
>>> double_me(3)
6
>>> z = double_me(7)
>>> z
14
```

Let's think about this for a moment.
We have defined a function, called `double_me`, which takes one input and returns one output, which is the input multiplied by two.
Then, we have assigned the output of `double_me(7)` to the variable `z`.
In this way, we can pass data around to different functions and modify our data.

There are some functions built-in to pythong that we don't have to write.
For example, the `print` function will become very useful.
```python
>>> x = 'My name '
>>> print(x)
My name
>>> y = 'is asher'
>>> print(x, y)
My name is asher
```

Here I open a file and look at what's inside it.
```python
>>> file = open('my_email.txt', 'r')
>>> file.read()
'my email: ashermancinelli@gmail.com'
```

Now, I did not write a function called `open`.
This is built in to python to make it easier for us to read, write, and modify files.
Python has lots of helpful built-in functions to make our lives easier.

What you should also notice is the `.` (dot or period) operator.
In the previous example, we set a variable (called `file`) to the output of a function call (`open`).
Then, in order to act on that variable, we *called a method* on it.
`read` is a function that is a part of the `file` variable.
We could have done the same thing in fewer lines like so:
```python
>>> open('my_email.txt', 'r').read()
'my email: ashermancinelli@gmail.com'
```

All data types in python have *methods* like these.
I would encourage you now to create a variable in your python interpreter, follow the variable name with a `.`, and press the *tab* key once or twice.
Python should show you some suggested methods that you are able to call on that variable.
For example,
```python
>>> some_variable = 'some string of characters'
>>> some_variable.
some_variable.capitalize(    some_variable.isdigit(       some_variable.rfind(
some_variable.casefold(      some_variable.isidentifier(  some_variable.rindex(
some_variable.center(        some_variable.islower(       some_variable.rjust(
some_variable.count(         some_variable.isnumeric(     some_variable.rpartition(
some_variable.encode(        some_variable.isprintable(   some_variable.rsplit(
some_variable.endswith(      some_variable.isspace(       some_variable.rstrip(
some_variable.expandtabs(    some_variable.istitle(       some_variable.split(
some_variable.find(          some_variable.isupper(       some_variable.splitlines(
some_variable.format(        some_variable.join(          some_variable.startswith(
some_variable.format_map(    some_variable.ljust(         some_variable.strip(
some_variable.index(         some_variable.lower(         some_variable.swapcase(
some_variable.isalnum(       some_variable.lstrip(        some_variable.title(
some_variable.isalpha(       some_variable.maketrans(     some_variable.translate(
some_variable.isascii(       some_variable.partition(     some_variable.upper(
some_variable.isdecimal(     some_variable.replace(       some_variable.zfill(
>>> some_variable.upper()
'SOME STRING OF CHARACTERS'
```

We can see that after pressing the *tab* key a couple times, python offered some suggested methods that we are able to call on a string variable.
I chose the `upper` method, but I encourage you to try some of the other builtin methods that work on strings.

If you are just reading this and are not able to run commands on your own machine, here are some examples.
```python
>>> variable = 'some string'
>>> variable.startswith('z')    # Does the string start with 'z'?
False
>>> variable.startswith('s')    # Does the string start with 's'?
True
>>> variable.count('s')         # How many 's' characters are in the variable?
2
>>> variable.count('x')         # How many 'x' characters are in the variable?
0
>>> variable.split(' ')         # Break the string into a list seperated by space characters
['some', 'string']
```

Sometimes we have to take an extra step to use code that someone else wrote.
For example, we might want to calculate the area of a circle with a radius of `2.4`.
We could create a variable for $\pi$, a function for `sin` and `cos` and `tan`...
However, someone else already has.
For that, we will *import* the *math library*.
```python
>>> import math
>>> math.pi
3.141592653589793
>>> math.e
2.718281828459045
>>> math.pi * (2.4 ** 2)
18.09557368467721
>>> math.sin(0.3)
0.29552020666133955
```

One of the primary reasons python is as popular as it is is because of how many libraries are written in python.
We will use many libraries in our programs.

2. Example Problem

As I wrote above, all programming is essentially changing data, gleaning new information from data, or automating some repetitive task.
Now, with some foundational knowledge underneath our metaphorical belts, let's tackle a real business problem that will save you time.
I will begin to use concepts that I have not yet addressed, however if you have read thus far I think you will be able to cope.
At this point, try not to think of the program as math, but rather as language.
When you don't understand what/how/why something is written the way it's been written, try to infer from context.
Feel free to alter all of the example files and see how changes in the code reflect in the behavior of the program.

At this point, you have only written code into the *interpreter*, like so:
```bash
> python
Python 3.7.6 (default, Dec 30 2019, 19:38:28)
[Clang 11.0.0 (clang-1100.0.33.16)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
Now we will be writing all of these individual commands into a file, and running the whole file as a collection of commands.
Nothing changes except that you will no longer see the output of each command unless you use the `print` function.

For example:
```bash
> python example1.py
Congratulations! You successfully ran your first python script.
```

Now if you open up the file `example1.py` in the folder `chapter1`, you'll see the commands that you just ran.
