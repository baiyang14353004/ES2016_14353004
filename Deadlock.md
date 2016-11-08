#实验报告
##
![](http://p1.bqimg.com/567571/8520b5d445149f42.png)
###死锁条件
死锁就是两个或者多个进程互相请求对方占有的资源,条件如下：

- 互斥条件：一个资源每次只能被一个进程使用
- 请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放
- 不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺
- 循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系

###对上述程序产生死锁的解释
第一次调用Deadlock.java,新建了一个线程t，然后对象A调用b.last()函数，对象B调用a.last()函数，for循环调用Deadlock.java,再次执行上述过程，一直执行直到死锁出现，资源b此时被占用得不到释放，而占用者又在等待另一资源a被释放，而占有资源a的占有者又在等待资源b，形成循环等待资源关系，因此形成死锁。