nodes = A node in ROS 2 is like a small program that does one specific job in a robot.
       -example = one node might control the wheels, another might read the camera, and another might detect obstacles.
        A node is a single task-running unit in ROS 2 

        for run my example open terminal 1 = python3 publisher_member_function.py
                                terminal 2 = python3 subscriber_member_function.py

topic = A topic in ROS can be explained like a channel or a message that allows different parts of a system to communicate with each other

service = A service in ROS is a way to enable two-way communication between nodes, where one node can send a request to another node, and the second node sends a response back to the first node.

parameter = In ROS, a parameter is a way to store and manage configuration data for nodes. It allows nodes to retrieve and set values that control their behavior at runtime, such as settings, thresholds, or operational modes.

          -example = Motor Speed Control: A robot may have a parameter called motor_speed to control how fast it moves. By changing this parameter, you can control the robot's speed without modifying the code.

action = An action is like a long task that a robot or system does,like navigation
        It takes time to finish (like moving to a destination).
        The system gives updates about how far it’s gone or how close it is to finishing.
        You can stop the task if you change your mind.

        there are 3 main component of it 
               Goal: The input for the task (what needs to be done).
               Feedback: The status or progress of the task.
               Result: The final output after the task is done.

               the example i used is python3 food_delivery_server.py
                                     python3 food_delivery_client.py

record and play turtle bot =
terminal 1 =ros2 run turtlesim turtlesim_node 
terminal 2 = ros2 run turtlesim turtlesim_node 
terminal 3 =ros2 topic list                 //select any one topic --- /turtle1/cmd_vel
terminal 4 = cd ros2_beg = ros2 bag record /turtle1/cmd_vel
after that go to terminal 2 and record
terminal = 5 ros2 bag info rosbag2_2025_04_24-23_59_50

 ros2 bag play rosbag2_2025_04_24-23_59_50
 for see record
             
