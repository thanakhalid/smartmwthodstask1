# smartmwthodstask1
Task 1: install and ROS on VirtualBox
1-start with installing VirtualBox from the organization website( https://www.virtualbox.org/ )
2-Then  download Ubuntu 18.04 image files from their website because it is recommended for ROS Melodic Morenia then follow these steps:
-click new in VirtualBox window to install the system 
-now go to the settings of the installed ubuntu and adjust them for your preference 
-then follow the steps in http://wiki.ros.org/melodic/Installation to install ros1
1-Configure your Ubuntu repositories
2-Setup your sources.list: sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
3-Set up your keys: sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
4-Installation:
First, make sure your Debian package index is up-to-date: sudo apt update
then, sudo apt install ros-melodic-desktop-full
5-Environment setup: echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
6-Dependencies for building packages:To install this tool and other dependencies for building ROS packages, run:
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. If you have not yet installed rosdep, do so as follows.
sudo apt install python-rosdep
With the following, you can initialize rosdep.
sudo rosdep init
rosdep update
