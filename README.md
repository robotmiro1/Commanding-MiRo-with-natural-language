# Commanding MiRo with natural language
## Objective of the Project
MiRo starts listening for a key-phrase when the user does a gesture using
the smartwatch. As it hears a key-phrase (e.g., “go close to the red ball and
on the left of yellow box”), it converts speech to text and understands the
key-phrase using CAGG. MiRo then recognizes the object of interest, it’s
colour and the action that MiRo needs to take with respect to that object of
interest.
As MiRo executes an action, a web-interface allows the user to know (i.e.,
get feedback) about whether (1) MiRo understood the command, (2) is
executing the action, and (3) has completed the action or not. While doing
its actions, MiRo localizes itself with respect to QR codes placed on the
static objects of interest.

## Architecture of the System

![alt text](https://github.com/robotmiro1/Commanding-MiRo-with-natural-language/blob/sloth_gesture/images/architecture.png)
It presents the overall architecture of the system with the help of a UML and it describes in simple words the overall architecture, which is designed to meet the objective of the project.

## Description of the System’s Architecture
This section presents in a detailed manner (in its sub-sections) each module within the architecture.
It describes details about the the modules within the architecture, i.e, **(i)** names of the key people who developed the module, **(ii)** mention the files (packages/nodes) found in the repository that are associated to the module, **(iii)** the prerequisites (e.g., all the hardware and software required) for the module, **(iv)** the inputs to the module, **(v)** the internal working of the module, and **(vi)** the outputs of the module.

### Module < Gesture_Processor >
The Module <Gesture_Processor> was developed by Amanzhol Raisov.
The node ‘Gesture processor’ subscribes to the information published by the node ‘IMU sensor’ and the sensor is inside the smartwatch which the user is wearing. This sensor is constantly publishing the IMU data on the topic. And the Gesture Processor node has subscribed to this topic. So, whatever information data has been published by the IMU sensor, it is received by the Gesture Processor. The Gesture processor then processes that information and tries to recognize, if a certain gesture has been performed or not. As soon as the gesture processor recognizes the required gesture, it publishes ‘1’ on the topic ‘ListenFlag’, else it publishes ‘0’. In our case, the required gesture is ‘up’.

## Installation and System Testing

### Module < Gesture_Processor >
![alt text](https://github.com/robotmiro1/Commanding-MiRo-with-natural-language/blob/sloth_gesture/images/Screenshot%20from%202020-02-25%2017-18-31.png)
                             Figure 1: rqt graph for the Gesture Processor

Before starting using Ubuntu 16.04 , make sure, that the Base Memory of the system (see on Virtual Box) has enough space so that in the future the system works correctly without failures.

Smartwatch is connected to the ROS master through the Wi-Fi (EmaroLab-WiFi). Find the IP address of your ROS master that is on the computer using this command:

	$ ifconfig
Now, connect your Smartwatch with the ROS master by inserting the IP address of ROS master, inside the Smartwatch
Install the Python development environment on your system
Check if your Python environment is already configured:

	$ python --version	
	$ pip --version
	$ virtualenv --version
	
On Ubuntu:	

	sudo apt update
	sudo apt install python-dev python-pip
	sudo pip install -U virtualenv  # system-wide install
	
Python virtual environments are used to isolate package installation from the system.
Create a new virtual environment by choosing a Python interpreter and making a ./venv directory to hold it:

	virtualenv --system-site-packages -p python2.7 ./venv

Activate the virtual environment using a shell-specific command:
	
	source ./venv/bin/activate
	
When virtualenv is active, your shell prompt is prefixed with (venv).
Install packages within a virtual environment without affecting the host system setup. Start by upgrading pip:

	pip install --upgrade pip
	
Each tensorflow version works only with specific version of Keras. Install tensorflow 1.10 and keras 2.1.6.
To install tensorflow 1.10 use following command:

	pip install tensorflow==1.10
	
To install Keras 2.1.6. use following command:

	pip install keras==2.1.6
	
Clone the directory from GitHub by using the following command:
	
	cd Downloads/
        git status
        git clone https://github.com/robotmiro1/Commanding-MiRo-with-natural-language.git

Jump to the Module Directory:
	
	cd catkin_ws/src/Gesture_Processor/src/
	
Open a new terminal and run the ROS Master:
	
	roscore
	
Run the Python Node:
	
	python gesture_recogniton.py
	
Visualize Published Messages:
	
	Rostopic echo ListenFlag
	
After building the correspong package, It has been possible to test its results:
	
	
	
### Module < name of the module >
	.
	.
	.
	
## Report

This is the link to the report: [Project Report](https://github.com/robotmiro1/Commanding-MiRo-with-natural-language/blob/sloth_gesture/Report%20-%20Commanding%20MiRo%20with%20natural%20language%20%5BProject%2012b%5D.docx)

## Authors
* Amanzhol Raisov: cornytravel@gmail.com

# Useful GitHub readme syntax

## To make hyper-link

For example, making a link to [ROS tutorials](http://wiki.ros.org/ROS/Tutorials)

## To show, how to execute some commands in the terminal

    ```
    sudo apt install ros-kinetic-opencv3 #(should be already installed with previous point)
    sudo apt install ros-kinetic-opencv-apps
    ```

## To exphasize about a particular command

For example: Please do a ```catkin_make```, once you have modified your code. 

## To add image(s) or video(s)

* To embbed an image

<p align="center"> 
<img src="https://github.com/yushakareem/test-delete/blob/master/light-bulb-2-256.gif">
</p>

Click the source for demostration video. [video](https://youtu.be/3E2BOBpMcWM)

## References

[Concept guide.](https://guides.github.com/features/wikis/)

[Syntax guide.](https://help.github.com/en/articles/basic-writing-and-formatting-syntax)

[Link to the repository that has this readme.](https://github.com/EmaroLab/GitHub_Readme_Template)
