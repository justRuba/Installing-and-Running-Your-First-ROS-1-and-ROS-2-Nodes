# Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes
This project is a beginner's guide to getting started with ROS 1 and ROS 2. It provides instructions on how to set up the development environment, install ROS 1 (Noetic) and ROS 2 (Foxy), and run your first nodes using the Turtlesim package. Additionally, it covers using ros1_bridge to facilitate communication between ROS 1 and ROS 2.

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

To check if ROS 1 Noetic installed correctly

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
