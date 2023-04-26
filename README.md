# ROS
This repository contains two Python scripts: talker.py and listener.py that implement a simple example of a talker and listener using the ROS (Robot Operating System) framework.
Requirements

    ROS
    Python

Usage

    Start the ROS Master: roscore
    In a new terminal window, run the talker.py script: rosrun <package_name> talker.py
    In another terminal window, run the listener.py script: rosrun <package_name> listener.py
    The listener.py script will print the messages sent by the talker.py script.

Talker.py

This script creates a ROS node called talker that publishes a message to the chatter topic every two seconds until it receives a keyboard interrupt (i.e., Ctrl-C).

The talker() function initializes the chatter publisher, which publishes messages of type std_msgs.msg.String to the chatter topic with a queue size of 10. The function also initializes the talker node with the anonymous=True flag, which ensures that the node has a unique name.

The loop in the talker() function generates a message (in this case, "hello world" followed by a number) and publishes it to the chatter topic using the publish() method of the chatter publisher. The loop also sleeps for two seconds between each message.
Listener.py

This script creates a ROS node called listener that subscribes to the chatter topic and prints any messages received on that topic to the console.

The listener() function initializes the listener node with the anonymous=True flag, which ensures that the node has a unique name. It also initializes a subscriber to the chatter topic that calls the chatter_callback() function whenever a new message is received.

The chatter_callback() function simply logs the received message to the console along with the ID of the node that called the function.

The spin() method of the rospy module is called at the end of the listener() function to ensure that the node continues to listen for messages until it is stopped.
