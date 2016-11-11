# Lab3 DOL实例分析&编程


**代码分析**
 
- src文件夹：各进程（生产者，消费者，处理模块等）的功能定义
- example1.xml：系统架构即模块连接方式定义
- /src 文件夹内包含2种文件：*.c, 与对应的.h，就是实现的模块，就是*.dot的框框的功能描述。（每个模块要实现2个接口，xxx_init和xxx_fire两个函数，分别是初始化这个模块是干了什么，以及这个模块开干的时候做什么）
-   ./example*.xml 里面定义了模块与模块之间是怎么连接的，就是有哪些框，哪些线，比如A框跟B框用一根线连起来，他们就在一起了。
-  xml是这样的：process就是那些框, sw_channel那些线, connection就是把线的那头连到框的那头。

> **任务：**
1. 修改example2，让3个square模块变成2个, tips:修改xml的iterator
2. 修改example1，使其输出3次方数，tips:修改square.c。

####任务实现####
-  实现任务1，为了让square模块由三个变为两个，我们需要修改xml的iterator,所以更改变量variable的值，将3改为2，就只进行两次迭代。
-  修改代码如下图

![code_change](http://photo.weibo.com/5175758726/wbphotos/large/mid/4040400098426606/pid/005EgXhsgw1f9nencgp9hj311y0lc498.png)

-  得到的dot图由原来的三个square变为两个，如下图

![example2_dot](http://photo.weibo.com/5175758726/wbphotos/large/mid/4040392666098442/pid/005EgXhsjw1f9ndsosea7j30e60dgq3h)

-  实现任务2，为使其输出三次方数，将原来的平方改为立方，代码如下。

![changecode2](http://photo.weibo.com/5175758726/wbphotos/large/mid/4040400098426606/pid/005EgXhsgw1f9nenfp1rxj311y0lcdiz.jpg)
-  现在得到的数据是

![now](http://photo.weibo.com/5175758726/wbphotos/large/mid/4040392666098442/pid/005EgXhsjw1f9ndskr8d2j30jm0cvwiy)

###实验感想###
- 这次实验并不难只要理解了只用改一点代码就可以得到结果了。但是一开始改完代码后也没有得到新的dot图，因为没有删掉原有的东西，就一直保持着原来的代码实现，只要将原先build的生成的文件删除掉，再重新build就可以了。
