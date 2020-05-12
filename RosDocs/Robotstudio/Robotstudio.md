# Robotstudio
RobotStudio is a program in which you can simulate all ABB-robots and products. A great advantage of simulation is that if a change has to be made or if a new application is developed, the production can always continue.
Simulation has its advantages and disadvantages. As mentioned earlier, simulation can ensure that production in, for example, a factory does not have to be stopped. Other advantages are that the risk of erroneous movements can be tested first, and the implementation time of the application can be shortened, because testcases have already been performed in the simulation. A disadvantage of simulation in RobotStudio is that you can only simulate efficiently if the station in RobotStudio exactly matches the application / station of reality. If this is not the case, it is possible that during the implementation things will come up that are not desirable, such as unexpected movements.

### Installation of RobotStudio
Go to: https://new.abb.com/products/robotics/robotstudio/downloads

Download RobotStudion under the subheader ‘RobotStudio’ > ‘Download RobotStudio’.
Be sure to put in the license of RobotStudio after the installation has finished. 

### Station of the real controller in RS
RobotStudio (RS) uses exactly the same software as that of what runs on the real controller of the robots. This makes it possible to get the workstation of the actual situation in RS via a backup.

### Making a backup of the real controller
##### Backup Requirements
To backup the real controller, the following requirements must be met:

- Be on the same network as the controller (robot).
- Access to the flex pendant.
- RobotStudio installed.

Als aan deze voorwaardes voldaan is, kan je beginnen met het maken van een backup van het robot station, om deze uiteindelijk ook te kunnen importeren in RobotStudio. Om te beginnen, ga in Robotstudio naar ‘File’ > ‘New’ > ‘Empty Station’ > en klik ‘Create’. Dit creeert een nieuw leeg station wat ons de mogelijkheid bied om met de echte controller te verbinden over het internet. 

![Robotstudio](../images/robotstudio1.png)
![Robotstudio](../images/robotstudio2.png)

Om verbinding te maken met de echte controller. Ga naar tabblad ‘Controller’ > ‘Add Controller’ (Dropdown menu) > en klik ‘Add Controller... - Add available controller on the network.’ 
A popup window will apear. Select the contoller you want to add and press ‘OK’. Now you can see the controller in the controller list. To make a backup of the controller

![Robotstudio](../images/robotstudio3.png)

Now we will install ROS on our controller

[Robotstudio with ROS >>>](/Robotstudio/RobotstudioRos.md)