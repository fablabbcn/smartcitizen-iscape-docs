Sensor Analysis Framework
=========================

The following section details the framework used for post processing the data in the iScape project. Based on [Jupyter Notebooks](http://jupyter.org/) and running [Python](http://www.python.org) and [R](https://www.r-project.org/), it is intended to provide a state-of-the-art data handling and analysis framework, which can be easily expanded due to it's flexibility and ease of use.

All the files and notebooks related to this document can be found online in our Github repository:

<a class="github-button" data-size="large" href="https://github.com/fablabbcn/smartcitizen-iscape-data" aria-label="Check the source code">Check the source code</a>

## Framework structure

The structure of this framework can be split between two main areas: one dedicated to sensor data analysis and model generation; and an automated sensor correction script that recovers sensor data from the API, processes it, and posts it back to the API with the use of the results obtained in the data analysis. This structure is decribed in the following diagram:

![](https://i.imgur.com/CLlzFs7.png)

Furthermore, within the sensor data analysis, a notebook and several scripts are included, intended for **modeling and data visualisation**, including exploratory data analysis and a testing environment for sensor model calibration. This includes interfacing with the **SmartCitizen API** in order to download available sensors from the platform, as well as local csv analysis. Further functionalities are explained in the following sections.

### Data analysis notebook

This notebook aims to provide the following features:

- An interface to either retrieve data from the Smart Citizen's API in a simple way or to load them from local sources (in csv format, compatible with the SCK SD card data)
- A data handling framework based on the well known [Pandas](http://www.pandas.org) package
- An exploratory data analysis interface to study sensor behaviour and correlations
- A flexible sensor calibration model interface with classical statistical methods such as linear regression, ARIMA, SARIMA-X among others, as well as more modern Machine Learning techniques with the use of LSTM (Long short term memory) networks and MLP (Multi Layer Perceptron) models for sequential data prediction and forecasting
- An interface to statistically validate and study the performance of these models, export and store them
- As a bonus, an interface to convert the python objects into the statistical analysis language R

The framework also provides several functionalities within signal analysis field using numpy and scipy frameworks. 

An example of the workflow can be seen below:

![](https://i.imgur.com/bAtUNFf.png)

!!! tip "Step by step guides"
	* [Install the framework](/Sensor Analysis Framework/guides/Install the framework/)
	* [Use Machine Learning to Create Models for Sensors Calibration](/Sensor Analysis Framework/guides/Creating Models for Sensors Calibration/)
	* [Post process the stations data](/Sensor Analysis Framework/guides/Post processing the Stations Data/)


#### Loading in the data

As mentioned, data can be downloaded from the SmartCitizen API with the KIT IDs or using local csv. In order to tidy up the data, the recordings are organised around the concept of **test**, an entity containing all the kits' references, sensors and general information regarding the conditions at which the measurements were carried out:

- Test Location, date and author
- Kit type and reference
- Sensor calibration data or reference
- Availability of reference equipment measurement and type

A brief schema of the test structure is specified below:

![](https://i.imgur.com/LkKgC9D.png)


All this structure is filled up at the test creation  with a dedicated script, saving future time to understand mismatching reading units, timestamps formats and so on.

Finally, the devices' data is stored as Time Series data, with DateTime index in ISO8601 format. This is an important consideration for data visualisation and posterious modelling.

An example from the API download can be seen in the below's image:

![](https://i.imgur.com/xJnWWf7.png)

#### Exploratory data analysis (WIP)

The device's data can be quickly analysed using a simple interface in order to quickly select the desired channels and timeframes. Some of the functionalities already included are:

- Time Series visualisation
- Correlation plot and pairs plot
- Correlogram
- Heatmaps for geospatial data

This section uses interactive plotting frameworks as [Plotly](http://plot.ly) and well know [matplotlib](http://matplotlib.org/) to serve differente exploratory analysis tools:

#### Data models (WIP)

The data models section includes an easy to use and full interface to select data from different devices within a test in order to calibrate different models. Since the data is mainly based on Time Series analysis, it interfaces with common statistics and machine learning frameworks such as [sci-kit learn](http://scikit-learn.org/), [tensorflow](https://www.tensorflow.org), [keras](http://keras.io/), and [stats models](http://www.statsmodels.org/dev/tsa.html#module-statsmodels.tsa). These frameworks provide tools to perform:

**Pre-processing stage:**

- **Outliers** detection with Holt-Winters methods (triple exponential smoothing)
- Data study and analysis for **multicollinearity** and **autocorrelation** in order to determine significant variables and avoid model overfit with non-significant exogenous variables
- **Trend decomposition** and **seasonality** analysis
- **Data split** between training and test dataset, with the possibility of rolling prediction

**Model stage:**

- **Baseline model** estimations in order to assess minimum targets for model quality (using naive regression models)
- **Ordinary Linear Regression** techniques for univariate and multivariate linear and non-linear independent variables
- **ARIMA-X** (Autorregresive, Integrated, Moving Average) models with exogenous variables using Box-Jenkis parameter selection methods
- More advanced **machine learning** techiques with RNN (Recurrent Neural Networks) for sequence predictions:
    - **MLP** (MultiLayer Perceptron) model with basic RNN cells
    - Single and multiple layers **LSTM** (Long-Thort Term Memory) networks with the possibility of including several shifted variables in the model training and prediction

An example of the model is shown below for the estimation of the SGX4514 CO with the use of the rest of the Kit's available sensor, using a single layer LSTM network only two weeks of training:

![](https://i.imgur.com/aoX2GcF.png)

Depending on the model selected, different validation techniques are implemented, in order to verify models' assumptions and avoid data misinterpretation (i.e. *Durbin Watson* or *Jacque Bera* test for linear regression). Finally, it is important to follow carefully the instructions as stated in the notebook, in order to avoid low model quality.

#### Model import/export and storage

Once the model is analysed and validated, it can be saved and exported. This allows using the model in the future with the same variables in other sensor studies. The model objects are serialised with [Pickle](https://docs.python.org/2/library/pickle.html) and can be uploaded to a git repository for later use.

## Source files

<a class="github-button" data-size="large" href="https://github.com/fablabbcn/smartcitizen-iscape-data/archive/master.zip" data-icon="octicon-cloud-download" aria-label="Download from GitHub">Download</a>

<a class="github-button" data-size="large" href="https://github.com/fablabbcn/smartcitizen-iscape-data" aria-label="Check the source code">Check the source code</a>