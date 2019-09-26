---
title: "For Loops"
teaching: 10
exercises: 15
questions:
- "How can I make a program do many things?"
objectives:
- "Explain what for loops are normally used for."
- "Trace the execution of a simple (unnested) loop and correctly state the values of variables in each iteration."
- "Write for loops that use the Accumulator pattern to aggregate values."
keypoints:
- "A *for loop* executes commands once for each value in a collection."
- "The first line of the `for` loop must end with a colon, and the body must be indented."
- "Indentation is always meaningful in Python."
- "A `for` loop is made up of a collection, a loop variable, and a body."
- "Loop variables can be called anything (but it is strongly advised to have a meaningful name to the looping variable)."
- "The body of a loop can contain many statements."
- "Use `range` to iterate over a sequence of numbers."
- "The Accumulator pattern turns many values into one."
---
## A *for loop* executes commands once for each value in a collection.

*   Doing calculations on the values in a list one by one
    is as painful as working with `pressure_001`, `pressure_002`, etc.
*   A *for loop* tells Python to execute some statements once for each value in a list,
    a character string,
    or some other collection.
*   "for each thing in this group, do these operations"

~~~
for number in [2, 3, 5]:
    print(number)
~~~
{: .python}

*   This `for` loop is equivalent to:

~~~
print(2)
print(3)
print(5)
~~~
{: .python}

*   And the `for` loop's output is:

~~~
2
3
5
~~~
{: .output}

## The first line of the `for` loop must end with a colon, and the body must be indented.

*   The colon at the end of the first line signals the start of a *block* of statements.
*   Python uses indentation rather than `{}` or `begin`/`end` to show *nesting*.
    *   Any consistent indentation is legal, but almost everyone uses four spaces.

~~~
for building in ['Jefferson', 'Madison', 'Adams']:
print(place)
~~~
{: .python}
~~~
IndentationError: expected an indented block
~~~
{: .error}

*   Indentation is always meaningful in Python.

~~~
first_name = "Thomas"
  last_name = "Jefferson"
~~~
{: .python}
~~~
  File "<ipython-input-7-f65f2962bf9c>", line 2
    last_name="Jefferson"
    ^
IndentationError: unexpected indent
~~~
{: .error}

*   This error can be fixed by removing the extra spaces
    at the beginning of the second line.

## A `for` loop is made up of a collection, a loop variable, and a body.

~~~
for building in ['Jefferson', 'Madison', 'Adams']:
    print(building)
~~~
{: .python}

*   The collection, `['Jefferson', 'Madison', 'Adams']`, is what the loop is being run on.
*   The body, `print(building)`, specifies what to do for each value in the collection.
*   The loop variable, `building`, is what changes for each *iteration* of the loop.
    *   The "current thing".

## Loop variable names follow the normal variable name conventions.

*   Loop variables will:
    *   Be created on demand during the course of each loop.
    *   Persist after the loop finishes.
        * Use a new variable name to avoid overwriting a data collection you need to keep for later
    *   Often be used in the course of the loop
        * So give them a meaningful name you'll understand as the body code in your loop grows.
        * Example: `for single_letter in ['A', 'B', 'C', 'D']:` instead of `for blah in ['A', 'B', 'C', 'D']:`

For example, you wouldn't want to do:
~~~
for kitten in [2, 3, 5]:
    print(kitten)
~~~
{: .python}

## Show loop using pens exercise and include something that's not a pen. 
* Stops automatically when you've run out of things, don't need to keep track of the size of the collection. 
* Doesn't matter what the loop variable is called.
* It gets replaced each time with the next thing. 

## The body of a loop can contain many statements.
Math example: 
~~~
primes = [2, 3, 5]
for p in primes:
    squared = p ** 2
    cubed = p ** 3
    print(p, squared, cubed)
~~~
{: .python}
~~~
2 4 8
3 9 27
5 25 125
~~~
{: .output}

## Use `range` to iterate over a sequence of numbers.

*   The built-in function `range` produces a sequence of numbers.
    *   *Not* a list: the numbers are produced on demand
        to make looping over large ranges more efficient.
*   `range(N)` is the numbers 0..N-1
    *   Exactly the legal indices of a list or character string of length N

~~~
for number in range(0,3):
    print(number)
~~~
{: .python}
~~~
0
1
2
~~~
{: .output}

## Or use `range` to repeat an action an arbitrary number of times.

*   You don't actually have to use the iterable variable's value.
*   Use this structure to simply repeat an action some number of times.
    *   That number of times goes into the `range` function.

~~~
for number in range(5):
    print("Again!")
~~~
{: .python}
~~~
Again!
Again!
Again!
Again!
Again!
~~~
{: .output}

## The Accumulator pattern turns many values into one.

*   A common pattern in programs is to:
    1.  Initialize an *accumulator* variable to zero, the empty string, or the empty list.
    2.  Update the variable with values from a collection.

Say we have the following list:
sizes = ['xs','s','m','l','xl']

Use the string method .upper() 
Write a for statement to:
* Create a new list with all the sizes in uppercase.
* Remember! You can’t append to a list that doesn’t exist.

~~~
sizes = ['xs','s','m','l','xl']
upper_sizes = []

for s in sizes:
    new_size = s.upper()
    upper_sizes.append(new_size)

print(upper_sizes)
~~~
{: .python}
~~~
['XS', 'S', 'M', 'L', 'XL']
~~~
{: .output}

> ## For loops become more powerful when we can start to do more to test the data.

> ## Practice Accumulating
>

