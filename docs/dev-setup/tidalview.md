---
title: TidalView Setup Guide
author: Ishaan Sayal
---
Whilst TidalView only requires Flutter in order to build and write code, it will be very hard to test your changes against TidalCore data without having TidalCore installed. Therefore, it is **highly** recommended to have TidalCore installed and configured with the prior instructions. 

While these steps are designed to be mostly OS agnostic and Flutter supports all the major OS and distributions, you may have to adjust the instructions for the specific OS and configuration you are using.

## Step 1: Installing Flutter

To install Flutter, follow the documentation on [their website](http://docs.flutter.dev/install/quick). We recommend installing VSCode and using the VSCode extension. 

## Step 2: Install Android Studio

To install Android Studio, it is recommended to use Jetbrains Toolbox, which can be installed on any platform. Once installed, you can download and install Android Studio using the app, and set it up. 
extension
Once installed, open `Settings` -> `Plugins` -> `Marketplace`, and install the Flutter plugin, and restart your IDE. 

## Step 3: Cloning TidalView

In your terminal, clone TidalView into a directory of your choice:
```bash title="bash"
git clone https://github.com/Stevens-Electric-Boatworks/waterboard
cd waterboard
```

Then, download all the required dependencies:
```bash title="bash"
flutter pub get
```

At this point, you should be able to build the application for your platform:
```bash title="bash"
flutter build [PLATFORM=windows,linux,macos,web]
```

!!! example
	```bash title="bash"
	flutter build windows
	```

You can now open the project directory in Android Studio, and you should be build and test for the different platforms. 

## Step 4: ROSBridge Setup

!!! note
	You need to follow the TidalCore prerequisite quite and installation guide in order to use ROSBridge.

While optional, this step is highly recommended so you can test your code with data from TidalCore/ROS2. To install ROSBridge, enter your sourced environment (whether this be via a container, WSL2, etc.), and run:
```bash title="bash"
sudo apt-get install -y ros-kilted-rosbridge-server
```

Then, to pick up the new package, run:
```bash title="bash"
source /opt/ros/kilted/setup.bash
```

Then, enter the TidalCore ROS2 environment by running:
```bash title="bash"
cd ~/eboat_src/ros_ws/ && source install/setup.bash
```
or, if you set it up following the optional instructions:

```bash title="Terminal"
ros
```

You will now be able to run ROSBridge by running the command:
```bash title="bash"
ros2 launch rosbridge_server rosbridge_websocket_launch.xml
```

!!! tip
	The ROSBridge command is quite tedious to type out. Therefore, it is recommended to add an alias for this command. You can do this by adding the following line to the bottom of your `~/.bashrc` file
	```bash title="~/.bashrc"
	alias rosbridge="ros2 launch rosbridge_server rosbridge_websocket_launch.xml"
	```


In TidalView settings, you can now set the IP to `locahost` and the port to `8080`, and it should automatically connect to ROSBridge.