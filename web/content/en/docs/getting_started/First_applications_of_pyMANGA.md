---
title: "First applications"
linkTitle: "First applications"
weight: 2
description:
---

<style type="text/css">
    details summary {color: white; background: #00305E; margin-bottom: 1em;}
    @media(min-width: 992px){
      details{width: 80%}
    }
</style>

Before you get started with your first applications, you should read the <a href="/docs/getting_started/installation">installation and preparation instructions</a> for your operating system, if you haven't already done so.  
This is especially recommended for beginners who have little experience with **Python** and the input console.  
Instructions are provided for Windows and Ubuntu and should be applicable to other operating systems with minor tweaks.

## 1 Setup without OpenGeoSys

> Here, we explain how to run a simple pyMANGA setup.  
> In this setup, 10 black mangrove trees grow at seawater salinity.  
> Tree growth follows the BETTINA approach.  
> Model output is written to the folder 'ModelOutput' in the same directory.  
> More examples can be found [here](/docs/benchmarks/) and in our [benchmark gallery](https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/).

After following the [installation](/docs/getting_started/installation) section, pyMANGA is installed and tested by running `py MANGA.py -h` in the command line. We can now provide a project file to **pyMANGA** and execute an example setup.

To do so, you need to add the path to the pyMANGA project file as input.  
For **Windows** type:

	py -3.7 MANGA.py -i Benchmarks/ExampleSetups/FirstApplication/example_setup.xml

respectively for **Ubuntu**:

    python MANGA.py -i Benchmarks/ExampleSetups/FirstApplication/example_setup.xml

***-i*** refers to the index or path of the file in which the input to be used for this example is defined.

This code calls **pyMANGA** with the control file 'example_setup.xml'.
For detailed information on the structure of control files see [Control File](/docs/control_file/) or the <a href="https://pymanga.github.io/pyMANGA/pyMANGA.html" target="_blank">pyMANGA documentation</a>.



## 2 Setup with OpenGeoSys

> Here, we explain how to run the complex pyMANGA setup 'OGS3D_SAZOI_BETTINA' from our <a href="https://github.com/pymanga/pyMANGA/tree/master/Benchmarks/" target="_blank">benchmark gallery</a>.
> More information on our benchmarks can be found <a href="https://pymanga.forst.tu-dresden.de/docs/benchmarks/" target="_blank">here</a>,
> and a detailed OGS setup can be found <a href="https://pymanga.forst.tu-dresden.de/docs/example_ogs_bettina/" target="_blank">here</a>.


This setup uses <a href="https://www.opengeosys.org/">**OpenGeoSys**</a> (OGS), which is a scientific open source project for the development of numerical methods for the simulation of thermo-hydro-mechanical-chemical (THMC) processes in porous and fragmented media.
To use **OGS**, you need to download and install it.
Again the installation is different for windows and ubuntu.


<details>
<summary >Installing OGS</summary>

To use **OGS**, you have to download and install it first.
pyMANGA has been tested with OGS version **6.4.0**.
On this <a href="https://www.opengeosys.org/releases/6.4.0/" target="_blank">homepage</a> you will find several variants of OGS version 6.4.0.
Select the variant with 'Python bindings' and 'Utilities'.

**Please make sure that you download exactly this version of OGS.**

Unzip the archive and move all folders it contains to:

	./ResourceLib/BelowGround/Individual/OGS/

The files must be located directly in this folder.

To check if OGS is executable on your computer, open a terminal in the **pyMANGA** root directory and enter the following:

	./ResourceLib/BelowGround/Individual/OGS/bin/ogs.exe

If OGS runs correctly, you will get the following output:

	PARSE ERROR:
	             Required argument missing: project-file

	Brief USAGE: 
	   ./ogs  [--enable-fpe] [--unbuffered-std-out]
	          [--config-warnings-nonfatal] [-l <LOG_LEVEL>] [-o <PATH>] [-r
	          <PATH>] [--] [--version] [-h] <PROJECT_FILE>

If this does not work, first check if you have installed the Python module "vtk" in version 9.2.2.

Please read the section about <a href="https://pymanga.forst.tu-dresden.de/docs/getting_started/installation/" target="_blank">installing pyMANGA</a> on Ubuntu. 
If you encounter insurmountable problems at this point, please <a href="https://github.com/pymanga/pyMANGA/issues/new" target="_blank">contact us</a>.


</details>

<details>
<summary>First applications of pyMANGA with OGS</summary>

By opening a terminal in the pyMANGA main level and entering the following command, you can start the next application example:

	python3 MANGA.py -i Benchmarks/ExampleSetups/OGSExampleSetup/OGS3D_SAZOI_BETTINA.xml
or

	py MANGA.py -i Benchmarks/ExampleSetups/OGSExampleSetup/OGS3D_SAZOI_BETTINA.xml


Note: The computation time when using OGS can take several hours.
You can reduce this time by opening 

***.\Benchmarks\ExampleSetups\OGSExampleSetup\OGS3D_SAZOI_BETTINA.xml*** 

and changing the line 22 to

	<delta_t_ogs> 604800 </delta_t_ogs>

This is the time step length (in seconds) that indicates how long the groundwater flow model calculates before extrapolating the rest of the BETTINA time step.
From the results, the pore water distribution is extrapolated under steady state assumptions.
Therefore, this parameter must be used very carefully, but it is a means to significantly reduce the computation time.

</details>

