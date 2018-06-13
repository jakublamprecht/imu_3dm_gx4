# Install

* Copy package to your workspace directory to `src` folder
* Run `catkin_make` in workspace directory

# How to run

## 1. Run roscore

* Open terminal and navigate to workspace directory
* Run

```bash
source devel/setup.bash
roscore
```

## 2. Run the package

* Open new tab in terminal and navigate to workspace directory, then run

```bash
source devel/setup.bash
roslaunch imu_3dm_gx4 imu.launch enable_filter:=true
```

**IMPORTANT:**
* *enable_filter* flag is required so that orientation information is sent to imu topic
* user must be added to the *dialout* group

## 3. Echo data

Data from the device is sent to /microstrain/imu topic.
To see the data run:

```bash
source devel/setup.bash
rostopic echo /microstrain/imu
```

# ROSBAG

## Record data

```bash
source devel/setup.bash
rosbag record -O packageName /microstrain/imu
```

## Play data

```bash
rosbag play packageName.bag
```

--loop flag can be added to cause endless loop
