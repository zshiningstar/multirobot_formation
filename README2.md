* ares_teleop:键盘控制小车运动
* ares_description:小车模型
* ares_gazebo:gazebo世界模型
* ares_navigation:导航避障碍


### 一、车队仿真
1 启动gazebo世界环境
```
roslaunch ares_gazebo ares_playground_gazebo.launch
```
2 启动键盘控制
```
rosrun rosrun ares_teleop mbot_teleop.py ||
rosrun rosrun ares_teleop ares_teleop.py 
```
* 注意：ares_base.xacro中 <commandTopic>/cmd_vel</commandTopic> 需要与键盘控制节点中的topic对应起来
（若都加上 / 则代表全局的话题消息，即车队中的所有车都会按照这个话题消息来运行）

3 启动车队控制
```
roslaunch ares_gazebo ares_cloister_gazebo.launch 
roslaunch ares_navigation navigation_demo.launch
roslaunch stage_first OnYourMarkGetSetGo.launch
```
* 在2Dnav Goal RVIZ里面设置终点即可导航行驶

