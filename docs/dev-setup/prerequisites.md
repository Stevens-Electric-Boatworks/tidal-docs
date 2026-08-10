---
title: Developer Environment Prerequisites
author: Ishaan Sayal
---
## TidalCore

!!! tip
	If you are new to Linux, it is recommended to follow the OS guides below, and hold off on installing TidalCore until after you have some familiarity working with Linux. The Linux guide below gives some pointers on what you should be looking to learn.

### OS Guide

TidalCore is built on top of ROS2 (Robot Operating System 2), and therefore will also require Linux (more specifically Ubuntu) in order to run. This guide will help you set up a Linux environment based on which OS you are using. 

The recommended configuration is either using Ubuntu directly, or dual-booting with Windows/Linux. However, it is still very possible to develop against TidalCore using only Windows. 

=== "Windows"

	​Windows features a tool called [WSL2](https://learn.microsoft.com/en-us/windows/wsl/install) (Windows Subsystem for Linux). WSL2 works by creating a container which runs your choice of Linux distribution, with the main benefit being that the distribution is contained, but can still be integerated into the rest of the OS/Developer Tools. 
		
	​	To get started, install the specific version of Ubuntu used by ROS2 Kilted Kaiju. This command must be run in an elevated (admin) powershell terminal:
		
	```powershell title="powershell"
	wsl --install ubuntu-24.04
	```
		
	​	On the first run, this will install WSL2, configure the required Windows features, and prompt for a reboot. 
		
	​	Once rebooted, you should be able to open the **Terminal** application, click on the `+` on the top bar, and click on Ubuntu.
	
	It recommended to take a good look around the Windows terminal app, and change the settings/theme/keybinds to your liking. You will be spending a lot of time in the terminal, so make it comfy for you.

	At this step, you are ready to install TidalCore.
			
=== "Linux"

	​The only two distributions supported by ROS2 is Ubuntu 24.04, and Redhat Enterprise Linux (RHEL) 9. 
	If you are not running either of them, you can optionally use a virtual machine to run Ubuntu (not recommended due to performance loss), or a container. 

	The following guide is for [Toolbx](https://containertoolbx.org/), which is installed by default on Fedora systems. To get started, create a toolbox with the specific ubuntu version:
	```bash title="bash"
	toolbox create --distro ubuntu --release 24.04 ros
	```
	This will create a container with a name of "ros". You can then enter the container by running:
	```bash title="bash"
	toolbox enter ros
	```
	Once you are in the container, you should be able to run Ubuntu commands without error, for example:
	```bash title="bash"
	apt list
	```
	The container itself is designed to seemleslly integrate with the host OS, and will have access to most of the host OS components (read toolbox documentation for more detail). Remember to rerun `toolbox enter ros` in every new terminal window you open, or else you will not be able to use Ubuntu commands.

	At this step, you are ready to install TidalCore. 
	

=== "Ubuntu"
	You need to ensure that you are running Ubuntu 24.04, but other than that, you should be good to go. 


### Linux Fundamentals

You are expected to be able to use Linux at a working level, which means navigating the filesystems, installing packages, running programs, using `sudo` when appropriate, and more. While it is out of the scope of this guide to give a tutorial on how to use Linux, there are many great guides and videos which can teach you the fundamentals. 

In general however, you should be familiar with the following:

* Using package managers to install and manage packages/system libraries
* Navigating the filesystem and understanding the purpose of the overall filesystem structure (such as `/usr/`, `/home/`, etc.)
* Move/copy files
* Editing files using a **terminal-based** file editor (such as vim, nano, Emacs, etc.)
* Managing file permissions using `chmod`
* Creating basic scripts using `bash`
* Environment Variables
* Working with `systemd` at a basic level (for example, running an application on startup)
* Basic networking concepts such as IP's, port, and a network

While there is always more to learn, having at least some familiarity with what each is supposed to do can go a long way. AI tools can also assist with navigating Linux and debugging issues.

!!! warning
	Always remember to be careful running random commands from the internet or from an LLM. If you are unsure what a command does, either google the command more, or ask the LLM for more details into what exactly the command does.
	 
	Commands that begin with `sudo` will be run as an administrator, and be sure be run them carefully.
## TidalShore

The only prerequisites is that your development machine is able to run and develop against web technologies. 

## TidalView

While TidalView is *technically* not dependent on ROS2 inherently (since it only requires a WebSocket connect from ROSBridge which can be done from a remote machine), you don't need to install TidalCore. 

However, if you wish to actually test your features and develop against the latest version, it is highly recommended that you install and configure TidalCore to be able to run TidalCore and ROSBridge. Follow the respective guides for more detail. 

Other than that, follow the TidalView set up guide.
