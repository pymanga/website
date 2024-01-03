
---
title: Set up new modules
linkTitle: Set up new modules
weight: 5

---

pyMANGA is designed to be modular and extensible. This means, that new modules can be added to the framework that extend the functionality of the model. This guide aims to provide instruction on how to implement new modules so that the overall structure of pyMANGA is maintained and the new module is compatible with the way pyMANGA runs simulations.  

This guide will use the plant model concept `Bettina` as an example to explain all requirements for building a module. As part of the plant models, `Bettina` is found in the folder `PlantModelLib`. The folder tree looks as follows and contains the following files:  

pyMANGA  
 ┣ PlantModelLib  
 ┃ ┣ Bettina  
 ┃ ┃ ┣ \_\_init__.py  
 ┃ ┃ ┣ Bettina.md  
 ┃ ┃ ┗ Bettina.py  

The file `__init__.py` is used to actually import the class that is implemented in `Bettina.py`. If possible, the filme `Bettina.md` contains the documentation of the module. However, at this point, pyMANGA does not now how to handle this module. pyMANGA checks for the state of all entries in the project file to determine which modules are used. This means, that the module needs to be added to the initialization part of pyMANGA where the xml tags are being processed to be able to check for the existence of e.g. plant module `Bettina`. Plant concepts are checked in `iniPlantDynamicConcept` of `/PopulationLib/Plant.py`. If the correct module is found, the appropriate plant model concept is imported. This is then parsed and processed along all other case queries in `ProjectLib/Project.py`. The case query can also be implemented directly in `Project.py` as is already done for example with the belowground resource concepts in `iniBelowgroundResourceConcept`.  
Overall, the final implementation of modules always depends on the exact use case and this guide aims to provide only a general workflow.  
Note that the class name of all modules is supposed to match the respective folder and file names.  

For creating meaningful and working documentation, please refer to our [documentation guide](../documentation)  