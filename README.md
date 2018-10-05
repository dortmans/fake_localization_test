# face_localization_test

Test of the [fake_localization](http://wiki.ros.org/fake_localization) package.

Prerequisites installation:
```
sudo apt-get install ros-kinetic-navigation-tutorials ros-kinetic-fake-localization ros-kinetic-robot-pose-publisher 
```

## Odometry data

Launch fake odom publisher to publish odometry on odom topic and odom --> base_link transform on tf:
```
roslaunch fake_localization_test fake_odom.launch
```

Echo odometry messages on odom topic:
```
rostopic echo /odom
```

## fake localizer

```
roslaunch navigation_stage move_base_fake_localization_10cm.launch
```fake localizer

```
roslaunch navigation_stage move_base_fake_localization_10cm.launch
```

## Our fake localizer

Launch our fake localization node, to publish map --> odom transform:
```
roslaunch fake_localization_test our_fake_localization.launch
```

## Test

Show the computation graph:
```
rqt_graph
```

Show tf tree:
```
rosrun rqt_tf_tree rqt_tf_tree
```

Echo tf transform from map to base_link:
```
rosrun tf tf_echo map base_link
```

Echo pose messages on pose topic:
```
rostopic echo /pose
```



## References

- [Publishing Odometry Information over ROS](http://wiki.ros.org/navigation/Tutorials/RobotSetup/Odom)
- [Introduction to tf](http://wiki.ros.org/tf/Tutorials/Introduction%20to%20tf)
- [robot_pose_publisher](http://wiki.ros.org/robot_pose_publisher)

