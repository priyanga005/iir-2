import numpy as np
import scipy.signal as signal
import matplotlib.pyplot as plt

# Filter specifications
f_c = 1000  # Cutoff frequency in Hz
f_s = 5000  # Sampling frequency in Hz
n = 4       # Filter order

# Normalize the cutoff frequency by the Nyquist frequency
nyquist = 0.5 * f_s
normalized_cutoff = f_c / nyquist

# Design the Butterworth high pass filter
b, a = signal.butter(n, normalized_cutoff, btype='high')

# Create a sample signal (e.g., a noisy sinusoidal signal)
t = np.linspace(0, 1.0, f_s)  # 1 second of data at f_s sampling rate
signal_input = np.sin(2 * np.pi * 500 * t) + 0.5 * np.random.randn(len(t))  # 500 Hz sine wave with noise

# Apply t
