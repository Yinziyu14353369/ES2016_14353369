#Lab4 Deadlock

> **死锁：**
死锁就是两个或者多个进程，互相请求对方占有的资源。

> **死锁形成的4个条件：**
- 互斥条件：一个资源每次只能被一个进程使用
- 请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放
- 不剥夺条件：进程已获得的资源，在未使用完之前，不能强行剥夺
- 循环等待条件：若干进程之间形成一种头尾相接的循环等待资源关系

####代码分析
**关键字 synchronized:
- 当它用来修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多只有一个线程执行该段代码。![synchronized](http://ww2.sinaimg.cn/large/005EgXhsgw1f9o5z52wrzj30n70hkgon.jpg)
- 当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞。
- 当t.start(),之后，线程t就被插入到调度队列里，当调度到他的时候，就跑run()里面的代码![runable](http://ww4.sinaimg.cn/large/005EgXhsgw1f9o5z5ymfrj30b50diact.jpg)

####死锁分析
- 一个线程在执行了一段时间之后，自己的时间片耗尽了的话，就会将CPU资源给到另一个线程继续执行。
- 当我们调大count的值，在while循环里消耗的时间也会变大，所以methodA得到的时间就会越少。
- 出现的情况就是在执行methodA的时候，还没有执行完成时间片就已经被耗尽了。此时主线程占有了A 的信号量却没有执行下一步。跳转到执行线程t，t线程获得B方法的信号量调用methodB,但这是A信号量已经被占用，所以t线程被阻塞，回到主线程，所以就有了循环等待，形成死锁。
- 下面是得到了死锁的截图
![deadlock](http://ww3.sinaimg.cn/large/005EgXhsgw1f9o5z6mjcej30xo0hhdiv.jpg)




**实验感想**
 
- 死锁的概念在操作系统已经学习过了，并且也做过了详细的实验，所以这次实验很容易就做完了。只是用java跑的时候前几次一直都没有产生死锁，多试几次就可以了。
- 顺便说一句终于可以在github上传图片了，用的微博的外部链接，真的好艰辛啊。