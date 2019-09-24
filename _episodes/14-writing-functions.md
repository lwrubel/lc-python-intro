---
title: "Writing Functions"
teaching: 10
exercises: 15
questions:
- "How can I create my own functions?"
objectives:
- "Explain and identify the difference between function definition and function call."
- "Write a function that takes a small, fixed number of arguments and produces a single result."
keypoints:
- "Break programs down into functions to make them easier to understand."
- "Define a function using `def` with a name, parameters, and a block of code."
- "Defining a function does not run it."
- "Arguments in call are matched to parameters in definition."
- "Functions may return a result to their caller using `return`."
---

## Break programs down into functions to make them easier to understand.

*   Human beings can only keep a few items in working memory at a time.
*   Understand larger/more complicated ideas by understanding and combining pieces.
*   Functions serve the same purpose in programs.
    *   *Encapsulate* complexity so that we can treat it as a single "thing".
*   Also enables *re-use*.
    *   Write one time, use many times.

## Define a function using `def` with a name, parameters, and a block of code.

*   Begin the definition of a new function with `def`.
*   Followed by the name of the function.
    *   Must obey the same rules as variable names.
*   Then *parameters* in parentheses.
    *   Empty parentheses if the function doesn't take any inputs.
    *   We will discuss this in detail in a moment.
*   Then a colon.
*   Then an indented block of code.

~~~
def print_greeting():
    print('Hello!')
~~~
{: .python}

## Defining a function does not run it.

*   Defining a function does not run it.
    *   Like assigning a value to a variable.
*   Must call the function to execute the code it contains.
*   The commands for the function are read and stored after the `def` block, but not actually executed until the function is called later on.
    *   Imagine getting a **recipe card** and keeping it in your kitchen.  You can cook it anytime, but you haven't completed any of the steps until you start that cooking process.
    *   This means that Python won't complain about problems until you call the function.  More specifically, just because the definition of a function runs without error doesn't mean that there won't be errors when it executes later.

~~~
print_greeting()
~~~
{: .python}
~~~
Hello!
~~~
{: .output}

## Arguments in call are matched to parameters in definition.

*   Functions are most useful when they can operate on different data.
*   Specify *parameters* when defining a function.
    *   These become variables when the function is executed.
    *   Are assigned the arguments in the call (i.e., the values passed to the function).

~~~
def print_date(year, month, day):
    joined = str(year) + '/' + str(month) + '/' + str(day)
    print(joined)

print_date(1871, 3, 19)
~~~
{: .python}
~~~
1871/3/19
~~~
{: .output}

## Functions may return a result to their caller using `return`.

*   Use `return ...` to give a value back to the caller.
*   May occur anywhere in the function.
*   But functions are easier to understand if `return` occurs:
    *   At the start to handle special cases.
    *   At the very end, with a final result.

*   Remember: [every function returns something]({{ page.root }}/04-built-in/).
*   A function that doesn't explicitly `return` a value automatically returns `None`.

> ## Definition and Use
>
> What does the following program print?
> Edwidge Danticat gave a lecture yesterday here. 
>
> ~~~
> def report(author):
>     return 'author was' + author
>
> report('Edwidge Danticat')
> ~~~
> {: .python}
> >
> > ## Solution
> > ~~~
> > author is Edwidge Danticat
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Calling by Name
>
> What does this short program print?
>
> ~~~
> def add_https(url):
>     joined = "https:" + url
>     return joined
>
> my_url = "//www.loc.gov/item/2006627699/"
> correct_url = add_https(my_url)
> print(correct_url)
> ~~~
> {: .python}
>
> ## Using the .format() method on strings
> We've been using the + to add strings together. We can also use format to create strings. 
>
> ~~~
> genre = "Fiction"
> subject = "Haitian Americans--{}".format(genre)
> print(subject)
> ~~~
> {: .python}

> ## [SLIDE] 
> ### Rewrite the add_https() function to use .format() instead of concatenating strings.
>
> ** Answer **
> ~~~
> def add_https(url):
>     joined = "https:{}".format(url)
>     return joined
>
> my_url = "//www.loc.gov/item/2006627699/"
> correct_url = add_https(my_url)
> print(correct_url)
> ~~~
> {: .python}
>