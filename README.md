# Nixie tube automatic gain control

Version: 1.0
Date: 2021-06-16

This is a hardware only project. The goal of the project was an automatic gain control (AGC) for nixie tubes, connected directly with the speaker output of an audio amplifier. The described circuit is designed for an output of 30Vpp max. For other requirements, the values have to be adjusted. The circuit was tested with the EM84 tube but should be also working with other nixies.

The control curve is  more or less linear over the whole volume range.  Only at very low volumes the signal is a bit lower and does not reach the max input for the nixie. But that should not be relevant in normal conditions.

### WARNING! This circuit uses dangerously high voltages. DO NOT work with these voltages unless you are properly trained or have the necessary experience. This may result in serious injury or death.



#### Description

The power supplies for the OpAmp and for the tube are not part of the description. The OpAmp requires +/-15V DC with an estimated current of 50mA. The power supply for the nixie tube depends on the tube type. For the EM84 the typical Ua is 250V DC and 6,3V AC for the filament. 

IC1A is the main amplifier (amplification <=1) for the signal to the tube gate. The feedback is controlled by a photo resistor (33k). D1 removes the positive part of the signal because the tube gate requires a negative voltage. R2 and C1 are a low-band filter to block higher audio frequencies causing flicker. R3-R6 are required for the tube's typical operation conditions. 

The IC1B part is used to "generate" a DC voltage, depending on the output level of IC1A. D2 cuts of all negative parts of the signal. The two low-band filters have a theoretically infinite low cut-off frequency. The output DC voltage is more or less the effective voltage of the AC input signal. R9/R10 can be used to adjust the ration between the raising and falling edge. The sample has a faster reaction on raising then on falling signals. 

IC1C is only a driver for LED1 (3mm, 7,5mcd, amber, low current). The LED illuminates the photo resistor and controls the feedback of IC1A. 

**I recommend to assemble the photo resistor together with the LED in an opaque "envelope".  For example in a black heat shrink tube**





![](https://github.com/AndreasExner/Hardware_NixieTube-AutomaticGainControl/blob/main/EM84_AGC_circuit.png?raw=true)



#### Example

![](https://github.com/AndreasExner/Hardware_NixieTube-AutomaticGainControl/blob/main/2021-06-20_18-08-54_1.jpg?raw=true)
