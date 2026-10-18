# turtlebot4-ros2-teleoperation# 🤖 TurtleBot4 Robotics Projects — ROS 2, Teleoperation, SLAM & Navigation

![ROS 2](https://img.shields.io/badge/ROS_2-Humble-22314E?logo=ros)
![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-E95420?logo=ubuntu&logoColor=white)
![Robotics](https://img.shields.io/badge/Robotics-TurtleBot4-blue)

## 📌 Overview

This repository documents my robotics projects using the **TurtleBot4 mobile robot**, the Robot Operating System 2 (ROS 2), and Python.

The projects explore how to communicate with a physical robot, control its movement through keyboard teleoperation, visualize sensor data, create maps of an environment, and use autonomous navigation tools to move toward a target location.

The work combines robotics software, sensor integration, robot motion control, mapping, and navigation.

## 🎯 Project Objectives

- Understand the ROS 2 architecture and communication system.
- Develop a Python-based ROS 2 node for robot teleoperation.
- Control a TurtleBot4 using keyboard commands.
- Work with ROS 2 topics, namespaces, and velocity commands.
- Visualize robot sensor data using RViz.
- Explore LiDAR and camera data.
- Generate maps of indoor environments using SLAM tools.
- Use the Nav2 navigation framework to navigate toward target locations.
- Understand the challenges of remote robot operation and autonomous navigation.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Robotics node development |
| ROS 2 Humble | Robot communication and software framework |
| TurtleBot4 | Mobile robotics platform |
| Ubuntu 22.04 | Development environment |
| RViz | Robot and sensor-data visualization |
| ROS 2 topics | Communication between nodes and robot components |
| `cmd_vel` | Velocity commands for robot movement |
| LiDAR | Environmental distance measurements |
| OAK-D camera | Camera and image data |
| SLAM tools | Mapping an environment |
| Nav2 | Autonomous robot navigation |

## 📂 Project Structure

```text
TurtleBot4-Robotics-Projects/
│
├── README.md
│
├── project-1-teleoperation/
│   ├── README.md
│   ├── src/
│   │   └── turtlebot4_teleop/
│   ├── screenshots/
│   └── docs/
│
├── project-2-mapping-navigation/
│   ├── README.md
│   ├── maps/
│   ├── screenshots/
│   └── docs/
│
└── media/
    ├── teleoperation-demo.gif
    └── navigation-demo.gif
```

*Note: This is the proposed repository structure. Add the source files, maps, screenshots, and videos that are actually available. The folders are not automatically created by this README.*

---

## 🚀 Project 1: Keyboard Teleoperation and Sensor Visualization

### Overview

The first project focuses on setting up the ROS 2 environment, connecting a development computer to a TurtleBot4, and implementing a customized version of the keyboard teleoperation program.

The objective is to control the robot remotely while observing its sensor information through RViz.

### Key Components

**1. ROS 2 environment setup**

- Install Ubuntu 22.04 and ROS 2 Humble.
- Install the TurtleBot4 desktop packages.
- Configure the ROS 2 discovery server and robot namespace.
- Verify communication by inspecting available ROS 2 topics.

**2. Python teleoperation node**

The project involves adapting the `teleop_twist_keyboard` program to communicate with the assigned TurtleBot4 namespace.

The teleoperation node sends velocity commands to the robot through its namespaced `cmd_vel` topic.

For example:

```text
/<robot_namespace>/cmd_vel
```

The namespace ensures that commands are directed to the intended robot.

**3. Sensor visualization with RViz**

RViz is used to visualize the robot model and available sensor information.

Relevant ROS 2 topics may include:

```text
/<robot_namespace>/scan
/<robot_namespace>/odom
/<robot_namespace>/tf
/<robot_namespace>/oakd/rgb/preview/image_raw
```

The exact topic names depend on the robot's namespace and configuration.

### How Teleoperation Works

```text
Keyboard Input
      |
      v
Python Teleoperation Node
      |
      v
ROS 2 Velocity Commands
      |
      v
TurtleBot4 Movement
      |
      v
Robot Sensor Data
      |
      v
RViz Visualization
```

### Learning Outcomes

- Understanding ROS 2 nodes, topics, and namespaces.
- Publishing velocity commands to control a mobile robot.
- Configuring communication between a computer and a physical robot.
- Visualizing LiDAR and camera data.
- Understanding the limitations of teleoperation when the operator cannot directly see the robot.

---

## 🗺️ Project 2: Mapping and Autonomous Navigation

### Overview

The second project builds on the ROS 2 foundation by exploring mapping and autonomous navigation using the built-in TurtleBot4 software.

The objective is to create a map of an indoor environment and navigate the robot toward a selected location without continuously controlling its movement through keyboard commands.

### Key Components

**1. Environment mapping**

The robot is driven through the environment while mapping tools collect sensor information and build a representation of the surroundings.

The resulting map is saved on the development computer.

**2. Autonomous navigation**

After creating a map, the robot can be instructed to navigate from a starting position toward a target location.

The Nav2 navigation framework supports the navigation process using the map, robot localization, planning, and motion-control components.

**3. Path planning**

The navigation system determines a route toward the target and works with the robot's control components to execute movement.

Sensor information helps the robot understand its surroundings and respond to obstacles according to the configured navigation system.

### Autonomous Navigation Workflow

```text
TurtleBot4 Sensor Data
          |
          v
     SLAM Mapping
          |
          v
      Saved Map
          |
          v
 Robot Localization
          |
          v
  Nav2 Path Planning
          |
          v
  Motion Controller
          |
          v
 Robot Moves to Goal
```

### Learning Outcomes

- Understanding the purpose of SLAM and environmental mapping.
- Generating and saving maps of indoor environments.
- Understanding the role of localization in navigation.
- Exploring Nav2 path planning and motion control.
- Comparing manual teleoperation with autonomous navigation.
- Identifying practical challenges in robot navigation and map-based movement.

---

## 🧠 Key Robotics Concepts

### ROS 2 Nodes and Topics

ROS 2 nodes are individual software components that perform specific tasks. Topics allow nodes to exchange messages using a publisher-subscriber communication model.

### Robot Teleoperation

Teleoperation means remotely controlling a robot. In this project, keyboard input is translated into velocity commands that control the robot's movement.

### Sensor Integration

The TurtleBot4 provides access to sensor information, including LiDAR scans, odometry, camera images, and transform data. These sources help with visualization, mapping, and navigation.

### SLAM

Simultaneous Localization and Mapping (SLAM) is the process of estimating a robot's position while constructing a map of its environment.

### Nav2

Nav2 is the ROS 2 navigation framework used to support goal-directed robot movement through planning, control, and related navigation components.

### Feedback and Motion Control

A mobile robot must execute movement commands while accounting for its estimated position and surrounding environment. Navigation systems use feedback and configured control components to guide the robot toward a target.

---

## 💻 Installation and Setup

### Prerequisites

The original project instructions specify:

- Ubuntu 22.04
- ROS 2 Humble
- TurtleBot4 software packages
- Access to a TurtleBot4 robot or a suitable development environment

### 1. Install ROS 2 Humble

Follow the official ROS 2 installation guide:

https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html

### 2. Install TurtleBot4 Desktop Packages

```bash
sudo apt update
sudo apt install ros-humble-turtlebot4-desktop
```

### 3. Configure the ROS 2 Environment

```bash
source /opt/ros/humble/setup.bash
```

For the original physical-robot setup, configure the TurtleBot4 discovery server using the official instructions:

https://turtlebot.github.io/turtlebot4-user-manual/setup/discovery_server.html

The robot namespace, discovery server ID, IP address, and ROS domain settings must match the assigned robot and network configuration.

### 4. Verify ROS 2 Communication

List the available topics:

```bash
ros2 topic list
```

Inspect the robot's velocity-command topic:

```bash
ros2 topic info /<robot_namespace>/cmd_vel
```

Replace `<robot_namespace>` with the actual namespace of the robot.

### 5. Install Navigation Packages

```bash
sudo apt install ros-humble-turtlebot4-navigation
```

### 6. Launch RViz

The original project uses the TurtleBot4 visualization launch file:

```bash
ros2 launch turtlebot4_viz view_model.launch.py namespace:=/<robot_namespace>
```

Replace `<robot_namespace>` with the correct robot namespace.

### 7. Explore Mapping and Navigation

Follow the official TurtleBot4 tutorials:

- [Generate a Map](https://turtlebot.github.io/turtlebot4-user-manual/tutorials/generate_map.html)
- [Autonomous Navigation](https://turtlebot.github.io/turtlebot4-user-manual/tutorials/navigation.html)
- [TurtleBot4 User Manual](https://turtlebot.github.io/turtlebot4-user-manual/)

---

## 🔧 Troubleshooting

### ROS 2 Topics Are Not Appearing

- Confirm that ROS 2 is installed and sourced.
- Check the ROS domain and discovery-server configuration.
- Verify that the robot and development computer can communicate over the network.
- Restart the ROS 2 daemon if necessary:

```bash
ros2 daemon stop
ros2 daemon start
ros2 topic list
```

### The Robot Does Not Respond to Keyboard Commands

- Verify the robot namespace.
- Confirm that the teleoperation node publishes to the correct `cmd_vel` topic.
- Inspect the topic using `ros2 topic info`.
- Check the robot's connection and operational status.

### Sensor Data Does Not Appear in RViz

- Confirm that the relevant sensor topic exists.
- Select the correct topic in RViz.
- Check the fixed frame and transform configuration.
- Verify that the robot is publishing sensor messages.

### Mapping or Navigation Does Not Work as Expected

- Confirm that a valid map has been generated and saved.
- Verify the robot's estimated starting position.
- Check the navigation configuration and sensor data.
- Ensure the robot has a usable route to the target.

---

## 📸 Demonstrations and Screenshots

Add screenshots and videos of your own implementation to these sections.

Recommended demonstrations:

1. TurtleBot4 responding to keyboard teleoperation.
2. RViz displaying LiDAR scans and the robot model.
3. A generated map of the indoor environment.
4. The robot navigating from a starting point to a goal.
5. A comparison of manual and autonomous navigation.

Example Markdown for adding an image:

```markdown
![TurtleBot4 visualization](media/rviz-visualization.png)
```

Example Markdown for adding a video link:

```markdown
[Watch the TurtleBot4 navigation demo](YOUR_VIDEO_URL)
```

Replace the example paths and URL with actual files before publishing.

---

## 📚 References

- [ROS 2 Humble Documentation](https://docs.ros.org/en/humble/)
- [TurtleBot4 User Manual](https://turtlebot.github.io/turtlebot4-user-manual/)
- [TurtleBot4 Python Node Tutorial](https://turtlebot.github.io/turtlebot4-user-manual/tutorials/first_node_python.html)
- [TurtleBot4 Mapping Tutorial](https://turtlebot.github.io/turtlebot4-user-manual/tutorials/generate_map.html)
- [TurtleBot4 Navigation Tutorial](https://turtlebot.github.io/turtlebot4-user-manual/tutorials/navigation.html)
- [teleop_twist_keyboard](https://github.com/ros-teleop/teleop_twist_keyboard)

## 🎓 Skills Demonstrated

- Python programming for robotics
- ROS 2 node development and communication
- Mobile robot teleoperation
- Robot velocity commands
- Sensor-data visualization
- SLAM and map generation
- Autonomous navigation concepts
- Path planning and motion control
- Robotics software configuration and troubleshooting

## 👨‍💻 Author

**Rauf Bairamov**

Computer Science graduate student and software engineer interested in robotics, autonomous systems, computer vision, and AI.

- GitHub: [@RaufBairamov97](https://github.com/RaufBairamov97)

---

*This repository documents robotics coursework and implementation work involving TurtleBot4, ROS 2, teleoperation, mapping, and navigation. See the individual project folders for implementation details and demonstrations.*
