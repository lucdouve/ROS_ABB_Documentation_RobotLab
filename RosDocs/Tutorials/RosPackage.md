# Creating a catkin package
### What makes up a catkin Package?
For a package to be considered a catkin package it must meet a few requirements:
- The package must contain a catkin compliant package.xml file.
  - That package.xml file provides meta information about the package.
- The package must contain a CMakeLists.txt which uses catkin.
  - If it is a catkin metapackage it must have the relevant boilerplate CMakeLists.txt file.
- Each package must have its own folder
  - This means no nested packages nor multiple packages sharing the same directory.

The simplest possible package might have a structure which looks like this:

> my_package/
>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CMakeLists.txt
>
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;package.xml

### Creating a catkin Package

First change to the source space directory of the catkin workspace you created in the Creating a Workspace for catkin tutorial:
> You should have created this in the Creating a Workspace Tutorial
>
> $ cd ~/catkin_ws/src

Now use the catkin_create_pkg script to create a new package called 'beginner_tutorials' which depends on std_msgs, roscpp, and rospy:
> $ catkin_create_pkg beginner_tutorials std_msgs rospy roscpp

This will create a beginner_tutorials folder which contains a package.xml and a CMakeLists.txt, which have been partially filled out with the information you gave catkin_create_pkg.

catkin_create_pkg requires that you give it a package_name and optionally a list of dependencies on which that package depends:
> This is an example, do not try to run this
>
> catkin_create_pkg <package_name> [depend1] [depend2] [depend3]

### Building a catkin workspace and sourcing the setup file
Now you need to build the packages in the catkin workspace:
> $ cd ~/catkin_ws
>
> $ catkin_make

After the workspace has been built it has created a similar structure in the devel subfolder as you usually find under /opt/ros/$ROSDISTRO_NAME.

To add the workspace to your ROS environment you need to source the generated setup file:
> $ . ~/catkin_ws/devel/setup.bash

### package dependencies
When using catkin_create_pkg earlier, a few package dependencies were provided. These first-order dependencies can now be reviewed with the rospack tool.
> $ rospack depends1 beginner_tutorials 

> roscpp
>
> rospy
>
> std_msgs

As you can see, rospack lists the same dependencies that were used as arguments when running catkin_create_pkg. These dependencies for a package are stored in the package.xml file.

[<<< Creating a workspace](/Tutorials/Workspace.md) || [Understanding ROS Nodes >>>](/Tutorials/RosNodes.md)
