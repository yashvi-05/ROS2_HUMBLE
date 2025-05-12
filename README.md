ROS 2 Concepts Overview
Nodes

A node in ROS 2 is like a small program that performs one specific task in a robot.

    Example:

        One node might control the wheels

        Another node might read data from the camera

        Another might detect obstacles

A node is the basic execution unit in ROS 2.

How to run an example:

    Terminal 1: python3 publisher_member_function.py

    Terminal 2: python3 subscriber_member_function.py

Topics

A topic in ROS 2 acts like a communication channel that nodes use to send and receive messages.
It allows one-way communication from publishers to subscribers.
Services

A service enables two-way communication between nodes. One node sends a request, and another node sends a response.

    Think of it like a client-server interaction where a client asks a question, and the server gives an answer.

Parameters

Parameters in ROS 2 are used to store and manage configuration data for nodes.
They can be updated at runtime without modifying the code.

    Example:
    A robot might have a parameter called motor_speed to control how fast it moves.
    You can change this parameter at runtime to adjust the robot’s speed.

Command to run a parameter example:

    python3 car.py

Actions

Actions are used for long-running tasks that provide feedback during execution.

    Example: Moving a robot to a destination (navigation task)

There are 3 main components of an action:

    Goal – What needs to be done

    Feedback – Status updates about progress

    Result – The final outcome

Example command:

    Server: python3 food_delivery_server.py

    Client: python3 food_delivery_client.py

ros2 bag (Record & Play) – TurtleBot Example

    Terminal 1: ros2 run turtlesim turtlesim_node

    Terminal 2: ros2 run turtlesim turtle_teleop_key

    Terminal 3: ros2 topic list

        Choose a topic to record, for example: /turtle1/cmd_vel

    Terminal 4:

cd ros2_beg  
ros2 bag record /turtle1/cmd_vel

Use teleop in terminal 2 to control and generate motion data

Terminal 5:

    ros2 bag info rosbag2_2025_04_24-23_59_50  
    ros2 bag play rosbag2_2025_04_24-23_59_50

        To replay the recorded data

Plugins

Plugins in ROS 2 can be used to extend functionality such as greeting in different languages or custom display tools in RViz.
Intermediate Concepts
Launch Files

Instead of launching each node individually, launch files allow you to start multiple nodes at once.

    Useful for managing complex systems like a publisher, subscriber, and parameter server together.

TF2 (Transform Library)

TF2 handles coordinate transforms in ROS 2.
It allows you to track the positions of different parts of the robot relative to one another.

There are two types:

    Static Transform – Fixed over time (e.g., base to camera)

    Dynamic Transform – Changes over time (e.g., robot moving)

    Visualized using RViz

URDF (Unified Robot Description Format)

URDF is an XML format to describe a robot’s structure, appearance, and physical properties.
Subtasks in URDF Tutorial

    Building a Visual Robot Model

        Define shape, size, and color using XML

    Making the Robot Movable

        Add joints and links to allow motion

    Adding Physical & Collision Properties

        Include mass, inertia, and collision elements for simulation

    Using Xacro to Clean Up Code

        Use macros and parameters to simplify URDF files

    Using URDF in Gazebo

        Load robot into the Gazebo simulator to test behavior

    Using URDF with robot_state_publisher (Python)

        Publish joint states for visualization and monitoring

Example Application:

If you want to simulate a 4-wheel robot without hardware:

    Use URDF to create a robot model with a rectangular chassis and 4 wheels

    Define dimensions, shapes, joint movements, center of mass, and colors

    Visualize the robot in RViz

    Simulate movement and physics in Gazebo

    Use a Python publisher node to send commands and control the robot

RViz (ROS Visualization Tool)

RViz is a tool for visualizing ROS data and robot models.
Subtasks in RViz

    Customize Display

        Add custom objects, adjust colors and views

    Customize Panels

        Add interactive tools like sliders (e.g., control motor speed)

    Markers

        Use shapes (Arrow, Cube, Sphere, Cylinder, etc.) to represent custom objects or robot data in 3D space
