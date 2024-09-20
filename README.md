
MATLAB code simulates an underwater acoustic communication system using amplitude modulation (AM). It calculates the Bit Error Rate (BER) of the system over various Signal-to-Noise Ratios (SNR) and compares it with the theoretical BER for Binary Phase Shift Keying (BPSK) in an AWGN channel. The code also factors in the effects of underwater environmental parameters such as temperature, salinity, depth, and pH on the signal attenuation.

Features
Modulation: Amplitude modulation (AM) based on two different frequencies for binary '1' and '0'.
Environmental effects: Signal attenuation is calculated using the Ainslie-McColm model, which incorporates factors such as temperature, salinity, depth, and pH.
Noise Addition: AWGN (Additive White Gaussian Noise) is added to simulate real-world noise.
Detection: The received signal is demodulated, and bit error rates (BER) are calculated for each SNR value.
Filtering: A bandpass filter is applied to isolate the frequencies of interest.
Getting Started
Prerequisites
Make sure you have:

MATLAB installed (R2019b or later recommended)
Signal Processing Toolbox
Files
main_script.m: This is the main script that simulates the communication system.
ainslie_mccolm_attenuation.m: Function to compute the attenuation of acoustic signals in water.
detect_AM.m: Function that performs AM demodulation and bit detection.
Code Overview
Parameters
Tb: Bit duration (1 ms in the script).
N: Number of bits (9000 in the script).
Fs: Sampling frequency (1 MHz).
fn1: Frequency for bit '1' (30 kHz).
fn2: Frequency for bit '0' (40 kHz).
Environmental Parameters
T: Water temperature (15°C).
S: Salinity (35 ppt).
D: Depth (100 meters).
pH: Water pH (8).
Functions
ainslie_mccolm_attenuation(f, T, S, D, pH):
This function calculates the attenuation coefficient (in dB) based on the Ainslie-McColm model for a given frequency f (in kHz) and environmental conditions.

detect_AM(received_signal, Fs, Tb, fn1, fn2):
This function demodulates the received AM signal using correlation with reference signals, and detects the transmitted bits.

Simulation
A random bit sequence of length N is generated and modulated using AM with the frequencies fn1 and fn2 for bits '1' and '0'.
The modulated signal is subjected to underwater attenuation and AWGN at different SNR levels.
The Bit Error Rate (BER) is computed for each SNR level.
Results are plotted, showing a comparison between the simulated BER and the theoretical BER for BPSK in an AWGN channel.
Outputs
BER vs SNR Plot: The script generates a plot comparing the simulated BER with the theoretical BER, giving insight into the system's performance at different SNR levels.
Usage
Clone the repository or download the files.
Open MATLAB and navigate to the folder containing the files.
Run main_script.m in the MATLAB environment.
Example Run
matlab
Copy code
% Execute the main script
main_script
After execution, you will see a BER vs SNR plot that compares the simulated and theoretical BER.

Modifications
You can change the parameters (e.g., frequencies, bit duration, environmental conditions) to simulate different scenarios.
The SNR range can be adjusted by changing the SNR_dB variable in the script.
References
Ainslie-McColm Attenuation Model: This model is used to calculate the attenuation of sound in seawater based on temperature, salinity, pH, and depth.
