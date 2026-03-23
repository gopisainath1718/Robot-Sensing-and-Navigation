# Robot Sensing and Navigation

This repository contains various modules and assignments related to Robot Sensing and Navigation, including GNSS, GPS, IMU integration, sensor fusion, ultrasonic mapping, and image stitching.

## Prerequisites

- **ROS Noetic / Melodic** (or compatible ROS 1 distribution) matches the host operating system.
- **Python 3** (or Python 2 depending on your ROS distribution).
- **MATLAB** (required for the `image_stiching` component).

## Cloning the Repository

To clone this repository and navigate into it, run the following commands in your terminal:

```bash
git clone https://github.com/gopisainath1718/Robot-Sensing-and-Navigation.git
cd Robot-Sensing-and-Navigation
```

## Running the Modules

Below are detailed instructions on how to build and execute each module inside this repository. Make sure to open a new terminal for `roscore` if your launch files don't automatically start a ROS master node.

### 1. ROS Basics
Contains a basic ROS Publisher and Subscriber built with Python (`publisher.py` and `subscriber.py`).

```bash
cd ROS_basics/catkin_ws
catkin_make
source devel/setup.bash

# In one terminal, run the publisher:
rosrun sample publisher.py

# In a separate terminal (after sourcing devel/setup.bash), run the subscriber:
rosrun sample subscriber.py
```

### 2. GNSS Driver
A self-contained ROS workspace for testing and interfacing with the GNSS driver.

```bash
cd gnss
catkin_make
source devel/setup.bash

# Launch the GNSS driver node:
roslaunch gnss_driver driver.launch
```

### 3. GPS Driver
ROS workspace containing nodes and data for the GPS driver.

```bash
cd gps
catkin_make
source devel/setup.bash

# Launch the GPS driver node:
roslaunch gps_driver driver.launch
```

### 4. IMU Driver
ROS workspace containing nodes and data for the IMU driver.

```bash
cd imu
catkin_make
source devel/setup.bash

# Launch the IMU driver node:
roslaunch imu_driver driver.launch
```

### 5. Sensor Fusion (IMU + GPS)
ROS workspace dedicated to fusing data from IMU and GPS sensors.

```bash
cd sensor_fusion
catkin_make
source devel/setup.bash

# Launch the sensor fusion node:
roslaunch imu_gps driver.launch
```

### 6. Ultrasonic Mapping
Contains driver configurations, raw data, analysis, and RViz results for mapping tasks using ultrasonic sensors coupled with IMU and GPS.

To launch the corresponding drivers:
```bash
# First, go to the directory:
cd "Ultrasonic mapping"

# Example: To launch the IMU driver
roslaunch imu_driver driver.launch

# Example: To launch the GPS driver
roslaunch gps_driver driver.launch
```

### 7. Image Stitching
Contains MATLAB scripts (e.g., `pano.m`, `harris.m`) and image datasets to perform panorama generation and homography operations.

1. Open **MATLAB**.
2. Set your current folder to `image_stiching` within this repository.
3. Open and run the primary scripts such as `pano.m` to observe the image stitching process.


## TO-DO
Need to update everything to work in ROS 2