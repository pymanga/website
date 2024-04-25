---
title: "Installation of pyMANGA"
linkTitle: "Installation of pyMANGA"
weight: 1
description: 
---

<style type="text/css">
    details summary {color: white; background: #00305E; margin-bottom: 1em;}
    @media(min-width: 992px){
      details{width: 80%}
    }
</style>

## 1 Requirements 

The software **pyMANGA** is written in the programming language [Python](https://www.python.org/) and uses Python libraries. 
That means, during the installation a local library with different **Python modules** will be installed on your computer.
These modules contain source code that is frequently used by many programmers.

If you are new to programming, it might be convenient to install a user interface, a so-called IDE, to work with Python. 
Those IDEs make code easier to read and support the installation and management of modules, for example.
Our team is happy to use [PyCharm](https://www.jetbrains.com/pycharm/) and [Spyder](https://www.spyder-ide.org/), respectively.
Both IDEs offer a free version.

## 2 Download pyMANGA 

First you need to download the current version of **pyMANGA**.  
You can do this either by cloning the [git-repositories](https://github.com/pymanga/pyMANGA/ "https://github.com/pymanga/pyMANGA/") (for advanced users) or by following the instructions below.  

The current version of **pyMANGA** can be found on this [homepage](https://github.com/pymanga/pyMANGA/ "https://github.com/pymanga/pyMANGA/").
Download the source code of the program as shown in <a href="/docs/getting_started/installation/#Figure_1">Figure 1</a> as zip file.

<figure class="alert">
     <img id="Figure_1" src="/pictures/getting_started/installation_of_pymanga/download_pymanga_ubuntu.png" title="Figure 1: You can download pyMANGA from the publicly available git repository.">
	 <figcaption>
     	<i><br><strong>Figure 1:</strong> You can download pyMANGA from the publicly available git repository.</i>
     </figcaption>
</figure>

This zip file must now be unpacked to any location. This example uses the root of your C:\ drive.
Make sure that there are no spaces and no umlauts (like ä,ö,ü,ß) in the file path.
This folder contains all the program components of **pyMANGA**, including ***MANGA.py***, which is the execution file that must be called to execute the program.
Furthermore, the folder contains a collection of benchmarks.

## 3 Install Python and Python Modules

In the following, we describe how to install the following software

- Python3
- Python Modules listed in the [requirements file](https://github.com/pymanga/pyMANGA/blob/master/requirements.txt)

Because the installation differs between operating systems, please select your operating system below.

> **Choosing the correct Python version:**  
> pyMANGA is tested with Python 3.7 and Python 3.11.  
> While current testing indicates that you may be fine using the latest stable release,
> we recommend using Python 3.11. at this point to avoid any unforeseen version related issues.

### 3.1 Ubuntu

<details>
<summary>Installation of Python in Ubuntu</summary>

**Ubuntu 18.04** includes a first installation of (**Python 2** and) **Python 3** by default.
In order to check which version is currently on the computer, after opening a new terminal window with the key combination **"CTRL + Alt + T "**, a version query can be started with the command:

	python3 -V 

It is recommended to update the package directory of the operating system first.
To update the current version, you can use the commands 

	sudo apt update
 
and 

	sudo apt -y upgrade 

to update the whole system - and thus the **Python 3** package.
The updated version can be checked again via the command

	python3 -V

If unexpected problems occur, you can use the command

	sudo apt-get install python3

to (re)install the package.

</details>



<details>
<summary >Installation of Python Modules in Ubuntu <a name="Installation_Ubuntu"></a></summary>

In order to run **pyMANGA**, you may need to install modules that are not yet in the **Python** library but are required by pyMANGA.
Since **Python** also plays an important role in the **Ubuntu** operating system, the pre-installed library is very extensive.
Therefore, it is recommended to install the program first and to install any missing modules after the first execution of the program - **pyMANGA** will tell you which modules are needed.

If **pyMANGA** cannot yet be executed due to missing modules in the local Python library - as mentioned at the beginning - one of the missing packages is displayed in an error message.
For the installation of **Python modules**, **pip** ("Pip installs Python") is suitable.
By opening a terminal window (key combination **Ctrl + Alt + T**) and entering the command

	sudo apt-get install python3-pip

pip can be installed.

To add a **Python module** to the library with **pip** the following command must be entered into a terminal:

	pip3 install name_of_the_module

The modules needed to run **pyMANGA** are listed in the [requirements file](https://github.com/pymanga/pyMANGA/blob/master/requirements.txt). Please download the requirements file by clicking the three dots on the right hand side of the github page and select "Download".
To install all modules listed in the requirements file, you can use the following command. Don't forget to adjust the file to the requirements file according to your download location (e.g. ) 

	pip3 install -r requirements.txt

</details>

### 3.2 Windows

<details>
<summary>Installation of Python in Windows</summary>

To run **pyMANGA**, you must first obtain an **interpreter** for the **Python** programming language.
An example would be **python<sup>T</sup><sup>M</sup>**.
To do this, open your browser and go to [python.org](https://www.python.org/).
In the drop-down menu under ***Download*** you will find the current release version for your operating system of **Python** (this manual describes the procedure for Windows, see <a href="/docs/getting_started/installation/#Figure_2">Figure 2</a>).

<figure class="alert">
     <img id="Figure_2" src="/pictures/getting_started/installation_of_pymanga/download_python_windows_1.jpg" title="Figure 2: Select the python version suitable for Windows on python.org.">
	 <figcaption>
     	<i><br><strong>Figure 2:</strong> Select the python version suitable for Windows on python.org.</i>
     </figcaption>
</figure>

<figure class="alert">
     <img id="Figure_3" src="/pictures/getting_started/installation_of_pymanga/download_python_windows_2.jpg" title="Figure 3: Select Python version 3.7.x from the list of available releases.">
	 <figcaption>
     	<i><br><strong>Figure 3:</strong> Select a stable Python release from the list of available releases. Please note: pyMANGA has only been tested with Python 3.7 and 3.11.</i>
     </figcaption>
</figure>

Open the downloaded file (***python-3.xx.xx-amd64.exe***) and install it on your computer (see <a href="/docs/getting_started/installation/#Figure_4">Figure 4</a>). 

<figure class="alert">
     <img id="Figure_4" src="/pictures/getting_started/installation_of_pymanga/installation_python_windows.jpg" title="Figure 4: Run the downloaded file and install python by following the instructions.">
	 <figcaption>
     	<i><br><strong>Figure 4:</strong> Run the downloaded file and install python by following the instructions.</i>
     </figcaption>
</figure>

This completes the **Python** installation. 
<!-- To start **pyMANGA** some additional preparations have to be made. Go to the subdirectory Preparation and select the appropriate file before your operating system. -->

</details>

<details>
<summary >Installation of Python Modules in Windows <a name="Installation_Ubuntu"></a></summary>

To install python modules, we use the **"Command Prompt"**.
You can easily find it by typing **"Command Prompt"** in the windows search window and opening it with a **mouse click**.
Since pyMANGA is a command line program, everything happens in the command prompt (see <a href="/docs/getting_started/installation/#Figure_5">Figure 5</a>).

<figure class="alert">
     <img id="Figure_5" src="/pictures/getting_started/installation_of_pymanga/open_command_prompt.jpg" title="Figure 5: Start the command prompt">
	 <figcaption>
     	<i><br><strong>Figure 5:</strong> Start the command prompt.</i>
     </figcaption>
</figure>

Now, we install all python modules that are needed to run pyMANGA. As a reminder, the [requirement file](https://github.com/pymanga/pyMANGA/blob/master/requirements.txt) lists all modules that we need to install and is included in the pyMANGA folder you downloaded earlier (<a href="/docs/getting_started/installation/#2-download-pymanga">Download pyMANGA</a>). 
In the command prompt navigate to your pyMANGA folder by using the `cd` command. If you saved the file to the root of your C:\ drive you can use the following command to navigate to the folder:  

	cd C:\pyMANGA

Pip lets us install all modules that are listed in the requirement file with one line of code. This might take a couple minutes. Type or copy the following code into the **command prompt** to start the installation (see <a href="/docs/getting_started/installation/#Figure_6">Figure 6</a>).  

	py -m pip install -r requirements.txt

<figure class="alert">
     <img id="Figure_6" src="/pictures/getting_started/installation_of_pymanga/install_packages_windows.png" title="Figure 6: Install the needed python packages using the command prompt.">
	 <figcaption>
     	<i><br><strong>Figure 6:</strong> Install the needed python packages using the command prompt.</i>
     </figcaption>
</figure>

Note: If the prompt says that ***pip*** is not up-to-date, you can use `upgrade pip` to update it.
However, this is not mandatory.

Now the preparations for using the **compiler** are finished.

<details>
<summary>Further explanations</summary>

- `cd` is short for **change directories** and is used to navigate to a specific folder.  
- `py` means you are calling **Python**. If you have multiple versions of Python installed on your computer, you can use e.g. `py -3.7` to call Python 3.7.
- `-m` means you are calling a module, in this case `pip`, which is used to `install` other **modules**.
- The `-r` flag tells `pip` to read the **requirements** file and install all modules listed in it.
  
</details>

</details>

## 4 Install pyMANGA

After you have set up **Python** on your computer, the next step is to install **pyMANGA**.
The execution of **pyMANGA** is platform dependent, too.

<details>
<summary >pyMANGA execution in Ubuntu <a name="Installation_Ubuntu"></a></summary>

Open a terminal window with the key combination **Ctrl + Alt + T** and navigate to the main level of the program.
Alternatively, you can also choose the graphical way by navigating to the location via Files.
There you can open the console by right-clicking and in the menu that opens, you have to use the field "Open in Terminal" to open a terminal window, where you are already in the main level of the program.

By typing 

	python3 MANGA.py -h

the program will be started.

</details>


<details>
<summary>pyMANGA execution in Windows</summary>

To execute pyMANGA, open the command prompt again. If you are unsure how to open and use the command prompt, please refer to the instructions in the section [Installation of Python Modules in Windows](#32-windows). If you closed the command prompt make sure to navigate to the pyMANGA folder again (e.g. `cd C:\pyMANGA`).  
Now we can run pyMANGA and check the **help** by typing the following command:

	py MANGA.py -h

Again, `py` means Python is called, `MANGA.py` represents the file to be called, and the `-h` flag calls the help. If everything works, pyMANGA provides possible arguments and how to use them to run the program with a project file (<a href="/docs/getting_started/installation/#Figure_7">Figure 7</a>). In the <a href="/docs/getting_started/first_applications_of_pymanga/">next section</a> we will explain how to run pyMANGA with a project file.

<figure class="alert">
     <img id="Figure_7" src="/pictures/getting_started/first_applications_of_pymanga/running_pymanga.jpg" title="Figure 7: pyMANGAs console output provides an example how to use the program and how to properly input a project file.">
	 <figcaption>
     	<i><br><strong>Figure 7:</strong> pyMANGAs console output provides an example how to use the program and how to properly input a project file.</i>
     </figcaption>
</figure>

Note: To find your file path, **right-click** on the ***pyMANGA*** **folder** and go to **Properties**.
Here you will find information about the location of the folder. To access the folder, you have to add the **name** of the **folder** (e.g. `/pyMANGA`) to the file-path.

</details>
