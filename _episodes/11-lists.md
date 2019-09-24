---
title: "Lists"
teaching: 10
exercises: 10
questions:
- "How can I store multiple values?"
objectives:
- "Explain why programs need collections of values."
- "Write programs that create flat lists, index them, slice them, and modify them through assignment and method calls."
keypoints:
- "A list stores many values in a single structure."
- "Use an item's index to fetch it from a list."
- "Lists' values can be replaced by assigning to them."
- "Appending items to a list lengthens it."
- "Use `del` to remove items from a list entirely."
- "The empty list contains no values."
- "Lists may contain values of different types."
- "Character strings can be indexed like lists."
- "Character strings are immutable."
- "Indexing beyond the end of the collection is an error."
---
## A list stores many values in a single structure.

*   Doing calculations with a hundred variables called `pressure_001`, `pressure_002`, etc.,
    would be at least as slow as doing them by hand.
*   Use a *list* to store many values together.
    *   Contained within square brackets `[...]`.
    *   Values separated by commas `,`.
*   Use `len` to find out how many values are in a list.

~~~
subjects = ['women', 'history', 'social conditions']
print('subjects:', subjects)
print('length:', len(subjects))
~~~
{: .python}
~~~
subjects: ['women', 'history', 'social conditions']
length: 3
~~~
{: .output}

## Use an item's index to fetch it from a list.

*   Just like strings.

~~~
print('first item of subjects:', subjects[0])
print('third item of subjects:', subjects[2])
~~~
{: .python}
~~~
first item of subjects: women
third item of subjects: social conditions
~~~
{: .output}

## Lists' values can be replaced by assigning to them.

*   Use an index expression on the left of assignment to replace a value.

~~~
subjects[0] = 'youth'
print('subjects is now:', subjects)
~~~
{: .python}
~~~
subjects is now: ['youth', 'history', 'social conditions']
~~~
{: .output}

## Appending items to a list lengthens it.

*   Use `list_name.append` to add items to the end of a list.

~~~
formats = ["image", "pdf", "web page"]
print('formats is initially', formats)
formats.append("archived web site")
formats.append("drawing")
print('formats has become:', formats)
~~~
{: .python}
~~~
formats is initially ['image', 'pdf', 'web page']
formats has become: ['image', 'pdf', 'web page', 'archived web site', 'drawing']
~~~
{: .output}

*   `append` is a *method* of lists.
    *   Like a function, but tied to a particular object.
*   Use `object_name.method_name` to call methods.
    *   Deliberately resembles the way we refer to things in a library.
*   We will meet other methods of lists as we go along.
    *   Use `help(list)` for a preview.
*   `extend` is similar to `append`, but it allows you to combine two lists.  For example:  

~~~
mime_types = ["image/gif", "image/jpg"]
other_mime_types = ["image/tif", "image/jpeg"]
print('mime_types is currently:', mime_types)
mime_types.extend(other_mime_types)
print('mime_types has now become:', mime_types)
formats.append(mime_types)
print('formats has finally become:', formats)
~~~
{: .python}  
~~~
mime_types is currently: ['image/gif', 'image/jpg']
mime_types has now become: ['image/gif', 'image/jpg', 'image/tif', 'image/jpeg']
formats has finally become: ['image', 'pdf', 'web page', 'archived web site', 'drawing', ['image/gif', 'image/jpg', 'image/tif', 'image/jpeg']]
~~~
{: .output}
Note that while `extend` maintains the "flat" structure of the list, appending a list to a list makes the result two-dimensional.

## Use `del` to remove items from a list entirely.

*   `del list_name[index]` removes an item from a list and shortens the list.
*   Not a function or a method, but a statement in the language.

~~~
pages = [2, 3, 12, 17, 95]
print('pages before removing last item:', pages)
del pages[4]
print('pages after removing last item:', pages)
~~~
{: .python}
~~~
pages before removing last item: [2, 3, 12, 17, 95]
pages after removing last item: [2, 3, 12, 17]
~~~
{: .output}

## The empty list contains no values.

*   Use `[]` on its own to represent a list that doesn't contain any values.
    *   "The zero of lists."
*   Helpful as a starting point for collecting values
    (which we will see in the [next episode]({{page.root}}/12-for-loops/)).

## Lists may contain values of different types.

*   A single list may contain numbers, strings, and anything else.

~~~
tags = [1865, "Tennessee, "railroads"]
~~~
{: .python}

## Character strings can be indexed like lists.

*   Get single characters from a character string using indexes in square brackets.

~~~
medium = 'photograph'
print('zeroth character:', medium[0])
print('third character:', medium[3])
~~~
{: .python}
~~~
zeroth character: p
third character: t
~~~
{: .output}

## Character strings are immutable.

*   Cannot change the characters in a string after it has been created.
    *   *Immutable*: cannot be changed after creation.
    *   In contrast, lists are *mutable*: they can be modified in place.
*   Python considers the string to be a single value with parts,
    not a collection of values.

~~~
medium[0] = 'C'
~~~
{: .python}
~~~
TypeError: 'str' object does not support item assignment
~~~
{: .error}

## Indexing beyond the end of the collection is an error.

*   Python reports an `IndexError` if we attempt to access a value that doesn't exist.
    *   This is a kind of runtime error.
    *   Cannot be detected as the code is parsed
        because the index might be calculated based on data.

~~~
print('99th letter of mediume is:', element[99])
~~~
{: .python}
~~~
IndexError: string index out of range
~~~
{: .output}

> ## String methods
>
You can use the method split() on a string to split it up on a separator character. Default is space. 

~~~
title = "Insurance maps of the city of New York"
title_words = title.split()
print(title_words)
~~~
{: .python}
~~~
['Insurance', 'maps', 'of', 'the', 'city', 'of', 'New', 'York']
~~~
{: .output}

Split can take a string to specify another character to split on.
~~~
year_info = "2019/2020"
years_list = year_info.split("/")
print(years_list)
~~~
{: .python}
~~~
['2019', '2020']
~~~
{: .output}

How would get just the first year in that list and assign it to a new variable?
~~~
start_year = years_list[0]
print(start_year)
~~~
{: .python}
~~~
2019
~~~
{: .output}

> ### Exercise: Split on something else

Given the subject heading below, split apart the subdivisions and assign the results
to a list called "subheadings". 
~~~
subject = "Railroads--United States--Maps"
~~~
{: .python}
~~~
subheadings = subject.split("--")
form = subheadings[-1]
~~~
{: .output}


> ## Bonus to join them together again
>
>
> ~~~
> new_subject = '--'.join(subheadings)
> ~~~
> {: .python}
> 
> ~~~
> Railroads--United States--Maps
> ~~~
> {: .output}
> 