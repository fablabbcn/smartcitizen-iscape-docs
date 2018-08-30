iSCAPE Sensors Documentation
============================

![](https://i.imgur.com/6mgROjt.jpg)

## Introduction

The [iSCAPE](https://www.iscapeproject.eu/) sensor platform builds on the legacy of previous [Smart Citizen](https://smartcitizen.me/) generations to develop a new set of tools especially aimed at providing meaningful environmental data insights on a low budget. That means this report documents new components, developed specifically for the project, but frames them inside the Smart Citizen ecosystem.

We believe building modular and reusable hardware is critical towards optimizing the research and development effort. By increasing the technology readiness levels of existing technologies, we can drastically improve the project exploitation strategy.

Environmental sensors play a critical role in the ISCAPE project the
primary goals being:

* Engage local communities at the Living Labs to deploy and learn about sensors as a novel way to learn about their environment, in particular cities air pollution issues.

* Provide a sensor infrastructure to enable the different sites to monitor the performance of their interventions.

To support this approach, we needed to accomplish three key
requirements:

* **Modularity:** The sensor hardware operates as a platform where new sensor modules can be shipped and deployed by the Living Labs themselves when they are finished enabling faster iterations and upgrades even after the project finishes.

* **Open design and documentation:** All the components developed are released on open source license to foster the collaboration between different the stakeholders. That especially aims at involving the Living Labs on the design of new sensing strategies and technologies.

* **Easy to use:** The technology needs to be accessible to ensure users engagement, especially for those sensors targeting at citizens, but also to ensure the technology development is ready to be exploded commercially after the project.

The following approach led the project to development of two sensor solutions: The [**Citizen Kit**](Citizen Kit) and the [**Living Lab Stations**](Living Lab Station).

![](https://i.imgur.com/2Amt2SV.jpg)

The following website contains the full documentation of the software and hardware sensor platform developed for the project. It is aimed at any project stakeholder to learn how to use the different components and also to contribute on its future development. 

## Sections

* **Main:** Contains the [**Citizen Kit**](Citizen Kit) and [**Living Lab Stations**](Living Lab Station) documentation to help participants to use them.

* **Components:** Contains all the documentation on the different [**hardware sensor modules**](Components) with detailed insights on the sensors behaviour and calibration.

* **Sensor Analysis Framework:** Contains all the documentation on the [**data post processing framework**](Sensor Analysis Framework) to obtain insights from the data calibrated by the sensors.

* **Sensor Platform:** Contains all the documentation on the [**sensors web platform**](Sensor Platform) were data is collected, stored and vizualized.

## Guides

The documentation contains multiple guides as step-by-step tutorials to perform important tasks as installing a sensor type or uploadig the software on the sensors.

!!! info "Example guides"

	* [Installing the Living Labs Station](Living Lab Station/#how-to-install)
	* [Installing the Citizen Kit](Citizen Kit/#how-to-install)
	* [Onboarding Sensors](Sensor Platform/Guides/Onboarding Sensors)
	* [Uploading SD Card Data](Sensor Platform/Guides/Uploading SD Card Data)
	* [Update the Firmware](Components/Firmware/Guides/Update the firmware)
	* [Edit the Firmware](Components/Firmware/Guides/Edit the Firmware)


## Open Source

**We're against black boxes!**

The entire project it is released under open source licenses: 

* Hardware components: [CERN Open Hardware License v1.2](https://www.ohwr.org/licenses/cern-ohl/license_versions/v1.2)
* Core firmware: [GNU GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html)
* Software platform: [GNU AGLP v3.0](https://www.gnu.org/licenses/agpl-3.0.en.html)

!!! info
	Check the **Source files** section for each component and explore the software source code and the hardware blueprints.

	![](https://i.imgur.com/X1fUET3.png)