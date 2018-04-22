# ros_nav

使用ros构建自主导航和避障系统。使用ros自带的导航功能包集，包括：使用tf发送变换，发布里程计信息，发布来自激光的传感器信息，基本的导航功能包集的配置。

![](http://wiki.ros.org/move_base?action=AttachFile&do=get&target=overview.png)

---
## listener和publisher

使用rospy监听和发布toplic。代码参考[python监听](python/notebook/listener.ipynb)和[python发布](python/notebook/publisher.ipynb)。

[Writing a Simple Publisher and Subscriber (Python)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29)

---
## tf

使用tf发布结点之间的坐标关系。代码参考[python tf发布](python/notebook/transform_broadcaster.ipynb)。

![no tf](http://chenguanfuqq.gitee.io/tuquan2/img_2018_4/ros_no_tf.png)

![fame坐标转换](http://chenguanfuqq.gitee.io/tuquan2/img_2018_4/frame_view.png)

### 数值查看结点之间的坐标关系

rosrun tf tf_echo base_link base_laser

```bash
## 输出结果
At time 1524295791.073
- Translation: [1.000, 0.000, 0.000]
- Rotation: in Quaternion [0.000, 0.000, 0.000, 1.000]
            in RPY (radian) [0.000, -0.000, 0.000]
            in RPY (degree) [0.000, -0.000, 0.000]
```

### 导出结点之间的坐标关系为pdf

rosrun tf view_frames

![tf view_frames结果](http://chenguanfuqq.gitee.io/tuquan2/img_2018_4/tf_broad.png)

### 细节查看结点之间的坐标关系

rosrun tf tf_monitor base_link base_laser

```bash
RESULTS: for base_link to base_laser         
Chain is: base_link -> base_laser            
Net delay     avg = 0.0292724: max = 0.0998455                                            

Frames:                                      
Frame: base_laser published by unknown_publisher Average Delay: 0.00025763 Max Delay: 0.000334684                                                                                    

All Broadcasters:                            
Node: unknown_publisher 11.4265 Hz, Average Delay: 0.00025763 Max Delay: 0.000334684
```


### 使用rviz查看tf

![](http://wiki.ros.org/robot_state_publisher?action=AttachFile&do=get&target=frames4.png)

![](http://wiki.ros.org/rviz/DisplayTypes/TF?action=AttachFile&do=get&target=TF.png)

[tf Debugging tools](http://wiki.ros.org/tf/Debugging%20tools) tf调试工具，类似echo，view等等。

[Writing a tf broadcaster (Python)](http://wiki.ros.org/tf/Tutorials/Writing%20a%20tf%20broadcaster%20%28Python%29) 使用python发布frame变化。

[Writing a tf listener (Python)](http://wiki.ros.org/tf/Tutorials/Writing%20a%20tf%20listener%20%28Python%29) 使用python监听frame变化。

[Adding a frame (Python)](http://wiki.ros.org/tf/Tutorials/Adding%20a%20frame%20%28Python%29)

[ROS初级十四 tf 配置](http://stevenshi.me/2017/06/08/ros-primary-tutorial-14/) 介绍了为什么要使用tf，以及base_link和laser_link之间的关系。

[为你的机器人配置 tf](http://wiki.ros.org/cn/navigation/Tutorials/RobotSetup/TF)

[rqt_reconfigure](http://wiki.ros.org/rqt_reconfigure) ros rqt reconfigure在线修改ros相关参数。

[navigation](http://wiki.ros.org/navigation) ros中关于导航部分。

[ROS导航仿真](https://stevenshi.me/2017/05/24/ros-navigation-simulation/) 使用rbx1进行导航仿真，对于理解整个pipeline有很大帮助。

[ROS中级二 利用Rviz实时观测模拟SLAM过程](https://stevenshi.me/2017/07/11/ros-intermediate-tutorial-2/) gmapping实现。

[ROS中级一 配置并使用ROS导航功能包集](http://stevenshi.me/2017/07/10/ros-intermediate-tutorial-1/) 对整个导航实物实现流程做了解释。
