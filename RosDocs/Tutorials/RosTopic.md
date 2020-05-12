# Understanding ROS Topics
### Setup 
Let's start by making sure that we have roscore running, in a new terminal:
> $ roscore

If you left roscore running from the last tutorial, you may get the error message:
> roscore cannot run as another roscore/master is already running. 
> Please kill other roscore/master processes before relaunching

This is fine. Only one roscore needs to be running.

#### Turtlesim
For this tutorial we will also use turtlesim. Please run in a new terminal:
> $ rosrun turtlesim turtlesim_node

We'll also need something to drive the turtle around with. Please run in a new terminal:
> $ rosrun turtlesim turtle_teleop_key

Now you can use the arrow keys of the keyboard to drive the turtle around. If you can not drive the turtle select the terminal window of the turtle_teleop_key to make sure that the keys that you type are recorded. Now that you can drive your turtle around, let's look at what's going on behind the scenes.

### ROS Topics
The turtlesim_node and the turtle_teleop_key node are communicating with each other over a ROS Topic. turtle_teleop_key is publishing the key strokes on a topic, while turtlesim subscribes to the same topic to receive the key strokes. Let's use rqt_graph which shows the nodes and topics currently running.

Note: If you're using electric or earlier, rqt is not available. Use rxgraph instead.

#### Using rqt_graph
rqt_graph creates a dynamic graph of what's going on in the system. rqt_graph is part of the rqt package. Unless you already have it installed, run:
> $ sudo apt-get install ros-<distro>-rqt
>
> $ sudo apt-get install ros-<distro>-rqt-common-plugins

replacing <distro> with the name of your ROS distribution (e.g. indigo, jade, kinetic, lunar ...)

In a new terminal:
> $ rosrun rqt_graph rqt_graph

You'll now get a screen with different topics that are connected to each other.

#### Introducing rostopic
The rostopic tool allows you to get information about ROS topics.

You can use the help option to get the available sub-commands for rostopic
> $ rostopic -h

[<<< Understanding ROS Nodes](/Tutorials/RosNodes.md) || [Understanding ROS Services >>>](/Tutorials/RosServices.md)
