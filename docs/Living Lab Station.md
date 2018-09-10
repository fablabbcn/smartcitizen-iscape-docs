Living Lab Station
==================

![](https://i.imgur.com/p9lDxiv.jpg)

The Living Lab Station, formerly known as the High-End Sensors,  is aimed at providing the Living Labs with a system for monitoring the performance of their interventions. The Station aims at providing a solution that can be used by the Living Labs not just from a scientific point of view but also as a tool to engage local communities on air pollution related issues.

![](https://i.imgur.com/QB5P4r9.jpg)

The station is designed with a modular principle where sensors can be added easily added expanding the capabilities of the installation or replaced when they are damaged or the sensors lifetime is over. From a costs perspective while being more expensive than the Citizen Kit it is also conceived as a low-cost solution. That allows to guarantee at least four stations will be available for each Living Lab to increase the spatial resolution and reliability of the measurements.

![](https://i.imgur.com/HUq7Anz.jpg)

The design builds on top of the Citizen Kit adding an extra set of more accurate sensors especially aimed at measuring air pollutants. The sensors include the Gas Sensor Board, featuring EC Carbon Monoxide, Dioxide Nitrogen and Ozone sensors and the PM Sensor Board, featuring a PM 2.5 / PM 10 sensor.

With all the sensor together this Kit provides information on Air Temperature, Relative Humidity, Noise Level, Ambient Light, Barometric Pressure, Particles Matter (PM 2.5 / 10),  Carbon Monoxide, Dioxide Nitrogen and Ozone. The sensors are later described in detail in the document at the Sensor Components section.


## Sensors

| Measurement                                  | Units                                          | Sensor                        | Component              |
|----------------------------------------------|------------------------------------------------|-------------------------------|------------------------|
| Air Temperature                              | ºC                                             | Sensirion SHT-21              | Urban Sensor Board     |
| Relative Humidity                            | % REL                                          | Sensirion SHT-21              | Urban Sensor Board     |
| Noise Level                                  | dBA                                  | Invensense ICS-434342         | Urban Sensor Board     |
| Ambient Light                                | Lux                                            | Rohm BH1721FVC                | Urban Sensor Board     |
| Barometric pressure and AMSL                 | Pa and Meters                                  | NXP MPL3115A26                | Urban Sensor Board     |
| Carbon Monoxide                              | µg/m3 (Periodic Baseline Calibration Required) | SGX MICS-4514                 | Urban Sensor Board     |
| Dioxide Nitrogen                             | µg/m3 (Periodic Baseline Calibration Required) | SGX MICS-4514                 | Urban Sensor Board     |
| Particle Matter PM2.5 (external - power req) | µg/m3                                          | PMS 7003                      | Urban Sensor Board     |
| Carbon Monoxide                              | ppm                                            | Alphasense CO-B4              | Gas Sensor Pro Board  |
| Dioxide Nitrogen                             | ppb                                            | Alphasense NO2-B43F           | Gas Sensor Pro Board  |
| Ozone                                        | ppb                                            | Alphasense OX-B431            | Gas Sensor Pro Board  |
| PM 1                                         | µg/m3                                          | Plantower PMS5003 Dual System | PM Sensors Board       |
| PM 2.5                                       | µg/m3                                          | Plantower PMS5003 Dual System | PM Sensors Board       |
| PM 10                                        | µg/m3                                          | Plantower PMS5003 Dual System | PM Sensors Board       |


## Components

The Living Labs Station is a modular system based on different sensor board that connected to a central datalogger. 

![](https://i.imgur.com/n5oiMwY.png)

!!! info "Living Lab Stations Components Setup"
    ![](https://i.imgur.com/vh4OLFX.png)

The station operates as a platform where new sensor modules can be shipped and deployed by the Living Labs themselves when they are finished enabling faster iterations and upgrades even after the project finishes.

![](https://i.imgur.com/FFUvfR6.jpg)

![](https://i.imgur.com/RRu8MiV.jpg)

!!! tip "Learn more"
    Learn more about all the components and the software inside the station in the [**Components**](/Components) documentation section.

## How to install?

![](https://i.imgur.com/zVPlOcz.jpg)

### Parts

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


### Assembly and configuration

The sensors are already assembled and **we strongly require to not swap** any of the sensors among them. 

!!! warning
    We keep track internally of all sensor deployments and it is very important not to swap the internal components between Station to avoid mismatchs on the calibration data.

!!! example "Step by step"
    You have to follow some simple **steps** to setup your SCK to capture data and store it on an SD card:

    * Remove the 3 protective stickers covering the Gas Sensors.


    ![](https://i.imgur.com/rIJvRva.jpg)


    * Use the small allen key to unscrew the 3 screw on top.

    ![](https://i.imgur.com/v86gjW6.jpg)

    * Remove the top cover


    ![](https://i.imgur.com/WesxBTl.jpg)


    * Use the big allen to remove the 3 screw.

    ![](https://i.imgur.com/pNRaoVQ.jpg)


    * Pull the cover out.

    ![](https://i.imgur.com/7wxWP68.jpg)


    * Make sure the **SD card** is inserted in the kit.

    ![](https://i.imgur.com/EqCErGS.jpg)

    * Connect the **battery** to your SCK. The led should turn **pink** indicating SD card logging. The SCK will try to start immediately, but since the clock is not yet configured it will blink for 5 seconds and the led will turn **red** (setup mode).

    ![](https://i.imgur.com/z4HcfuF.jpg)

    ![](https://i.imgur.com/o8V3bb4.jpg)

    * Syncronize the **RTC** (Real Time Clock) of the SCK with [UTC time](https://en.wikipedia.org/wiki/Coordinated_Universal_Time). The simplest way of doing this is to join to your SCK WiFi network:

    * With your computer or smartphone search for a wifi network named **_SmartCitizenXXXX_** (The exact name should come in a sticker in the back of your kit).

        ![](https://i.imgur.com/lTYtmCZ.png)

    * Once you join the network a **_Network Login_** screen should appear, if this doesn't happen open your browser and type **192.168.1.1** as the URL.


    * Go to **_SD Card Mode_**

        ![](https://i.imgur.com/MqN8t0m.png)


     * Once the time it's sync the led should turn **pink** again and your sensor will start logging data to the SD card.

        ![](https://i.imgur.com/dwXZGMz.png)



    * :clap: Congratulations! You are ready close the enclosure and start capturing data.

!!! warning
    The configuration of enabled/disabled sensors is stored on the SDcard so **the cards shouldn't be swaped between kits.**

!!! warning
    :computer:  If you have problems with a SD Card be sure to format it with _FAT32_ filesystem and don't copy any configuration file before inserting it on the kit, the kit will re-save the last valid configuration on the new sdcard.

!!! info "Done for today? Turn off"
    Every time you want to stop the Kit from logging simply press the button for 5 seconds. The led should stop bliking and your Kit will be _OFF_. To turn it _ON_ simply press the button again.

!!! info "Get your data"

    _Download the data from the SD card_

    First turn off your Kit by pressing the button for 5 seconds. Then remove the micro SD card and plug the card on your computer using a Micro SD card reader.

    You will find inside a `YYYY-MM-DD.CSV`  with all the data. Check the **[SD card file description](https://hackmd.io/jlHlJXV6SziaCx2Mak3T1Q?both#Sensor-data-collection)** section for more info.

    _:warning: **Data processing** The collected data requires a custom and complex data processing using the **[iScape Sensor Analysis Framework](https://github.com/fablabbcn/smartcitizen-iscape-data)** The process will be fully documented here on the next few weeks._


!!! tip "Is your Kit not working properly? Factory reset"

    This will fully reset the Kit and should help you fix any issues you might have.

    Disconnect and connect the battery without any USB cable being connected. Then press the button until the light goes off and on again (around 15 sec).


### Sensor data collection

The data will be collected in **SD card mode** during this deployment.

!!! tips "Upload data from the SD card manually"
    Read the documentation on [**Manual CSV data upload**]()

### Sensor considerations

**Electrochemical sensor**

The electrochemical sensors **need stabilisation time under the testing conditions** they will be at. It is important to set and power the sensors with sufficient time (1-2 days) on the test environment for them to adapt. The newer the sensor, the more stabilisation time it requires. For this deployment, you will be receiving brand new sensors.

Humidity and temperature extremes will require of further sensor adaptation, in order to dry out or absorb the necessary humidity for their proper functioning.

!!! danger
    Do not extract/attach the sensor capsule from the base board while powered, this could irreversibly damage the sensor.

**Particle Sensor**

The particle sensors measurements are delivered as averages of the two sensors with periodic validity checks. We are currently developing one-shot strategies for battery life improvement, but in the meantime, please make sure the sensor has reliable energy supply if you will use these sensors permanently.

### Sensor data processing

We have developed an algorithm that ingests the data from either the platform or the local csv and processes electrochemical sensor sensor data. This algorithm is **in validation stage** and will be included in the online platform flow from Smart Citizen once validated.

!!! info "Sensor Analysis Framework"
    Learn more about the sensors calibration on the [Sensor Analysis Framework](/Sensor Analysis Framework) section.

## Outdoor installation

Use the perforated steel tape and the M6 provided to mount the Station on any street light or pole. The Pack also includes the required wrench.

![](https://i.imgur.com/36El7ds.jpg)

## Setup the internal power supply

The Station can be directly powered at 220V AC (Consumption MAX 33W).

!!! warning "Batteries"
    The Living Lab Station has a higher consumption, mostly due to the fans on the two PM sensors.

    That means the internal battery last just for 20h, and it is only aimed at providing backup power.

    _For example, we can connect the station on the street light electric line, so the Station gets charged during the night when the lights are on._

!!! info "Solar Panel"
    Unfortunately, we are having some problems with the PV Solar Panel system to power the Station independently. The system is currently under tests, and it will be available in the next few months.

    ![](https://i.imgur.com/vfp6nB5.jpg)

!!! example "Step by step"

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


## LED colors

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