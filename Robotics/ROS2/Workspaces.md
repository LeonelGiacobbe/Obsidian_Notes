---
Status: Not started
Nav2: false
---
To create a workspace:

- make a new directory and `cd` to it
- create a directory inside called `src`
- call the command `colcon build`. _NOT_ inside the `src` folder. In the one above it

Inside `~/mydir/install`. There will be another `setup.bash` file. We need to source this in order to be able to use our custom ROS2 nodes:

- run `gedit ~/.bashrc`
- add this line: `source ~/mydir/install/setup.bash` to the last line of the `bashrc` file  
    Doing this will source the workspace for every terminal. You need to do this for every custom workspace that we create.