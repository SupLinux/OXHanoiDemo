汉诺塔问题本身不难，主要是结合来做动画同时解决多个动画顺序执行的问题。

利用分线程来做算法逻辑，主线程跑动画，动画比较耗时，所以算法逻辑需要等待，否则会出现多个动画一起动的情况。

解决这个问题的方法是使用dispatch_semaphore_t信号量来控制等待，直到遇到动画的时候等待，动画完成后再继续跑算法，这个方法只有在算法处于分线程时可以做到，否则会阻塞动画的执行。

将塔做了对象抽象出来，将其坐标、已经堆放的盘子个数作为其属性，这样代码结构会更加清晰简单。

效果：

![](https://github.com/Cloudox/OXHanoiDemo/blob/master/demo.gif)

详细说明查看[我的博客](http://blog.csdn.net/cloudox_/article/details/72453843)

觉得有意思谢谢加星~
