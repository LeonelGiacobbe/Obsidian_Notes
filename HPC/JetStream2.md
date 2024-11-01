### Three phases
- Homework
	![[Pasted image 20240912101027.png]]
- Benchmarking (24 hours)
	![[Pasted image 20240912101131.png]]
- 48-hour competition
	![[Pasted image 20240912101152.png]]
### Access Instances
- Named with team's submission ID
- SSH Keys are set up on the rocky user with full root access
- Login nodes have public IP address and DNS record
- Compute Nodes are only available on a subnet, only accessible through login node.

### Installing software and running jobs
- Full Sudo access to users 
- No central scheduler to submit to (teams can install their own if they want)
- GPU drivers are preinstalled **DO NOT UNINSTALL `nvidia-linux-grid` PACKAGE**

### Resource Usage
- Users can shelve Service Units to reduce power usage and allow them to be used by other people.
- During Homework phase:
	- Team's SU should be active for a max average of 25 hours/week (try not to exceed this limit)

### Where to find Homework inputs & submissions
- Inputs & instructions:
	- Google classroom
		- This is also the place to get help
	- read only mount at `/indyscc-inputs`
- Submissions:
	- TBD
  