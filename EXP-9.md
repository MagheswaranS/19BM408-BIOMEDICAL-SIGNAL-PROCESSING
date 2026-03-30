# HANNING WINDOW BASED FIR FILTER DESIGN

# AIM:

To design a Low Pass FIR filter using Hanning (Hann) Window and analyze its response.
# THEORY :

Hanning window is defined as:

w(n)=0.5-0.5cos⁡(2πn/N)

Characteristics:

1)Smooth tapering at ends

2)Reduced spectral leakage

3)Moderate stopband attenuation (~31 dB)

4)Wider main lobe than Hamming

Design Equation:

h(n)=h_d (n)⋅w(n)

# ALGORITHM :
1.	Select N and ωc
2.	Compute ideal response
3.	Generate Hanning window
4.	Multiply and obtain FIR coefficients
5.	Plot response

# MATLAB CODE :
```
clc;
clear;
close all;

N = 20;
wc = 0.4*pi;
n = 0:N;
alpha = N/2;

hd = sin(wc*(n-alpha))./(pi*(n-alpha));
hd(alpha+1) = wc/pi;

w = hann(N+1)';
h = hd.*w;

freqz(h,1);
title('FIR using Hanning Window');
```
# OUTPUT GRAPH :
<img width="694" height="622" alt="image" src="https://github.com/user-attachments/assets/9e232b30-7b58-4582-b4d9-e44be0217f1c" />

# RESULT :
The FIR filter was designed using Hanning window.
