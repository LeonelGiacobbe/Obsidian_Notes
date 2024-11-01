### How molecular simulation works 
$F$ = $m \times a$
$F = -\delta U$
- Calculate acceleration, velocity and position of atoms

### How NAMD uses parallel computation 
- Places close-by atoms into patches
	- This improves memory locality
- Patches are divided amongst processors and processors compute the behavior of the patches 
- Processors can access nearby patches via proxy
- Uses `charm++`, similar to `mpi`

### Performance tuning in a NAMD Config file 
![[Pasted image 20240922222549.png]]
