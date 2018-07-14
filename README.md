## sawyer_robot
*******************************
##### Installation dependence
```bash
sudo apt-get install ros-kinetic-ros-control ros-kinetic-control-toolbox ros-kinetic-realtime-tools ros-kinetic-ros-controllers 
```

*******************************
##### Workstation_Setup
```bash
mkdir -p ~/sawyer_ws/src
cd ~/sawyer_ws/src
git clone https://github.com/GJXS1980/sawyer_robot.git
cd ~/sawyer_ws
catkin_make
echo "source ~/sawyer_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

*******************************
##### environmental_Setup
```bash
cp ~/sawyer_ws/src/sawyer_robot/intera_sdk/intera.sh ~/sawyer_ws
cd ~/sawyer_ws
gedit intera.sh
```
The revised content is as follows:
```bash
# Specify Robot's hostname
robot_hostname="robot_hostname.local"

#your_ip="192.168.XXX.XXX"
your_hostname="my_computer.local"

# Specify ROS distribution (e.g. indigo, hydro, etc.)
ros_version="kinetic"
```

*******************************
##### Initialize SDK environment
```bash
cd ~/sawyer_ws
./intera.sh
#get rostopic list from robot
rostopic list
```

*******************************
##### Test sawyer_simulator
1. Start Joint Torque Springs example:
```bash
cd ~/sawyer_ws
./intera.sh sim
roslaunch sawyer_gazebo sawyer_world.launch
#*in a new terminal*
cd ~/sawyer_ws
./intera.sh sim
rosrun intera_examples joint_torque_springs.py
```
2. Start Simulated Pick and Place example:
```bash
cd ~/sawyer_ws
./intera.sh sim
roslaunch sawyer_sim_examples sawyer_pick_and_place_demo.launch
```

****************************************
>Reference
>
>[Workstation_Setup](http://sdk.rethinkrobotics.com/intera/Workstation_Setup)
>
>[RethinkRobotics](https://github.com/RethinkRobotics)
>
>[Gazebo_Tutorial](http://sdk.rethinkrobotics.com/intera/Gazebo_Tutorial)

****************************************







