# Robot-Arm-Control-Using-ROS
Control a robot arm actuator using Robot Operating System (ROS) platform with Rviz, Gazebo and Moveit Simulator.


1-Install Ubuntu to work with ROS platform. I will use Ubuntu-18.04 .

2-Instal ROS Melodic using the commands bellow in the terminal.
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

sudo apt-get update

sudo apt-get install ros-kinetic-desktop-full

apt-cache search ros-kinetic

echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

sudo apt install python-rosdep

sudo rosdep init

rosdep update

sudo apt-get install ros-noetic-catkin

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/

catkin_make

cd ~/catkin_ws/src

git clone https://github.com/smart-methods/arduino_robot_arm.git

cd ~/catkin_ws

rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-kinetic-moveit

sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

sudo nano ~/.bashrc

at the end of the (bashrc) file add the follwing line
(source /home/lojain/catkin_ws/devel/setup.bash)
then
ctrl + o

source ~/.bashrc

roslaunch robot_arm_pkg check_motors.launch

![Screenshot from 2021-07-16 19-22-43](https://user-images.githubusercontent.com/87448729/126088335-4686cd84-9b14-4253-8ea0-5513d947b21d.png)

3-Control the Arm in Gazebo simulator (real simulation).

cd catkin/src/arduino_robot_arm/robot_arm_pkg/scripts then sudo chmod +x joint_states_to_gazebo.py

roslaunch robot_arm_pkg check_motors.launch

roslaunch robot_arm_pkg check_motors_gazebo.launch

rosrun robot_arm_pkg joint_states_to_gazebo.py

![Screenshot from 2021-07-16 19-42-26](https://user-images.githubusercontent.com/87448729/126088742-2b8c8a3c-04e8-4feb-b454-3d60e859f2ab.png)

Task is Done .
