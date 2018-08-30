Introduction to Low Cost Air Quality Calibration
================================================

!!! note "Section under development"
    The following section is currently a work in progress.

## Testing methodologies and calibration models

**1.1. Field calibration of a cluster of low-cost available sensors for air quality monitoring. Part A: Ozone and nitrogen dioxide - [Link](https://www.sciencedirect.com/science/article/pii/S092540051500355X#fig0010)**

Note on **evaluation of calibration method**

>The evaluation of sensor performances took into account hourly values. It was carried out using only values predicted by each calibration method. For each one, regression and difference-based analysis were conducted to evaluate their performance. These included the calculation of the coefficient of determination (R2),comparing the slope and intercept of the regression line with objective values of 1 and 0 respectively. The mean bias error (MBE)and the root mean squared error (RMSE) standardized with the standard deviation of the reference measurements were used to draw a target diagram [38].To assess the performance of each calibration method at individual air pollutant levels, we have also calculated the measurement uncertainty using orthogonal regression of the estimated outputs against reference data. This uncertainty was compared to the DQO for indicative method that corresponds to a rela-tive expanded uncertainty of 30% for O3 and 25% for NO2 at the limit value set by the European Directive. The estimation method of the uncertainty, which corresponds to the relative expanded uncertainty Ur, was carried out using Eq. (1) where b0 and b1 are the slope and intercept of the orthogonal regression and RSS the sum of square of residuals is calculated using Eq. (2).
>
>![](https://i.imgur.com/fNjTyC6.png)

Note on **correlation**:

> An important aspect of the dataset is the lack of independence between parameters. Usually, O3 is highly correlated with temperature and anti-correlated with relative humidity and CO2 and to alower extent with CO and NO2. As a consequence, it will be difficult to estimate O3 correctly using temperature, relative humidity and CO2 as estimators.

Note on **field deployment**

> Theses multi-sensors were either calibrated against standard gas mixtures or using artificial neural network under field conditions. The latter method resulted in mixed results **either satisfactory for short periods or generally weak for longer data series**.

Note on **drift over time**
>Finally the drift over time of each calibration methods was plot-ted in order to evidence general trends. To ease the detection ofpossible patterns by filtering noise, the daily residuals were plottedbetween reference measurements and sensor predictions ratherthan the hourly ones.
>
Note for **number of sensors**:

> One shall remember that implementing the ANN-MLR requires a set of 7 sensors, of which 2 NO2 MOx and 2 NO2 electrochemical sensors, 1 O3 electrochemical sensor, 1 CO electrochemical sensor and absolute humidity(therefore temperature and relative humidity sensor). Moreover,all gas sensors were previously calibrated using correction models (Table 2) including reference measurements for O3.

**1.2. Field calibration of a cluster of low-cost commercially availablesensors for air quality monitoring. Part B: NO, CO and CO2 - [Link](https://www.sciencedirect.com/science/article/pii/S092540051631070X)**

Note on **target diagram and stats**

Better explained below (06)

>Fig. 3 gives the target diagram for LR, MLR and ANNs calibration methods for NO (green), CO (red) and CO2(black). The target diagram is used for evaluating sensor data against reference measurements. This diagram is an evolution of the Taylor diagram, which was based on the geometrical relation between the Centred Root Mean Square Error (CRMSE) and the standard deviation of both reference (RM) and sensor data (S). The target diagram allows to extend the notion of the Taylor diagram by distinguishing the root Mean Square Error (RMSE) within the contributions from (a) the Mean Bias Error (MBE) and (b) the CRMSE (see Eqs. (1)–(3)).MBE and CRMSE values are gathered in Tables 4 and 5. This plot represents the normalised RMSE as the quadratic sum of the normalised MBE on the Y-axis versus the normalised CRMSE on the x-axis. The distance between each point and the origin represents the normalised RMSE for each platform sensor. Furthermore, target scores are plotted in the left quadrant of the diagram when the standard deviation of the sensor responses is lower than the one of the references measurements and conversely. In the original approach of the target diagram, RMSE, MBE and CRMSE can be normalised using the standard deviation of the reference measurements (RM). Sensors with random error equivalent to the variance of the observations stand in the circle area of radius 1. Target scores inside this circle indicate a variance of the residuals between sensor and reference measurement equal or lower than the variance of the reference measurements. In fact, sensors within the target circle are better predictors for the reference measurements than mean concentrations over the whole sampling period.
>
>![](https://i.imgur.com/NUXh8Fj.png)

Note on **measurement span**

>For the CO sensors, even though ANNs methods were found by far to be the most efficient methods, all calibration methods produced RMSEs falling outside the target circle. This evidenced a **lack of agreement between CO sensor values and reference measurements**. Our first guess is that this situation was primarily caused by the limited range of CO level at the test site (50% of data in a range of less than 0.2 umol/mol) which did not allow a correct fit of the calibration function.
>
**2. Sensors 2017, 17, 1653 - [Link](http://www.mdpi.com/1424-8220/17/7/1653)**

Notes on **baseline resistance spread**

> The consequence of this model is that the sensor’s response is only partially a function of the amount of gas to which the surface is exposed. Instead, **the sensor will have a baseline resistance that is related to the bulk and particle boundary resistance. Because of the random geometry of the granular sensor surface, the baseline resistance will vary between individual sensors**.

Notes on **cross-sensitivity**

> Although the deployment of multiple different sensors can compensate for the cross-sensitivity issues in calibration, it cannot eliminate it. **MOS sensors can thus be used only in situations where any interfering species can either be measured by other means, or they must be calibrated regularly and used in locations where the background varies in concentration slowly compared with the target gases**.

Notes on **target accuracy**

> The target accuracy at 95% confidence is 20μg/m3 for both $NO_2$ European directives define target and absolute maximum thresholds for the concentration of both these gases. For $NO_2$, the maximum average yearly concentration is 40 μg/m3 and hourly concentrations must not exceed 200 μg/m3 more than eighteen times a year. For $O_3$, the daily 8-h mean must not exceed 120 μg/m3 more than 25 times over three years. Urban environments frequently experience NO2 levels that exceed the yearly target. An accuracy of 20μg/m3 would provide enough resolution to make these sensors a useful supplement to modelling and satellite campaigns, in the context of these targets.

Notes on **mounting and flow** (we have reproduced this issue)

> An important practical consideration with any in situ air quality sensor design is ensuring adequate flow of sampling air through the device. **Stale air inside a casing will produce unrepresentative results**, and even sensors mounted outside a casing might not get a properly-mixed sample.
>
> ![](https://i.imgur.com/wKuthZo.png)


Note on **calibration time and fit selection**

>Even with the use of these techniques, the phenomenon of sensor drift was not corrected for here, and it truncated trustworthy results to data to within four months from calibration. This is a similar scale as has been reported by Spinelle et al. and Masson et al. and somewhat of an improvement over the results described in the former. An analytical approach to counteracting this drift might be "merging calibrations", where a sensor is calibrated at the start and end of a four-month campaign, and the coefficients gradually change from one end of the experiment run to the other.
>
>![](https://i.imgur.com/QL6RTmS.png)

Notes on **ageing**

> Further to this, it is clear that there are two major factors in the longevity of a sensor’s calibration. The first is the natural degradation of the heater element, which becomes hotter over prolonged use [15] and causes the sensor’s response profile to vary. The second is the effect of slowly-varying interfering gases, which over the course of months shift the sensor’s baseline. The first problem may have an engineering solution, but the second will involve taking the results of the tests in an artificial atmosphere, identifying the most critical species and either measuring or possibly modelling their likely concentrations during deployments.
>

Note on **packaging testing**

> The calibration setup for the sensors is not currently optimal, but the strong correlation of sensor voltages within the same housing suggests a solution in **ensuring that the same packet of air reaches the MOS sensors as the reference instrument, in as little time as possible**. The rapid rate at which NOx compounds evolve and the sensitivity of the Leighton system to sunlight means that the representativity of the calibration environment is even more critical than it would be for more specific sensors.

**3. Christian Kjær Jensen - Assessing the applicability of low-cost electrochemical gas sensors for urban air quality monitoring. Master’s thesis. January 2016**

**4. Practical field calibration of electrochemical NO2 sensors for urban
air quality applications**

Note on influence of **T-H O3 on AlphaSense**

> As all electrochemical NO2 sensors, the Alphasense NO2-B4 sensor is not very selective to the target gas. The sensor response can best be explained as a linear combination of NO2, O3, temperature and humidity signals ($R^2≈ 0.9$). As a consequence, a linear combination of the Working Electrode and the Auxiliary Electrode alone give poor indication of ambient NO2 concentrations. The accuracy varies greatly between different sensors ($R^2$ between 0.3 and 0.7). For the Urban AirQ campaign, temperature and relative humidity were included in a multilinear regression approach. The results improve significantly with $R^2$ values typically around 0.8. This corresponds well with the findings of Jiao et al. (2016), who find an adjusted $R^2=0.82$ for the best performing electrochemical NO2 sensor in their evaluation, when including T and RH.

> Best results are obtained by also including ozone measurements in the calibration model: R2 increases to 0.9. Spinelle et al. (2015b) used a similar regression and found $R^2$ ranging from 0.35 to 0.77 for 4 electrochemical NO2 sensors during a two week calibration period, but dropping to 0.03—0.08 when applied to a successive 5-month validation period. Low NO2 values at their semi-rural site partly explains this poor performance, but most likely also unaccounted effects such as changing sensor sensitivity and signal drift.
>
**5. Mobile sensor network noise reduction and recalibration using a Bayesian network**

The related work can be placed in three categories: colocated sensor calibration, sensor abnormality detection, and Bayesian network based approaches.

**Colocated**: Those techniques require that the co-located sensors are of the same type and thus should have the same response from the physical environment. In contrast to the previous work, our technique can work on mobile sensing devices containing various types of metal oxide sensors.

**Sensor Abnormality**: crap

**Bayesian Networks**: Mola


### Other readings

* Masson, N.; Piedrahita, R.; Hannigan, M. Approach for quantification of metal oxide type semiconductor gas sensors used for ambient air quality monitoring. Sens. Actuators B Chem. 2015, 208, 339–345.

* Piedrahita, R.; Xiang, Y.; Masson, N.; Ortega, J.; Collier, A.; Jiang, Y.; Li, K.; Dick, R.; Lv, Q.; Hannigan, M.; et al. The next generation of low-cost personal air quality sensors for quantitative exposure monitoring. Atmos. Meas. Tech. 2014, 7, 3325–3336.

* Assessment of air quality microsensors versus reference methods: The EuNetAir joint exercise - [Link](https://ac.els-cdn.com/S1352231016307610/1-s2.0-S1352231016307610-main.pdf?_tid=d8c22a86-0506-11e8-a86b-00000aacb35d&acdnat=1517238940_360f2c53828a1084c70bedb5d76219ae)

*  GUIDE TO THE DEMONSTRATION OF EQUIVALENCE  OF AMBIENT AIR MONITORING METHODS - [Link](http://ec.europa.eu/environment/air/quality/legislation/pdf/equivalence.pdf)

## Testing and calibration

We can split the sensor testing into this sequence (for both **mics** and **alphasense**):

**1. Characterisation**: Base testing for assessing general sensor response, stabilisation time or operational modes

**2. Calibration**: Assess actual concentration functions once we know how to operate the sensor itself. Include other factors such as environmental effects, cross-sensitivity, etc.

**Note**: sensor calibrations from alphasense is [all in here](https://drive.google.com/drive/folders/10ekx0_KFzeYvsL9WS5DWXQeoQy2rGcJW).

### Characterisation Testing

#### Mics
**Basic**
- Sensor response
- Sensor limits (baseline and max reading)
- Heating time and stabilisation time

**Advanced**
- Humidity and temperature (probably not to be donee on the chamber)
- Pulse Mode operation

<div style="text-align:center">
<img src="https://i.imgur.com/Na3ZCYp.png" width="500px">
</div>


#### Alphasense

Questions to answer:

- Is the Sensitivity varying with temperature (YES) - Ask alphasense for data.
- Is the reading varying with temperature (WDK) - Ask alphasense and calibrate on our own
- Do we want to input the zero currents measured as offset on our boards?
    - Furthermore - Do they change with time / temperature / humidity? (NO/NO/NO)
**Basic**
- Measure Zero currents and check if n is the same with what alphasense's giving us
- Measure convertion factor between nA/mV with Jano's tester board
- Ask alphasense for:
    - Sensitivity variation over time
    - Sensitvity variation with temperature/humidity
    - Zero currents / offset variation with temperature/humidity

**Advanced**
- Long term deployment with colocation in:
    - Barcelona?
    - Alphasense?
    - iScape?

### Calibration

We could divide it in two stages, depending on how the results turn out to be:
1. chamber testing* for determining *f* functions and
2. outdoor testing* for checking *g* and *h* functions:

$$
Concentration = f(SensorParams, T, H) + g(T,H) + h(Others)
$$

#### Chamber testing

**Mics**

We need to characterise several sensor parameters. The sensor response is apparently something like:

$$
log_{10}(Concentration) = f(Rs, Ro) = \beta_1+\beta_2 log_{10}(Rs/Ro)
$$

Where:
- Rs is the sensor response
- Ro is the baseline resistance, normally at Zero air
- $\beta$s are log linear correlation coefficients (from SGX AAN)

:::info
This is based on SGX datasheet:

![](https://i.imgur.com/Z8HOaKM.jpg)
:::

The _f_ function must be calibrated and the baseline resistance needs to be monitored through the sensor sensitivity. **SGX** defines the sensitivity as:

$$
Sensitivity_{CO}  = {Ro_{pure-air} \over Rs_{60ppm-CO}}
$$

$$
Sensitivity_{NO_2} = {Rs_{0.25ppm-NO_2} \over Ro_{pure-air}}
$$

With **CO** measured at 23ºC 50%RH and **NO2** at 23ºC and <5%RH.

However, due to hardware and testing limitations, we could monitor our own sensitivity defined as:

$$
Sensitivity_{CO}  = {Rs_{pure-air} \over Rs_{50ppm-CO}}
$$

$$
Sensitivity_{NO_2} = {Rs_{10ppm-NO_2} \over Rs_{pure-air}}
$$

_Both at 23ºC and 50%RH._

With this, we should be able to monitor the sensor sensitivity in controlled conditions so that we can assess the shape of the f(Rs,Ro) component of the calibration. Define pre and post exposure tests in order to find what the Sensitivity variation is and re-calculate gas concentrations based on Rs readings.

**Alphasense**

**NA**: If alphasense provides us with [all this data](https://drive.google.com/drive/folders/10ekx0_KFzeYvsL9WS5DWXQeoQy2rGcJW), we could skip this characterisation: although we should verify some of the data with random batches.

After having characterised PCB settings, we need to obtain the factor _n_ in this formula:

$$
Concentration = {I_{WE}-n(I_{AE}) \over Sensitivity(T,H)} + g(T,H) + h(Others)
$$

For this we need to test for the relationship between working and auxiliary electrodes currents relationship with **zero air testing**: 20min good flow of zero air for all three sensors. Also, ideally, the sensor current is directly proportional to:

$$
I_L = k C_T
$$

In controlled conditions. Therefore, we need to assess this value and with it the f function.

#### Combined testing

For both sensors, it would be desirable to **assess the models including sensor reading, T, H and other sensor data** for cross-sensitivity and their uncertainty. These are the *g* and *h* functions and they should be based on additional sensor data for reference.

Reference sensor possibilities:

- outdoor with other reference sensors
- iScape sensing campaigns
- or more indoor testing with more calibrated gas bottles (expensive, not a good approach)

We also need to check how the sensor behaves in a **temporal manner**:

* Repeteability
* Short term drift
* Long term drift

**Proposal: Inchamber - Outdoor testing sequences**

Using any of the above references, perform *in-chamber with bottles* + *outdoor exposure with reference*, *in-chamber with bottles* testing. Vary exposure time to uncontrolled pollutants and conditions and recenter data with calibration bottles to understand:
- How the sensor drifts in short and long term
- What's the longest time we can test in uncontrolled exposure
- Identify if we can extract data from calibration chamber and prioritise it in the modelling

Calibration and modelling is reviewed below.

## Calibration and model notes

For the outdoor exposure time, we need to understand how the sensor is exposed in an uncontrolled environment. We need to answer these questions:

- **Are the readings *multicollinear*?**: do several sensor readings could be correlated with others and therefore not prioritised in our model?
- **Are the readings *heteroscedastic***: does the sensor reading vary in the different measurement conditions? Is it likely that we will overfit data? Is it likely that sensor readings in different conditions would have different variabilities?
- Are we going to be calibrate with a **small amount of observations** vs **number of variables** (T, H, sensor readings mics (CO, NO2), aS (O3 + NO2, NO2, CO))?

If so, we should then use reference sensors:

- Check regularisation techniques: Lasso / Ridge to reduce model complexity
- Check PCR or PLS for feature extraction: create different principal components that are not *multicollinear* (but depend on other variables)
- If dependent variable is continuous and model is suffering from collinearity or there are a lot of independent variables: PCR, PLS, ridge, lasso and elastic net regressions. Then select the final model based on Adjusted R-Square, RMSE, AIC and BIC.