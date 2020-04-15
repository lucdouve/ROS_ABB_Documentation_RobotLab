# Creating a Workspace environment in ROS
In the Robotlab we have a few different setups. One of those is the 2 ABB IRB 2600’s on an 10 meter long IRBT 2005 track. We will be setting this environment up in a ROS package. This tutorial should both work for ROS Kinetic and Melodic

To start off create a clean workspace with the following commands.

> mkdir -p ~/catkin_ws/src
>  cd ~/catkin_ws/
>  catkin_make

If you are installing Melodic or use Python 3 in general than the first catkin_make command in a clean catkin workspace must be:
> catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3

After building (using catkin_make) your workspace, you must always use the source command.
> source devel/setup.bash

You can also setup your terminal to trigger this command, when you open the terminal window. This way, you don’t have to enter the source command every time when you’re want to work with this workspace. To automatically execute this command, edit the bashrc file:
> gedit ~/.bashrc

Add: *source ~/catkin_ws/devel/setup.bash*  to the end of the file.

To create a new package cd to your src folder and use the following command. Give your package a name. you can leave the dependencies alone for now.
> catkin_create_pkg <package_name> [depend1] [depend2] [depend3]

**NOTE:** Since we will be using ABB robot, we need to download a few files from git. While in your src folder use the following commands.

> git clone [https://github.com/ros-industrial/abb_experimental.git](https://github.com/ros-industrial/abb_experimental.git)

> git clone [https://github.com/ros-industrial/abb.git](https://github.com/ros-industrial/abb.git)

> git clone https://github.com/ros-industrial/industrial_core.git

Afterwards you want to navigate to the root folder of your workspace and build your workspace again.

> catkin_make

