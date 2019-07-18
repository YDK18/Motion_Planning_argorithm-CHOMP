# Install ROS

Follow all the instructions to install ROS. Please make sure you have followed all steps and have the latest versions of packages installed:

> rosdep update
> sudo apt-get update
> sudo apt-get dist-upgrade

Source installation requires wstool, catkin_tools, and optionally clang-format:

> sudo apt-get install python-wstool python-catkin-tools clang-format-3.9

# Create Workspace and Source

Optionally create a new workspace, you can name it whatever:

> mkdir ~/catkin_ws
> cd ~/catkin_ws

Next, source your ROS workspace to load the necessary environment variables, depending on what version of ROS you installed.

> source /opt/ros/kinetic/setup.bash

# Download Source Code

By default, we will assume you are building the latest branch - master. This branch builds for ROS Kinetic and newer, e.g. on Ubuntu 16.04 and newer. If you would like to build an older release of MoveIt from source, see the section below.

Pull down required repositories and build from within the root directory of your catkin workspace:

> wstool init src

> wstool merge -t src https://raw.githubusercontent.com/ros-planning/moveit/master/moveit.rosinstall

> wstool update -t src

> rosdep install -y --from-paths src --ignore-src --rosdistro kinetic

> catkin config --extend /opt/ros/kinetic --cmake-args -DCMAKE_BUILD_TYPE=Release

# Build MoveIt

> catkin build

# Source the Catkin Workspace

> source ~/catkin_ws/devel/setup.bash



