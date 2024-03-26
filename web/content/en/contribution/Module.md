
---
title: Create new modules
linkTitle: Create new modules
weight: 5

---

pyMANGA is designed to be modular and extensible. This means, that new modules can be added to the framework to extend the functionality of pyMANGA. This guide aims to provide instructions on how to implement new modules so that the overall structure of pyMANGA is maintained and the new module is compatible with the way pyMANGA runs simulations.  

In the following, we describe this in more detail using the existing plant model concept `Bettina`. As part of the plant models, `Bettina` is located in the `PlantModelLib` folder. The folder tree looks as like this:  

pyMANGA  
 ┣ PlantModelLib  
 ┃ ┣ Bettina  
 ┃ ┃ ┣ \_\_init__.py  
 ┃ ┃ ┣ Bettina.md  
 ┃ ┃ ┗ Bettina.py  

- `__init__.py` is used to actually import the class that is implemented in `Bettina.py` as well as the non-technical documentation fo the module
- `Bettina.md` contains the non-technical documentation of the module
- `Bettina.py` contains the class `Bettina`

Plant modules are initialized in `iniPlantDynamicConcept` of `/PopulationLib/PlantGroup.py`. If the correct module is found, the corresponding plant module is imported. This is then parsed and processed with all other case queries in `ProjectLib/Project.py`. 

Resource and ModelOutput modules are initialized in `ProjectLib/Project.py` .  

For creating meaningful and working documentation, please refer to our [documentation guide](../documentation)  