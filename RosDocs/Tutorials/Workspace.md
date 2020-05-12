# Creating a Workspace
To learn some ROS basics, make a clean workspace.

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

[Creating Packages >>>](/Tutorials/RosPackage.md)
