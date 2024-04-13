# Package: [Xsens_driver](https://github.com/xsens/xsens_mti_ros_node)

## Global Architecture

## Configurations

## Topics ROS

### `/$AUV_name$/imu`

We use [Xsens Mti 300]() in our AUVs.
And it's documentation and usage instructions can be found on the official website given above.
## Usage instructions

1. **Build**: Build the ros package in the same catkin workspace as the AUV keep the package inside the hardware_layer.
2. **Redirect**: Redirect the topic of packager publisher to /$AUV_name$/imu for the software to access it.
3. **Set-Up**: <b>NOTE</b>- Change the IMU reset config in the code to prevent continuous heading reset of the IMU. Install Mti software manager in a windows/linux machine and there you can config the device . Disable the magnetometer otherwise it will always take true North as reference position
4. **Launch**: Launch the given launch file.

5. **Check**: The data will start logging on the terminal.

## Services
1. **/nav/imu_quat**- to reset the heading of the imu on will.

## Troubleshoot
1. **Proper Mti device not found**: Check the port name+no. Check the physical USB connection.
<!-- 2. **DVL Ros package getting disconnected with DVL after some time**: Keep the web GUI open in background always while running the ros package it resolves this issue. -->
