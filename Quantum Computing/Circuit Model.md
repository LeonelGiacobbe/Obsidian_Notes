>READ TOP-DOWN, LEFT-RIGHT
>Use https://algassert.com/quirk to design quantum circuits

- For an n-qubit system, a quantum circuit is represented by a 2^n x 2^n unitary matrix
- Must be reversable
	- Same number of inputs and outputs
	- By knowing the output, we can work backwards and get the input
- Only represents combinational logic, not sequential


>In real-world quantum computers, these gates are **APPROXIMATED**
### Single-qubit Gates
-  A rotation by any amount in any direction is known as a `gate`
- `Pauli` gates: rotates out qubit by $\pi$ radians around the x, y or z axis.
	- Note that `XX  = YY = ZZ = I`
	- `Pauli X` is also known as the `NOT` gate

### Manipulating quantum states
- `H`, or `Hadamard` gate: rotates by $\pi$ around the `(+x, +z)` diagonal.
	- Provides a uniformly-random superposition state (50% of observation 0, 50% of 1).
	- `HH = I`
- `CNOT`: flip the second qubit if the state of the first qubit is 1
	- `CCNOT` or `Toffoli`: flips the third qubit if the state of first two qubits are 1
		- Useful, since it can represent any Boolean expression.

