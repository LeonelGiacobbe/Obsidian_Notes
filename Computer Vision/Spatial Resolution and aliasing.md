### Spatial Resolution
- Spatial aliasing is insufficient sampling along the space axis, which occurs due to insufficient spatial resolution. (see [[Sampling and Quantization]])
- This can lead to undersampling, where the sampling rate is considerably lower than the original rate of data.
### Spatial aliasing problem
- Causes when different continuous signals become indistinguishable from one another due to how they are being sampled
	- Example: Two different sine waves go through the same points from time to time. If we sample at those times, there is no way to distinguish between the two waves.
	- One solution is oversampling an image at a higher frequency than intended, then downsizing to the desired size. This is known as _anti aliasing_. To avoid moire patterns, ensure to execute [[Low-pass Filters]] before downsizing.
		- Downsizing incorrectly can lead to moire patterns, which look like fine textures across surfaces that shouldn't have them.