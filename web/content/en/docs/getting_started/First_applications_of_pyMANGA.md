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

> Here, we explain how to run the complex pyMANGA setup 'OGS3D_SAZOI_BETTINA' from our [benchmark gallery](https://github.com/jbathmann/pyMANGA/tree/master/Benchmarks/ModuleBenchmarks/GrowthAndDeath/SimpleBettina).
> More information on our benchmarks can be found [here](/docs/benchmarks/),
> and a detailed OGS setup can be found [here](/docs/example_ogs_bettina/).

This setup uses <a href="https://www.opengeosys.org/">**OpenGeoSys**</a> (OGS), which is a scientific open source project for the development of numerical methods for the simulation of thermo-hydro-mechanical-chemical (THMC) processes in porous and fragmented media.
To use **OGS**, you need to download and install it.
Again the installation is different for windows and ubuntu.


<details>
<summary >First applications of pyMANGA with OGS in Ubuntu</summary>

On this <a href="https://github.com/ufz/ogs/releases/tag/6.2.2">homepage</a> you will find several variants of OGS version 6.2.2 at the bottom of the page.
Select the variant **"ogs-6.2.2-Linux-5.3.4-arch1-1-ARCH-x64-python--de-utils "** and download the compressed folder or use this [link](https://github.com/ufz/ogs/releases/download/6.2.2/ogs-6.2.2-Linux-5.3.4-arch1-1-ARCH-x64-python-de-utils.tar.gz) directly. 
**Please make sure that you download exactly this version of OGS.**

Unzip the folder and move the three folders it contains (_bin_, _lib_ and _share_) seen from the pyMANGA main level to the following folder:

	./ResourceLib/BelowGround/OGS

The files must be located directly in this folder.
To check if OGS is executable on your computer, open a terminal in the **pyMANGA** main level and enter the following:

	./ResourceLib/BelowGround/OGS/bin/ogs

If OGS runs correctly, you will get the following output:

	PARSE ERROR:
	             Required argument missing: project-file

	Brief USAGE: 
	   ./ogs  [--enable-fpe] [--unbuffered-std-out]
	          [--config-warnings-nonfatal] [-l <LOG_LEVEL>] [-o <PATH>] [-r
	          <PATH>] [--] [--version] [-h] <PROJECT_FILE>

If this does not work, first check if you have installed the Python module "vtk" in version 8.1.2.
Please also read the <a href="/en/docs/first_steps/installation#Installation_Ubuntu">section on installing pyMANGA in Ubuntu</a>.
If you encounter insurmountable problems at this point <a href="/en/impressum">contact</a> us.


Now you can start the next application example by opening a terminal in the **pyMANGA** main level and entering the following command:

	python3 MANGA.py -i Benchmarks/ExampleSetups/OGSExampleSetup/OGS3D_SAZOI_BETTINA.xml

</details>

<details>
<summary>First applications of pyMANGA with OGS in Windows</summary>

To use **OGS** you have to download and install it first.
To do so, go to the following [website](https://www.opengeosys.org/releases/ "https://www.opengeosys.org/releases/") and scroll down until you find **version 6.4.0** and download it (see <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_2">Figure 2</a> and <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_3">Figure 3</a>).

<figure class="alert">
     <img id="Figure_2" src="/pictures/getting_started/first_applications_of_pymanga/version_ogs_windows.jpg" title="Figure 2: OGS version selection">
	 <figcaption>
     	<i><br><strong>Figure 2:</strong> OGS version selection.</i>
     </figcaption>
</figure>
</figure>

<figure class="alert">
     <img id="Figure_3" src="/pictures/getting_started/first_applications_of_pymanga/download_ogs_windows.jpg" title="Figure 3: Make sure to select the correct version including Python bindings.">
	 <figcaption>
     	<i><br><strong>Figure 3:</strong> Make sure to select the correct version including Python bindings.</i>
     </figcaption>
</figure>


Select the file to be downloaded according to your operating system.
Then unzip the zip file, copy the ***bin*** folder and paste it into the ***pyMANGA-master*** folder in the following path (see <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_4">Figure 4</a>).

	pyMANGA-master\ResourceLib\BelowGround\OGS

<figure class="alert">
     <img id="Figure_4" src="/pictures/getting_started/first_applications_of_pymanga/ogs_path.jpg" title="Figure 4: OGS location within pyMANGA.">
	 <figcaption>
     	<i><br><strong>Figure 4:</strong> OGS location within pyMANGA.</i>
     </figcaption>
</figure>


**OGS** is now installed. To test if it works properly, open the ***_Bin_*** folder, press **shift** and the **right mouse button** and select **Open PowerShell window here** (see Figure <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_5">Figure 5</a>).

<figure class="alert">
     <img id="Figure_5" src="/pictures/getting_started/first_applications_of_pymanga/ogs_powershell.jpg" title="Figure 5: Open PowerShell in the correct location with shift+right click.">
	 <figcaption>
     	<i><br><strong>Figure 5:</strong> Open PowerShell in the correct location with shift+right click.</i>
     </figcaption>
</figure>


Copy the path that appears in the **PowerShell window** and append ***\OGS*** and press Enter.
The following <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_6">Figure 6</a> shows the PowerShell window output when OGS is running smoothly. 

<figure class="alert">
     <img id="Figure_6" src="/pictures/getting_started/first_applications_of_pymanga/output_ogs_runs.jpg" title="Figure 6: If your PowerShell output looks like this, OGS is installed properly.">
	 <figcaption>
     	<i><br><strong>Figure 6:</strong> If your PowerShell output looks like this, OGS is installed properly.</i>
     </figcaption>
</figure>

Now you can start the next application example by opening the command prompt in the ***pyMANGA-master*** folder and starting pyMANGA as usual.
Then enter the following command (see <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_7">Figure 7</a>).

	py -3.7 MANGA.py -i \Benchmarks\ExampleSetups\OGSExampleSetup\OGS3D_SAZOI_BETTINA.xml

<figure class="alert">
     <img id="Figure_7" src="/pictures/getting_started/first_applications_of_pymanga/run_ogs_sample_setup.jpg" title="Figure 7: Example run of pyMANGA with OGS enabled.">
	 <figcaption>
     	<i><br><strong>Figure 7:</strong> Example run of pyMANGA with OGS enabled.</i>
     </figcaption>
</figure>


Note: The computing time can take several hours.
You can reduce this by opening 

***.\Benchmarks\ExampleSetups\OGSExampleSetup\OGS3D_SAZOI_BETTINA.xml*** 

and changing the line 22 to

	<delta_t_ogs> 604800 </delta_t_ogs>

This is the time step length, which indicates how long the groundwater flow model calculates before the rest of the BETTINA time step is extrapolated, given in seconds.

From the results the pore-water distribution is extrapolated under steady state assumptions.
Consequently, this parameter has to be used very carefully but is a means to significantly reduce computing time (see <a href="/docs/getting_started/first_applications_of_pymanga/#Figure_8">Figure 8</a>).

<figure class="alert">
     <img id="Figure_8" src="/pictures/getting_started/first_applications_of_pymanga/set_timestep_length.jpg" title="Figure 8: You can modify the time step length to reduce runtime (line 22).">
	 <figcaption>
     	<i><br><strong>Figure 8:</strong> You can modify the time step length to reduce runtime (line 22).</i>
     </figcaption>
</figure>

</details>

