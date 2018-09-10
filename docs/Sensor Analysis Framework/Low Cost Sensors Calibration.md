Low Cost Sensors Calibration
============================

## Principles

The **sensor calibration procedure** for the iScape sensor solution can be split into three stages:

1. **Behaviour assesment**: Base testing for assessing general sensor response, stabilisation time or operational modes. Pulse mode operation is also explored in this stage for energy saving purposes.

2. **Characterisation**: Laboratory condisiorAssess generic sensor parameters sensitivity, zero and span.

3. **Modelisation**: Include other variables such as environmental factors and sensor cross-sensitivity.

Each of these stages apply differently depending on the type of sensor, for instance the electrochemical sensors present in the *Station* are already characterised by the manufacturer, while the Metal Oxyde Sensors in the *Urban Board* of the *Citizen Kit* are not. The different characteristics of these sensors make different calibration approaches to be carried out.

An **initial behaviour assessment** is to be carried out in laboratory conditions in order to determine the optimal operational modes. This includes basic parameters such as sensor response, heating time and temperature as well as more advanced ones such as heating pulse mode operation. For this purpose, a portable, open source, reproducible **test cell** has been developed for controlled testing with a web based acquisition interface.

Secondly, **base calibration parameters** need to be determined in controlled conditions. In this stage, the aim would be to find parameters such as:

- **Sensor sensitivity**: the sensor response per each ppm of target pollutant in _nominal_ conditions
- **Zero**: the sensor reading in zero air (pure air at 25degC).
- **Sensor response** (t<sub>90</sub>)
- **Sensor range**: maximum and minimum readings for the sensor

Finally, after this initial calibration assessment, it is critical to gather as much data as possible from **long term sensor deployments**. These deployments should aim to cover the widest range of sensor exposure conditions, in order to generate robust models. While dealing with low cost sensors this stage is very important, as it is detailed in the sections below.

These sensor deployments serve for two main purposes: to generate **quantitative classification methods** that can classify the air quality in predefined ranges (i.e. 'poor', 'fair', good'); and to generate **predictive qualitative models** for more accurate values. Either of them need large amounts of data if the models are aimed to be representative. Additionally, by the mere nature of the data and the sensors themselves, these models would need to be capable of:

- Robust to noise
- Learn non-linear relationships
- Multivariate inputs
- Learned temporal dependence

These needs make **machine learning** methods great canditates for modeling the data. Traditionally, time series forecasting has been dominated by linear methods because they are well understood and effective on many simpler forecasting problems. However, deep learning neural networks are able to automatically learn arbitrary complex mappings from inputs to outputs and support multiple inputs and outputs. Therefore, deep learning methods such as MLPs and LSTMs offer a lot of promise for the type of problem presented in the iScape project. The combination of these algorithms with large amounts of data gathered during the iScape project offers a great opportunity to demonstrate the use of low cost sensors for air quality monitoring.

These deployments should at least guarantee the following needs:

- A checked reference measurement for the sensors to be compared against it
- Sufficient sensor stabilisation time and varied operational conditions
- Careful monitoring of the sensor correct operation: connectivity and power supply, among others

## Metal Oxyde Sensors

Due to their construction, low cost metal oxyde sensors suffer from high levels of spread for their baseline resistance and sensitivity. As well, these sensors are generally reactive to other pollutants in the atmosphere, with low selectivity of the actual target pollutant and drifts in their behaviour can be seen after some weeks of exposure. Therefore, metal oxyde sensors require a careful characterisation and modelisation in both, laboratory and open air conditions.

Furthermore, metal oxyde sensors show short and long term drifts in their calibrations. For this reason, a **recursive calibration** approach is proposed. This procedure would comprise:

![](https://i.imgur.com/TELqobn.png)

- **Sensor characterisation** in laboratory conditions to assess sensitiviy, baseline resistances sensor-to-sensor spread, aiming to obtain normalising factors for each sensor or group of sensors
- **Sensor collocation** with reference equipment for model development, accounting for the laboratory factors obtained in the previous stage and in order to include more complex environmental factors
- **Sensor deployment** stage with independent measurement
- **Sensor re-assessment** by either laboratory characterisation or collocation with reference equipment. This could serve for correction for the model parameters used during the deployment and to assess the sensor reliability and need for replacement

Further to the sensor re-assessment, other deployments could be explored should there not be sensor breakdown.

!!! info "SGX MICS-4514 implementation"
	Read more on the SGX MICS-4514 implementation on the [**Urban Sensor Board**](/Components/Urban%20Sensor%20Board/#metal-oxide-no2-and-co-sensor).

## Electrochemical Sensors

The **electrochemical sensor** manufacturer keeps a database of the sensor sensitivities and zero currents (baseline response) of each individual sensor. Therefore, the calibration approach for the electrochemical sensors is reduced to an in-field validation of their behaviour and a model proposal that is described in the [*Electrochemical sensor baseline methodology* Section](https://docs.iscape.smartcitizen.me/Components/Gas%20Pro%20Sensor%20Board/Electrochemical%20Sensors/#sensor-calibration).

Surely, further models developed after long term data collection with field deployments are to be considered in order to improve sensor readings.

!!! info "Alphasense Series B implementation"
	Read more on the Alphasense Series B implementation on the [**Gas Pro Sensor Board**](/Components/Gas%20Pro%20Sensor%20Board/).

## PM Sensors

The selected PM sensor is as well, characterised by the manufacturer and it provides an accurate measurement with it's calibration. As with the above mentioned electrochemical sensors, a long term field deployment with reference equipment is to considered in order to develop more complex models including environmental features such as humidity, which has been demonstrated to have an influence on PM readings.

!!! info "Plantower PMS 5003"
	Read more on the Plantower PMS 5003 implementation on the [**Gas Pro Sensor Board**](/Components/PM%20Sensor%20Board/).