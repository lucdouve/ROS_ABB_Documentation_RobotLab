# Understanding ROS Services
### ROS Services 
Services are another way that nodes can communicate with each other. Services allow nodes to send a request and receive a response.

### Using rosservice
rosservice can easily attach to ROS's client/service framework with services. rosservice has many commands that can be used on services, as shown below:

Usage:
> rosservice list         print information about active services
>
> rosservice call         call the service with the provided args
>
> rosservice type         print service type
>
> rosservice find         find services by service type
>
> rosservice uri          print service ROSRPC uri

#### rosservice list
> $ rosservice list

The list command shows us that the turtlesim node provides nine services: reset, clear, spawn, kill, turtle1/set_pen, /turtle1/teleport_absolute, /turtle1/teleport_relative, turtlesim/get_loggers, and turtlesim/set_logger_level. There are also two services related to the separate rosout node: /rosout/get_loggers and /rosout/set_logger_level.

#### rosservice type
Usage:
> rosservice type [service]

Let's find out what type the clear service is:
> $ rosservice type /clear

This service is empty, this means when the service call is made it takes no arguments (i.e. it sends no data when making a request and receives no data when receiving a response). Let's call this service using rosservice call:
#### rosservice call
Usage:
> rosservice call [service] [args]

Here we'll call with no arguments because the service is of type empty:
> $ rosservice call /clear

This does what we expect, it clears the background of the turtlesim_node.

Let's look at the case where the service has arguments by looking at the information for the service spawn:
> $ rosservice type /spawn | rossrv show

> float32 x
>
> float32 y
>
> float32 theta
>
> string name
>
> ---
> string name

This service lets us spawn a new turtle at a given location and orientation. The name field is optional, so let's not give our new turtle a name and let turtlesim create one for us.
> $ rosservice call /spawn 2 2 0.2 ""

The service call returns with the name of the newly created turtle.
The turtlesim should now have an extra turtle.



[<<< Understanding ROS Topics](/Tutorials/RosTopic.md) ||
