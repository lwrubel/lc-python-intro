---
title: "Data Types and Type Conversion"
teaching: 10
exercises: 10
questions:
- "What kinds of data do programs store?"
- "How can I convert one type to another?"
objectives:
- "Explain key differences between integers and floating point numbers."
- "Explain key differences between numbers and character strings."
- "Use built-in functions to convert between integers, floating point numbers, and strings."
keypoints:
- "Every value has a type."
- "Use the built-in function `type` to find the type of a value."
- "Types control what operations can be done on values."
- "Strings can be added and multiplied."
- "Strings have a length (but numbers don't)."
- "Must convert numbers to strings or vice versa when operating on them."
- "Can mix integers and floats freely in operations."
- "Variables only change value when something is assigned to them."
---
## Every value has a type.

*   Every value in a program has a specific type.
*   Integer (`int`): whole numbers like 3 or -512.
*   Floating point number (`float`): fractional numbers like 3.14159 or -2.5.
*   Whole numbers may also be stored as floats, e.g. `1.0`, but `1.0` would still be stored as a `float`.
*   Character string (usually called "string", `str`): text.
    *   Written in either single quotes or double quotes (as long as they match).
    *   The quotation marks aren't printed using `print()`, but may appear when viewing a value in the Jupyter Notebook or other Python interpreter.

## Use the built-in function `type` to find the type of a value.

*   Use the built-in function `type` to find out what type a value has.
*   This works on variables as well.
    *   But remember: the *value* has the type --- the *variable* is just a label.
    *   When you change the value of a variable to a new data type, the results of `print(type(your_variable))` will change accordingly.

~~~
print(type(52))
~~~
{: .python}
~~~
<class 'int'>
~~~
{: .output}

~~~
title = "Wildlife of Costa Rica"
print(type(title))
~~~
{: .python}
~~~
<class 'str'>
~~~
{: .output}

## Types control what operations (or methods) can be performed on a given value.

*   A value's type determines what the program can do to it.

~~~
print(5 - 3)
~~~
{: .python}
~~~
2
~~~
{: .output}

~~~
print('hello' - 'h')
~~~
{: .python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-2-67f5626a1e07> in <module>()
----> 1 print('hello' - 'h')

TypeError: unsupported operand type(s) for -: 'str' and 'str'
~~~
{: .error}

## You can use the `+` and `*` operators on strings.

*   "Adding" character strings concatenates them.

~~~
full_name = 'Henriette' + ' ' + 'Avram'
print(full_name)
~~~
{: .python}
~~~
Henriette Avram
~~~
{: .output}

SKIP SKIP SKIP
*   Multiplying a character string by an integer _N_ creates a new string that consists of that character string repeated  _N_ times.
    *   Since multiplication is repeated addition.
* There are more ways that traditional math operators will work on other data types.  There isn't a perfect formula for figuring out what they do, so experimentation is valuable.

~~~
separator = '=' * 10
print(separator)
~~~
{: .python}
~~~
==========
~~~
{: .output}

## Strings have a length (but numbers don't).

*   The built-in function `len` counts the number of characters in a string.

~~~
print(len(full_name))
~~~
{: .python}
~~~
15
~~~
{: .output}

*   But numbers don't have a length (not even zero).

~~~
print(len(52))
~~~
{: .python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-3-f769e8e8097d> in <module>()
----> 1 print(len(52))

TypeError: object of type 'int' has no len()
~~~
{: .error}

## Must convert numbers to strings or vice versa when operating on them.

*   Cannot add numbers and strings.

~~~
print(1 + '2')
~~~
{: .python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-4-fe4f54a023c6> in <module>()
----> 1 print(1 + '2')

TypeError: unsupported operand type(s) for +: 'int' and 'str'
~~~
{: .error}

*   Not allowed because it's ambiguous: should `1 + '2'` be `3` or `'12'`?
*   Some types can be converted to other types by using the type name as a function.

~~~
print(1 + int('2'))
print(str(1) + '2')
~~~
{: .python}
~~~
3
12
~~~
{: .output}

This is useful for working with identifiers, other numbers that you want to work with.
They may actually be better handled as strings than numbers. For example for using regular expressions
on them. However, if you want to validate them, see if the check digit is right, that requires 
using them as an integer. 

## Can mix integers and floats freely in operations.

*   Integers and floating-point numbers can be mixed in arithmetic.
*   Python automatically converts integers to floats as needed.

~~~
print('half is', 1 / 2.0)
print('three squared is', 3.0 ** 2)
~~~
{: .python}
~~~
half is 0.5
three squared is 9.0
~~~
{: .output}

## Variables only change value when something is assigned to them.

*   If we make one cell in a spreadsheet depend on another,
    and update the latter, the former updates automatically.
*   This does **not** happen in programming languages.

~~~
year = 2019
next = 2019 + 1
year = 2000
print('year is', first, 'and next is', next)
~~~
{: .python}
~~~
year is 2000 and second is 2020
~~~
{: .output}

*   The computer reads the value of `year` when doing the multiplication,
    creates a new value, and assigns it to `next`.
*   After that, `next` does not remember where it came from.

> ## Fractions
>
> What type of value is 3.4?
> How can you find out?
>
> > ## Solution
> >
> > It is a floating-point number (often abbreviated "float").
> >
> > ~~~
> > print(type(3.4))
> > ~~~
> > {: .python}
> > ~~~
> > <class 'float'>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

MAYBE USE THIS DEPENDING ON TIME
> ## Choose a Type
>
> What type of value (integer, floating point number, or character string)
> would you use to represent each of the following?  Try to come up with more than one good answer for each problem.  For example, in  # 1, when would counting days with a floating point variable make more sense than using an integer?  
>
> 1. Number of days since the start of the year.
> 2. Time elapsed since the start of the year.
> 3. Call number of a book.
> 4. Standard book loan period.
> 5. Number of reference queries in a year.
> 6. Average library classes taught per semester.
>
> > ## Solution
> > 1. Integer  
> > 2. Float  
> > 3. String
> > 4. Integer  
> > 5. Integer  
> > 6. Float  
> {: .solution}
{: .challenge}


> ## Automatic Type Conversion
>
> What type of value is 3.25 + 4?
>
> > ## Solution
> >
> > It is a float:
> > integers are automatically converted to floats as necessary.
> >
> > ~~~
> > result = 3.25 + 4
> > print(result, 'is', type(result))
> > ~~~
> > {: .python}
> > ~~~
> > 7.25 is <class 'float'>
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


> ## Strings to Numbers
>
> Where reasonable, `float()` will convert a string to a floating point number,
> and `int()` will convert a floating point number to an integer:
>
> ~~~
> print("string to float:", float("3.4"))
> print("float to int:", int(3.4))
> ~~~
> {: .python}
>
> ~~~
> string to float: 3.4
> float to int: 3
> ~~~
> {: .output}
>
> **Note:** conversion is some times also called typecast.
>
> If the conversion doesn't make sense, however, an error message will occur
>
> ~~~
> print("string to float:", float("Hello world!"))
> ~~~
> {: .python}
>
> ~~~
> ---------------------------------------------------------------------------
> ValueError                                Traceback (most recent call last)
> <ipython-input-5-df3b790bf0a2> in <module>()
> ----> 1 print("string to float:", float("Hello world!"))
>
> ValueError: could not convert string to float: 'Hello world!'
> ~~~
> {: .error}
>
> Given this information, what do you expect the following program to do?
>
> What does it actually do?
>
> Why do you think it does that?
>
> ~~~
> print("fractional string to int:", int("3.4"))
> ~~~
> {: .python}
>
> > ## Solution
> > What do you expect this program to do? It would not be so unreasonable to
> > expect the Python `int` command to convert the string "3.4" to 3.4 and an
> > additional type conversion to 3. After all, Python performs a lot of other
> > magic - isn't that part of its charm?
> >
> > However, Python throws an error. Why? To be consistent, possibly. If you
> > ask Python to perform two consecutive typecasts, you must convert it
> > explicitly in code.
> >
> > ~~~
> > num_as_string = "3.4"
> > num_as_float = float(num_as_string)
> > num_as_int = int(num_as_float)
> > print(num_as_int)
> > ~~~
> > {: .python}
> > ~~~
> > 3
> > ~~~
> > {: .output}
> > We could also write it in a single line like this: `int(float("3.4"))`
> {: .solution}
{: .challenge}


