---
title: "Variable Scope"
teaching: 10
exercises: 10
questions:
- "How do function calls actually work?"
- "How can I determine where errors occurred?"
objectives:
- "Identify local and global variables."
- "Identify parameters as local variables."
- "Read a traceback and determine the file, function, and line number on which the error occurred, the type of error, and the error message."
keypoints:
- "The scope of a variable is the part of a program that can 'see' that variable."
---
## The scope of a variable is the part of a program that can 'see' that variable.

*   There are only so many sensible names for variables.
*   People using functions shouldn't have to worry about
    what variable names the author of the function used.
*   People writing functions shouldn't have to worry about
    what variable names the function's caller uses.
*   The part of a program in which a variable is visible is called its *scope*.

~~~
access_url = 'http://memegenerator.net/'

def extract_domain(uri):
    domain = uri[7:-1]
    return domain
~~~
{: .python}

*   `access_url` is a *global variable*.
    *   Defined outside any particular function.
    *   Visible everywhere.
*   `uri` and `domain` are *local variables* in `extract_domain`.
    *   Defined in the function.
    *   Not visible in the main program.
    *   Remember: a function parameter is a variable
        that is automatically assigned a value when the function is called.

~~~
print('domain is:', extract_domain('http://metafilter.com/'))
print('url after call:', domain)
~~~
{: .python}
~~~
domain is: metafilter.com
~~~
{: .output}
~~~
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-22-9860e4547781> in <module>()
      1 print('domain is:', extract_domain('http://metafilter.com/'))
----> 2 print('url after call:', domain)
      3 

NameError: name 'domain' is not defined
~~~
{: .error}

