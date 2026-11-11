# Direct Installation

Install ROS 2 Jazzy or Humble, colcon and rosdep, then create a workspace and clone the repositories. Use the `humble` branch of `omron_amr` for ROS 2 Humble; `main` targets Jazzy. Select compatible branches of the other repositories for your workspace.

```bash
mkdir -p ~/colcon_ws/src
cd ~/colcon_ws/src
git clone --recurse-submodules https://github.com/CollaborativeRoboticsLab/omron_amr.git
git clone https://github.com/CollaborativeRoboticsLab/capabilities2.git -b experience-integration
git clone https://github.com/CollaborativeRoboticsLab/fabric.git -b experience-integration
git clone https://github.com/CollaborativeRoboticsLab/fabric_capabilities.git -b experience-integration
git clone https://github.com/CollaborativeRoboticsLab/fabric_generator_prompttools.git
git clone --recurse-submodules https://github.com/CollaborativeRoboticsLab/prompt_tools.git -b experience-integration
git clone https://github.com/CollaborativeRoboticsLab/prompt_capabilities.git -b experience-integration
git clone https://github.com/CollaborativeRoboticsLab/nav2_capabilities.git -b experience-integration
git clone https://github.com/CollaborativeRoboticsLab/omron_amr_capabilities.git
cd ~/colcon_ws
rosdep install --from-paths src --ignore-src --rosdistro "$ROS_DISTRO" -y
colcon build --symlink-install
source install/setup.bash
```

See the [Omron AMR repository](https://github.com/CollaborativeRoboticsLab/omron_amr) for robot-specific prerequisites and configuration. Configure the robot connection before running the [example plans](../README.md#running-plans).