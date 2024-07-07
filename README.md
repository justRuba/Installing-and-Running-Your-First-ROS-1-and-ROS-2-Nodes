# Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes
Guide to getting started with ROS 1 and ROS 2. Provides instructions on how to set up the development environment, install ROS 1 (Noetic) and ROS 2 (Foxy), and run the first nodes using the Turtlesim package.
## **1. Download and Install VirtualBox**
- Set up VirtualBox to create a virtual environment for development.  
[VirtualBox Download](https://www.virtualbox.org/wiki/Downloads)

## **2. Download and Install Ubuntu 20.04 Desktop Image**
- Download the Ubuntu 20.04 desktop image.  
[Ubuntu 20.04 Desktop Image](https://releases.ubuntu.com/20.04/)

- Create a New Virtual Machine in VirtualBox:
  
  Open VirtualBox and click on "New" to create a new virtual machine.
  
  Name your virtual machine (e.g., "Ubuntu 20.04") and choose "Linux" as the type, and "Ubuntu (64-bit)" as the version.

- Allocate Memory and Create Virtual Hard Disk:

  Allocate at least 2GB of RAM to the virtual machine.

  Create a new virtual hard disk (VDI) and allocate sufficient storage space (e.g., 20GB or more).

- Install Ubuntu 20.04:

  Select your newly created virtual machine and click "Start".

  Follow the Ubuntu installation wizard using the Ubuntu 20.04 desktop image you downloaded.

  Choose the "Erase disk and install Ubuntu" option.

  Complete the installation and restart your virtual machine.

- Configure Ubuntu:

  Log in to Ubuntu and perform initial setup (This may include updating packages, configuring network settings, and adjusting display preferences).

That's what your VirtualBox looks like!


  ![Ubuntu 20 4](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/90858fd5-7a1e-44c4-a286-5a8c9f221ba2)


## **3. Install ROS 1 Noetic**

Follow these steps to install ROS 1 (Noetic) on Ubuntu 20.04:

- Step 1: Set up sources.list
 
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

- Step 2: Set up keys

```bash
 sudo apt install curl
```
Also 

```bash
 curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

- Step 3: Installation
  
3.1 Update package index:
  
```bash
sudo apt update
```
3.2 Desktop-Full Install:

```bash
 sudo apt install ros-noetic-desktop-full
```
3.3 To find available packages, use:

```bash
 apt search ros-noetic
```
- Step 4: Environment setup

```bash
 source /opt/ros/noetic/setup.bash
```

- Step 5: Dependencies for building packages

```bash
 sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

5.1 Initialize rosdep

```bash
 sudo apt install python3-rosdep
```
Also

```bash
sudo rosdep init
```
```bash
rosdep update
```

To check if ROS 1 Noetic was installed correctly

![ROS1](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/9e06e2f5-cfe1-4b3f-b60e-38fef480bbe2)

## **4. Install ROS 2 Foxy**

Follow these steps to install ROS 2 (Foxy) on Ubuntu 20.04:

Before starting make sure to have a locale that supports UTF-8

- Step 1: Setup Sources

```bash
apt-cache policy | grep universe 
```

- Step 2: Add the ROS 2 apt repositories to your system

```bash
sudo apt update && sudo apt install curl gnupg2 lsb-release
```
```bash
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg 
```
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

- Step 3: Ensure your system is up to date before installing new packages

```bash
sudo apt update 
```
```bash
sudo apt upgrade
```

- Step 4: ROS2 Desktop Install

```bash
sudo apt install ros-foxy-desktop
```
```bash
sudo apt install ros-foxy-ros-base 
```
```bash
source /opt/ros/foxy/setup.bash   
```
To check if ROS 2 Foxy was installed correctly

![Ros2](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/1d343c78-c71a-486c-bbd8-09309a5a796c)

## **4. Manipulate the Turtlesim Package in ROS Noetic**

Open Four Terminals

- Step 1 :

In one of the four Terminals,

Launching

```bash
roscore  
```
is typically the first step when you want to use ROS, as it sets up the essential infrastructure for communication and coordination between different parts.

- Step 2: Starts the turtlesim simulator window

In another one,

```bash
rosrun turtlesim turtlesim_node  
```

![turtle](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/e3833822-61ed-4158-bf01-8e5eab90067a)

- Step 3: Manipulate

In another one, 

```bash
rosrun turtlesim turtle_teleop_key
```
provides an interactive way to explore how to control robots using keyboard inputs in a simulated environment.

![Manipulate](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/4de03724-cd07-428e-9f82-ab227117683f)

- Step 4: Graphical tool 

In Last one,

```bash
rqt_graph
```
graphical representation of your ROS network.

![graph](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/d1d43c02-9813-49a5-b397-32f0173a0a03)

## **6. Manipulate the Turtlesim Package in ROS 2 Foxy**

 Follow a workflow similar to what I did in ROS 1 but with the added step of ensuring that I am using ROS 2 commands and packages, not ROS 1.

 - Step 1: The First Terminal
   
![ros2-1](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/e23e788d-dd79-4b74-a6c0-73358a3d2569)

- Step 2: The Second Terminal

![Ros2-2](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/fd63b3ec-22cf-4e2b-a1d5-cbf01a0ba59d)

The Result:

![Ros2_3](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/assets/134620937/f1abb4b9-c125-4f28-92e3-ea78509e79ca)
