In this document you will get a brief introduction to what is noise margin and what are the applications of noise margin. We will also go through how to calculate noise margin from the VTC curve obtained from the SPICE simulation of a CMOS inverter and also compare the noise margins for variation of transistor size as done for rise time, fall time and switching threshold. 

# Noise Margin
Noise margin is another factor that counts for the robustness of a CMOS inverter. Noise margin for a CMOS inverter refers to the amount of noise voltage that a digital circuit can tolerate at its input without causing an incorrect output level or logic error. It quantifies the robustness of the inverter against electrical disturbances or variations, ensuring that the circuit operates correctly even in the presence of unwanted signals or noise.

# Deriving Noise Margins
## Working of an Inverter
We know that an inverter gives the compliment of whatever input is given. The ideal VTC waveform for an inverter is as shown below. 

| Input        | Output       | 
| ------------ | ------------ | 
| 0            | 1            | 
| 1            | 0            |  

## Noise Margins

![Ideal VTC](images/ideal%20vtc.png)

The slope here is infinite, which makes it a very good device with no deffects. But a practical inverter does not behave as such. An intermediate inverter VTC is given below that gives us an idea of differnt voltage levels.

![Little bit practival VTC](images/little%20practical%20.png)

In the above waveform, there are different voltage levels such as -
- VIL = Input low voltage
- VIH = Input high voltage
- VOH = Output high voltage 
- VOL = Output low voltage

It can also be deduced that:
- The range between 0-VIL is considered logic 0. Any value between this range will give an output between VOH and Vdd as logic 1.
- The range between VIH-Vdd is considered logic 1. Any value between this range will give an output between VOL and 0 as logic 0. 

Let's implement this on a more practical VTC waveform like the one given below. 

![Practical VTC](images/Practival%20VTC.png)

It can be observed that the waveform is not very straight due to the non idealities of the inverter. The range VOH-Vdd is considered as logic 1. The range 0-VOL is considered as logic 0. 

Another point to be noted is that `VOH` lies between `VIH and Vdd`. This is so that the next stage of the input detectd logic 1 at the output of the invertor. A similar observation is made where `VOL` lies between `VIL and 0`. This is so that the next stage of the input detects logic 0 at the output of the invertor. Now to obtain the noise margins we plot all the voltage levels onto a single line as shown below:

![One Line Plot](images/One%20line%20Plot.png)

From the plot we can observe the following - 
- NMH = VOH - VIH (Logic 1)
- NML = VIL - VOL (Logic 0)
- Undefined Region (Unkown logic state, can be either 0 or 1)

## Applications 
Noise margins are maily used for detecting bumps which can be further explained from the below image:

![Bump Detection](images/Bump%20Detection%20.png)

From the above images, the following observations can be made:
- The first bump is between VOL-VIL, so it represents logic 0.
- The second bump is in the uncertain region meaning it can take values of either 0 or 1. 
- The third bump is between VIH-VOH, so it represents logic 1

Thus the conclusion that the first and third bumps are valid can be made. 

# Determining Noise Margin 
In this section we are going to look at how to measure the nosie margin of a CMOS inverter from the SPICE simulation output. The SPICE deck used for this experiment is given below:

![SPICE Deck](images/spice%20deck.png)

The output recived upon simulation is given below:

![VTC curve](images/vtc%20curve.png)

To find the noise margins we simple click at the points where `slope = -1` and perform calculations on the obtained co-ordinate values. 

![VTC Noise Margin](images/vtc%20noice%20margin.png)

### Voltage Co-ordinates
![Output Co-ordinates](images/noise%20margin.png)
From the above voltage points, the following outputs are obtained:
- VIL = 0.78351 V
- VIH = 0.96593 V
- VOH = 1.68718 V
- VOL = 0.13333 V
- NMH = VOH - VIH = 0.72125 V
- NML = VIL - VOL = 0.65018 V

# Noise Marging Comparision
With reference to the previous section, we are going to compare the noise margins for devices with respect to Wp/Lp = x(Wp/Lp) with a starting value of Wn = 0.36u and Ln = 0.15u. Upon following the steps from above, the below obseravtions were made:

| Wp/Lp        | Wn/Ln        | NMH (V)             | NML (V)        | 
| ------------ | ------------ | ------------------- | -------------- | 
| Wp/Lp        | 2(Wn/Ln )    | 0.736268            | 0.641758       | 
| Wp/Lp        | 3(Wn/Ln )    | 0.725275            | 0.672528       | 
| Wp/Lp        | 4(Wn/Ln )    | 0.702562            | 0.693407       | 
| Wp/Lp        | 5(Wn/Ln )    | 0.692670            | 0.697802       | 

# Conclusion 
In conclusion, we can tell:
- When the CMOS inverter operates in NML and NMH it can be used for digital design.
- When the CMOS inverter operates in the uncertain NM, it can be used for analog design. 

