+++ 
draft = false
date = 2021-01-15T18:10:00-03:00
title = "Python: some advance topics"
description = ""
slug = "" 
tags = ["GIL", "async", "PEP"]
categories = ["Python"]
externalLink = ""
series = []
+++


# Links

## Async-Await
- [Async IO - Real Python](https://realpython.com/async-io-python/)  
- [python async features - Real Python](https://realpython.com/python-async-features/)  
- [Coroutines and Tasks](https://docs.python.org/3/library/asyncio-task.html)
- [Fast & Asynchronous in Python - Accelerate Your Requests Using asyncio](https://towardsdatascience.com/fast-and-async-in-python-accelerate-your-requests-using-asyncio-62dafca83c33)
- [Developing with asyncio - Python docs](https://docs.python.org/3/library/asyncio-dev.html)


### GIL and concurrency
The Python interpreter is not fully thread-safe, in order to support multithreading there is a "global lock" in CPython. Other implementations doesn't have GIL, such Jython, IronPython. Cython has GIL but it can be released by a "with" statement.

- [Global Interpreter Lock - GIL](https://wiki.python.org/moin/GlobalInterpreterLock)
- [Thread State and GIL](https://docs.python.org/3/c-api/init.html#thread-state-and-the-global-interpreter-lock)
- [multithreading vs multiprocessing](https://medium.com/contentsquare-engineering-blog/multithreading-vs-multiprocessing-in-python-ece023ad55a)
- [multithreading in python](https://timber.io/blog/multiprocessing-vs-multithreading-in-python-what-you-need-to-know/#:~:text=The%20multiprocessing%20library%20gives%20each,modify%20the%20same%20memory%20concurrently.)
- [Faster web scraping - Nick from RAPIDS](https://beckernick.github.io/faster-web-scraping-python/)  
- [MASNUM - the different forms of concurrency](http://masnun.rocks/2016/10/06/async-python-the-different-forms-of-concurrency/)


### Conventions: 
- [PEP 8 - Style Gide for Python Code](https://www.python.org/dev/peps/pep-0008/)
- [PEP 257 - Docstring conventions](https://www.python.org/dev/peps/pep-0257/)
- [PEP 518 - Specifying Minimum Build System Requirements for Python Projects](https://www.python.org/dev/peps/pep-0518/) (aka pyproject.toml)
- [PEP 484 - Type Hints](https://www.python.org/dev/peps/pep-0484/#arbitrary-argument-lists-and-default-argument-values)


## other topics

- [usage of `__main__.py`](https://www.geeksforgeeks.org/usage-of-__main__-py-in-python/)
- [What the heck is `pyproject.toml`](https://snarky.ca/what-the-heck-is-pyproject-toml/)
- [hypermodern python setup](https://cjolowicz.github.io/posts/hypermodern-python-01-setup/) & [awesome-pyproject](https://github.com/carlosperate/awesome-pyproject)
- [ConfigParser](https://docs.python.org/3/library/configparser.html)
- [Python code Quality: Linters](https://realpython.com/python-code-quality/#linters)
- [awesome-python (vinta)](https://github.com/vinta/awesome-python)

### Floating Point issues
- [Floating Point: issues and limitations](https://docs.python.org/3/tutorial/floatingpoint.html)
- [decimal module](https://docs.python.org/3/library/decimal.html#module-decimal)

