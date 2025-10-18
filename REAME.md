# Week 4 RISV Workshop
This week you will learn about the following topics.

## 1. Introduction to NMOS and Its Operating Regions
An NMOS (n-channel MOSFET) is a type of MOS transistor built on a p-type substrate with n-type source and drain regions, controlled by a voltage applied to a polysilicon gate separated by a thin insulating oxide layer. The operation of an NMOS is determined by the gate-to-source voltage VGS and the drain-to-source voltage VDS.

## 2. SPICE Simulation Overview
SPICE (Simulation Program with Integrated Circuit Emphasis) is a standard tool to model and analyze circuits. By writing a SPICE deck (text file describing the circuit, device models, and inputs), you can simulate:
- DC analysis: For voltage transfer characteristics (VTC) of an inverter.
- Transient analysis: For timing characteristics like rise time (tr) and fall time (tf).

## 3. CMOS Inverter Analysis-VTC, Threshold, and Transient
- VTC (Voltage Transfer Characteristic): Shows output voltage as a function of input voltage. Simulate an inverter in SPICE while sweeping the input from 0 to VDD. 
    - The switching threshold (Vm): Input voltage at which output equals input, often solved with formulas involving (W/L)n and (W/L)p.
- Switching Characteristics: By using transient simulation, you can extract rise time and fall time. Increasing the pMOS width (Wp/Lp)relative to nMOS can balance the tr and tf, optimizing for speed or symmetry based on application.
- Noise Margin: Key reliability metric-the noise margin high (NMH) and noise margin low (NML) are calculated from the VTC (e.g., NMH = VOH - VIH, NML = VIL - VOL). SPICE helps quantify noise margins as sizing or process variables change.

## 4. Power Scaling, Device Robustness, and Process Variation
- Lowering supply voltage or shrinking device dimensions (W/L, oxide thickness) has direct effects on VTC, gain, energy, and margins. Simulations can show how an inverter remains robust (produces correct logic output despite variation or noise) under such variation.
- By simulating inverters with strong/weak PMOS and NMOS, you can see how device sizing and process variation impact performance and reliability.