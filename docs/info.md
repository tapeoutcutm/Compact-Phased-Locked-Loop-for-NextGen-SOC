<!---


## How it works



Phase Frequency Detector (PFD):
The PFD is implemented using D flip-flops with inputs A and B, and outputs QA and QB. It compares the phases of the two input signals and produces pulses indicating the phase difference. When A leads B, QA goes high while QB goes low; when B leads A, the opposite occurs. If the signals are aligned, both outputs remain inactive. These signals drive the control of the Voltage-Controlled Oscillator (VCO), enabling phase and frequency locking in the PLL. The PFD is critical in applications such as clock synchronization, frequency synthesis, and communication systems.


Charge Pump (CP):
The charge pump translates the PFD outputs into a control voltage for the VCO. It typically consists of switches and a capacitor. A positive pulse from the PFD charges the capacitor by connecting it to a reference voltage, while a negative pulse discharges it to ground. The resulting voltage is proportional to the phase error, providing continuous adjustment of the VCO frequency.


Voltage-Controlled Oscillator (VCO):
The VCO is designed as a ring oscillator with an odd number of inverting stages connected in a loop, generating a periodic signal. By varying the bias voltage of the transistors in the stages, the oscillation frequency can be tuned. Within the PLL, the VCO frequency is locked to the reference through feedback, ensuring stable oscillation.


Frequency Divider (FD):
The frequency divider, based on D flip-flops, reduces the VCO output frequency by an integer factor. The toggling action of the flip-flops divides the frequency by 2, 4, or 8, depending on configuration. This scaled-down signal is fed back to the PFD for comparison with the reference, enabling frequency multiplication or division in the PLL loop.





## How to test

**PFD**: Apply input pulses with phase difference between them and A and B pins at PFD input. Observe the output at QA and QB pins with output pulses based on +ve or -ve phase difference between signal applied at input pins of PFD.

**CP**: Apply input pulses at QA and QB input pins of charge pump replicating the output of PFD circuit. Based on whether QA or QB pulses are high, the output of charge pump circuit will demonstrate charging and discharging behaviour respectively. Charging and discharging rate can be controlled by changing bias voltage cp_bias to either increase of decrease current.

**VCO**: Apply a control voltage, vctrl=0.9V to VCO's input and measure the resulting output frequency. Verify that the output frequency varies with the applied control voltage within the specified range i.e. 0.75V to 1V. Check VCO frequency tuning range by sweeping the control voltage across and observing the output frequency response.

**FD**: Input a signal with a frequency (40 to 80MHz range) to input of frequency divider. Measure the output frequency using a oscilloscope. Verify that the output frequency is one-eighth of the input frequency.


## External hardware
2-channel function/waveform generator with varying frequency and pulse time generation.
2-channel Oscilloscope to measure output signal waveforms.

