## Analog Interfacing

Accuracy: The proximity of measurement results to the true value.
Precision: The repeatability of reproducibility of the measurement
Measurement resolution: The smallest change in the underlying physical quantity that produces a response in the measurement. 

Analog to Digital Signal Conversion:
  * **Time Quantisation** - The signal value read only in specific times, typically consistent intervals.
      * This can cause ***Alaising*** which is frequency ambiguity of signal components.
  * **Amplitude Quantisation** - The amplitude of each sample can only take one of a finite number of values
      *  This adds ***Quantisation Noise*** which is an irreversible corruption of the signal
   
**The Nyquist Theorem**

The Nyquist Theorem states that in order to uniquely determine a signal with no spectral components above a certain frequency f_m (the highest frequency in the signal), the sampling rate f_s must be at least twice that frequency f_s >= 2 x f_m.

### **Types of Analog to Digital Converters**

**Analog to Digital Flash Converter**
> An A/D flash converter offers high-speed conversion without the need for successive approximation, however, it is an expensive solution. 
  It works by using a **Comparator Array**:
  There is a bank of comparators, each comparing the input analog voltage against a reference voltage derived from a resistor ladder network. The number of comparators in the array is equal to the desired number of output bits of the ADC. Therefore, we have 2^n - 1 comparators.

**Analog to Digital Flash Converter Cascade**
> An A/D Flash Converter Cascade has multiple smaller ADCs connected in series to achieve a higher resolution analog-to-digital conversion. Each individual flash ADC in the cascade handles a fraction of the total input voltage range, and their outputs are combined to produce a higher-resolution digital output.
  However, it is important that the Vin is stable during the conversion so sample and hold.

 **Analog to Digital Counter Ramp Converter**
 > This A/D converter generates a linear ramp signal which starts at a known voltage. e.g., 0V, and increases linearly with time. The analog input voltage is compared against the ramp signal using a comparator. A counter starts counting when the ramp signal is less than the input voltage and stops counting when the ramp signal exceeds the input voltage.
   The counter represents the digital output of the A/D converter.

**Analog to Digital Successive Approximation**
> The A/D converter starts by comparing the input analog voltage to a reference voltage, it begins with the MSB of the digital output. Based on the comparison result, the ADC decides whether the MSB of the digital output should be 0 or 1 and continues doing this iteratively.

**Delta-Sigma Converter Concept**
> This converter starts by *oversampling* the signal. Then it takes the *average* of them to help smooth out any noise. Then the *averaged value* is *compared* against a reference value. Any differences in this comparison are then *filtered* out.

## **Timing Interfacing**
Timing interfacing is the use of bistate (square) waveforms to communicate between electronic devices. Common applications include PWM, waveform frequency or time spacing interfaces and consists of *3 main parameters* period, frequency and duty cycle. 

**Some Waveform Basics**
Period(s) = Thigh + Tlow = Tperiod
Frequency(Hz) = 1/Tperiod
Duty Cycle(%) = 100 * Thigh / (Thigh + Tlow)
F = (Zero Crossings)/(2*Twindows)

## **Pulse Width Modulation**
Pulse Width Modulation is used to approximate analog (multi-value) waveforms. I.e., 100% DC is high time equal to the pulse period, 20% DC is high time is 1/5 of the pulse period.
I.e. to calculate Duty Cycle (high time)/period * 100

#How does PWM work?#
> a simple comparator with a sawtooth carrier can turn a sinusoidal command into a pulse-width modulated output. It takes two signals, a command (modulating) signal and chopping (carrier) signal. When the command signal passes over the carrier signal it is low, and the other times it is high.
 
