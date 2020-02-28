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

	.
	.
	
### Module < name of the module >
	.
	.
	.
	
## Installation and System Testing
![alt text](https://github.com/robotmiro1/Commanding-MiRo-with-natural-language/blob/sloth_gesture/images/Screenshot%20from%202020-02-25%2017-18-31.png)
This section presents (in its sub-sections) how to install/run and test the modules. **Note that:** If all the modules have successfully completed their work and integrated everything together, then this section can present the overall **Installation and Testing** procedure for the the "whole" system, instead of having a sub-section dedicated for each module. 

Please keep in mind, **do not** include in your repository the “entire” code of the external libraries that your module may use. Hence accordingly, **describe** to the new users how they can “install” the external libraries and then **describe** how they can “install” your module that uses those libraries. Afterwhich, **describe** how to run and test your module. Finally, show **(i)** the rqt_graph generated when the module is running, **(ii)** images or links to the videos showing the working of the module (in real or in simulation).

### Module < name of the module >
	.
	.
	.
	
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
