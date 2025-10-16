This document will give you a step by step process on how to write a SPCIE deck for a CMOS inverter and perform simulations to obtain the VTC curve and also calculate rise time and fall time from transient simulations.We deepdive into second - order effects like switching threshold (Vm) and derive equations to find Vm as a function of W/L and vice versa. We have also performed transient analysis for CMOS inverters with varrying the width of PMOS transistors as a multiple of NMOS transistors (Wp/Lp=x.Wn/Ln) and compared the resulting rise and fall times, determining which pair is best suited for which application.

# VTC SPICE Simulation
The steps required to perform SPICE simulation to obtain the VTC curve are
- Component connectivity - Connect the components in the right manner. 
- Component values - Give component values like (W/L)n, (W/L)p, Vin, Vdd, Cload ect.
- Identify the nodes - Creating nodes is essential to write SPICE code.
- Name the nodes - Give suitable names to nodes that can be furhter used to write SPICE code. 
- Write the SPICE code - Define the circuit in terms of SPICE code along with the type of simulation that needs to be performed and link the requiered library file.

![CMOS Invertor](images/CMOS%20Invertor%20.png)

The SPICE code for the above transistor is given below 



