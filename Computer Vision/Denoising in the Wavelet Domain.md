- Input wavelet signal across the time variable
- The discrete wavelet transform returns two components
	- Important features in image (from wavelet function)
	- approximation components (non important and can be removed). This comes from the scale function

### Wavelet decomposition (1D and 2D)
- Original wavelet -> Low-pass filter -> Down-sampling = Approximation Coefficients
- Original wavelet -> High-pass filter -> Down-sampling = Detail Coefficients

- We can perform this process multiple times (output of low-pass filter in first level is used in wavelet decomposition function). Can do this `n` times, resulting in `n` levels of coefficients. **FOR 1D DECOMPOSITION**
- `2D` decomposition gives you `LL`, `LH`, `HL` and `HH` components, each giving you more focus on specific components of an image.

### Thresholding
- Targeting minimizing mean squared error
- `VisuShrink` proposes a universal method to find appropriate threshold. 
	- `t = stddev*sqrt(2*ln(N)))`, where `N` is the sample size
- `Hard Threshold`: called "keep or kill". Threshold is absolute and discards everything outside it.
- `Soft Threshold`: does not delete all values outside of threshold. It sets them to zero.
- There's also improved threshold functions. Components are not deleted or set to zero, but scaled to a small value in a non-linear way.