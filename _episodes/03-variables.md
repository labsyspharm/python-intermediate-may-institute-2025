---
title: "Variables and Assignment"
teaching: 15
exercises: 10
questions:
- "How can I store data in programs?"
objectives:
- "Write programs that assign scalar values to variables and perform calculations with those values."
- "Correctly trace value changes in programs that use scalar assignment."
keypoints:
- "Use variables to store values."
- "Values are displayed as output."
- "Use `print` to render strings."
- "Variables must be created before they are used."
- "Variables can be used in calculations."
- "Use an index to get a single character from a string."
- "Use a slice to get a substring."
- "Use the built-in function `len` to find the length of a string."
- "Python is case-sensitive."
- "Use meaningful variable names."
---
## Python is a programming Language

*   Bash is another programming language, used for the shell
*   Like Bash, python operates on the *read-evaulate-print loop* (REPL). When you enter an expression,
    python reads your code, evaulates and executes it, prints the output, and then loops back to the next
    line or block of code.


## Python can be used as a simple calculator

*   The usual mathematical operations are supported (we will go into more detail on this later)
*   Two main kinds of number: `int` for integers, and `float` for numbers with decimals.
*   Exponents use `**`

~~~
In [1]: 1 + 3
Out[1]: 4

In [2]: 4 * 5
Out[2]: 20

In [3]: 1/2
Out[3]: 0.5

In [4]: 2**3
Out[4]: 8
~~~
{: .language-python}

*   The usual order of operations are obeyed

~~~
In [5]: 6/2 + 3 * 5**2
Out[5]: 78.0
~~~
{: .language-python}

*   You can also type arbitrary sequences of characters in quotes, called strings.
*   You can perform operations on those strings

~~~
In [6]: 'hello'
Out[6]: 'hello'

In [7]: 'hello' + 'world'
Out[7]: 'helloworld'

In [8]: 3 * 'hello'
OUt[8]: 'hellohellohello'
~~~
{: .language-python}

*   Operations are generally intuitive.
*   Some do not work because they do not make sense (we will discuss this more
   [here](https://labsyspharm.github.io/python-novice-gapminder/03-types-conversion/index.html#type-control-operations))

~~~
In [9]: 'hello' + 3
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-9-c9c9952ff2b4> in <module>
----> 1 'hello' + 3

TypeError: Can't convert 'int' object to str implicitly
~~~
{: .error}
*   This is the first of many errors we will encounter in python.
*   The last line of an error message is usually the most informative.
*   We will look at error messages in detail [later]({{ page.root }}/15-scope/#reading-error-messages).


## Use variables to store values.

*   **Variables** are names for values.
*   In Python the `=` symbol assigns the value on the right to the name on the left.
*   The variable is created when a value is assigned to it.
*   Here, Python assigns an age to a variable `age`
    and a name in quotes to a variable `first_name`.

~~~
In [1]: age = 42

In [2]: first_name = 'Ahmed'
~~~
{: .language-python}

*   Variable names
    * can **only** contain letters, digits, and underscore `_` (typically used to separate words in long variable names)
    * cannot start with a digit
*   Variable names that start with underscores like `__alistairs_real_age` have a special meaning
    so we won't do that until we understand the convention.

## Use `print` to display values in the midst of your script.

*   Python has a built-in function called `print` that prints things as text.
*   Call the function (i.e., tell Python to run it) by using its name.
*   Provide values to the function (i.e., the things to print) in parentheses.
*   To add a string to the printout, wrap the string in single or double quotes.
*   The values passed to the function are called **arguments**

~~~
In [3]: print(first_name, 'is', age, 'years old')
~~~
{: .language-python}
~~~
Ahmed is 42 years old
~~~
{: .output}

*   `print` automatically puts a single space between items to separate them.
*   And wraps around to a new line at the end.
*   Also note the lack of quotes around the strings.

## Variables must be created before they are used.

*   If a variable doesn't exist yet, or if the name has been mis-spelled,
    Python reports an error. (Unlike some languages, which "guess" a default value.)

~~~
In [1]: last_name
~~~
{: .language-python}
~~~
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-1-e1aeda7b4fde> in <module>
----> 1 last_name

NameError: name 'last_name' is not defined
~~~
{: .error}


## Variables can be used in calculations.

*   We can use variables in calculations just as if they were values.
    *   Remember, we assigned the value `42` to `age` a few lines ago.

~~~
age = age + 3
age
~~~
{: .language-python}
~~~
45
~~~
{: .output}

## Use an index to get a single character from a string.

*   The characters (individual letters, numbers, and so on) in a string are
    ordered. For example, the string `'AB'` is not the same as `'BA'`. Because of
    this ordering, we can treat the string as a list of characters.
*   Each position in the string (first, second, etc.) is given a number. This
    number is called an **index** or sometimes a subscript.
*   Indices are numbered from 0.
*   Use the position's index in square brackets to get the character at that
    position.
    
![an illustration of indexing](../fig/2_indexing.svg)

~~~
atom_name = 'helium'
atom_name[0]
~~~
{: .language-python}
~~~
'h'
~~~
{: .output}

## Use a slice to get a substring.

*   A part of a string is called a **substring**. A substring can be as short as a
    single character.
*   An item in a list is called an element. Whenever we treat a string as if it
    were a list, the string's elements are its individual characters.
*   A slice is a part of a string (or, more generally, any list-like thing).
*   We take a slice by using `[start:stop]`, where `start` is replaced with the
    index of the first element we want and `stop` is replaced with the index of
    the element just after the last element we want.
*   Mathematically, you might say that a slice selects `[start:stop)`.
*   The difference between `stop` and `start` is the slice's length.
*   Taking a slice does not change the contents of the original string. Instead,
    the slice is a copy of part of the original string.

~~~
atom_name = 'sodium'
atom_name[0:3]
~~~
{: .language-python}
~~~
'sod'
~~~
{: .output}

## Use the built-in function `len` to find the length of a string.

~~~
len('helium')
~~~
{: .language-python}
~~~
6
~~~
{: .output}

*   Nested functions are evaluated from the inside out,
     like in mathematics.

## Python is case-sensitive.

*   Python thinks that upper- and lower-case letters are different,
    so `Name` and `name` are different variables.
*   There are conventions for using upper-case letters at the start of variable names so we will use lower-case letters for now.

## Use meaningful variable names.

*   Python doesn't care what you call variables as long as they obey the rules
    (alphanumeric characters and the underscore).

~~~
flabadab = 42
ewr_422_yY = 'Ahmed'
print(ewr_422_yY, 'is', flabadab, 'years old')
~~~
{: .language-python}

*   Use meaningful variable names to help other people understand what the program does.
*   The most important "other person" is your future self.

> ## Swapping Values
>
> Fill the table showing the values of the variables in this program
> *after* each statement is executed.
>
> ~~~
> # Command  # Value of x   # Value of y   # Value of swap #
> x = 1.0    #
> y = 3.0    #
> swap = x   #
> x = y      #
> y = swap   #
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > # Command  # Value of x   # Value of y   # Value of swap #
> > x = 1.0    # 1.0            not defined    not defined    
> > y = 3.0    # 1.0            3.0            not defined    
> > swap = x   # 1.0            3.0            1.0            
> > x = y      # 3.0            3.0            1.0            
> > y = swap   # 3.0            1.0            1.0            
> > ~~~
> > {: .output}
> > 
> > These three lines exchange the values in `x` and `y` using the `swap`
> > variable for temporary storage. This is a fairly common programming idiom.
>{: .solution}
{: .challenge}

> ## Predicting Values
>
> What is the final value of `position` in the program below?
> (Try to predict the value without running the program,
> then check your prediction.)
>
> ~~~
> initial = 'left'
> position = initial
> initial = 'right'
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > 'left'
> > ~~~
> > {: .output}
> >
>> The `initial` variable is assigned the value `'left'`.
> > In the second line, the `position` variable also receives
>> the string value `'left'`. In third line, the `initial` variable is given the
>> value `'right'`, but the `position` variable retains its string value
>> of `'left'`.
>{: .solution}
{: .challenge}

> ## Challenge
>
> If you assign `a = 123`,
> what happens if you try to get the second digit of `a` via `a[1]`?
>
> > ## Solution
> > Numbers are not strings or sequences and Python will raise an error if you try to perform an index operation on a
> > number. In the [next lesson on types and type conversion]({{ page.root }}/03-types-conversion/#convert-numbers-and-strings)
> > we will learn more about types and how to convert between different types. If you want the Nth digit of a number you
> > can convert it into a string using the `str` built-in function and then perform an index operation on that string.
> >
> > ~~~
> > a = 123
> > a[1]
> > ~~~
> > {: .language-python}
> > ~~~
> > TypeError: 'int' object is not subscriptable
> > ~~~
> > {: .error}
> > 
> > 
> > ~~~
> > a = str(123)
> > a[1]
> > ~~~
> > {: .language-python}
> > ~~~
> > '2'
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Choosing a Name
>
> Which is a better variable name, `m`, `min`, or `minutes`?
> Why?
> Hint: think about which code you would rather inherit
> from someone who is leaving the lab:
>
> 1. `ts = m * 60 + s`
> 2. `tot_sec = min * 60 + sec`
> 3. `total_seconds = minutes * 60 + seconds`
>
> > ## Solution
> >
> > `minutes` is better because `min` might mean something like "minimum"
> > (and actually is an existing built-in function in Python that we will cover later).
> {: .solution}
{: .challenge}

> ## Slicing practice
>
> What does the following program print?
>
> ~~~
> atom_name = 'carbon'
> print('atom_name[1:3] is:', atom_name[1:3])
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > atom_name[1:3] is: ar
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Slicing concepts
>
> 1.  What does `thing[low:high]` do?
> 2.  What does `thing[low:]` (without a value after the colon) do?
> 3.  What does `thing[:high]` (without a value before the colon) do?
> 4.  What does `thing[:]` (just a colon) do?
> 5.  What does `thing[number:some-negative-number]` do?
> 6.  What happens when you choose a `high` value which is out of range? (i.e., try `atom_name[0:15]`) 
>
> > ## Solutions
> >
> > 1. `thing[low:high]` returns a slice from `low` to the value before `high`
> > 2. `thing[low:]` returns a slice from `low` all the way to the end of `thing`
> > 3. `thing[:high]` returns a slice from the beginning of `thing` to the value before `high`
> > 4. `thing[:]` returns all of `thing`
> > 5. `thing[number:some-negative-number]` returns a slice from `number` to `some-negative-number` values from the end of `thing`
> > 6. If a part of the slice is out of range, the operation does not fail. `atom_name[0:15]` gives the same result as `atom_name[0:]`.
> >
> {: .solution}
{: .challenge}
