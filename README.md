# IntroPowerElectronics---Design-and-implementation-of-Boost-Buck-converter
Introduction of basic mathematical theory and analysis techniques for power electronics to design and implement any converter. serves as a layer of knowledge before my 3rd yr as a EEE undergrad.


## The basic concept

Power coverters convert power from one form to another form at high efficientcy.


That could mean converting power from a power plant for it to be used in households or in industry. the power is converted based on what the load requires that could mean that the power needs to be in AC (alternating current) to spin motors & to be efficiently transmitted or to DC (Direct current) for batteries chargers etc...


INPUT FILTER -----> POWER STAGE ---->OUTPUT FILTER

<p align="center">
  <img src="assets/Power Electronics Basics And Tools For Design-2.jpg" alt=" Power Electronics Basics " width="500"/>
</p>

Filters help reduce the noise, the noise comes from high frequency switching from capacitors ( voltage ripple ) and inductors ( current ripple ).


What makes power converters better?

- minituisation
- high efficientcy 
- better system bandwidth ( bandwidth is the measure which reacts to unexpected changes like current surges time to react to a sudden change is proportionate to bandwidth in your control loop )


## Linear Power Supply 

Why are power converters needed? can i just use a potential divider to get the output voltage i need?   


<p align="center">
  <img src="assets/Linear_Power_Supply.jpg" alt="Linear Power Supply" width="500"/>
</p>


from the diagram above, this type of set up is used with power transistors in IC circuits for low power application there could be some filtering but it isn't essential. 

Typical Application which CAN'T be used here: microcontrollers becuase of high clock cycles

Typical Application which CAN be used: brushed DC motors, heating elements


 ## Typical power supply model
 

<p align="center">
  <img src="assets/PowerConverterPWM.jpg" alt="PWM" width="500"/>
</p>


if i had a heating element at the load and i needed to control the average voltage ( Vx_Average ) i can just use the switch to pulsate between Vin & 0V. if the load was going to be a microprocessor then this would cause the load to break. This is called PWM moduation where i control the average voltage by controlling the fraction of the time that the switch is on compared to when the switch is off.


<p align="center">
  <img src="assets/PowerConverterLPF.jpg" alt="LPF" width="500"/>
</p>


This type of adjustment will turn this pulsating voltage from a pwm to a v out which just has the DC component using A low pass filter (LPF) to attenuate the AC component (there is a ripple which is introduced but can be improved with a better cut of freqiency of the LPF).



 # Tools to Analyse Circuits
 
 ## Root Mean Squared of a signal (RMS)
 
 X(t) is some random signal with AC and DC components, im going to intergrate this X(t) which will give me the total energy of the signal but because the signal is sinusoidal i could be integrating a negative (-ve) and positive (+ve) which will give me Energy total = 0 which is wrong. this is where i get my rms value.
 
 <p align="center">
  <img src="assets/RMSPART1.jpg" alt="Signal as an Energy P1" width="500"/>
</p>

  <p align="center">
  <img src="assets/RMSPART2.jpg" alt="Signal as an Energy P2" width="500"/>
</p>
 
 
  ## Orthonogality for a continous waveform
  
  -  This is relating calculus which i have done in my 2nd yr modules about vectors. if two vectors are at 90 degrees out of phase then they equal 0 is they are the same magnitude. 
  
 - if i have a sin * cos of the same frequency then the integration is also =  0 
 
  - then the last one is a useful trig identity
  
  
  <p align="center">
  <img src="assets/Orthonogality.jpg" alt="Orthoganol" width="500"/>
</p>


 ## Average power going thorugh an inductor
 
 this part will use a simple circuit and the defenition of RMS that i disscussed to find the average power going through an inductor
 
   <p align="center">
  <img src="assets/InductorAvgPower.jpg" alt="Inductor Power" width="500"/>
</p>


