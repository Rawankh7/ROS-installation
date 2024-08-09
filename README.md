# ROS-installation
TASK 1 in AI field
Step one is to install a virtual machine ( I installed VirtualBox in this case )
then we download a apprpiate version of ubuntu ( 20.04 ) 
using Termenal in Ubuntu we run the needed commands to install ROS1 
# Update package list
sudo apt update

# Install required dependencies
sudo apt install curl gnupg lsb-release -y

# Add the ROS repository to the sources list
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu focal main" > /etc/apt/sources.list.d/ros-latest.list'

# Import the ROS repository key
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

# Update package list again to include the new ROS packages
sudo apt update

# Install ROS 1 Noetic desktop full version
sudo apt install ros-noetic-desktop-full -y

# Initialize rosdep
sudo rosdep init
rosdep update

# Set up the ROS environment in the bash profile
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc



# Verify the installation by starting the ROS master node
roscore
