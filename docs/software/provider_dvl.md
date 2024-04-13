# Package: Provider DVL

## Global Architecture

## Configurations

## Topics ROS

### `/provider_dvl/pd0_packet`

The `pd0_packet topics contains all the informations of the DVL.
It is being sent from the DVL at every signals.

The specifications of the PD0 packets can be found on the Teledyne Documentation (c.f. Github).
It is composed of the other messages of the DVL and does not contain any raw data. The specifications for all the other messages can also be found on the documentation.

	# sonia_msgs/PD0Packet
	std_msgs/Header header
	  ...

!!!Note
	As the message AcquisitionConfigure to BottomTracking are also provided on other topics described below, you will be able to see the description for each one through their specific section.

### `/provider_dvl/acquisition_conf`

???

	# sonia_msgs/AcquisitionConfiguration
	std_msgs/Header header

### `/provider_dvl/output_conf`

???

	# sonia_msgs/OutputConfiguration
	uint8 BEAM=0

### `/provider_dvl/status`

???

	# sonia_msgs/Status
	std_msgs/Header header

### `/provider_dvl/cell_readings`

???

	# sonia_msgs/CellReadings
	std_msgs/Header header

### `/provider_dvl/bottom_tracking_conf`

???

	# sonia_msgs/BottomTrackingConfiguration
	std_msgs/Header header

### `/provider_dvl/bottom_tracking`

???

	# sonia_msgs/BottomTracking
	std_msgs/Header header

### `/provider_dvl/twist`

???

	# geometry_msgs/TwistWithCovarianceStamped
	std_msgs/Header header
