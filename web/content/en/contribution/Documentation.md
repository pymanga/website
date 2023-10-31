
---
title: Documentation
linkTitle: Documentation
weight: 4

---

Our documentation is available [here](https://pymanga.github.io/pyMANGA/pyMANGA.html).  
The documentation is build on [pdoc](https://pdoc.dev/), a tool for python to auto-generate API documentation. If you want to contribute to the documentation, we recommend to clone the [source code](/contribution/download) repository and build the documentation locally for testing purposes before creating a pull request. 

## Building the documentation locally

> If you have any difficulties understanding this walkthrough please check the [Getting started](../../docs/getting_started/installation/) section first. This will help you set up pyMANGA and Python on your system.  
> This walkthrough assumes that you have already installed pyMANGA and Python on your Windows system.

In order to generate a local copy of the documentation from the source code, we need to install the pdoc python library and run the necessary commands. We recommend to install pdoc using pip: 

    py -m pip install pdoc

Afterwards, we can generate the documentation by running the following command in the root directory of the source code repository (`./pyMANGA/`):

    py -m pdoc --docformat google -o ./docs ..\pyMANGA\

This will generate a folder called `docs` in the root directory of the source code repository. This folder is ignored by git and will not be pushed to the remote repository. The documentation can be viewed by opening `index.html` in the `docs` folder with a web browser.

## Editing and creating documentation

### Source code documentation

The documentation is written in the source code using docstrings (`"""`). The docstrings are written in the [Google style](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings) and are parsed by pdoc. 

#### Example code documentation  

    """
    Update tree geometry.

    For equation formulation, see Peters, Olagoke and Berger
    ([2018](https://doi.org/10.1016/j.ecolmodel.2018.10.005)), Appendix B (Bettina ODD), section 7.2,
    heading 'increase of allometric measures'.
    Sets:
        multiple float
    """

### Markdown documentation

Documentation can also be written in Markdown format. The requires a Markdown file with the actual documentation and a Python file that tells pdoc to include the markdown file and to parse it for the documentation. This is best explaing following a simple example.

#### Example markdown documentation

Let's create a documentation for the sub-library *AboveGround* from the *Resource* library. We want to navigate to the correct folder and create the documentation there. Navigate to `./pyMANGA/ResourceLib/AboveGround/`. Now we need a Markdown file containing the actual information and a Python file that tells pdoc to include the Markdown file and parse it for the documentation. Name the Markdown file according to the object we document (in this case `AboveGround.md`) and write your documentation. Now, we need the parse file for pandoc at the same location which is always called `__init__.py`. This file should contain the following code:

    """
    .. include:: ./Aboveground.md
    """

This tells pdoc to include the Markdown file and parse it for the documentation. Everything else written inside of the docstring (`"""`) is also included in the documentation. This could look like this:

    """

    @author: johndoe  

    .. include:: ./Aboveground.md
    """
    
