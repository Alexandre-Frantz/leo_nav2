# leo_nav2
A custom ROS2 package that launches a ROS2 Navigation 2 node for autonomous navigation. Create to easily modify multiple `.yaml` configuration files for the Nav2 node. 

## Building the project 

### Dependencies

This project depends on the Nav2 package from ROS2 

Installing this package is **required** in order to use this repository. The link to the installation guide can be found [here](https://docs.nav2.org/getting_started/index.html).

### Setting up the Workspace

1. Setup a [colcon workspace](https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Creating-A-Workspace/Creating-A-Workspace.html)
2. Enter your `src` folder
```
cd ~/<your_ros2_ws>/src
```
3. Clone this reposistory into the `src` folder of your `ros2_ws`
```
git clone https://github.com/Alexandre-Frantz/leo-common-ros2.git
```
4. Install dependencies using [rosdep](https://docs.ros.org/en/humble/Tutorials/Intermediate/Rosdep.html#how-do-i-use-the-rosdep-tool):
   ```
   cd ..
   sudo rosdep init
   rosdep update
   rosdep install --from-paths src -y --ignore-src
   ```
8. Build the project and source the workspace:
   ```
   colcon build --symlink-install
   source install/setup.bash
   ```

### Run custom Nav2 launch
To launch the custon Nav2 node: 

```
ros2 launch leo_nav2 leo_nav2.launch.py
```

If you wish to see a list of arguments 

```
ros2 launch leo_nav2 leo_nav2.launch.py --show-args

```

## Custom Configuration file

By default, this project launches with an existing `.yaml` configuration file. It is found in `leo_nav2/config/`. This can be directly modified, or you can also make a new one and provide it to the launch file either through the CLI using *launch arguments* or directly replace it in the code. 