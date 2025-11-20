# Wavelets

> **See also:** [[Signal Processing]]

---

## What are Wavelets?

> [!caption|right]
> ![[Pasted image 20221214165111.png]]
>
> A Meyer wavelet from $t=[-10,10]$

A signal can be represented as a series of frequency bands (**filterbank**). For instance, the signal can be divided into bands over $[f,2f]$.

All of these bands are scaled versions of some fundamental band (with scale 1). The fundamental band comes from shifting some generating function $\psi$ (the **mother wavelet**)

One example of a mother wavelet is the Meyer wavelet
$$\begin{align}
\DeclareMathOperator{\sinc}{sinc} \psi_{\text{Meyer}} & =2\sinc(2t)-\sinc (t) \\
&=\frac{{\sin(2\pi t)-\sin(\pi t)}}{\pi t}
\end{align}$$
where $\DeclareMathOperator{\sinc}{sinc}\sinc(t)=\sin(\pi t) / \pi t$, the normalized form

If we know scaling factor $a$ and shifting factor $b$, the mother wavelet can be transformed by $$\begin{align}
\psi_{a,b}(t) & =\frac{1}{\sqrt{ a }}\psi\left( \frac{t-b}{a} \right)
\end{align}$$

> [!example] Code demo
> ```jupyter
> import numpy as np
> import matplotlib.pyplot as plt
>
> t = np.arange(-10, 10, 0.01)
> psi = 2 * np.sinc(2 * t) - np.sinc(t)
>
> plt.plot(t, psi)
> ```

> [!question] Why not use a windowed Fourier transform?
> By windowing the Fourier transform to discrete time windows, high and low frequencies cannot be analyzed at the same time.
>
> There is also inefficiency: all $\frac{T}{2 \cdot\delta t}$ time windows must be analyzed independently

## Properties of Wavelets

**Admissibility:** the wavelet has no offset
- Admissibility enables the wavelet transform to be reversible
- Effectively means that wavelets look like band-passes
$$\begin{align}
\lim_{ \omega \to 0 } \Psi(\omega ) & =0 \\
\int \frac{\lvert \Psi(\omega )\rvert^{2}}{\omega} \, d\omega & <\infty
\end{align}$$

**Regularity:** the wavelet is localized in frequency and time
$$\gamma(s,0)=\frac{1}{\sqrt{ s }}\left[ f(0)M_{0}s+\frac{f^{(1)}(0)}{1!}M_{1}s^{2}+\frac{f^{(2)}(0)}{2!}M_{2}s^{3}\dots \right]$$
where $f$ denotes the function that is being analyzed, $\gamma$ is the wavelet transform, and $M_{n}$ are the moments

Given admissibility, $M_{0}=0$. If all moments up to $M_{n}$ are also 0, then coefficients of the transform decay as fast as $s^{n+2}$

## Discrete Wavelet Transforms

> [!warning] Problems
> 1. With the continuous wavelet transform, the wavelet is convolved over all points in the entire signal, leading to **redundancy**
> 2. The wavelet transform still generates infinitely many wavelets. We want to restrict this with a **bandpass filter**
> 3. There are no **analytic solutions** to the wavelet transform

### Redundancy

We can get rid of redundancy by modifying the transform equation to $$\Psi_{j,k}(t)=\frac{1}{\sqrt{ s_{0}^{j} }}\Psi\left( \frac{{t-k\tau_{0}s_{0}^{j}}}{s_{0}^{j}} \right)$$
where $j$ functions like $a$ and $k$ functions like $b$. Typically we choose $s_{0}=2$ (**dyadic sampling**), which equates to octaves and is natural for computers/music/human ears. We also choose $\tau_{0}=1$ for dyadic sampling.

> [!important|ws-med right]
> You don't need an orthonormal basis, but it's useful to reduce *noise sensitivity* and improve *shift invariance* (change when shift in time).
> 
> This also forces the signal to have finite energy, which is reasonable for real signals.


The sum of energies of the wavelets over the entire signal, over all wavelets, should be between bounds $A$ and $B$ with $A=B$ in order to constitute a **tight frame**. In that case, the wavelets can behave like a *orthonormal basis*

To make an orthonormal wavelet basis, you need a good selection for the mother wavelet that satisfies $$\int \Psi_{j,k}(t)\Psi_{m,n}^{*}(t)\, dt=\begin{cases}
1 & j=m\text{ and }k=n \\
0 & \text{otherwise}
\end{cases} $$

Then the original signal can be reconstructed as $$f(t)=\sum_{j,k}\gamma(j,k)\psi_{j,k}(t)$$

### Bandpass Filters

> [!question] How many wavelets is enough to analyze the signal?

From Fourier theory, we know that compressing in time is the same as stretching in time: $$\mathcal{F}(f(at))=\frac{1}{|a|}\hat{f}\left( \frac{\omega}{a} \right)$$
i.e. compressing a wavelet in the time domain → stretching & multiplying it in the frequency domain

The solution is to then set up a filter bank of wavelets that each look at different frequencies. For very low frequencies, a **scaling function** ($\phi$, averaging filter) acts like a low-pass and looks at the remaining frequencies.

### Calculating the Wavelet Transform

We can divide the problem of generating a filter bank into using an **iterative filter bank**. We iteratively divide the bands into a high-pass and a low-pass, then divide the LP into HP and LP, etc. This means we don't need to explicitly calculate all the filters.

A scaling function can be expressed in terms of another scaling function. This means that we can express the input signal in terms of some scaling function at a scale $j$ $$f(t)=\sum_{k}\lambda_{j}(k)\phi(2^{j}t-k)$$
We can express the signal as a combination of scaling functions and wavelets $$f(t)=\sum_{k}\lambda_{j-1}\phi(2^{j-1}t-k)+\sum_{k}\gamma_{j-1}(k)\psi(2^{j-1}t-k)$$
where $\lambda$ and $\psi$ are calculated as $$\begin{align}
\lambda_{j-1}(k) & =\langle f(t),\phi_{j,k}(t) \rangle \\
\gamma_{j-1}(k) & =\langle f(t),\psi_{j,k}(t) \rangle 
\end{align}$$

Both $\lambda_{j-1}$ and $\psi_{j-1}$ can be expressed in recursive form as a function of $\lambda_{j}$ and $\psi_{j}$. Because of this recursive property, the resolution of the filter bank doesn't get reduced compared to the input signal.