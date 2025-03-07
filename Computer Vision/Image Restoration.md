### In presence of noise
- Use spatial filtering.
- Can't reverse transformation since noise tends to be randomized and hard to predict.
- Can only transform into the frequency domain if there is periodic noise

## MEAN FILTERS
### Averaging Mean filters
- Each pixel in restored image is replaced by the average of all the pixels in the modified sub-image
### Geometric mean filter
- Each pixel in restored image is replaced by the product of all the pixels, to the power of `m/n`, where `m` and `n` is the size of the sub-image
	- More details are preserved compared to averaging filters

### Harmonic Mean filter
- Works well with salt noise but not with pepper noise
- Also works well with Gaussian noise
- Divides size of sub-image by the summation of `1/x` where x is a pixel value => 
### Contra-harmonic mean filter
- Gives more weight to smaller pixel intensity values
- If the order of the function is positive, it eliminates pepper noise. If the order is negative, it eliminates salt noise. Becomes perfectly arithmetic at `Q=0`

## STATISTIC FILTERS

### Median filters
-  Each pixel in the restored image is defined by the image pixel of the sub-image of the original image.
- Provides less blurring than other linear filters

### Max and min filters
- Each pixel in the restored image is defined as the min or max of the sub-image at that location
- Max helps reduce pepper noise
- Min helps reduce salt noise

### Midpoint filters
- Each pixel is defined as half of the addition of the min and max values of the sub-image at that location
- Can be applied multiple times to improve performance