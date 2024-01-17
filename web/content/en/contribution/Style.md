
---
title: Style
linkTitle: Style
weight: 2

---

## Most important rules to remember

- Never use global variables.
- Give descriptive names to functions, variables, and file names; avoid abbreviation.
    - Variable names start lowercase and then with underscore (*this_examlpe*). Class member variables start with an underscore., which makes them private (*self._class_variable*).
    - Regular functions or class methods start lowercase and then camel case (*thisExample*).
    - Classes start with uppercase and then camel case (*ThisExample*).
- Define only one class per file.
- Document your code.

## Naming

The most important consistency rules are those that govern naming. The style of a name immediately informs us what sort of thing the named entity is: a type, a variable, a function, a constant, a macro, etc., without requiring us to search for the declaration of that entity. The pattern-matching engine in our brains relies a great deal on these naming rules.

Naming rules are pretty arbitrary, but we feel that consistency is more important than individual preferences in this area, so regardless of whether you find them sensible or not, the rules are the rules.
### General Naming Rules
Function names, variable names, and filenames should be descriptive; eschew abbreviation. Types and variables should be nouns, while functions should be imperative verbs.
#### File Names
Filenames should be camel case and do not include underscores (_) or dashes (-). The name must match the class that is defined in the file.

#### Type Names
Type names start with a capital letter and have a capital letter for each new word, with no underscores: *MyExcitingClass*, *MyExcitingEnum*.
#### Variable Names
Variable names are lowercase names with underscores: *_my_exciting_member_variable*. But be consistent in a file!
#### Function Names
Function names should represent an action. Regular functions start lowercase an then camel case. Accessors and mutators match the name of the variable with a "get" or "set" prefix: *doSomeStuff()*, *doSomeStuffOnThing()*, *getMyExcitingMemberVariable()*, *setMyExcitingMemberVariable()*.
#### Module Names
Module names start with a capital letter and then camel case. If modules use single inheritance use the parent name first and add the new name, e.g. BettinaNetwork has the parent class Bettina. For multiple inheritance use the method resolution order, e.g., NetworkFixedSalinity which resolves Network first and then FixedSalinity. One-word names are strongly recommended. Also, avoid new modules if switches in existing modules are sufficient.

## Comments

Though a pain to write, comments are absolutely vital to keeping our code readable.
The following rules describe what you should comment and where.
But remember: while comments are very important, the best code is self-documenting.
Giving sensible names to types and variables is much better than using obscure names that you must then explain through comments.

When writing your comments, write for your audience: the next contributor who will need to understand your code. Be generous — the next one may be you!

### Comment Style

We use [pdoc](https://pdoc.dev/) for to build our [documentation page](https://pymanga.github.io/pyMANGA/pyMANGA.html).
Therefore, comments in google docstring format are added below each method definition.
With pdoc, we can create a browsable source code documentation.

For comments inside the implementation use the # syntax. 

Have a look at the [Network](https://github.com/pymanga/pyMANGA/blob/master/ResourceLib/BelowGround/Network/Network/Network.py) resource module to see an example.

### Comment Tense

We (try to) use present-tense and imperative style, e.g. “create” instead of “creates”.

#### Module Comments
Modules in the ResourceLib or PlantModelLib should contain a short description of the concept written as a Markdown document in the same folder as the module.
This document should also contain the definition of inputs that need to be defined in the pyMANGA project file.
Include an import of this markdown file the respective ``__init__.py``.

#### Class Comments
Every class (module) should have an accompanying comment that describes what it is for and how it should be used.

#### Function Comments
Declaration comments describe use of the function; comments at the definition of a function describe operation.

Note: Inherited functions can also inherit the docstring shown on the documentation page if it is not overwritten.
An example where this is used is the ``prepareNextTimeStep`` function that is required in each resource module.

#### Variable Comments
In general the actual name of the variable should be descriptive enough to give a good idea of what the variable is used for. In certain cases, more comments are required.

#### Implementation Comments
In your implementation you should have comments on tricky, non-obvious, interesting, or important parts of your code.

#### Punctuation, Spelling and Grammar
Pay attention to punctuation, spelling, and grammar; it is easier to read well-written comments than badly written ones.

#### TODO Comments
Use TODO comments for code that is temporary, a short-term solution, or good-enough but not perfect.

## Formatting

Coding style and formatting are fairly arbitrary, but a project is much easier to follow if everyone uses the same style.
Individuals may not agree with every aspect of the formatting rules, and some rules may take some getting used to, but it is important that all project contributors follow the style rules so that everyone's code is easy to read and understand.
We use Google's **yapf** software to automatically follow the clang format (<a href="https://github.com/google/yapf" target="_blank">yapf</a>).

## Commit messages

At the start of commit message reference to the library you are updating in square-brackets, e.g. “[PML] ...” for PlantModelLib.

Exceptions are:
- “yapf” - reformat code with the yapf auto-reformatter (in PyCharm: crt+alt+L)
- "[doc]..." - documentation related commits
- "[ci] ..." - ci related commits
- "[bmk] ..." - benchmark related commits

## Exceptions to the Rules

The coding conventions described above are mandatory.
However, like all good rules, these sometimes have exceptions, which we discuss here.
You may diverge from the rules when dealing with code that does not conform to this style guide.

Use common sense and BE CONSISTENT.

If you are editing code, take a few minutes to look at the code around you and determine its style.
If they use spaces around their if clauses, you should, too.
If their comments have little boxes of stars around them, make your comments have little boxes of stars around them too.

The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you are saying, rather than on how you are saying it.
We present global style rules here so people know the vocabulary.
But local style is also important.
If code you add to a file looks drastically different from the existing code around it, the discontinuity throws readers out of their rhythm when they go to read it.
 Try to avoid this.

OK, enough writing about writing code; the code itself is much more interesting.
You might be interested in checking out a good reference. 
We would suggest to check the belowground competition concept `SymmetricZOI.py` that can be found at [pyMANGA/ResourceLib/BelowGround/Individual/SymmetricZOI/](https://github.com/pymanga/pyMANGA/blob/master/ResourceLib/BelowGround/Individual/SymmetricZOI/SymmetricZOI.py).  
Have fun!

