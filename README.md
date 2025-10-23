# DSBSC-using-Python

# Aim


To implement and analyze (DSBSC) using Python's NumPy and Matplotlib libraries. 

# Apparatus Required

1.	Software: Python with NumPy and Matplotlib libraries
2.	Hardware: Personal Computer
  
# Theory

DSB-SC (Double Sideband Suppressed Carrier) is a type of amplitude modulation where the carrier wave is suppressed, and only the two sidebands (which contain the actual information) are transmitted. This saves power and reduces bandwidth waste compared to standard AM.

In DSB-SC, the amplitude of the carrier is still varied according to the message signal, but the carrier itself is not transmitted.


# Algorithm


1.	Initialize Parameters: Set the values for carrier frequency, message frequency, sampling frequency, and frequency deviation.
2.	Generate Time Axis: Create a time vector for the signal duration.
3.	Generate Message Signal: Define the message signal as a cosine wave.
4.	Compute the Integral of the Message Signal: Calculate the integral of the message signal over time.
5.	Generate FM Signal: Apply the DSBSC modulation formula to obtain the modulated signal.
6.	Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.

# Program

```
import numpy as np
import matplotlib.pyplot as plt
Am = 3.11;
fm = 352;
Ac = 6.22;
fc = 3520;
fs = 35200;
t=np.arange(0,2/fm,1/fs)
m = np.cos(2 * np.pi * fm * t)
c=np.cos(2*np.pi*fc*t)
s1 = (Ac + m) * np.cos(2 * np.pi * fc * t)
s2 = (Ac - m) * np.cos(2 * np.pi * fc * t)
s = s1 - s2
s = m * c
plt.subplot(3,1,1)
plt.plot(t, m)

plt.subplot(3,1,2)
plt.plot(t,c)

plt.subplot(3,1,3)
plt.plot(t,s)

```

# Output Waveform

<img width="765" height="551" alt="Screenshot 2025-10-23 225550" src="https://github.com/user-attachments/assets/29c54bc1-8eaa-48be-86d3-5a56aea6d6a1" />


## Tabular Column

![WhatsApp Image 2025-10-23 at 22 13 45_b876fc7f](https://github.com/user-attachments/assets/a051e75b-f3d1-45ce-bd8c-a84e98bd418d)


## Result

The message signal, carrier signal, and DSBSC signal will be displayed in separate plots. The modulated signal will show amplitude variations corresponding to the amplitude of the message signal.
