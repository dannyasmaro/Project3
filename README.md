# Poject 3: ROS Library for Roomba

## About

For this project, we create one ROS publisher and one ROS subscriber: publisher for the Range Sensor State, and a subscriber for Left and Right Wheel Control. 



- **Publisher Node:** to publish six sensors’ reading 
- **Subscriber Node:** to drive left and right wheels of the Roomba.

## Required Resources 
 
- A Raspberry Pi 3 board. RP3 can be purchase [Here.](https://www.amazon.com/CanaKit-Raspberry-Complete-Starter-Kit/dp/B01C6Q2GSY/ref=pd_cp_147_1?_encoding=UTF8&psc=1&refRID=VNATY560QJRKQD417K2Q)
- Ubuntu installed on Raspberry Pi 3. Ubunto can be downloaded [Here.](https://ubuntu-mate.org/blog/ubuntu-mate-for-raspberry-pi-3/) 
- ROS Kinetic installed on Raspberry Pi 3. ROS Kinetic can be downloaded [Here.](http://wiki.ros.org/kinetic/Installation/Ubuntu)
- You can find python code for iRobot serial communication library [Here.](https://pypi.python.org/pypi/pycreate2/0.7.3)


## Getting Started

- Do begin the user must download the ROS kinetic package for Ubuntu. [Click hrere to download ROS Kinetic](http://wiki.ros.org/kinetic/Installation/Ubuntu). *Please make sure to install the Desktop Full (Recommended) version.*

*Note: this project is to auto navigate the irobot roomba using ROS in raspberrypi, so after you install ros kinetic follow the instructions below:

- Next the user needs to create a 'work space' and a ' package'. To do so please follow steps (4.1 ,4.2) in the link below:
[ROS Kinetic Publisher and Subscriber In Python](https://www.intorobotics.com/ros-kinetic-publisher-and-subscriber-in-python/).

- Then save the two files found in here inside /your_work_space/src/your_pakage_name/src/

- Go to /your_work_spase directory and type:
```
$rosdep update

$rosdep install --from-paths src -i -y

$catkin_make

$source ./devel/setup.bash

$pip install pycreate2
```
- In a new session/shell type to initiate roscore:
```
$cd /your_work_space
$source ./devel/setup.bash
$export ROS_MASTER_URI=http://[pi_ip_address]:11311
$export ROS_IP=[pi_ip_address]
$roscore
```
- Now in the original session type to run the publishers:
```
$cd /your_work_space/src/your_pakage_name/src/
$chmod u+x 'file_names.py'
$sudo usermod -a -G dialout $USER  #give permission to the USB port to serial
$rosrun 'your_pakage_name' 'file_name.py'
```
- In a new session/shell type to run the subscriber:
```
$cd /your_work_space
$source ./devel/setup.bash
$export ROS_MASTER_URI=http://[pi_ip_address]:11311
$export ROS_IP=[pi_ip_address]
$cd /your_work_space/src/your_pakage_name/src/
$chmod u+x 'file_names.py'
$rosrun 'your_pakage_name' 'file_name.py'
```



