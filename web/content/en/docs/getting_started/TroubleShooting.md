---
title: "Troubleshooting"
linkTitle: "Troubleshooting"
weight: 3
description:
---

### ModuleNotFoundError

You've tried running ``py -3.7 MANGA.py -h`` and got an error message like this:

> ModuleNotFoundError: No module names 'matplotlib'

This means, that python can not find the module (or package) 'matplotlib'.
There are two common reasons for this.
First, the module is not installed.
Second, python can't find it.

To check which modules are installed type ``pip list``.
If the module is not listed there, install it using ``pip install matplotlib``.

In case it's listed there it's likely that the paths for python are not configured correctly.
Make sure that you check the 'Add Python 3.7 to PATH' box.

<figure class="alert">
     <img id="Figure_3" src="/pictures/getting_started/InstallPythonWindows.png">
</figure>

Modules other than matplotlib can also cause this error. 
Make sure you install all of them.


In case you've installed multiple python versions, make sure that you install modules with the respective python version.
Using an IDE helps to manage modules.
In PyCharm, for example, you can open project settings (ctl+alt+s) and navigate to ``Project | Python Interpreter`` (navigation bar on the left).
In this window, you can select the Python version, see which packages are installed and manage them.