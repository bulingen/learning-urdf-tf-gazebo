# Learn URDF, TF and Gazebo

## How to construct a URDF

Without having a complete package, a URDF can be constructed by using the preinstalled URDF tutorial display launch file, like this:

```bash
ros2 launch urdf_tutorial display.launch.py model:=/absolute/path/to/my_robot.urdf
```

## Create a PDF for inspecting frames of URDF

```bash
ros2 run tf2_tools view_frames
```

Then a PDF will created in the folder you're in.

## Other useful commands

```bash
ros2 run robot_state_publisher robot_state_publisher --ros-args -p robot_description:="$(xacro my_robot.urdf)"

ros2 param get /robot_state_publisher robot_description

ros2 run joint_state_publisher_gui joint_state_publisher_gui

rqt_graph

ros2 run rviz2 rviz2

# view the raw urdf, which has been generated with xacro
ros2 param get /robot_state_publisher robot_description

# open gazebo from ros2 command
ros2 launch ros_gz_sim gz_sim.launch.py gz_args:=empty.sdf

# open gazebo from terminal
gz sim
```

## Spawn a robot in Gazebo

```bash
ros2 run robot_state_publisher robot_state_publisher --ros-args -p robot_description:="$(xacro my_robot.urdf.xacro)"

ros2 launch ros_gz_sim gz_sim.launch.py gz_args:="empty.sdf -r"

ros2 run ros_gz_sim create -topic robot_description

ros2 run rviz2 rviz2 -d src/my_robot_description/rviz/display.rviz
```