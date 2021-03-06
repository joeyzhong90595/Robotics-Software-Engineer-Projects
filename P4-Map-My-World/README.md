# Map My World

[![](https://s3-us-west-1.amazonaws.com/udacity-robotics/Extra+Images/RoboND_flag.png)](http://www.udacity.com/robotics)

## Result Demonstration 

### Video demonstration

 [![Video demonstration](./demonstration/P4.gif)](https://youtu.be/0-CT9uMzt8s)

## Overview - SLAM

This project created a 2D occupancy grid and 3D octomap from the apartment environment using the built robot with the [RTAB-Map](http://wiki.ros.org/rtabmap_ros) package. The robot had to move a few rounds around the environment in order to properly portray the environment. After creating the map, a `db` file was saved in the launch folder originally and was moved to the maps folder for future use.

**3D view of the map**

![3D](./demonstration/3d_view.png)

**Occupancy Grid**

![grid](./demonstration/occupancy_grid.png)

**Features**

![features](./demonstration/features.png)

## Run Instruction

If one does not have RTAB-Map package installed

```
$ sudo apt-get install ros-melodic-rtabmap-ros
```

To build the scripts

```
$ cd home/catkin_ws
$ catkin_make
```

Launch the world, the robot and the slam module in gazebo

```
$ roslaunch slam_robot world.launch
$ roslaunch slam_robot teleop.launch
$ roslaunch slam_robot mapping.launch
```

## Directory Structure

```
P4-Map-My-World                    # Map My World Project
├── slam_robot                     # slam_robot package                   
│   ├── launch                     # launch folder for launch files   
│   │   ├── robot_description.launch
│   │   ├── world.launch
│   │   ├── teleop.launch
│   │   ├── mapping.launch
│   │   ├── mapping_with_visualization.launch
│   │   ├── localization.launch
│   ├── meshes                     # meshes folder for sensors
│   │   ├── hokuyo.dae
│   ├── urdf                       # urdf folder for xarco files
│   │   ├── my_robot.gazebo
│   │   ├── my_robot.xacro
|   |   ├── materials.xacro
│   ├── worlds                     # world folder for world files
│   │   ├── apartment.world
│   │   ├── apartment.rviz
│   ├── maps                       # maps created after salm
│   │   ├── apartment.db
│   ├── CMakeLists.txt             # compiler instructions
│   ├── package.xml                # package info 
├── demonstration                  # Demonstrate file for README 
│   ├── p4.gif
│   ├── 3d_view.png
│   ├── features.png
│   ├── occupancy_grid.png
└── README.md                      # Readme file                                          
```