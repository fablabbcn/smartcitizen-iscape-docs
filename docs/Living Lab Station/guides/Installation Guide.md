## How to install?

Living Lab Station Installation Guide
=====================================


**What's on the Kit?**

![](https://i.imgur.com/zVPlOcz.jpg)


## Sensors

**2x iSCAPE Living Lab Stations v2.0**


* iSCAPE Living Lab Station
    * Urban Board 2.0
    * Data Board 2.0
    * PM Board 2.0 + 2 PM sensors
    * Gas Pro Board 2.0 with 3 EC sensors
    * 6Ah Battery

* Accessories
    * MicroSD card 512MB
    * USB Charger
    * MicroSD to SD card adapter
    * USB Power Supply
    * 2m 3 Wire 220V cable
    * Mounting brackets and screws
    * Mounting tools (1x Wrench + 2 Allen Keys)


_Please read the documentation carefully if you have any question contact us at support@smartcitizen.me_

## Sensor naming and reference

Both Kits are setup to log data every 60 seconds on the sdcard. The target pollutants measured will be, **per station** are:

- **Electrochemical Sensor**:
    - CO: AlphaSense CO-B4
    - NO2: AlphaSense NO2-B43F
    - O3: AlphaSense OX-B431
- **Particle Sensors**:
    - **PM1**, **PM2.5**, **PM10**: 2 x PlanTowerPMS5003

For tracking purposes these will be the sensor references:

**Electrochemical Sensors**
| | CO-B4 (slot 1) | NO2-B43F (slot 2) | OX-B431 (slot 3)   |
| :--------: | :--------: | :--------: | :--------: |
| **Citizen 2**   | 162581717     | 202160410     | 204160162     |
| **Citizen 3**   | 162581725     | 202160407     | 204160154     |

 **PM Sensors**
| | PMS5003#1 | PMS5003#2 |
| :--------: | :--------: | :--------: |
| **Citizen 2**   | 2017122902980     | 2017122902941     |
| **Citizen 2**   | 2017122902976     | 2017122902977     |

### Sensor assembly

The sensors are already assembled and **we strongly require to not swap** any of the sensors among them. We keep track internally of all sensor deployments and it is very important to keep the KITS as they are in order to avoid calibration data mismatch.

# Station Setup

You have to follow some simple **steps** to setup your SCK to capture data and store it on an SD card:


* Remove the 3 protective stickers covering the Gas Sensors.

	![](https://i.imgur.com/ABkoqXW.jpg)

* Use the small allen key to unscrew the 3 screw on top.

	![](https://i.imgur.com/lqXwztR.jpg)

* Remove the top cover

	![](https://i.imgur.com/7zl4k7r.jpg)

* Use the big allen to remove the 3 screw and pull the cover up.

	![](https://i.imgur.com/mE9B2D8.jpg)

* Make sure the **SD card** is inserted in the kit.

    ![](https://i.imgur.com/UUjeVAF.jpg)


    :::danger
    :warning: The configuration of enabled/disabled sensors is stored on the SDcard so **the cards shouldn't be swaped between kits.**
    :::

    :::warning
    :computer:  If you have problems with a SD Card be sure to format it with _FAT32_ filesystem and don't copy any configuration file before inserting it on the kit, the kit will re-save the last valid configuration on the new sdcard.
    :::


* Connect the **battery** to your SCK. The led should turn **pink** indicating SD card logging. The SCK will try to start immediately, but since the clock is not yet configured it will blink for 5 seconds and the led will turn **red** (setup mode).

![](https://i.imgur.com/OjH85pZ.jpg)


* Syncronize the **RTC** (Real Time Clock) of the SCK with [UTC time](https://en.wikipedia.org/wiki/Coordinated_Universal_Time). The simplest way of doing this is to join to your SCK WiFi network:

    * With your computer or smartphone search for a wifi network named **_SmartCitizenXXXX_** (The exact name should come in a sticker in the back of your kit).

        ![](https://i.imgur.com/lTYtmCZ.png)

    * Once you join the network a **_Network Login_** screen should appear, if this doesn't happen open your browser and type **192.168.1.1** as the URL.


    * Go to **_SD Card Mode_**

        ![](https://i.imgur.com/MqN8t0m.png)


     * Once the time it's sync the led should turn **pink** again and your sensor will start logging data to the SD card.

        ![](https://i.imgur.com/dwXZGMz.png)



* :clap: Congratulations! You are ready close the enclosure and start capturing data.

 :::success

**TURN OFF**

_Done for today?_

Every time you want to stop the Kit from logging simply press the button for 5 seconds. The led should stop bliking and your Kit will be _OFF_. To turn it _ON_ simply press the button again.

:::

:::info
**GET THE DATA**

_Download the data from the SD card_

First turn off your Kit by pressing the button for 5 seconds. Then remove the micro SD card and plug the card on your computer using a Micro SD card reader.

You will find inside a `YYYY-MM-DD.CSV`  with all the data. Check the **[SD card file description](https://hackmd.io/jlHlJXV6SziaCx2Mak3T1Q?both#Sensor-data-collection)** section for more info.

_:warning: **Data processing** The collected data requires a custom and complex data processing using the **[iScape Sensor Analysis Framework](https://github.com/fablabbcn/smartcitizen-iscape-data)** The process will be fully documented here on the next few weeks._

:::

:::warning

**FACTORY RESET**

_Is your Kit not working properly?_

This will fully reset the Kit and should help you fix any issues you might have.

Disconnect and connect the battery without any USB cable being connected. Then press the button until the light goes off and on again (around 15 sec).
:::


### Sensor data collection

The data will be collected in **SD card mode** during this deployment.

**NB:** we are currently developing a direct CSV upload to the Smart Citizen platform that will be available in the following weeks.

#### SD card file description

The data logged to sdcard will be saved in a CSV [_comma separated value_](https://en.wikipedia.org/wiki/Comma-separated_values) file.

The header of the data will be written at the top of the file and every time a sensor is _enabled_ or _disabled_. The posible values are:

* **Time** The time at wich the readings were taken in [ISO UTC Combined date and time](https://en.wikipedia.org/wiki/ISO_8601#UTC) format. Each sensor could have its own reading interval and they are grouped in 15 seconds intervals, so it is posible (if a sensor has longer reading interval) that there are some columns without a reading for each line.
* **Battery-%**
* **Noise-dBc**
* **Humidity-%**
* **Temperature-C**
* **Light-Lux**
* **Gases Board 1A-mV**	Gas Pro Board **Carbon Monoxide** auxilliary electrode.
* **Gases Board 1W-mV**	Gas Pro Board **Carbon Monoxide** working electrode.
* **Gases Board 2A-mV**	Gas Pro Board **Nitrogen Dioxide** auxilliary electrode.
* **Gases Board 2W-mV**	Gas Pro Board **Nitrogen Dioxide** working electrode.
* **Gases Board 3A-mV**	Gas Pro Board **Ozone + Nitrogen Dioxide** auxilliary electrode.
* **Gases Board 3W-mV**	Gas Pro Board **Ozone + Nitrogen Dioxide** working electrode.
* **PM1.0** PM1.0 in ug/m3
* **PM2.5** PM2.5 in ug/m3
* **PM10.0** PM10.0 in ug/m3

### Sensor considerations

**Electrochemical sensor**

The electrochemical sensors **need stabilisation time under the testing conditions** they will be at. It is important to set and power the sensors with sufficient time (1-2 days) on the test environment for them to adapt. The newer the sensor, the more stabilisation time it requires. For this deployment, you will be receiving brand new sensors.

Humidity and temperature extremes will require of further sensor adaptation, in order to dry out or absorb the necessary humidity for their proper functioning.

:::danger
Do not extract/attach the sensor capsule from the base board while powered, this could irreversibly damage the sensor.
:::

**Particle Sensor**

The particle sensors measurements are delivered as averages of the two sensors with periodic validity checks. We are currently developing one-shot strategies for battery life improvement, but in the meantime, please make sure the sensor has reliable energy supply if you will use these sensors permanently.

:email: For more information about the working principle of the alphasense electrochemical sensors, please email [oscar@smartcitizen.me](mailto:oscar@smartcitizen.me).

### Sensor data processing

We have developed an algorithm that ingests the data from either the platform or the local csv and processes electrochemical sensor sensor data. This algorithm is **in validation stage** and will be included in the online platform flow from Smart Citizen once validated.

**For this deployment**, we would require you to send the data from reference sensor and the SmartCitizen sensors for us to process them and validate the workflow. If the above mentioned algorithm is sucessful, it will be included in the online data processing flow and, obviously, shared with the processed data.

:email: _Please, send the data back to [oscar@smartcitizen.me](mailto:oscar@smartcitizen.me) and we will postprocess the readings for you._

## Outdoor installation

Use the perforated steel tape and the M6 provided to mount the Station on any street light or pole. The Pack also includes the required wrench.

![](https://i.imgur.com/lrUYl3Y.jpg)


## Setup the internal power supply

The Station can be directly powered at 220V AC (Consumption MAX 33W).

:::warning
:battery: **BATTERIES**

The Living Lab Station has a higher consumption, mostly due to the fans on the two PM sensors.

That means the internal battery last just for 20h, and it is only aimed at providing backup power.

_For example, we can connect the station on the street light electric line, so the Station gets charged during the night when the lights are on._
:::

:::info
:sunny: **SOLAR PANEL**

Unfortunately, we are having some problems with the PV Solar Panel system to power the Station independently. The system is currently under tests, and it will be available in the next few months.
:::

* Remove the two covers using the allen keys as explained on the setup instructions.
    ![](https://i.imgur.com/WPb3tnr.jpg)

* Remove the USB cable and bring inside the 220V power cable.

    ![](https://i.imgur.com/y54xC4p.jpg)

* Connect the cable wires with the power supply.

    ![](https://i.imgur.com/U49BppQ.jpg)

* Remove the third cover and place the power adapter as seen on the picture.

    ![](https://i.imgur.com/WYvxUyy.jpg)

* Close the cover and run the Setup process again

    ![](https://i.imgur.com/JAK6NMd.jpg)


# Understanding LED colors

![](https://i.imgur.com/nIUBtbj.png)


* **Red:** The Station is in Setup Mode, this means that it is waiting to be configured.

    _The Station will enter this mode (after blinking) when there is an error and some user action is required (ej. no SD card) once the problem is solved it will return to the original mode._

    _You can enter this mode manually by clicking the button if you want to change configuration parameters._

* **Pink**
    * **Breathing:** The Station is logging data to SD card. _Everything it's all right!_

    * **Blinking:** The Station is trying to log data to SD card but there is a problem. _You should try the setup process again._


* **Battery feedback:**

    * When the Station is working on batteries the led will be **on** only when reading sensors or saving data. The rest of the time it will show a **little blink** every 2 seconds as a heartbeat.

    * On low battery (less than 10%) the led will do a **triple orange blink**.

    * If the Station is connected and charging the battery it will do a little **orange** blink every two seconds. When the battery is fully charged (or no battery is connected) this blink will turn **green.**
