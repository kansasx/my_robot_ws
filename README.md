# ROS 2 Mobile Robot URDF and Gazebo Integration

This project demonstrates how to create a **URDF model for a differential drive mobile robot** and how to **bridge communication between ROS 2 and Gazebo** for simulation.

It focuses on robot description, visualization, and physics-based simulation rather than real hardware control.

---

## Project Description

The project covers the complete workflow for simulating a mobile robot in ROS 2:

- Modeling a wheeled mobile robot using URDF
- Publishing robot state and TF frames
- Visualizing the robot in RViz
- Spawning and simulating the robot in Gazebo
- Bridging ROS 2 and Gazebo for joint and state updates

This provides a foundation for understanding how simulated robots are structured before moving to real hardware.

---

## Concepts Demonstrated

- URDF (links, joints, inertial properties)
- Coordinate frames and TF
- `robot_state_publisher`
- ROS–Gazebo integration
- Simulation versus real-robot control architecture

---

## Workspace Structure

my_ros_ws/
├── src/
│   ├── my_robot_description/
│   │   ├── launch/
│   │   │   └── display.launch.xml
│   │   ├── rviz/
│   │   │   └── urdf_config.rviz
│   │   └── urdf/
│   │       ├── common_properties.xacro
│   │       ├── mobile_base.xacro
│   │       ├── mobile_base_gazebo.xacro
│   │       └── my_robot.urdf.xacro
│   │
│   └── my_robot_bringup/
│       ├── config/
│       │   └── gazebo_bridge.yaml
│       └── launch/
│           └── my_robot.launch.xml
│
├── README.md
└── .gitignore



---

## Requirements

- Ubuntu 22.04
- ROS 2 Jazzy
- Gazebo (ROS 2 compatible)
- colcon

---

## Build the Workspace

```bash
cd my_ros_ws
rosdep install --from-paths src --ignore-src -r -y
colcon build
source install/setup.bash
---

## Visualize the Robot in Rviz and run the robot in Gazebo
ros2 launch my_robot_bringup my_robot.launch.xml

---

## Simulation Note

In simulation, Gazebo directly applies forces to the robot joints.

---

For a real robot, a hardware driver would be required to translate ROS commands into motor signals and read encoder feedback. This project focuses only on simulation.

Author
Orngu Joseph Mtsor
Mechanical Engineering | Robotics | Control Systems
