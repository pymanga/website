---
title: "Plant-and resource modules"
linkTitle: "Plant-and resource modules"
weight: 2
description:
---

## Design of plant-and resource benchmarks

Benchmarks concerning the plant and resource modules are clustered in sets belonging to a certain plant growth concept (i.e., plant module).
Each set has a reference plant, which is an individual plant, growing with the particular growth concept but without competition or resource limitation (<a href="/docs/Benchmarks/#Figure_1">Figure 1a</a>).
The output metrics of each benchmark are the plant geometry parameters available for the particular plant module, e.g., stem height, crown, root and stem radius (<a href="/docs/Benchmarks/#Figure_1">Figure 1b</a>).
Additional outputs relevant for the tested module might be specified.

<figure class="alert">
    <img id="Figure_1" src="/pictures/benchmarks/reference_tree.jpg">
    <figcaption>
        <i><br><strong>Figure 1:</strong> (a) Module combination to create the pyMANGA reference plant (T<sup>0</sup>). (b) Geometry of T<sup>0</sup> over time.</i>
    </figcaption>
</figure>

Within a set, benchmarks are classified based on the compartment of the module tested, i.e. below-ground interaction, above-ground interaction and plant mortality. 
Modules of the other compartments are defined as for the reference plant  (<a href="/docs/Benchmarks/#Figure_2">Figure 2a</a>). 
This means, for example, to test the below-ground module ‘FixedSalinity’, above-ground interaction is disabled (SimpleTest) and mortality is mechanistic.

The general structure of each benchmark is a 2-plant setup, without recruitment (<a href="/docs/Benchmarks/#Figure_2">Figure 2b</a>).
The plants are placed centered in a 22x22 m model domain with a fixed distance of 2 m. 
The initialization of those plants is based on the geometry of the reference plant. 
The initial population is designed in a way that the respective geometry triggers a potentially critical situation of the concept. 
In some below-ground modules, this is for example the case, when the root systems of the plants overlap.
Thus, we defined an initial population for each compartment ([Table_1](#Table_1)). 
Each initial population is stored in ‘Benchmarks/ModuleTests/<plant_module>/\<compartment>/’.

If land- and seaward boundary conditions need to be defined in a setup, salinity is set to 25 ppt at the landward boundary and to 35 ppt at the seaward boundary. 
Random seed of all setups is 643879.


Time step length is 1e6 seconds (~12 days) and simulation time is 5e8 secs (~ 15.8 years, i.e. 500 time steps).
Output is written after the first and last time step. 
The first output is used for automatic testing.

<figure class="alert">
     <img id="Figure_2" src="/pictures/benchmarks/basic_setup.jpg">
     <figcaption>
        <i><br><strong>Figure 2:</strong> (a) Overview below-ground interaction setups. (b) Schematic representation of benchmark setup (based on Bathmann et al. 2020).</i>
     </figcaption>
</figure>

The following files must be provided for each benchmark
- pyMANGA project file
- Results csv file (`<output_times> [2e6, 5e8] </output_times>`) of type `OneTimestepOneFile`
- All files required to run the setup, e.g. OGS project file (if applicable)
 
The files are stored in 'Benchmarks/ModuleBenchmarks/<plant_module>/\<compartment>/' with the name of the module tested.

## Overview of existing modules and benchmarks

Here is an overview of which modules and benchmarks are available. Modules marked in blue have already been benchmarked. Click on the button to go to the appropriate folder.

### Modules tested with SimpleBettina

SimpleBettina works with all resource and mortality modules and has therefore the most comprehensive collection of benchmarks.

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Aboveground</span>
        </h3>
        <hr>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NULL</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">AsymZOI</span></a>
    </div>
</div>

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Belowground</span>
        </h3>
        <hr>
        <div class="flex-row" style="gap:10px">
            <span class="tag tag-inactive">NULL</span>   
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">FixedSalinity</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-inactive">FON</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">OGS</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-inactive">OGS-External</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">SymZOI</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">SymZOI-FS</span></a>
        </div>
    </div>
</div>      

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Mortality</span>
        </h3>
        <hr>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NoGrowth</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">Memory</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">RandomGrowth</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">Random</span></a>
        <br><br>
        <p style="margin-bottom: 0;"><small><i>Parameter 'k_die' set extremely low in order to force trees to die</i></small></p>
    </div>
</div>


### Modules tested with NetworkBettina

Network modules enable the formation of groups, representing root grafted trees.
Grafted trees can exchange water, based on the water potential gradient between them.

The module describing the group formation as well as the water exchange is 'SimpleNetwork'.
All other below-ground network modules are children of this module and one or two other existing below-ground modules allowing for example the definition of a salinity gradient ('NetworkFixedSalinity').
Network below-ground modules must be combined with the growth module 'NetworkBettina' which is based on 'SimpleBettina' but describes resource allocation to form the root graft.


<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Aboveground</span>
        </h3>
        <hr>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NULL</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">AsymZOI</span></a>
    </div>
</div>

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Belowground</span>
        </h3>
        <hr>
        <div class="flex-row" style="gap:10px">
            <span class="tag tag-active">NULL</span>   
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">SimpleNetwork</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NetworkFixedSalinity</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-inactive">NetworkOGSLargeScale</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-inactive">NetworkOGSLargeScale-External</span></a>
        </div>
    </div>
</div>      

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Mortality</span>
        </h3>
        <hr>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NoGrowth</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">Memory</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">RandomGrowth</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">Random</span></a>
        <br><br>
        <p style="margin-bottom: 0;"><small><i>Parameter 'k_die' set extremely low in order to force trees to die</i></small></p>
    </div>
</div>


### Modules tested with SimpleKiwi

In SimpleKiwi, crown and root radius are not explicitly defined as in Bettina as the tree is only described by dbh and height.
Hence, below- and above-ground modules, which depend on crown and root radius would not work.
We therefore use the equation suggested by Berger and Hildenbrandt (2000) to scale dbh to the so called zone of influence to estimate root and crown radii.
This means however that root and crown radii are equal.




<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Aboveground</span>
        </h3>
        <hr>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NULL</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">AsymZOI</span></a>
    </div>
</div>

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Belowground</span>
        </h3>
        <hr>
        <div class="flex-row" style="gap:10px">
            <span class="tag tag-inactive">NULL</span>   
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">FixedSalinity</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-inactive">FON</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">OGS</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-inactive">OGS-External</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">SymZOI</span></a>
            <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">SymZOI-FS</span></a>
        </div>
    </div>
</div>     

<div class="container">
    <div class="border rounded p-3 mt-1">
        <h3>
            <span class="text-primary">Mortality</span>
        </h3>
        <hr>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">NoGrowth</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">Memory</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">RandomGrowth</span></a>
        <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/BelowgroundCompetition/FixedSalinity" target=”_blank”><span class="tag tag-active">Random</span></a>
        <br><br>
        <p style="margin-bottom: 0;"><small><i>Parameter 'k_die' set extremely low in order to force trees to die</i></small></p>
    </div>
</div>

