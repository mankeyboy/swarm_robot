#Swarm_robot
Model : swarm_robot for gazebo using ros
===========================

This model has been built using a mesh created in 3D Solidworks and by using values from the .urdf to create a .sdf file. This uses plugins from ros and the SDF format for its description.

Prerequisites :
---------------
- Install [ros_indigo_desktop_full](http://wiki.ros.org/indigo/Installation/Ubuntu). The ros.org site has ample description for it.

- Even though this model *will* [read as : should, haven't tested] work with the Gazebo 2.2 version that comes bundled with ros-indigo, in light of future modifications, it is highly recommended that Gazebo 6 wrappers be installed as listed below. Take note that as of last checking, the wrappers will only work with x64 machines, there are no sources for 32-bit machines. 

```sh 
# Add the appropriate apt repo (substitute 'trusty' for the right value):
$ sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu trusty main" >  /etc/apt/sources.list.d/gazebo-latest.list'
# Add the osrfoundation.org package repository key
$ wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
# Update your list of packages
$ sudo apt-get update
# Install the Gazebo6 wrappers
$ sudo apt-get install ros-indigo-gazebo6-ros-pkgs
```
Process :
-------------
1. Now, clone this repository into wherever you want, provided that that directory be listed in the $GAZEBO_MODEL_PATH. Personally, I keep it in ~/.gazebo/models ; don't have to edit ~/.bashrc that way.

2. Next step, make sure you have swarm_simulator repository setup in your catkin workspace. You have two options, I prefer the first one though both work:
       * Copy the model.sdf from the cloned directory and replace the swarmRobot.sdf in the sdf folder with this. Rename it to       swarmRobot.sdf
       * Edit the one_swarmRobot.launch to give the absolute address for the model.sdf

3. Run the swarm_simulator as earlier. It should run without any issues. To check all the rostopics being published, run:
```
 rostopic list
```
