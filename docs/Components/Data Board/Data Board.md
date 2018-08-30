Data Board
==========

The data board is powered by an ARM M0+ 32-bits at 48Mhz running the Smart Citizen 2.0 software, combining the low power consumption of the ARM M0 family with the power of a 32-bits processor with 32KB of RAM and 256KB FLASH memory. That offers enough program storage and memory space to support multiple auxiliary sensors and no expense. 

The Data Board connects to the sensor board providing power, analog and digital communications (12 bits ADC, GPIO, I2C, I2S, VCC). Moreover, it includes a Seeed Studio standard Grove connector where off the shelf modules from the same manufacturer can be connected. The external add-ons can be enabled or disabled from the board to save power. The connector supports an independent I2C bus by default, but it can be configured in software to support other uses (GPIO, I2C and UART). The Smart Citizen Gas and Smart Citizen PM sensor boards described above use this bus receive power and communications from the board. 

The board includes a battery management controller with a 2000mAh Lithium polymer cell capable of powering the device in standby for more than two weeks. On a normal operation, the battery will last for more than a week to one day, when all the sensors are enabled and recording every minute. The controller allows the batteries to be easily charged using the boards micro USB connector using any standard USB power adapter like the ones used on Smartphones. On remote areas, it can also be powered using a selection of PV Panels like Voltaics Systems 6W panel.  


### LED Color codes

#### Normal operation
* **<font color="#FFF" style="BACKGROUND-COLOR: #FF0015; padding: 4px;">Red soft pulsing</font>** >> Apmode
* **<font color="#FFF" style="BACKGROUND-COLOR: #0099FF; padding: 4px;">Blue soft pulsing</font>** >> wifi.
* **<font color="#FFF" style="BACKGROUND-COLOR: #FF77EF; padding: 4px;">Pink soft pulsing</font>** >> sdcard.
* **Other color + <font color="#FFF" style="BACKGROUND-COLOR: #FF9100; padding: 4px;">Orange soft pulsing</font>** >> on battery.
* **Other color + <font color="#FFF" style="BACKGROUND-COLOR: #47D847; padding: 4px;">Green soft pulsing</font>** >> battery charging.

### SD Card

https://hackmd.io/V41GoPhARay1XBMm7N6XIw#


## Guides

[Debugging the SCK](https://hackmd.io/_zWIF3lpT9u82JZmDTz0qA#)
[Updating the Smartcitizen Kit 2.0](https://hackmd.io/jZWs9IgVSPu118EmSEOApg?both)
[Developer guide: Building and flashing the Smartcitizen Kit firmware.](https://hackmd.io/YHHq9GylRq-mTKk8z_XWEQ#ESP8266-filesystem)

:::info
Dev notes 2.0 https://hackmd.io/0dPsKRCWQOyYB4au6itS5g#CO-and-NO2-Sensor-MICS-4514


ESP Notes
https://hackmd.io/Gc8GT0I1QkaY487bIkfKMg

:::