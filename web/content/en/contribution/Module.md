
---
title: Set up new modules
linkTitle: Set up new modules
weight: 5

---

pyMANGA is designed to be modular and extensible. 
This means, that new modules can be added to the framework to extend the functionality of the model. 
This guide aims to provide instructions on how to implement new modules in such a way that the overall structure of pyMANGA is maintained and the new module is compatible with the pyMANGA structure.  

This guide will use the plant model concept `Bettina` as an example to explain all requirements for building a module.
As part of the plant models, `Bettina` is located in the folder `PlantModelLib`. 
The folder tree looks like this and contains the following files:  

pyMANGA  
 ┣ PlantModelLib  
 ┃ ┣ Bettina  
 ┃ ┃ ┣ \_\_init__.py  
 ┃ ┃ ┣ Bettina.md  
 ┃ ┃ ┗ Bettina.py  

The file `__init__.py` is used to actually import the class that is implemented in `Bettina.py`. 
If possible, the file `Bettina.md` contains the documentation of the module. 

Note that the class name of the module should match the corresponding folder and file name.  
Otherwise pyMANGA  will not be able to find the module during the model initialization where the xml tags are being processed to be able to check for the existence of e.g. the plant module `Bettina`. 
Plant concepts are checked in `iniPlantDynamicConcept` of `/PopulationLib/Plant.py`. 
If the correct module is found, the corresponding plant model concept is imported. 
This is then parsed and processed with all other case queries in `ProjectLib/Project.py`. 

Overall, the final implementation of the modules always depends on the exact use case. 
This guide is intended to provide a general workflow.

To create meaningful and working documentation, please see to our [Documentation Guide](../documentation).
