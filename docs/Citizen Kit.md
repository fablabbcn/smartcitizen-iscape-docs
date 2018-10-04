Citizen Kit
===========

![](https://i.imgur.com/zv4cwc3.jpg)

The Citizen Kit, formerly known as the Low-Cost Sensor, is aimed at providing a low-cost environmental sensor solution non-technical users can easily deploy. The design developed for the project is a complete reiteration of the  Smart Citizen Kit, a piece of hardware for citizen sensing already tested in other projects for more than five years. On this iteration, new sensors had been added, and all the electronic design has been redone from the ground up to improve the data accuracy and reduce the manufacturing costs.

![](https://i.imgur.com/KH6Kny0.jpg)

The design is built around two boards the Smart Citizen Data Board and the Smart Citizen Urban Sensor Board. The first board contains the data acquisition, the power management, and the communication unit. The second contains a set of sensors aimed at the outdoor urban environment including: Air Temperature, Relative Humidity, Noise Level, Ambient Light and Barometric Pressure. The board also features a section especially focused on Air Quality including a Air Particles, a Carbon Monoxide, and a Dioxide Nitrogen detectors. This sensor while not capable of offering precise measurements can be used to understand the behavior of different urban locations especially when they are calibrated on the field using certified equipment. Both boards are later described in detail on the Sensor Components section.

From the non-technical user side, the sensor includes an easy to follow online setup process that guides the users on the whole install procedure: The Smart Citizen Onboarding.

![](https://i.imgur.com/NfWr2Rg.jpg)

The sensor does not require to stay always powered but requires charging at least every two days. The charging is done using a standard USB adapter like on any Smartphone; a process already by many users familiar.

!!! warning "Citizen Kit Enclosure"
	Please, notice the final enclosure for the Citizen Kit its is under development as the one shopwcased on the documentation does not support the PM sensor yet. The documentation will be updated once the new enclosure is ready.


## Sensors

| Measurement                                  | Units                                        | Sensor                | Component              |
|----------------------------------------------|----------------------------------------------|-----------------------|--------------------|
| Air Temperature                              | ºC                                           | Sensirion SHT-31      | Urban Sensor Board |
| Relative Humidity                            | % REL                                        | Sensirion SHT-31      | Urban Sensor Board |
| Noise Level                                  | dBA                                | Invensense ICS-434342 | Urban Sensor Board |
| Ambient Light                                | Lux                                          | Rohm BH1721FVC        | Urban Sensor Board |
| Barometric pressure and AMSL                 | Pa and Meters                                | NXP MPL3115A26        | Urban Sensor Board |
| Carbon Monoxide                              | ppm (Periodic Baseline Calibration Required) | SGX MICS-4514         | Urban Sensor Board |
| Dioxide Nitrogen                             | ppb (Periodic Baseline Calibration Required) | SGX MICS-4514         | Urban Sensor Board |
| Particle Matter PM2.5 (external - power req) | µg/m3                                        | PMS 7003              | Urban Sensor Board |

## How to install?

!!! info "Onboarding app"
	Visit the onboarding app at [onboarding.iscape.smartcitizen.me](https://onboarding.iscape.smartcitizen.me)

!!! example "Step by step"

	1. Welcome page
	![](https://i.imgur.com/ZuziVwg.png)

	2. Select all the parts you received to ensure you are not missing any part
	![](https://i.imgur.com/dw5hMOh.png)
	![](https://i.imgur.com/uuzBG3J.png)

	3. Turn on your Kit
	![](https://i.imgur.com/EwRK7NY.png)

	4. Close the cover of your device
	![](https://i.imgur.com/KReeIh8.png)

	5. Choose the Wi-Fi network you want to connect to
	![](https://i.imgur.com/9Xr6Vur.png)

	6. You will reiceive a message when the Kit it is connected
	![](https://i.imgur.com/Zl6ajaM.png)

	7. Add a name to your sensor
	![](https://i.imgur.com/xEdLjYF.png)

	8. Select the location for your sensor
	![](https://i.imgur.com/dkG5gyI.png)

	9. Add your email to register the Kit under your name
	![](https://i.imgur.com/GAlSNeS.png)

	10. Add a user name for people to see you on the platform
	![](https://i.imgur.com/sQ1Ze1w.png)

	11. Add a password to protect your account
	![](https://i.imgur.com/6jF08gy.png)

	12. You are done!
	![](https://i.imgur.com/UDFD55K.png)

	13. Visit the Kit on the platform. Wait one minute till it publishes data
	![](https://i.imgur.com/xwPTZ06.png)

	14. Look at the data!
	![](https://i.imgur.com/mmrDVFC.png)

## Troubleshooting

!!! info "Reboot your Kit"
	You can fully reboot your Kit by pressing the reset button located under the sensors board as seen on the picture.

	![](https://i.imgur.com/tAofJ0g.png)

	That will not delete any configuration, it will simply restart your device.

	Press the `RESET` button for a second. The light will go off and on and the device will start again.



<!-- !!! info "Factory reset your Kit"
	You can fully reset the Kit to the default settings so you can register again your device.

	Press the main button for 15 seconds. After 5 seconds the light will go off and will go on again after 15 seconds. Then you can release the button and your device will be fully resetted as a brand new Kit.

	![](https://i.imgur.com/tAofJ0g.png) -->

## Technical specs

### Components

The Citizen Kit is a modular system based on different sensor board that connected to a central datalogger.

!!! info "Citizen Kits Components Setup"
    ![](https://i.imgur.com/il20Xqa.png)

!!! tip "Learn more"
    Learn more about all the components and the software inside the kit in the [**Components**](/Components) documentation section.

### Connectivity

###### WI-FI
The SCK 2.0 is designed to publish data using your home or office Wi-Fi. It currently supports most standard networks (b/g/n) with open, WEP or WPA/WPA2 authentication.

WPA2 Enterprise networks are not currently supported.

###### Internal memory
The SCK 2.0 includes an internal memory to store more than one week’s worth of data incase the device loses its Wi-Fi connection. Data is published automatically when the connection recovers.

###### SD Card
For operation in remote areas, the kit can store data in CSV format on an SD/SDHC MicroSD card with a standard FAT file system. Alternately, while in Wi-Fi mode when an SD card is in place, the kit also stores the published data on the SD card as a backup. In both cases, data can later  be uploaded manually to the platform using the “Manual Data Upload” option.

### Power Management

###### Battery lifetime
The SCK 2.0 comes with a 2000mAh LiPo battery. The battery is meant to be a complete power option for short-term measurements and a backup solution when the kit it is used for long periods. The battery lifetime lifetime is dependent on which sensors are enabled or disabled:

* All sensors publishing over Wi-Fi: 12 hrs.
* All sensors publishing on SD card: 13 hrs.
* Without air quality sensors over Wi-Fi: 10 days
* Without air quality sensors on SD card: 25 days

###### Battery charging
The SCK 2.0 has a micro USB port and can be charged like any Smartphone or Tablet using a dedicated adapter or a computer USB port.
We recommend using a tablet power adaptor, instead of a computer USB port, for quicker charging. Autonomy can be extended by using a Power Bank, a 5V PV Panel, or with a through-glass induction charger (currently under development).

### Configuration And Updates

###### Configuration
Our online onboarding website guides you through the assembly and configuration process. You’ll need a computer with an internet connection to start using the SCK 2.0.

###### Software Updates
The SCK 2.0 has two components that need periodic updates. The SCK 2.0 appears as a USB Storage device and the new firmware can be installed on your kit by simply downloading the new firmware release and then dragging and dropping into the SCK 2.0 device root folder. The Wi-Fi module firmware is updated automatically over-the-air every time the main processor firmware is updated.

### Physical

* Dimensions: 60 x 60 x 20 mm (approx.)
* Dimensions w/ enclosure: 110 x 110 x 50mm (approx.)
* Weight: 65 gr.
* Weight w/ enclosure: 160 gr.



