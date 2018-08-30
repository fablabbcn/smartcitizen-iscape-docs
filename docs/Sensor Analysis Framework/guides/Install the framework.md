iSCAPE Sensor Analysis Framework
================================

Welcome to the first version of the [iSCAPE](https://www.iscapeproject.eu/) Sensor Analysis tools. The framework is built with the purpose of helping on the calibration process of the sensors on field tests and it aim to be the primary tool for manipulating the sensors data. The framework is built on [Jupyter Notebooks](http://jupyter.org/) and the data analysis tools are based on [Pandas](http://pandas.pydata.org/) and are ready to later support [Scikit](http://scikit-learn.org/stable/index.html).

![](https://i.imgur.com/sAOtjv3.jpg)

The current notebook supports data from the iSCAPE Citizen Sensors we provided you but we will add support to integrate the data from existing equipment. Currently all the data is loaded as CSV files but it is also ready to get live data directly from the Smart Citizen API in the future.

The primary goal of the tools is to help us validate the different iSCAPE sensors and calculate their calibration values that later might automatically applied to the data the sensors push online.

_Notice this is currently a single Notebook that should work as a boilerplate to new Notebooks each with each own specific purpose._

[Complete Documentation](https://hackmd.io/KYTghgHArGAMBmBaAxrA7GxAWAjAZjEQhwiQjQDY08ATNYrWAJiA/publish)
[Github Repository](https://github.com/fablabbcn/smartcitizen-iscape-data)

<a href="https://www.iscapeproject.eu/"><img src="https://i.imgur.com/xqyPGi4.png" alt="Drawing" style="width: 120px; margin-bottom: 20px;"/></a>


## How to install the framework

The following data analysis framework is built on Python 2.7 and Jupyter Notebooks. Here we will show you how to install it:

1. Dowload and Install Anaconda for Python 2.7 https://www.continuum.io/downloads

2. Visit [Github](https://github.com/fablabbcn/smartcitizen-jupyter) to download the project folder or simply use `git`.


3. Open the **Anaconda Navigator** app and launch the **Jupyter Notebook**.

![](https://i.imgur.com/IBR56I7.png)

![](https://i.imgur.com/5Hlnmxh.png)

4. Using the **Jupyter Notebook** website browse your computer to find the project folder.

![](https://i.imgur.com/66901MG.png)



:::success

:rocket: **READY?**

Go and check [How to use the notebook]()

:::

:::info

**LEARN MORE** 

Still wondering what this is? Read this introduction to [Jupyter](http://jupyter-notebook.readthedocs.io/en/latest/examples/Notebook/Notebook%20Basics.html)

:::

:::warning

**ADVANCED INSTALLATION** 

If you are already familiar with Python and you like to avoid installing **Anaconda** and follow the [Advanced users installation](#advanced-users-installation)

:::

:::danger

**WORRIED ABOUT YOUR EXISTING PYTHON?** 

Do you have already a Python environment you use for other work and you are worried about updating some packages? 

Learn how to [load a dedicated environment](#how-to-run-the-project-isolated-from-your-python-environment)

:::


## How to use the notebook

The **[MICS Analysis Notebook](https://github.com/fablabbcn/smartcitizen-iscape-data/blob/master/notebooks/MICS-Analysis-v0.1.ipynb)**  is designed as fully interactive tool for data. Later on you might like to customize them and make them static for specific purposes.

### Load the data

Load the data from your Smart Citizen Kits in CSV format to analyse the data or prepare it for other applications. You can run a single one but to take full advantatge of the functionalities you should load two files.

![](https://i.imgur.com/Cez1vGY.gif)


:::info

**REFERENCE EQUIPMENT** 

We plan to add support to the file format of your calibration equipment in order to analyse and compare the data using the same approach.

:::

### Plot the data

This allows you to plot your data over time by sensor and device. On the next iterations you will be able to select the time range you want. 

![](https://i.imgur.com/okY8vCi.gif)

### Cross sensors interferances

This module displays a simple correlation table per device that might be helpful to have an overview to possible cross sensors interferances.

![](https://i.imgur.com/L6MvKld.gif)
![](https://i.imgur.com/YuQ8BPM.gif)

### Sensor Correlations

This module is the core module towards understanding cross device correlation and determination. This currently allows you to look at the determination across two different devices but in the upcoming days it might support to correlate the data against your reference equipment.

![](https://i.imgur.com/CvUuWpL.gif)


___________________

## Advanced installation features

### How to run the project isolated from your Python environment

_Do you have already a Python environment you use for other work and you are worried about updating some packages?_

**Conda** can load a dedicated environment for you to run **Python** and **Jupyter** based on the `environment.yml` configuration file we provide.

Open your favourite shell on the directory you have your project. _(`cmd.exe` on windows)_ 
 
Run the following commands:

* This will install and load the Python environment we prepared for iSCAPE

    `conda env create -f environment.yml`

* Now activate the environment

    `source activate iscape`
    
*  Ready, run to run Jupyter

    `jupyter notebook`


### Advanced users installation

If you do not want to install **Anaconda** you can install all the dependencies manually. Just follow the steps above:

#### Install Python

Python is the main programming language we will use for Data Analysis.

- On Windows download and run the [installer](https://www.python.org/downloads/windows/) for Python 2.7
- Mac cames directly with python built in. However you can install the latest version using [Hombrew](https://brew.sh/) and then run `$ brew install python`
- On Linux simply use your distribution package manager like `$ apt` in Debian or Ubuntu. 

#### Install Pip

Pip is the packet manager Python uses and it comes installed by default. If you have any issues you can download pip [here](https://pip.pypa.io/en/stable/installing/). 

#### Installl Jupyter

Jupyter Notebooks allows us to quickly learn, develop and improve our tools by providing a common convenient framework and UI. 

Simply run `pip install jupyter` on your terminal to install it.

#### Download the source

[Download](https://github.com/fablabbcn/smartcitizen-jupyter) from Github or simply use `git`

```
git clone https://github.com/fablabbcn/smartcitizen-jupyter.git
```

#### Run the notebook

On your terminal go to the folder where tou downloaded your files and then run `jupyter notebook` this will open a new webpage and you will be available to run your code there.


___________________

<img src="https://i.imgur.com/xqyPGi4.png" alt="Drawing" style="width: 150px; margin-bottom: 20px;"/>

_The [Smart Citizen Team ](https://smartcitizen.me/kits/)for the [iSCAPE Project](https://www.iscapeproject.eu/)_

___________________

![](https://www.iscapeproject.eu/wp-content/uploads/2016/09/European-flag1.png)

iSCAPE has received funding from the European Community’s H2020 Programme under Grant Agreement No. 689954.
