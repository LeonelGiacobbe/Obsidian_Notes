---
Status: Not started
Nav2: false
---
## Running SLAM in the Turtlebot

To run the SLAM feature of the [[Turtlebot3]]:

- run `ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True`
- This makes a map based on the data that was scanned by the [[Turtlebot3]]'s LIDAR.
- To save a map: `ros2 run nav2_map_server map_saver_cli -f path/mapName`, where path is the path to the directory where we want to save, and `mapName` is the name of the map.

## The SLAM map

When generating a map, two files get created:

- The `.pgm` file is an image of the map
    - White is free space
    - Black is obstacle
    - grey is unknown.
- The `yaml` file contains:
    - Resolution: meters per pixel
    - Origin: coordinates of lowest left point in the map.
    - `occupied_thresh`: a value that determines how certain the program must be to mark a pixel as occupied. Example: if `ocuppied_thresh = 0.7`, then the program must be 70% sure the pixel is occupied to mark it as occupied.
    - `free_thresh`: same thing as `occupied_thresh` but for free space

### Parameters to fine tune the performance of slam

  
Note: These parameters are found in  
`turtlebot3_slam/config/gmapping_params.yaml`.

- `maxUrange`: sets the maximum usable range for the lidar sensor
- `map_update_interval`": how often the map gets updated. Smaller number -> more frequent, but also more resource expensive.
- `minimumScore`: number value that determines whether the mapping was successful or not.
- `linearUpdate`: runs scan process when robot travels a longer distance than this value
- `angularUpdate`: runs scan process when robot rotates more than this value.