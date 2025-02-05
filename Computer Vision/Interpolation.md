- Practice of generating unknown pixels based on nearby known pixel values

### Nearest neighbor
- Makes pixel bigger
- The intensity of a pixel in the new image is the intensity of the original nearest neighbor
- Fastest processing
- Not suitable for detailed images

### Bilinear Interpolation
- Considers closest 2x2 neighborhood surrounding the unknown pixel
- Takes weighted average and assigns that value to the unknown pixel
- Smoother looking that neighbor approach
- less blocking effect due to anti-aliasing

### Bicubic Interpolation
- Does the same thing as Bilinear, but considering a 4x4 neighborhood, containing 16 pixels.
- Produces sharper image than other two methods
- Almost no blocking
- Used as standard in many programs