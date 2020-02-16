
### Index

1. Intro
2. Data
3. Example Problem

### Intro

This should read like a short tutorial or intro textbook.
If you have any questions, feel free to let me know and I can clarify.

This tutorial is geared towards python, but most of these concepts will apply broadly.
This text contains lots of 'helpfully untrue' statements: simplifications that will help you understand a concept.

To get started, you should already have downloaded and installed anaconda.
This let's you run python programs and installs some helpful stuff for you.
Downloading and installing may take about an hour, but if you just follow the installer's directions, most of the defaults should work fine for you.
After installing, press the 'start' button and search for the 'anaconda prompt' or something with a similar name, and run it.
This is called a 'command prompt', 'terminal', or 'shell', but don't be scared off - this is just a quick way to tell your computer what you would like to do.
If you then type the word `python` into your prompt, you will enter a python 'repl', which means that each line of code you type will be ran immediately.
For example, when I type `python` into my shell, I see something like this:
```bash
> python
Python 3.7.6 (default, Dec 30 2019, 19:38:28)
[Clang 11.0.0 (clang-1100.0.33.16)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
Now, anything you type will be ran as python code.
I will use this for many examples.


### Data

Pretty much all of programming is changing data from one format to another, exactracting new data from existing data, or automating something to do with data.

Each line of code will be turned into 1's and 0's and ran by the computer one way or another.
Try to think about this like you would any math concept; there are inputs and outputs.
The words you type into a file will change the 1's and 0's you feed into your computer, and in turn change how your computer behaves.

Let's look at some examples:

The line below is a comment; anything written after a '#' character will not be ran by the computer.
Rather, what you type after a '#' is to be read by humans writing or changing your code.
Good programmers usually write quite a few comments so that any other human reading the program knows what's going on.
```python
>>> # This line's is a comment
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
```

Numbers like these are called *integers*, and they do not have decimals.
```python
>>> 3
3
>>> 1200
1200
>>> 1e3     # Some scientific notation!
1000.0
```

We also have another data type called a *string*.
This is just a collection of letters or numbers that are not variables, but are treated only as literal text.
```python
>>> 'this is a string'
'this is a string'
>>> 'one string' + 'another string'
'one stringanother string'
>>> "a third string"
"a third string"
```

You can see that what's inside the `'` or `"` characters are treated as literal text, not variables or code.

You can do some basic math too:
```python
>>> 1 + 1
2
>>> 5 - 2
3
>>> 2 * 3
6
>>> 3 / 2
1.5
```

Let's extend the math comparison.
In math, as with programming, we have functions and variables.

```python
>>> x = 5
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
```

We've assigned the value `5` to the variable `x`, and then the value `10`, and then we set it to a string.

Single numbers alone are not used as often as groups of numbers.
We can use a `list` for this:
```python
>>> x = [ 1, 2, 3 ]
>>> x
[1, 2, 3]
>>> x[0]
1
>>> x[1]
2
>>> x[2]
3
```

You can see that we can use something called an 'index' to get a certain value of a list.
Note also that the first element of the list has an index of `0`.
This means that the third element of the list has an index of `2`.
What happens if we try to get an index outside the range of the list?

```python
>>> x
[1, 2, 3]
>>> x[3]    # max index is 2!
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

Python gives us some helpful information about what went wrong.
This will be very helpful later on when we try to figure out where we've made a mistake.

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

Let's try something more useful.
Here I open a file and look at what's inside it.
```python
>>> file = open('my_email.txt', 'r')
>>> file.read()
'my email: ashermancinelli@gmail.com'
```

Now, I did not write a function called `open`.
This is built in to python to make it easier for us to read, write, and modify files.
Python has lots of helpful built-in functions to make our lives easier.

2. Example Problem

As I wrote above, all programming is essentially changing data, gleaning new information from data, or automating some repetitive task.
