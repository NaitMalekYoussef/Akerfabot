# Akerfabot
A DIY robot that helps collect the trash in the woods. Image recognition will be uses to detect trash and collect it using a robotic arm.

# Description
AkerfaBot is a robot that will help collect trash thrown in the woods and beaches. The idea is to have a robot made from reusable materials, such as, hover board, box, and robotic arm, controlled with a processing unit (an NVIDIA Jetson nano) in order to collect the trash.
The robot will take as an input a stream of images, and will have as an output a command to move toward the trash, collect it using the robotic arm and put it in the box.
The robot will execute the following tasks:

* Identify the trash
* Collect the trash
* Log the position and status if collected successfully or not
The robot might have a system to charge the batteries of the hover board using solar power.

![The robot architecture](idea_.png)
# History:
Sometimes, when I go jogging in the woods, I notice that there is some trash (bottles, paper, glass ...) thrown in the forest. And sometime I wanted to collect all that trash, but why not build a robot that can do that automatically. The idea is to have a robot built mostly from reused materials, such as, hoverboard, plastic or wood box, metal pieces for the robotic arm, web camera. The robot will used image recognition to detect the presence of trash in the woods, then move toward it, collect it using the robotic arm and throw it into the box. So the trash will be collected by the robot while I’m doing my favorite sport.

# Main robots’ tasks:
The robot will execute the following tasks:

Identify the existence of any kind of trash using image recognition (paper, bottles, plastic …)
Move toward the identified object and collect it
Log the position and the status of the task (success or failed)
### Fist task: trash identification:
The robot will use image recognition in order to identify the existence of any king of trash in the woods/beach. A model will be trained upon various images of mostly all kind of trash. The model will be then used to identify the objects in a stream of images coming from a camera attached to the robot. The used camera could be a USB webcam or a Raspberry camera. For the processing unit, a NVIDIA Jetson Nano development board will be used.

### Second task: trash collection:
After identifying the trash location, the robot will move to the position and collect the trash using the robotic arm.

### Third task: logging:
Logging will help us to determine the efficiency of the robot. After any identification of a trash and attempt to collect it, the robot will log the coordinate of the position and the status of the operation, if it succeeded or failed.
This log will be then used to improve the robot algorithm, regarding moving and collecting the trash.

# Challenges:
The process of building this project might raise the following challenges:
First, the robot will use a hover board as mechanism to move and navigate. So first we need to figure out how to control the hoverboard using the NVIDIA Jetson Nano. In fact there are already projects that use Arduino to control the hoverboard, so it won’t be a real problem except some tweaking and configuration. Also, there might be a problem about the wheels, especially when using the robot in the beach. To overcome this problem, another design might be investigated in which we will use a tank wheel.
Second problem that the robot might encounter is regarding the sense of dept. After detecting the trash object, the robot need to know the exact distance and how to collect the object using the arm. To overcome this problem, we might implement an algorithm to processed the distance just from the image, or use other solution that might include a second camera or even a LIDAR.
The third problem is related to the autonomy of the robot. For instance all the component of the robot will run from the hoverboard battery. However, a solar panel might be added in order to charge the battery when needed.

# Built process:
1. Train a model for trash recognition
2. control the hoverboard motors using the NVIDIA Jetson Nano
3. built the robotic arm
4. Assemble everything
5. test and improvement
