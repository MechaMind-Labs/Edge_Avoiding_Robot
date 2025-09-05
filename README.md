# 🤖 Simulated Edge-Avoidance Robot

This repository contains a **ROS 2-based mobile robot simulation** with an **edge-avoidance behavior**.  
The robot uses a simulated **LIDAR sensor in Gazebo** and reacts to edges or drops detected in its environment.

---

## 📦 Prerequisites

- ✅ **OS:** Ubuntu 22.04  
- ✅ **ROS 2:** Humble Hawksbill  
- ✅ **Simulation Tools:** Gazebo & RViz (included in ROS 2 Desktop Full)  
- ✅ **Python:** 3.10+  

---

## 🧰 Step-by-Step Installation

### 1️⃣ Install ROS 2 Humble  
Follow the official ROS 2 installation guide:  
👉 [ROS 2 Humble Installation](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html)

### 2️⃣ Source ROS 2 and Add to `.bashrc`
```bash
source /opt/ros/humble/setup.bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
````

### 3️⃣ Source `.bashrc`

```bash
source ~/.bashrc
```

---

## 🧠 Workspace Setup

### 5️⃣ Install Git

```bash
sudo apt install git
```

### 6️⃣ Clone This Repository

```bash
cd ~
git clone git@github.com:MechaMind-Labs-LLP/Edge_Avoiding_Robot.git
cd Edge_Avoiding_Robot
```

---

## ⚙️ Setup ROS Dependencies

### 7️⃣ Install `rosdep` and initialize

```bash
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
```

### 8️⃣ Install package dependencies

```bash
rosdep install --from-paths src -y --ignore-src --skip-keys="ament_python"
```

---

## 🧱 Build the Workspace

```bash
cd ~/Edge_Avoiding_Robot
colcon build
```

### 9️⃣ Source the workspace

```bash
source install/setup.bash
echo "source ~/Edge_Avoiding_Robot/install/setup.bash" >> ~/.bashrc
```

---

## 🧩 (Optional) Shell Autocompletion

```bash
sudo apt install python3-colcon-argcomplete
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
echo "source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash" >> ~/.bashrc
```

---

## 🚀 Run the Simulation

### Terminal 1: Launch Gazebo with the robot

```bash
ros2 launch bot_bringup simulated_robot.launch.py
```

### Terminal 2: Run the Edge Detection Node

```bash
ros2 run bot_script edge_detection
```

✅ You should now see:

* Gazebo with the robot and a world environment
* The robot running an **edge avoidance algorithm** using LIDAR data

---

## 📁 Project Structure

```
Edge_Avoiding_Robot/
├── src/
│   ├── bot_description/   # URDF and Gazebo assets
│   ├── bot_controller/    # Robot control nodes
│   ├── bot_bringup/       # Launch files
│   ├── bot_script/        # Edge detection and logic
```

---

## 🛠 Troubleshooting

* If LIDAR is not detecting correctly, check its **pose and scan angle** in `bot_description`.
* Always source the workspace in every new terminal:

  ```bash
  source ~/Edge_Avoiding_Robot/install/setup.bash
  ```

---

## 🙌 Credits

Maintained by **[Curious-Utkarsh](https://github.com/Curious-Utkarsh)**
Inspired by real-world **edge-avoidance robotics** applications.

---
