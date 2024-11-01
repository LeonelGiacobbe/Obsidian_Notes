---
Status: Not started
Nav2: false
---
> [!important]  
> Full user guide can be found at: MAVS Python User Guide  

[[MAVS-Python Example Simulation]]

## MAVS Coordinate System

- East-North-Up
- Origin is always (0,0,0)
- By default, positive X points East, Positive Y points North, positive Z points up

## Creating a simulation object

```Python
import mavs
import mavs_python_paths
mavs_data_path = mavs_python_paths.mavs_data_path

# Declaring simulation object
my_sim = mavs.MavsSimulation()

# Loading the simulation
my_sim.Load(mavs_data_path + 'path/to/sim/file'

# Running the simulation
dt = 1/30.00 # 30hz update, refreshes 30 times per second
while True:
	my_sim.Update(dt, throttle = 1.0, # can be updated via keyboard input

										steering = 0.0, # can be updated via keyboard input

										braking = 0.0,  # can be updated via keyboard input

										update_actor = True)
```

  

## Creating and editing environment

```Python
import mavs

# Create an environment inside an object called env
env = mavs.MavsEnvironment() # Creates a pointer to a MAVS class

env.DeleteEnvironment() # deletes pointer to class, ready to be reassigned
```

We can edit the environment conditions with the following commands:

- `env.SetRainRate(x)` . x is a float. The units are in mm
- `env.SetTurbidity(x)`. x is a float from 2.0-10.0
- `env.SetFog(x)` x is a value from 0-100 (100 being the maximum)
- `env.SetCloudCover(x)` x is a float from 0.0-1.0 (1.0 being completely covered by clouds)
- `env.SetSnow(x)` x is a float. Units in mm
- `env.SetWind([x,y])`x and y are float units, representing strength in East/North. Units in m/s

  

In order to animate the dynamic components of a scene, the time inside the simulation must be advanced. That is done by:

```Python
dt = 0.1 # float value in seconds
env.AdvanceTime(dt)
```

  

## ==MAVS Scenes==

- Made of meshes
- Can be loaded from scene definition file with `MavsEmbreeScene()`
    
    ```Python
    import mavs
    mavs_data_path = mavs_python_paths.mavs_data_path
    
    scene = mavs.MavsEmbreeScene()
    scene_path = 'path/to/scene/file'
    scene.Load(mavs_python_paths.mavs_data_path + '/' + scene_path)
    ```
    
- Or create a random scene with `MavsRandomScene()`.
    - Physical aspects of the scene may be defined with attributes of the `MavsRandomScene` class. For an (incomplete, I think) list of those attrivutes, see ==[MAVS Python User Guide](https://gitlab.com/cgoodin/mavs-binaries/-/blob/master/docs/MavsPythonUserGuide.pdf?ref_type=heads)====.== ==Chapter 4.==

### Adding a Scene to the environment

```Python
import mavs
env = mavs.MavsEnvironment() # Creates a pointer to a MAVS class
scene = mavs.MavsEmbreeScene() # OR mavs.MavsRandomScene()
env.SetScene(scene.scene)
```

### Other functionality

To generate labeled training data, scene labeling must be turned on. It is turned off by default

- `nameOfSceneObject.TurnOnLabeling()`
- `nameOfSceneObject.TurnOffLabeling()`

  

  

# Actors and Animations

Actors and animations are dynamic moving objects in a simulated environment.

Actors don’t have an ‘animation’ to them. Their physics are controlled externally.

Animations are actually animated. An example may be a walking pedestrian.

> [!important]  
> TO DO: finish summarizing chapter 5(actors and animations). Not prioritized because it will barely be used for RC-Car simulation.  

  

# ==Sensor Simulations==

There are four basic sensor types in MAVS:

- Camera
- Lidar
- RTK
- Radar

If a sensor is mounted to a vehicle, we can provide a coordinate offset from the vehicle’s center of gravity.

```Python
relative_offset = [1.0, 0.0, 0.6]
relative_orientation = [1.0, 0.0, 0.0, 0.0]
sensor.SetOffset(relative_offset, relative_orientation)
#'sensor' is any of the MAVS sensors mentioned above
```

Before updating a sensor and reading its data, its position must be set. Note that the values below represent the position of the vehicle the sensor is mounted to and, if we declared and offset like above, that offset will be applied automatically.

```Python
current_position = [52.0, 17.3, 2.56]
current_orientation = [0.7071, 0.0, 0.0, 0.7071]
sensor.SetPose(current_position, current_orientation)
```

Once the position is set, we can start reading sensor calculations with `.Update()`. This function takes two parameters:

- `env`, which is a `MavsEnvironment()` instance object
- `dt`, which is a float value representing the hz (calculations per second)

### LIDAR

A Lidar object is created as follows:

```Python
import mavs_interface

lidar = mavs_interface.MavsLidar('lidar_model')

# The lidar model argument must be one of the following strings:
# "M8" * "HDL-64E" * "HDL-32E" * "VLP-16" * "OS1" * "OS2" * "LMS-291" * "RS32"
```

Commands for customizing Lidar behavior

```Python
\#---- Set the pose where p is the global position and q the orientation of the base vehicle -----#
lidar.SetPose(p,q)
\#---- Update the sensor, the second argument is the time step ----#
lidar.Update(env,0.1)
\#--- Display a top-down view of the point cloud ----#
lidar.Display()
\#--- Save column text file with x,y,z, intensity, r,g,b
lidar.SaveColorizedPointCloud("cloud.txt")
\#---- Save a rendering of the point cloud ----#
lidar.SaveLidarImage("cloud.bmp")
\#---- Save a labeled version of the point cloud ----#
lidar.SaveLabeledPointCloud(fname)
\#---- Accessing a Python list with world coordinates ----#
points = lidar.GetPoints() # Array with n rows (number of points) and 3 columns
\#---- Sets offset for lidar, arg1 = [x,y,z]. arg2 = [x,y,z,theta]
.SetOffset(arg1, arg2) # example: .SetOffset([0.0, 0.0, 1.830],[1.0,0.0,0.0,0.0])
# x,y,z are all in meters
```