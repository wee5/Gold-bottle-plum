# java：多线程4：锁



## 线程同步与锁

* 原因：java允许多线程并发控制；多线程同时操作一个可共享资源变量时，会导致数据不准确，且相互冲突；**加入锁避免该线程在没有完成操作前被其他线程调用，保证变量的唯一性和准确性**
* **同步方法：**
  * **同步函数：用synchronized关键字修饰方法；**因为每个java对象都有一个内置锁，synchronized修饰方法后，内置锁会保护整个方法；**调用该方法之前，要先获得内置锁；否则会处于阻塞状态**
  * **同步方法：用synchronized修饰代码块；**代码块会自动被加上内置锁，从而实现同步
* 补充：**静态的同步方法使用的锁是该方法所在类的字节码文件对象（类名.class）**；因为静态内存中没有本类对象，但是一定有该类对应的字节码文件对象，该对象类型是Class；而且静态方法中不能定义this
* **同步的前提：**
  * 两个或以上的线程
  * 使用同一个锁
  * 同步中只能有一个线程在运行
  * 只能同步方法，不能同步变量和类
  * 没必要同步类中所有方法
  * 若一个线程在对象上获得一个锁，就没有任何其他线程可以进入（该对象的）类中的任何一个同步方法
  * 线程睡眠时，持有的锁不会释放
* 同步的优劣势：解决多线程的安全问题；多个线程需要判断，消耗资源，降低效率
* **如何确定是否需要同步：**
  * 明确哪些代码是多线程运行代码
  * 明确共享数据
  * 明确多线程运行代码中哪些语句是操作共享数据



## 死锁

* **描述：**进程A中包含资源A，进程B中包含资源B；进程A下一步需要进程B，进程B中下一步需要进程A；两个进程相互等待对方释放资源，形成循环等待的死锁
* 死锁形成的条件（均满足后产生）
  * 互斥条件：资源不能被共享，只能被同一个进程使用
  * 请求与保持条件：已经得到资源的进程可以申请新的资源
  * 非剥夺条件：已经分配的资源不能从相应的进程中强制剥夺
  * 非剥夺条件：已经分配的资源不能从相应的进程中强制剥夺
  * 循环等待条件：系统中若干进程形成环路，该环路中每个进程都在等待相邻进程占用的资源

