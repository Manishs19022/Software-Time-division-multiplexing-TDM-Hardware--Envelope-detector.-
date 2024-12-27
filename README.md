# Software-Time-division-multiplexing-TDM-Hardware--Envelope-detector.-

# • TDM: 
 A multiplexing technique by which multiple data signals can be transmitted over a common communication channel in different time slots is known as Time Division Multiplexing (TDM).It allows the division of the overall time domain into various fixed length time slots.  

A single frame is said to be transmitted when it’s all signal components gets transmitted over the channel. The multiplexing allows the transmission of several signals over a common channel. However, one may need to differentiate between the various signal for proper data transmission. 

So, in time division multiplexing, the complete signal gets transmitted by occupying different time slots. The name itself is indicating here that basically time division is performed in order to multiplex multiple data signals. 

# • ENVELOPE DETECTOR: 

In envelope detector is a fundamental electronic circuit used to extract the envelope of a modulated waveform. It plays a crucial role in demodulating amplitude-modulated (AM) signals, where the information is encoded in the amplitude variations of a carrier wave. 

The envelope detector essentially retrieves the varying amplitude signal 
from the modulated carrier wave, which can then be further processed to recover the original information. 

Typically consisting of a diode, a capacitor, and sometimes a resistor, the envelope detector rectifies the input signal (converting it from AC to DC) and smoothens out the resulting waveform to approximate the original envelope. This process is essential in various applications, including radio communication, where AM signals are prevalent, as well as in audio and telecommunications systems. 

The simplicity and effectiveness of envelope detectors make them indispensable in analog communication technologies, ensuring efficient extraction of modulated signals for subsequent amplification or processing.


![image](https://github.com/user-attachments/assets/2b91c25e-ea11-4740-a6f0-4a084ab088ba)





# Code:

fs = 1000;              

t = 0:1/fs:1;             

% Two example signals 

signal1 = sin(2*pi*10*t); % 10 Hz sine wave 

signal2 = cos(2*pi*10*t); % 20 Hz cosine wave 

 
%Time Division Multiplexing 

TDM_signal = zeros(1, 2 * length(t)); % Initialize TDM signal 

 
%Interleave signals 

TDM_signal(1:2:end) = signal1;        % Assign signal1 to odd indices 

TDM_signal(2:2:end) = signal2;        % Assign signal2 to even indices 

 
%Time vector for TDM signal 

t_TDM = 0:1/fs:(length(TDM_signal)-1)/fs; 

 
%Plotting the signals 

figure; 

 
subplot(3,1,1); 

plot(t, signal1); 

title('Signal 1'); 

xlabel('Time (s)'); 

ylabel('Amplitude'); 

 
subplot(3,1,2); 

plot(t, signal2); 

title('Signal 2'); 

xlabel('Time (s)'); 

ylabel('Amplitude'); 
 

subplot(3,1,3); 

plot(t_TDM, TDM_signal); 

title('Time Division Multiplexed Signal'); 

xlabel('Time (s)'); 

ylabel('Amplitude');




# Result:

![image](https://github.com/user-attachments/assets/2483a782-c1fa-404c-8ffa-135f60debc97)
