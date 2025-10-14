This document gives a brief description on how the drain current `Id` is a function of gate - to - source voltage `VGS` and how the drain current is affected by transistor sizing. It compares the output waveforms obtained from the spice simulation of a long - channel and a short - channel MOSFET. We also discuss how in a short - channel MOSFET, there are four regions of operation and discuss the drain current formula for each. The second part of the document consists of deriving the voltage transfer characteristics (VTC) of a CMOS invertor step by step, while keeping in mind that the main focus of study is characterizing the MOS device as a switch.

# SPICE simulation 
Upon simulation of the circuit shown below - 
![Circuit](images/Circuit.png)

The following waveform was obtained 
![Waveform](images/Id%20vs%20VDS.png)

The below waveform mentions the regions of operation for the same NMOS device simulated, where the green line indicates `Edge of Saturation` that is when VDS = VGS - Vth.
![Regions of operation](images/EOS.png)

The simulation is performed on a NMOS MOSFET that has characteristics W = 5u and L = 2u (considered as long channel MOSFET), whose W/L value is 2.5. We are going to compare with another device with same W/L value close to 2.5 but that actual values of W = 0.39u and L = 0.18u. 

**Expectation** Since the W/L values are somewhat simlar, the outputs will be same. 
**Reality** The output waveforms are going to be different and we are going to plot them and make observations do decode this mystery. 

Upon simulation of the same SPICE netlist, but with a short channel MOSFET, the simulation results are are shown below - 
![Short Channel Simulation](images/)

