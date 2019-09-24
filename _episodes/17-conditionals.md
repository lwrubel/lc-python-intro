---
title: "Conditionals"
teaching: 10
exercises: 15
questions:
- "How can programs do different things for different data?"
objectives:
- "Correctly write programs that use if and else statements and simple Boolean expressions (without logical operators)."
- "Trace the execution of unnested conditionals and conditionals inside loops."
keypoints:
- "Use `if` statements to control whether or not a block of code is executed."
- "Conditionals are often used inside loops."
- "Use `else` to execute a block of code when an `if` condition is *not* true."
- "Use `elif` to specify additional tests."
- "Conditions are tested once, in order."
- "Create a table showing variables' values to trace a program's execution."
---
## Use `if` statements to control whether or not a block of code is executed.

*   An `if` statement (more properly called a *conditional* statement)
    controls whether some block of code is executed or not.
*   Structure is similar to a `for` statement:
    *   First line opens with `if` and ends with a colon
    *   Body containing one or more statements is indented (usually by 4 spaces)

~~~
filesize = 520
if filesize > 500:
    print(filesize, 'is large')

filesize = 34
if filesize > 500:
    print (filesize, 'is large')
~~~
{: .python}
~~~
520 is large
~~~
{: .output}

## Conditionals are often used inside loops.

*   Not much point using a conditional when we know the value (as above).
*   But useful when we have a collection to process.

~~~
filesizes = [34, 800, 230, 1200, 11.5]
for f in filesizes:
    if f > 500:
        print(f, 'is large')
~~~
{: .python}
~~~
800 is large
1200 is large
~~~
{: .output}

## Use `else` to execute a block of code when an `if` condition is *not* true.

*   `else` can be used following an `if`.
*   Allows us to specify an alternative to execute when the `if` *branch* isn't taken.

~~~
filesizes = [34, 800, 230, 1200, 11.5]
for f in filesizes:
    if f > 500:
        print(f, 'is large')
    else:
        print(f, 'is small')
~~~
{: .python}
~~~
34 is small
800 is large
230 is small
1200 is large
11.5 is small
~~~
{: .output}

## Use `elif` to specify additional tests.

*   May want to provide several alternative choices, each with its own test.
*   Use `elif` (short for "else if") and a condition to specify these.
*   Always associated with an `if`.
*   Must come before the `else` (which is the "catch all").

~~~
filesizes = [34, 800, 230, 1200, 11.5]
for f in filesizes:
    if f > 1000:
        print(f, 'is huge')
    elif f > 500:
        print(f, 'is large')
    else:
        print(f, 'is small')

~~~
{: .python}
~~~
34 is small
800 is large
230 is small
1200 is huge
11.5 is small
~~~
{: .output}

## Conditions are tested once, in order.

*   Python steps through the branches of the conditional in order, testing each in turn.
*   So ordering matters.
*   Often use conditionals in a loop to "evolve" the values of variables.

> ## Compound Relations Using `and`, `or`, and Parentheses
>
> Often, you want some combination of things to be true.  You can combine
> relations within a conditional using `and` and `or`.  Continuing the example
> above, suppose you have
>
> ~~~
> num_pages = [120,  50,  452,  98,  850]
> height = [26, 28, 45, 15, 35]
>
> for i in range(5):
>     if num_pages[i] > 300 and height[i] > 30:
>         print("Thick heavy book!")
>     elif num_pages[i] > 100 and num_pages[i] <= 200 and height[i] <= 30:
>         print("Typical size.")
>     elif num_pages[i] <= 100 and height <= 30:
>         print("Light object.")
>     else:
>         print("Whoa!  Something is up with the data.  Check it")
> ~~~
> {: .python}
>
> Just like with arithmetic, you can and should use parentheses whenever there
> is possible ambiguity.  A good general rule is to *always* use parentheses
> when mixing `and` and `or` in the same condition.  That is, instead of:
>
> ~~~
> if num_pages[i] <= 100 or num_pages[i] >= 200 and height[i] > 30:
> ~~~
> {: .python}
>
> write one of these:
>
> ~~~
> if (num_pages[i] <= 100 or num_pages[i] >= 200) and height[i] > 30:
> if num_pages[i] <= 100 or (num_pages[i] >= 200 and height[i] > 30):
> ~~~
> {: .python}
>
> so it is perfectly clear to a reader (and to Python) what you really mean.
{: .callout}

> ## Tracing Execution [SLIDE]
>
> What does this program print?
>
> ~~~
> filesize = 71
> if filesize > 50.0:
>     filesize = 25.0
> elif filesize <= 50.0:
>     filesize = 0.0
> print(filesize)
> ~~~
> {: .python}
> > ## Solution
> > ~~~
> > 25.0
> > ~~~
> > {: .output}
> >
> {: .solution}
{: .challenge}
