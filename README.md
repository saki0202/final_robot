# final_robot
## Title:clarn robot     1100452 仙洞田 咲(SAKI SENDODA)

### Project Goals:
・The goal of this project is to design and build a robot that can automatically clean specific rooms or areas. The robot will efficiently clean while avoiding obstacles.

・A larger goal was to create a robot that could autonomously identify its position in the room and recognize the room's layout, as well as detect locations of dirt. However, due to time constraints, this could not be achieved.

・We aimed to use an existing Gazebo simulation from GitHub and replace the robot within it with one designed using Fusion360 to create an autonomous detection robot.

### System Design:
Provide system diagrams and detailed module descriptions, including the mechanical design of the cleaning robot, sensor layout, ROS package structure, and software flowcharts.

Using Fusion360, we designed the model of the cleaning robot as taught in class.


### Testing Results:
Testing results show that despite our efforts to connect the robot with Gazebo until the last moment, we ultimately could not complete it in time.


### Challenges and Solutions:

We used a Gazebo simulation environment found on the internet.
Converting an existing Gazebo simulation environment to work with our self-made robot was very challenging and time-consuming.

# Installation
Download this ROS package.
```
   cd ~/catkin_ws/src
   git clone https://github.com/rt-net/raspimouse_sim.git

```
I used the Gazebo simulation environment provided by RT Corporation's GitHub repository Raspberry Pi Mouse Simulation Environment as a reference for my project. 

Download the dependent ROS packages.
```
cd ~/catkin_ws/src
git clone https://github.com/ryuichiueda/raspimouse_ros_2.git
git clone https://github.com/rt-net/raspimouse_description.git
rosdep install -r -y -i --from-paths raspimouse*
```


## fusion360

Using Fusion360, we created a robot modeled as a cleaning robot.
![](messageImage_1719213936142.jpg)

## moving with URG
```
roslaunch myrobot_1100452_description gazebo.launch
```
![](./messageImage_1719205852679.jpg)

## SLAM
```
# 1st terminal
roslaunch raspimouse_gazebo raspimouse_with_willowgarage.launch
```
![](messageImage_1719215211154.jpg)

```
# 2nd terminal
roslaunch raspimouse_ros_examples slam_gmapping.launch
```
![](messageImage_1719217825656.jpg)

```
# 3rd terminal
roslaunch raspimouse_ros_examples teleop.launch key:=true mouse:=false
```
![](messageImage_1719221678069.jpg)


