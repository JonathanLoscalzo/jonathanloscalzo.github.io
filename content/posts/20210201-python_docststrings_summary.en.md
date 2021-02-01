+++ 
draft = false
date = 2021-02-01T14:59:26-03:00
title = "Documenting Python code with Doctstring"
description = ""
slug = "" 
tags = ["docstrings"]
categories = ["Python"]
externalLink = ""
series = []
+++


It is important for a project to have a documentation on methods, classes and modules is one step to enhance quality on it. 
Not to confuse "block comments" (using #) with docstring comments. 

Next developers generation will be thankfully with your graceful documentation (or not, but you must write it anyway)


I've started using this plugin for vscode: *Python Docstring Generator(njpwerner.autodocstring)* with snippets for docstrings, but also Pycharm generates docstring automatically. 


Documenting stuffs let comunicate the purpose and usage (and in some cases test) our artifacts for the next developer generation, also yourself in the future, who needs to fix or just understand what are you thinking when you developed these lines...

In python, docstring are simple as: 

Document a method
```
def method(var1: TypeVar1) -> TypeRes :
    """ Single description of purpose """

```

Document a package
```
# in __init__.py file
""" Single description of purpose """

```
Note: just the same for a module

## Where

Docstring could be read with the method `__doc__` of any artifact, also we could use builtin `help()` to read full documentation in an standard format.

```
>>> print(math.__doc__)
This module is always available.  It provides access to the
mathematical functions defined by the C standard.

```

## How-to

PEP257 standarize conventions related to docstring writing in python code. 

There are two main conventions: one-line and multi-line docstring

### [one-line](https://www.python.org/dev/peps/pep-0257/#one-line-docstrings)
It is just one line (as its name :) ). This line describes the artifact (method, module or package) as a command, such: "Return the sum of a list of numbers", "Do a binary search", and so on. 

### [multi-line](https://www.python.org/dev/peps/pep-0257/#multi-line-docstrings)

This docstring is recommended due to its long-nature. 

This documentations should show: 
- single description at first line
- blank line
- description of a script: 
    - usage message & quick reference (such cli programs)
    - arguments and a description (such: `--param : explanation`)
- description of a module
    - list classes of its
    - exceptions
    - functions

```
>>> print(pickle.__doc__)
Create portable serialized representations of Python objects.

See module copyreg for a mechanism for registering custom picklers.
See module pickletools source for extensive comments.

Classes:

    Pickler
    Unpickler

Functions:

    dump(object, file)
    dumps(object) -> string
    load(file) -> object
    loads(string) -> object

Misc variables:

    __version__
    format_version
    compatible_formats

```
- description of a package: 
    - same as module, adding modules exported
- description of a function
    - summarize of its behavior
    - arguments and optional arguments
    - return value
    - optional: side effects
    - possible exceptions it may raise
    - restrictions

```
def fun(p:int, s: str, d:float=20, *args, **kwards) -> bool:
    """[summary]

    Args:
        p (int): [description]
        s (str): [description]
        d (float, optional): [description]. Defaults to 20.

    Returns:
        bool: [description]
    """
    pass

```

- description of a class

```
>>> print(pd.DataFrame.__doc__)

    Two-dimensional, size-mutable, potentially heterogeneous tabular data.

    ....

    Parameters
    ----------
     ...

    See Also
    --------
    ....

    Examples
    --------
    ....
    
```

### Formats

Ok, I didn't show up just one format... Which is the correct one? All of them. 
PEP257 doesn't explain the format (see also PEP 287), so exists several conventions, but most common are (I took these bullets from daouzli's post): 

- [reStructuredText](https://www.python.org/dev/peps/pep-0287/), probably the most popular for Python docstrings format, with several forms also and that is mainly used in conjonction with Sphinx. Note that this format is used for the Python documentation.
- Epytext (Javadoc based), that was used years ago for Python but can still be found
- Google style, that can take several forms
- Numpydoc, looks like Google docs, used for the numpy related projects (but not only)

What are the purpose of these formats? Some tools could read these information and generate auto-html-documentation, such swagger for rest-apis. 
The most popular in python-world is Sphinx, it converts reStructured text into HTML, PDF, LaTeX and manuals


## References
- [Real Python - python-code-quality](https://realpython.com/python-code-quality/#)
- [flake8-docstrings](https://pypi.org/project/flake8-docstrings/)
- [pydocstyle](https://github.com/pycqa/pydocstyle)
- [PEP257 - Docstring conventions](https://www.python.org/dev/peps/pep-0257/)
- [PEP8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)
- [PEP8 - Documentation Strings section](https://www.python.org/dev/peps/pep-0008/#documentation-strings)
- [Hypermodern Python Chapter 5: Documentation](https://cjolowicz.github.io/posts/hypermodern-python-05-documentation/)
- [programiz - docstrings](https://www.programiz.com/python-programming/docstrings)
- [stackoverflow - docstring formats](https://stackoverflow.com/questions/3898572/what-is-the-standard-python-docstring-format)
- [daouzli - Docstring formats](http://daouzli.com/blog/docstring.html)
- [python devguide - documenting](https://devguide.python.org/documenting/)
- [the Hitchhiker's guide to python - Documentation](https://docs.python-guide.org/writing/documentation/)
- [pyment - create-update-convert docstrings in existing python files](https://github.com/dadadel/pyment)
- [PEP287 - docstring format](https://www.python.org/dev/peps/pep-0287/) proposes a syntax for Python docstrings, PEPs, and other uses.
- [PEP256 - ](https://www.python.org/dev/peps/pep-0256/), standarize extraction and process Python docstrings with DPS framework (docutils) (see also road-map-to-the-docstring-peps section)
- [sphinx - getting started with rst](https://sphinx-tutorial.readthedocs.io/step-1/)

