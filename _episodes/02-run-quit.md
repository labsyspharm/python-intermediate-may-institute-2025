---
title: "Running and Quitting"
teaching: 5
exercises: 0
questions:
- "How can I run Python programs?"
objectives:
- "Run the `ipython` command prompt."
- "Write a python file."
- "Execute a python file, both in the script and out."
keypoints:
- "Python scripts are plain text files."
- "Use the `ipython` for editing and running Python."
---

## Running an `ipython` session

- Ipython is a common and very powerful way to test small pieces of python
code.

- It is also the basis for many other python tools such as Jupyter and is
emulated in many other environments, such as IDEs.

- To run `ipython`, first enter your terminal, then simply type:

~~~
$ ipython
~~~
{: .language-bash}

and you should see a prompt like this, but more colorful:

~~~
Python 3.6.6 (default, Sep 19 2018, 12:51:03)
Type 'copyright', 'credits' or 'license' for more information
IPython 6.5.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]:
~~~
{: .output}

- To exit the `ipython`, type `exit` and hit enter.


## Creating an executable python file

- Like shell scripts, you can save your code in a file

- Now create a directory somewhere called `swc-python`

- Open up `atom`, either by clicking on the icon or typing `atom` in
  your terminal.

- Now, in your terminal, create a new directory under `swc-python` called
  `scripts`.

- In atom, create a new file, and then save it as `test.py` in the `scripts`
  directory.

- This is a python script file. Note that `.py` indicats a python file, but this
  is convention, not requirement.

- In your terminal, navigate to the `scripts` directory.

- You can now run the script using
  ```
  $ python test.py
  ```

- Similarly, if you start up `ipython` again, from within `ipython` you can do
  ```
  In [1]: run test.py
  ```
  which will run all the code in `test.py` as though entered into `ipython`.

{% include links.md %}
