# EXP-01 IDEAL SAMPLING
# NAME: KAMESHWARAN A
# REG NO:212223060110
### Aim:

To ensure the sample accurately represents the population with minimal bias and sufficient size using python code

### Tools required:

python IDE with Numpy and Scipy

### Program:
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.signal import resample
fs = 100
t = np.arange(0, 1, 1/fs) 
f = 5
signal = np.sin(2 * np.pi * f * t)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal')
plt.title('Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
t_sampled = np.arange(0, 1, 1/fs)
signal_sampled = np.sin(2 * np.pi * f * t_sampled)
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.stem(t_sampled, signal_sampled, linefmt='r-', markerfmt='ro', basefmt='r-', label='Sampled Signal (fs = 100 Hz)')
plt.title('Sampling of Continuous Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
reconstructed_signal = resample(signal_sampled, len(t))
plt.figure(figsize=(10, 4))
plt.plot(t, signal, label='Continuous Signal', alpha=0.7)
plt.plot(t, reconstructed_signal, 'r--', label='Reconstructed Signal (fs = 100 Hz)')
plt.title('Reconstruction of Sampled Signal (fs = 100 Hz)')
plt.xlabel('Time [s]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.legend()
plt.show()
```

### Output Waveform:

![image](https://github.com/user-attachments/assets/9fa0eb54-404a-4bd5-bd0e-45fe6ae10da4)
![image](https://github.com/user-attachments/assets/284914eb-cea2-42aa-9faf-2cf28c7a110f)
![image](https://github.com/user-attachments/assets/4f72ca1a-999e-41df-ae7b-44c8a1180b30)

### Results:

An ideal sampling process was conducted using Python, ensuring randomness and eliminating bias. A representative sample of 20% was selected from the population using a random sampling method, maintaining statistical validity and accuracy for further analysis.
