
---
title: Documentation
linkTitle: Documentation
weight: 4

---

Our documentation is available [here](https://pymanga.github.io/pyMANGA/pyMANGA.html).  
The documentation is build on [pdoc](https://pdoc.dev/), a tool for python to auto-generate API documentation. If you want to contribute to the documentation, we recommend to clone the [source code](/contribution/download) repository and build the documentation locally for testing purposes before creating a pull request. 


## Editing and creating documentation
### Markdown documentation

Each module should contain a non-technical documentation with the following sections:
- Description
- Usage
- Attributes
- Value
- Details
  - Purpose
  - Process overview
  - Sub-processes
- References
- Author(s)
- See Also
- Examples

This structure is inspired by the ODD protocol (<a href="https://www.jasss.org/23/2/7.html" target="_blank">Grimm et al. 2020</a>)

The module documentation is written in markdown format.
An example using this <a href="https://github.com/pymanga/pyMANGA/blob/master/ProjectLib/doc_template.md" target="_blank">Template</a> can be found <a href="https://pymanga.github.io/pyMANGA/pyMANGA/ResourceLib/BelowGround/Individual/FixedSalinity.html" target="_blank">here</a>.

The markdown file should be placed in the module folder and must be imported to be found by pdoc.
To do so, include the following code in the `__init__.py` of the respective module.

    """
    .. include:: ./<Module-name>.md
    """

Please note that anything else written inside the docstring (`"""`) will also be included in the documentation.


### Source code documentation

The documentation is written in the source code using docstrings (`"""`). 
The docstrings are written in the [Google style](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings) and are parsed by pdoc. 

#### Example code documentation  

    """
    Update tree geometry.

    For equation formulation, see Peters, Olagoke and Berger
    ([2018](https://doi.org/10.1016/j.ecolmodel.2018.10.005)), Appendix B (Bettina ODD), section 7.2,
    heading 'increase of allometric measures'.
    Sets:
        multiple float
    """


## Building the documentation locally

> If you have any difficulties understanding this walkthrough please check the [Getting started](../../docs/getting_started/installation/) section first. This will help you set up pyMANGA and Python on your system.  
> This walkthrough assumes that you have already installed pyMANGA and Python on your Windows system.

In order to generate a local copy of the documentation from the source code, we need to install the pdoc python library and run the necessary commands. We recommend to install pdoc using pip: 

    py -m pip install pdoc

Afterwards, we can generate the documentation by running the following command in the root directory of the source code repository (`./pyMANGA/`):

    py -m pdoc --docformat google -o ./docs ..\pyMANGA\

This will generate a folder called `docs` in the root directory of the source code repository. This folder is ignored by git and will not be pushed to the remote repository. The documentation can be viewed by opening `index.html` in the `docs` folder with a web browser.
