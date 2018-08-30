Inside the MICS Metal Oxide sensors
===================================

The SGX Mics is comprised of two main elements:

* A SNO2 substrate as a sensor element
* A heater element

The SnO2 is a chemically sensitive **metal oxide** which can have interactions with molecules to be detected in the target gas. The reactions that can occur on SnO2 surface are **adsorption and catalytic reactions**. They take place at the so called **active sites** and at grain boundaries or at three phase boundaries (e.g. with metallic contacts or at metallic surface clusters). The metal oxide substrate is basically a collection of sites at which different molecules can be absorbed and therefore interact in various manners with the species present in the atmosphere: either through catalytic reaction, surface reaction, grain boundary reaction _among others_.
_[Source: Modelling of water adsorption on SnO2 Surface]._

The sensor element is typically heated to a few hundred degrees (ºC) using a small resistive heater. There are many ways to descrbe the regions within the sensor, but it can be described as in [1]: **the surface, which interacts with the gas, the bulk, which is unaffected by it, and the particle boundary, which lies in between these two**. The particle boundary is situated at a distance from any material exposed to the atmosphere into the sensor that chemical electrostatic effects can propagate (the so called Debye length), and this is related to the material’s physical properties. At high temperatures, oxygen atoms bond onto the boundary, extracting electrons in the process from the semiconductor’s surface region. The oxygen either then directly reacts with ambient gases, or these gases also bond onto the sensor, which causes more charge carriers to be withdrawn or injected into the surface region. All these effects change the sensor resistance and it is measured accordingly:

[^1]: Naisbitt et al.

In the case of the SGX 4514, the detection  of  the  pollution  gases  is  achieved  by  measuring the sensing resistance of both sensors:

* RED sensor resistance decreases in the presence of CO and hydrocarbons.
* OX sensor resistance increases in the presence of NO2.

### Manufacturer considerations

[MiCs Datasheet](http://files.manylabs.org/datasheets/MICS-4514.pdf)
[MiCs FAQ](https://www.sgxsensortech.com/content/uploads/2014/08/AN2-%E2%80%93-Frequently-Asked-Questions-for-MiCS-Gas-Sensors.pdf)
[SGX Metal Oxide Gas Sensors - How to use and how they perform](https://www.sgxsensortech.com/content/uploads/2014/08/AN-0172-SGX-Metal-Oxide-Gas-Sensors-V1.pdf)

### Internal Reference
![](https://i.imgur.com/EUCes5C.png)

_Diagram of the various types of interaction between atmospheric gases and an MOS sensor surface. In the leftmost region, the sensor is unpowered (and exhibits the base resistance). The three other regions of the diagram describe different processes that actually occur simultaneously to varying degrees. The sensor’s output is the resistance across the whole of the sensor material, which forms a resistor network with contributions from both the bulk and surface regions (although the non-sensitive surface will have similar properties to the bulk). **This model of the sensor material also explains the wide variation in base resistance between individual sensors of the same type, as the random nature of the surface geometry means an equally random network of resistances**. This diagram is a two-dimensional representation of a three-dimensional material; in an actual sensor, the sensitive region is spread into the surface with a distance dependent on the grain size and arrangement resulting from the sintering._

Note on **response**
> The  change  in  resistance  with  the  change  in  gas  concentration  is  not  a  linear  response.  The  response can be measured and fitted to a **polynomial relationship**.

Note on **performance**
> Because of this and  other factors the sensors are best employed where the end user is looking to  detect  instances or trends of gas presence rather than seeking to obtain high accuracy  such as that  achieved  by  more  sophisticated  analytical  type  systems.  For  these  ‘event  sensing ‘applications the level of accuracy required is not great and there are unlikely to be safety related issues.

Note on **calibration**
> Each  sensor  will  have a  different  resistance  in  air  and  how  much  this  resistance  changes  with concentrations  of  the  target  gas  will  also differ.  Therefore  to  convert from  resistance  readings  to concentration  it  is  necessary  to  derive  a  **calibration  curve  for  each  sensor**.  This  will  require measuring the resistances in air and at a number of gas concentrations over the desired range. **It  is  important  that  the concentrations  are  in  a  background  of  air  as  Oxygen  is  needed  for  the sensor to work correctly**. The more points the better the accuracy.

**Environmental** Factors Effects:

* Temperature & humidity effect are large
* Pressure effect is low
* Flow (and therefore temperature) effect is large: use of PTFE (teflon) filters to reduce it
* Lifetime

**Atmospheric effects**

* Cross sensitivity (non-exclusivity)
* Poisoning