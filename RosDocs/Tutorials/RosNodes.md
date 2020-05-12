# Understanding ROS Nodes
### Prerequisites
For this tutorial we'll use a lighweight simulator, to install it run the following command:
> $ sudo apt-get install ros-<distro>-ros-tutorials
>
Replace '<distro>' with the name of your ROS distribution (e.g. indigo, jade, kinetic)

### Quick Overview of Graph Concepts
- Nodes: A node is an executable that uses ROS to communicate with other nodes.
- Messages: ROS data type used when subscribing or publishing to a topic.
- Topics: Nodes can publish messages to a topic as well as subscribe to a topic to receive messages.
- Master: Name service for ROS (i.e. helps nodes find each other)
- rosout: ROS equivalent of stdout/stderr
- roscore: Master + rosout + parameter server (parameter server will be introduced later)

### Nodes
A node really isn't much more than an executable file within a ROS package. ROS nodes use a ROS client library to communicate with other nodes. Nodes can publish or subscribe to a Topic. Nodes can also provide or use a Service.

### roscore
roscore is the first thing you should run when using ROS.

Please run:
> $ roscore

You will see something similar to:
> ... logging to ~/.ros/log/9cf88ce4-b14d-11df-8a75-00251148e8cf/roslaunch-machine_name-13039.log
Checking log directory for disk usage. This may take awhile.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.
>
>started roslaunch server http://machine_name:33919/
ros_comm version 1.4.7
>
>SUMMARY
======
>
>PARAMETERS
> * /rosversion
> * /rosdistro
>
>NODES
>
>auto-starting new master
process[master]: started with pid [13054]
ROS_MASTER_URI=http://machine_name:11311/
>
>setting /run_id to 9cf88ce4-b14d-11df-8a75-00251148e8cf
process[rosout-1]: started with pid [13067]
started core service [/rosout]

If roscore does not initialize, you probably have a network configuration issue. See [Network Setup - Single Machine Configuration](https://wiki.ros.org/ROS/NetworkSetup#Single_machine_configuration)

If roscore does not initialize and sends a message about lack of permissions, probably the ~/.ros folder is owned by root, change recursively the ownership of that folder with:
> $ sudo chown -R <your_username> ~/.ros

### Using rosnode
Open up a new terminal, and let's use rosnode to see what running roscore did... Bear in mind to keep the previous terminal open either by opening a new tab or simply minimizing it.

rosnode displays information about the ROS nodes that are currently running. The rosnode list command lists these active nodes:
> $ rosnode list

You will see:
> /rosout

### Using rosrun
rosrun allows you to use the package name to directly run a node within a package (without having to know the package path).

Usage:
> $ rosrun [package_name] [node_name]

So now we can run the turtlesim_node in the turtlesim package.

Then, in a new terminal:
> $ rosrun turtlesim turtlesim_node

You will now see a turtlesim window.

In a new terminal:
> $ rosnode list

You will see something similar to:
> /rosout
/turtlesim

We see our new /turtlesim node. Let's use another rosnode command, ping, to test that it's up:
> $ rosnode ping turtlesim



[<<< Creating Packages](/Tutorials/RosPackage.md) || [Understanding ROS Topics >>>](/Tutorials/RosTopic.md)
