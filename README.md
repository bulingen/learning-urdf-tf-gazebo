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
```