# Nixie tube automatic gain control

Version: 1.1
Date: 2021-06-24

This is a hardware only project. The goal of the project was an automatic gain control (AGC) for nixie tubes, connected directly with the speaker output of an audio amplifier. The described circuit is designed for an output of 30Vpp max. For other requirements, the values have to be adjusted. The circuit was tested with the EM84 tube but should be also working with other nixies.

The control curve is  more or less linear over the whole volume range.  I've tested input signals from 1Vpp up to 30Vpp.

### WARNING! This circuit uses dangerously high voltages. DO NOT work with these voltages unless you are properly trained or have the necessary experience. This may result in serious injury or death.



#### Description

The power supplies for the OpAmp and for the tube are not part of the description. The OpAmp requires +/-15V DC with an estimated current of 50mA. The power supply for the nixie tube depends on the tube type. For the EM84 the typical Ua is 250V DC and 6,3V AC for the filament. 

IC1A is the first stage of the variable amplifier for the signal. The feedback is controlled by a photo resistor (33k). 

I've added IC1D for a better control of the nixie's maximum gate voltage. There are some variations between different types or brands, and often between tubes of the same series. 

D1 removes the positive part of the signal because the tube gate requires a negative voltage. R2 and C1 are a low-band filter to block higher audio frequencies causing flicker. R3/R4 are required for typical operation conditions. 

The IC1B part is used to "generate" a DC voltage, depending on the output level of IC1A. D2 cuts of all negative parts of the signal. The two low-band filters have a theoretically infinite low cut-off frequency. The output DC voltage is more or less the effective voltage of the AC input signal. R9/R10 can be used to adjust the ration between the raising and falling edge. The sample has a faster reaction on raising then on falling signals. 

IC1C is only a driver for LED1 (3mm, aproximately 3000-5000mcd, warm white). The LED illuminates the photo resistor and controls the feedback of IC1A. 

**I recommend to assemble the photo resistor together with the LED in an opaque "envelope".  For example in a black heat shrink tube**





![](https://github.com/AndreasExner/Hardware_NixieTube-AutomaticGainControl/blob/main/EM84_AGC_circuit_V1.1.png?raw=true)



#### Example

![](https://github.com/AndreasExner/Hardware_NixieTube-AutomaticGainControl/blob/main/2021-06-20_18-08-54_1.jpg?raw=true)
