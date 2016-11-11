#Lab5 ROS安装
> **什么是ROS**
Robot operation system,一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。我们主要用它的仿真功能。

###ROS配置
根据网上的教程，就可以输入命令对ROS进行安装。
- 添加source,list：`sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc)main" > /etc/apt/sources.list.d/ros-latest.list'`
- 添加keys：`sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116`
- 确保虚拟机的软件包索引是最新的`sudo apt-get update`
- 桌面完整版安装`sudo apt-get install ros-jade-desktop-full`（网不好的话这里真的超级慢慢慢慢……）
- 初始化rosdep：`sudo rosdep init` `rosdep update`
- 环境配置`echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc source ~/.bashrc`
- 安装rosinatall `sudo apt-get install python-rosinstall`
**到这里基本就已经配置完成了，接下来就测试它是否能够正常使用**

###测试ROS
安装成功后可以用实例程序来测试。
- 新开一个终端，输入指令：`roscore`
- 再打开第二个新终端，输入指令：`rosrun turtlesim turtlesim_node` 然后会得到一个乌龟的界面![turtlr](http://ww3.sinaimg.cn/large/005EgXhsgw1f9o5z4rkg5j311y0lc467.jpg)(额其实这时候应该是没有白线乌龟在屏幕正中央的)
- 打开第三个终端，输入指令，由键盘控制小乌龟移动`rosrun turtlesim turtle_teleop_key`    ![control](http://ww3.sinaimg.cn/large/005EgXhsgw1f9o5z3iii7j311y0lctgk.jpg)
- ![](http://ww3.sinaimg.cn/large/005EgXhsgw1f9o5z11jkbj311y0lcwqr.jpg) 额这里可以看到让乌龟碰了好多次壁……

**至此可以确定ROS已经配置完成可以正常使用了**


###实验体会
   这次配置ROS照着教程输入命令就可以了，也没有遇到什么问题。但是一个重要的教训就是以后网不好的时候就不要下载安装了，实在是太慢了……（而且我还撞上了双十一……）
