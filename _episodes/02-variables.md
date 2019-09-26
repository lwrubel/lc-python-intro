---
title: "Variables and Assignment"
teaching: 10
exercises: 10
questions:
- "How can I store data in programs?"
objectives:
- "Write programs that assign values to variables and perform calculations with those values."
- "Correctly trace value changes in programs that use assignment."
keypoints:
- "Use variables to store values."
- "Use `print` to display values."
- "Variables persist between cells."
- "Variables must be created before they are used."
- "Variables can be used in calculations."
- "Use an index to get a single character from a string."
- "Use a slice to get a substring."
- "Use the built-in function `len` to find the length of a string."
- "Python is case-sensitive."
- "Use meaningful variable names."
---
## Use variables to store values.

*   Variables are names for values.
*   In Python the `=` symbol assigns the value on the right to the name on the left.
*   The variable is created when a value is assigned to it.
*   Here, Python assigns an age to a variable `age`
    and a name in quotation marks to a variable `building`.

(Adams was ready for occupancy December 2, 1938. So we'll say it's 81. )
~~~
building = 'Adams'
age = 81
~~~
{: .python}

*   Variable names:
    *   cannot start with a digit
    *   cannot contain spaces, quotation marks, or other punctuation
    *   *may* contain an underscore (typically used to separate words in long variable names)

## Use `print` to display values.

*   Python has a built-in function called `print` that prints things as text.
*   Call the function (i.e., tell Python to run it) by using its name.
*   Provide values to the function (i.e., the things to print) in parentheses.
*   To add a string to the printout, wrap the string in single quotations.
*   The values passed to the function are called 'arguments'

~~~
print(building, 'is', age, 'years old')
~~~
{: .python}
~~~
Adams is 81 years old
~~~
{: .output}

*   `print` automatically puts a single space between items to separate them.
*   And wraps around to a new line at the end.

## Variables must be created before they are used.

*   If a variable doesn't exist yet, or if the name has been mis-spelled,
    Python reports an error.
    *   Unlike some languages, which "guess" a default value.

~~~
print(num_floors)
~~~
{: .python}
~~~
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-1-c1fbb4e96102> in <module>()
----> 1 print(num_floors)

NameError: name 'num_floors' is not defined
~~~
{: .error}

*   The last line of an error message is usually the most informative.

> ## Variables Persist Between Cells
> Variables defined in one cell exist in all other cells once executed,
> so the relative location of cells in the notebook do not matter
> (i.e., cells lower down can still affect those above).
> Remember: Notebook cells are just a way to organize a program:
> as far as Python is concerned,
> all of the source code is one long set of instructions.
{: .callout}

## Variables can be used in calculations.

*   We can use variables in calculations just as if they were values.
    *   Remember, we assigned 121 to `age` a few lines ago.

~~~
age = age + 3
print('Age in three years:', age)
~~~
{: .python}
~~~
Age in three years: 84
~~~
{: .output}

## Use an index to get a single character from a string.

*   The characters (individual letters, numbers, and so on) in a string are
    ordered. For example, the string 'AB' is not the same as 'BA'. Because of
    this ordering, we can treat the string as a list of characters.
*   Each position in the string (first, second, etc.) is given a number. This
    number is called an index or sometimes a subscript.
*   Indices are numbered from 0 rather than 1.
*   Use the position's index in square brackets to get the character at that
    position.

(My example is for Field guide to the wildlife of Costa Rica)
~~~
call_num = 'QL228.C8 H46 2002'
print(call_num[0])
~~~
{: .python}
~~~
Q
~~~
{: .output}

## Use a slice to get a substring.

*   A part of a string is called a substring. A substring can be as short as a
    single character.
*   A slice is a part of a string (we'll learn about slices of other objects soon).
*   We take a slice by using `[start:stop]`, where `start` is replaced with the
    index of the first element we want and `stop` is replaced with the index of
    the element just after the last element we want.
*   Taking a slice does not change the contents of the original string. Instead,
    the slice is a copy of part of the original string.

~~~
print(call_num[0:4])
~~~
{: .python}
~~~
QL228
~~~
{: .output}

## Use the built-in function `len` to find the length of a string.

~~~
print(len('Laura'))
~~~
{: .python}
~~~
7
~~~
{: .output}

*   Nested functions are evaluated from the inside out,
    just like in mathematics.

## Python is case-sensitive.

*   Python thinks that upper- and lower-case letters are different,
    so `Name` and `name` are different variables.
*   There are conventions for using upper-case letters at the start of variable names
    so we will use lower-case letters for now
*   Use meaningful variable names to help other people understand what the program does.
*   The most important "other person" is your future self.

> ## Slicing
>
> What does the following program print?
>
> ~~~
> lib_name = 'Library of Congress'
> print('lib_name[1:3] is:', lib_name[1:3])
> ~~~
> {: .python}
>
> 1.  What does `lib_name[low:high]` do?
> 2.  What does `lib_name[low:]` (without a value after the colon) do?
> 3.  What does `lib_name[:high]` (without a value before the colon) do?
> 4.  What does `lib_name[:]` (just a colon) do?
> 5.  What does `lib_name[number:negative-number]` do?
>
> > ## Solution
> > ~~~
> > library_name[1:3] is: ib
> > ~~~
> > {: .output}
> > 1.  It will slice the string, starting at the `low` index and ending an element before the `high` index
> > 2.  It will slice the string, starting at the `low` index and stopping at the end of the string
> > 3.  It will slice the string, starting at the beginning on the string, and ending an element before the `high` index
> > 4.  It will print the entire string
> > 5.  It will slice the string, starting the `number` index, and ending a distance of the absolute value of `negative-number` elements from the end of the string
> {: .solution}
{: .challenge}

