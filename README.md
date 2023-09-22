# checkpoint6-autonomous-navigation

<p>The goal of this project is to design a navigation system of RB-1 robot that works in a warehouse. Tghe project is divided into several tasks including,</p>

<ol>
  <li>create a map of the warehouse</li>
  <li>localize RB-1 in the map</li>
  <li>launch Nav2 system that allows to send navigation goals to the robot</li>
  <li>configure all required navigation parameters</li>
</ol>

## Mapping
<p>The warehouse map is generated by a cartographer and occupancy_grid nodes</p>


ros2 launch map_server map_server.launch.py map_file:=warehouse_map_sim.yaml


<img alt="simulation map" src="https://github.com/ptientho/checkpoint6-autonomous-navigation/blob/main/Screen%20Shot%202023-09-21%20at%2010.47.23%20PM.png"/>

## Localization
<p>After that use map_server node to feed the map in and use amcl node provided by ROS to localize the robot in the map</p>


ros2 launch localization_server localization.launch.py map_file:=warehouse_map_sim.yaml


[![amcl](https://res.cloudinary.com/marcomontalbano/image/upload/v1695352298/video_to_markdown/images/google-drive--19I_8vkm8f01p3NrhUAf2V0YU56Jd_aE3-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://drive.google.com/file/d/19I_8vkm8f01p3NrhUAf2V0YU56Jd_aE3/view?usp=sharing "amcl")

<p>Move the robot to see the particle clouds are converging to the robot location.</p>

## Navigation


ros2 launch path_planner_server pathplanner.launch.py


<p>Manually send the navigation goals to the robot in Rviz.</p>


[![nav2](https://res.cloudinary.com/marcomontalbano/image/upload/v1695353312/video_to_markdown/images/google-drive--1gElInkLMaJh923sihuv8NjlDJRLB3pli-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://drive.google.com/file/d/1gElInkLMaJh923sihuv8NjlDJRLB3pli/view?usp=sharing "nav2")

## Send goals to the robot through Nav2 API



