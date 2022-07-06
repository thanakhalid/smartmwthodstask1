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
----------------------
# smartmethodstask2

task2:download ROS2 in jetson nano:
1-install ubuntu,preferablly custom one for jetson nano
2-then we need a way to flash the image into our sd card,for example balena etcher 
3-now we need to extract the zip file we downloaded , the command to extract the Ubuntu image: tar -xvjf Xubuntu-20.04-l4t-r32.3.1.tar.tbz2
4-now to flash the image, select the image in etcher, select target for example micro SD then click flash
5-go to the SD card that you flashed then go to boot then extlinux.conf, add the following in the file in label: FDT /boot/tegra210-p3448-0000-p3449-0000-b00.dtb
notes: 
To find out which .dtb file is compatible with your Nano run the following on the Nano (e.g. with official Nvidia image): cat /sys/firmware/devicetree/base/compatible
This command could also work instead: fdtget /boot/dtb/*.dtb / compatible
If you have the Jetson Nano B01, you have to add the following line in the extlinux.conf: FDT /boot/tegra210-p3448-0000-p3449-0000-b00.dtb
6-eject the SD file,put the sd card in the jetson nano 
7- you will be bot into ubunto
8-the just install ROS into the ubuntu like the documation in this link:http://docs.ros.org/en/rolling/Installation/Alternatives/Ubuntu-Development-Setup.html

