    ---
title: "Built-in Functions and Help"
teaching: 15
exercises: 10
questions:
- "How can I use built-in functions?"
- "How can I find out what they do?"
- "What kind of errors can occur in programs?"
objectives:
- "Explain the purpose of functions."
- "Correctly call built-in Python functions."
- "Correctly nest calls to built-in functions."
- "Use help to display documentation for built-in functions."
- "Correctly describe situations in which SyntaxError and NameError occur."
keypoints:
- "Use comments to add documentation to programs."
- "A function may take zero or more arguments."
- "Commonly-used built-in functions include `max`, `min`, and `round`."
- "Functions may only work for certain (combinations of) arguments."
- "Functions may have default values for some arguments."
- "Use the built-in function `help` to get help for a function."
- "Every function returns something."
- "Python reports a syntax error when it can't understand the source of a program."
- "Python reports a runtime error when something goes wrong while a program is executing."
- "Fix syntax errors by reading the source code, and runtime errors by tracing the program's execution."
---
## Use comments to add documentation to programs.

~~~
# This sentence isn't executed by Python.
name = 'Library Carpentry'   # Neither is this comment - anything after '#' is ignored.
~~~
{: .python}

## A function may take zero or more arguments.

*   We have seen some functions already --- now let's take a closer look.
*   An *argument* is a value passed into a function.
*   Any arguments you want to pass into a function must go into the `()`
    * `print("I am an argument and must go here.")`
*   You must always use parentheses, because this is how Python knows you are calling a function.
    * You leave them empty if you don't want or need to pass any arguments in.
*   `len` takes exactly one.
*   `int`, `str`, and `float` create a new value from an existing one.
*   `print` takes zero or more.
    *   `print()` prints a blank line.

~~~
print()
~~~
{: .python}
~~~

~~~
{: .output}

## Commonly-used built-in functions include `max`, `min`, and `round`.

*   Use `max` to find the largest value of one or more values.
*   Use `min` to find the smallest.
*   Both work on character strings as well as numbers.
    *   "Larger" and "smaller" use (0-9, A-Z, a-z) to compare letters.
    *   This means that:
        *   `'a'` is smaller than `'b'`
        *   `'A'` is smaller than `'a'`
        *   `'0'` is smaller than `'a'`
    *   This is useful for ordering alphabetically.

~~~
print(max(1, 2, 3))
print(min('a', 'b', 'c'))
print(min('a', 'A'))
~~~
{: .python}
~~~
3
a
A
~~~
{: .output}

## Functions may only work for certain (combinations of) arguments.

*   `max` and `min` must be given at least one argument.
*   And they must be given things that can meaningfully be compared.

~~~
print(max(1, 'a'))
~~~
{: .python}
~~~
TypeError: unorderable types: str() > int()
~~~
{: .error}

## Functions may have default values for some arguments.

*   `round` will round off a floating-point number.
*   By default, rounds to zero decimal places.

~~~
round(3.712)
~~~
{: .python}
~~~
4
~~~
{: .output}

*   We can specify the number of decimal places we want.

~~~
round(3.712, 1)
~~~
{: .python}
~~~
3.7
~~~
{: .output}

## Use the built-in function `help` to get help for a function.

*   Every built-in function has online documentation.

~~~
help(round)
~~~
{: .python}
~~~
Help on built-in function round in module builtins:

round(...)
    round(number[, ndigits]) -> number

    Round a number to a given precision in decimal digits (default 0 digits).
    This returns an int when called with one argument, otherwise the
    same type as the number. ndigits may be negative.
~~~
{: .output}

## Python reports a syntax error when grammar rules (that's Python grammar, not English grammar) have been violated.

*   You've seen errors when you try to use a function incorrectly.
    * Can also have errors when you use punctuation incorrectly.
*   Python will run the program up until that point, but if the grammar of that line
    of code has produced an error, then the program will shut down with an error.

~~~
# Forgot to close the quotation marks around the string.
name = 'Adama
~~~
{: .python}
~~~
SyntaxError: EOL while scanning string literal
~~~
{: .error}

*   Look more closely at the error message:
~~~
print("hello world"
~~~
{: .python}
~~~
  File "<ipython-input-6-d1cc229bf815>", line 1
    print ("hello world"
                        ^
SyntaxError: unexpected EOF while parsing
~~~
{: .error}

*   The message indicates a problem on first line of the input ("line 1").
    *   In this case the "ipython-input" section of the file name tells us that
        we are working with input into IPython.
*   The `-6-` part of the filename indicates that
    the error occurred in cell 6 of our Notebook.
*   Next is the problematic line of code,
    indicating the problem with a `^` pointer.

## Python reports a runtime error when something goes wrong while a program is executing.

## Every function returns something.

*   Every function call produces some result.
*   If the function doesn't have a useful result to return,
    it usually returns the special value `None`.

~~~
result = print('example')
print('result of print is', result)
~~~
{: .python}
~~~
example
result of print is None
~~~
{: .output}


> ## Spot the Difference
>
> 1. Predict what each of the `print` statements in the program below will print.
> 2. Does `max(len(rich), poor)` run or produce an error message?
>    If it runs, does its result make any sense?
>
> ~~~
> start = "2018"
> end = "2020"
> print(max(len(start), end))
> ~~~
> {: .python}
>
> > ## Solution
> >
> > ~~~
> > TypeError: '>' not supported between instances of 'str' and 'int'
> > ~~~
>{: .solution}
{: .challenge}

