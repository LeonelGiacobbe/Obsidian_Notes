
### Polarization of a Photon
What are the chances a photon passes through a polarized filter?
	- 2D unit vector
		- All possible polarizations can be written as a lin comb of the vectors `<1,0>` and `<0,1>`
	- Measurements are based on an orthogonal subspace chosen arbitrarily
	- The probability that a photon passes through a filter relies on how close it is to the axis of that filter, i.e. mainly horizontally orientated photons have a high chance of going through a horizontal filter
	- If the photon does pass through a filter, then it is polarized in the orientation of said filter


### Qubit State
- A 2D complex vector space
- Qubits can be in a superposition state
	- Any lin comb of a vertical and horizontal component

### Measuring a qubit
- Returns 0 with a probability `|a|^2`
- Returns 1 with a probability `|b|^2`
	- Where `a` and `b` are the vertical and horizontal components mentioned in `Polarization of a photon`
- Measured in terms of an orthogonal basis

>An unknown quantum state cannot be reliably copied


### Tensor product
- Used to describe the combination of multiple qubits
- If you have an `n-qubit` system, the quantum state of that qubit is `2^n`
	- For a `2D` qubit, the quantum state will be 4-dimensional
- Used for entangled states
	- Way to measure if n qubits can be combined to produce a quantum state
	- Two qubits are entangled if they cant be factored into `|P>` $\oplus$ `|Q>` (see [[Notation]])