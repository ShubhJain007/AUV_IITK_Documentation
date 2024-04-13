# Vision

This file describe how the vision is working and software is interfacing with ROS.
You may find here every information you need about the services and messages.

## Collecting and processing data
We have two cameras in the bot one is forward facing and uses Go Pro 11 and other one is downward facing and uses a logitech Camera. 
### Data gathering

The vision of the bot is available on topics `/front_camera/raw_image` and `/bottom_camera/raw_image`. The topics name and pattern is same as in UUV_Simulator. Since we are building our software taking that as a reference.
You can view the live image output on rqt-image-view.

### Data processing

The data processing will be done on jetson. We are planning to first use some filteration algorithms or image processing and then use Yolo on top of that to detect various underwater objects for the tasks. Currently since we are testing we are utilising Yolo V3 on our custom datasets from the pool.

## Global Architecture


