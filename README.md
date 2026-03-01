## How to Run Lab 2
> Previous lab [Lab 1](https://github.com/Oleksandr-Na-no/Robotics_Lab_1/blob/main/README.md)
### 1. Prepare the Environment

Open the Docker container from the **[robotics_lpnu](https://github.com/RybOlya/robotics_lpnu/tree/master)** repository.


> **Note:** Navigate to the `robotics_lpnu/` folder (`cd robotics_lpnu/`) and run:
>
> ```bash
> ./scripts/cmd run
> ```

---

### 2. Clone the Project

Inside the container:

```bash
source /opt/ros/jazzy/setup.bash
cd /opt/ws/src/code
git clone https://github.com/Oleksandr-Na-no/Robotics_Lab_2
cd /opt/ws/src/code/Robotics_Lab_2
```

---

### 3. Build the Workspace (first time or after changes)

```bash
cd /opt/ws
colcon build --packages-select lab2
source install/setup.bash
```

> ⚠️ Rebuild every time you change `package.xml`, `setup.py`, launch files, or add new nodes.

---

### 4. Launch Gazebo + Bridge + RViz2

```bash
cd /opt/ws/src/code/Robotics_Lab_2
source install/setup.bash
ros2 launch lab2 gazebo_ros2.launch.py
```

**You should see:**

* Gazebo window with the robot
* RViz2 window with LiDAR visualization
* ROS–Gazebo bridge running

Keep this terminal open.

---

### 5. Run the Robot Controller (new terminal)

```bash
cd /opt/ws
source install/setup.bash
ros2 run lab2 robot_controller
```

✅ The robot should start moving.

---

### 6. Run LiDAR Subscriber (new terminal)

```bash
cd /opt/ws
source install/setup.bash
ros2 run lab2 lidar_subscriber
```

✅ You will see LiDAR statistics in the console.

---
