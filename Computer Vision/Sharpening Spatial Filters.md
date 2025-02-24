- Highlights fine details in images
- Since blurring is based on averaging, sharpening is based on differentiation. See [[Spatial Domain enhancement]]

### First derivatives
- Implemented using the magnitude of the gradient
- Can be approximated using absolute values. `vf = abs(Gx) + abs(Gy)`
### Second order derivatives
- Constructs a Laplacian Filter Mask
	- Laplacian is a kind of isotropic filter
		- Rotation invariant (rotate <-> filter order does not matter)
- Laplacian operator = `f(x,y+1)+ f(x,y-1) -2f(x,y)`
- Highlights gray level discontinuities
- Obtain modified image by adding the Laplacian operator to the original image