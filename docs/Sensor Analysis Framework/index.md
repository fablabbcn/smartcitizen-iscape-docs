Sensor Analysis Framework
=========================

The following section details the framework used for post processing the data in the iScape project. Based on [Jupyter Notebooks](http://jupyter.org/) and running [Python](http://www.python.org) and [R](https://www.r-project.org/), it is intended to provide a state-of-the-art data handling and analysis framework, which can be easily expanded due to it's flexibility and ease of use.

All the files and notebooks related to this document can be found under https://github.com/fablabbcn/smartcitizen-iscape-data.

## Framework structure

The structure of this framework can be summarised as:

- One notebook intended for research and deep data analysis, including exploratory data analysis and a testing environment for sensor model calibration
- One notebook intended for data analysis and report generation, providing a compatible framework to quickly validate test campaigns and generate insights and data visualisations

Both frameworks include interfacing with the **SmartCitizen API** in order to download available sensors from the platform, as well as local csv analysis. Further functionalities are explained below:

### Data analysis notebook

This notebook aims to provide the following features:

- An interface to either retrieve data from the Smart Citizen's API in a simple way or to load them from local sources (in csv format, compatible with the SCK SD card data)
- A data handling framework based on the well known Pandas (http://www.pandas.org) package
- An exploratory data analysis interface to study sensor behaviour and correlations
- A flexible sensor calibration model interface with classical statistical methods such as linear regression, ARIMA, SARIMA-X among others, as well as more modern Machine Learning techniques with the use of LSTM (Long short term memory( networks and MLP (Multi Layer Perceptron) models for sequential data prediction and forecasting
- An interface to statistically validate and study the performance of these models, export and store them
- As a bonus, an interface to convert the python objects into the statistical analysis language R

The framework also provides several functionalities within signal analysis field using numpy and scipy frameworks. 

An example of the workflow can be seen below:

```flow
st=>start: Data Load from API
e=>end: Export Model to API
op=>operation: Add and modify channels
op2=>operation: Exploratory data analysis
op3=>operation: Data model testing and visualisation
cond=>condition: Is the model satisfactory?

st->op->op2->op3->cond
cond(yes)->e
cond(no)->op3
```

#### Loading in the data

As mentioned, data can be downloaded from the SmartCitizen API with the KITs IDs or using local csvs. Several recordings can be grouped and, in order to tidy up the data, it is organised around the concept of **test**, an entity containing all the Kit references, sensors and general information regarding the conditions, grouping and, in general, all necessary information that the devices:

- Test Location, date and author
- Kit type and reference
- Sensor calibration data or reference
- Availability of reference equipment measurement and type

Finally, the devices' data is stored as Time Series data, with DateTime index in ISO6001 format. This is an important consideration for data visualisation and posterious modelling.

An example from the API download can be seen in the below's image:

![](https://i.imgur.com/xJnWWf7.png)

#### Exploratory data analysis

The device's data can be quickly analysed using a simple interface in order to quickly select the desired channels and timeframes. Some of the functionalities already included are:

- Time Series visualisation
- Correlation plot and pairs plot
- Correlogram
- Heatmaps for geospatial data

This section uses interactive plotting frameworks as [Plotly](www.plot.ly) and well know [matplotlib](http://matplotlib.org/) to serve differente exploratory analysis tools:

:::warning
Include plots examples here
:::

#### Data models

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
    - MLP (MultiLayer Perceptron) model with basic RNN cells
    - Single and multiple layers LSTM (Long-Thort Term Memory) networks with the possibility of including several shifted variables in the model training and prediction

Depending on the model selected, different validation techniques are implemented, in order to verify models' assumptions and avoid data misinterpretation (i.e. *Durbin Watson* or *Jacque Bera* test for linear regression). An example of the model is shown below for the estimation of the SGX4514 NO2 value with 

### Data visualisation notebook

This notebook is meant to use the results and analysis performed in the _data analysis notebook_ in order to:

- Provide a similar interface to that from the Data analysis notebook to retrieve data from the API or local sources and handle the data efficiently
- Load models generated previously and apply them to newly captured data
- Analyse the performance of these models and make reports with state-of-the-art data visualisation techniques

:::warning
IMAGE / GIF / ?
:::