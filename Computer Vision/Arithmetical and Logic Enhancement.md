- Pixel by pixel operations on multiple images
	- `AND`, `OR`, `XOR`, etc.
- Image subtraction `G(x,y) = F(x,y) - H(x,y)`
	- Used in medical imaging

### Image averaging
- Can take a regular image, add random noise
- `Noisy(x,y) = Regular(x,y) + RandNoise(x,y)`
- An enhanced image can be created by adding the average of a set input of noisy images
- `Variance = (1/k)n^2(x,y)`
	- As `k` increases, the noise of the pixel values decreases
	- Higher amount of noisy images makes the average result be closer to the original image, since `diff(x,y) = og(x,y) - avg(x,y)`