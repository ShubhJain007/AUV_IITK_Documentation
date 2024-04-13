# <a name="title"></a> Installation

This document provides all the steps for configuring your environment.

Currently, our whole environment is set up on Ubuntu 18.04 and ROS Melodic. We are yet to commit the completely working AUV repository on our github but nevertheless installation procedure will remain the same!


<!-- There is two kind of environment to configure.
You can either configure a production environment, which is the environment that is running on the submarine.
Or you can also configure a development environment, that is going to help you to develop our softwares. -->

<!-- Once you have correctly installed and configured you environment, you are ready to use our softwares.
In order to simplify the usage of S.O.N.I.A. Software, we are using a single git repository that regroup all the modules that we use as git submodule. -->

This repository is located at `-----` and you will have to be part of the AUV IITK organisation to access it. If it is not the case yet, please ask an administrator to add you.
<!-- This repository is composed of several branches:

- `ros_sonia_ws:core` - Barbones environment for running the submarine
- `ros_sonia_ws:desktop` - Full environment for development. -->

You will find the details on how to install and configure you environment on all the specific sections (we are assuming you have full ros-melodic-desktop already set up):

- [Installing Packages](#pack)
- [Installing UUV_Simulator ](#soft_auv7)

### <a name="pack"></a> Install packages
Clone the repository in the src folder of your catkin workspace.

The repository requires the following ROS packages to run: usb_cam, geographic_msgs, rosserial_arduino, underwater_sensor_msgs, ros-melodic-grid-map, ros-melodic-image-geometry, ros-melodic-tf. To use some interpolation functions, you'll need to install scipy.

You can build and install those packages from their respective sources or you can use the following command in Ubuntu 18.04 to install them. If you are building from source or using a different package manager, make sure you are building the melodic version of these packages to ensure maximum compatibility.

	sudo apt-get install ros-melodic-usb-cam \
						ros-melodic-geographic-msgs \
						ros-melodic-rosserial-arduino \
						ros-melodic-underwater-sensor-msgs \
						ros-melodic-grid-map \
						ros-melodic-image-geometry \
						ros-melodic-tf

	pip install scipy
Now Build the whole repo package by running 

	catkin_make

<!-- Now install bash_it in order to have a better command line interface:

	git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it
	~/.bash_it/install.sh
	rm ~/.bashrc.bak
	sed -i -e 's/bobby/nwinkler/g' ~/.bashrc

Now edit your `~/.bashrc` and add the following configuration at the beginning of the file:

	# If not running interactively, con't do anything
	case $- in
	    *i*) ;;
	      *) return;;
	esac

	if ! shopt -oq posix; then
	  if [ -f /usr/share/bash-completion/bash_completion ]; then
	    . /usr/share/bash-completion/bash_completion
	  elif [ -f /etc/bash_completion ]; then
	    . /etc/bash_completion
	  fi
	fi

And source the other bash files at the end of your file:

	# Load common aliases
	if [ -f ~/.bash_aliases ]; then
	    . ~/.bash_aliases
	fi

	# Load SONIA Configuration
	if [ -f ~/.bash_sonia ]; then
	    . ~/.bash_sonia
	fi

Then resource your `.bashrc`:

	source ~/.bashrc -->

## Install AUV_IITK Software <a name="software"></a>

### <a name="soft_auv7"></a> Installing Anahita

<!-- Installing software is really simple, just execute the following command and enjoy the show (Be aware that at some point you might need to do some actions[ i.e press ENTER]):

	cd ~
	wget http://sonia-auv.readthedocs.org/assets/files/melodic_18_04_new/sonia_install.sh
	sudo chmod +x sonia_install.sh
	./sonia_install.sh
	# SYSTEM WILL REBOOT. AFTER IT, EXECUTE THE FOLLOWING :
	./sonia_install.sh
	
	# Then remove the file
	rm sonia_install.sh

### <a name="soft_auv7"></a> Fix network problem on Jetson AGX

	sudo su
	echo 'net.ipv4.udp_rmem_min = 12288' >> /etc/sysctl.conf
	echo 'net.core.netdev_max_backlog = 4096' >> /etc/sysctl.conf
	echo 'net.unix.max_dgram_qlen = 118148' >> /etc/sysctl.conf
	echo 'net.core.rmem_max = 536870912' >> /etc/sysctl.conf
	echo 'net.core.rmem_default = 536870912' >> /etc/sysctl.conf

	sysctl -p
	exit -->
