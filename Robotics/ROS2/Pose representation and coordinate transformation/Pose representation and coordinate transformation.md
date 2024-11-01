---
Status: Not started
Nav2: false
---
> [!important]  
> Useful Resources:tf2_ros  

  

## Reference frames

There are 3 main reference frames within a simulation:

- Map frame: rigid, never changes
- Base frame: could be considered as the axis of the chassis of the robot. May not be aligned with map reference **(REALLY IMPORTANT TO TAKE THIS INTO ACCOUNT)**
- LIDAR frame: frame of reference of the sensor’s laser. Frame that will be used the most

  

Odometry: not exactly a reference frame itself; it represents relationship between different frames

Graphic example:

![[Screenshot_from_2024-02-09_08-58-55.png]]

  

## Transforming references from one frame to another