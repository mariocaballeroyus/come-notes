[[Integral Transform Methods]]

The **Discrete Fourier Transform (DFT)** is used to convert a sequence of values, typically in the time or spatial domain, into components of different frequencies. 

It transforms a finite discrete signal into a sum of sinosouds with varying amplitudes and frequencies. Mathematically, for a sequence of $N$ data points, the DFT is given by:

$$
X(k) = \sum_{n=0}^{N-1}{x(n) e^{-j 2\pi kn/N}}, \qquad
k = 0, 1, 2, \dots, N-1
$$
## Periodicity

The DFT assumes that the signal being transformed is **periodic** with a period equal to the number of samples in the sequence, $N$. This assumption of periodicity leads to the folding back of higher frequencies, which will be discussed later. 
## Sampling Interval

The sampling interval $T_s$ is the time between consecutive samples in the discrete signal. For a continous-time signal, the sampling time interval is the inverse of the sampling frequency:
$$
T_s = \frac{1}{f_s}
$$
The sampling frequency determines the Nyquist frequency, which is the highest frequency that ca be accurately represented:
$$
f_{\text{max}} = \frac{f_s}{2}
$$
## Symmetry of Frequencies

When performing a DFT on a real-valued signal, the resulting frequency spectrum exhibits a specific symmetry that is often referred to as **conjugate symmetry**. 

- The positive frequencies (from $k=0$ to $k=N/2$) correspond to the actual frequency components of the signal.
- The negative frequencies (from $k=N/2$ to $k=N-1$) are actually the mirror image (complex conjugates) of the positive freqéncies. 

To avoid aliasing (where higher frequencies fold back into the sampled signal), the sampling frequency must be at least twice the highest frequency component of the signal.
