## 《面试题储备》

### 阿里一面：

1. 两个无限长度链表（也就是可能有环） 判断有没有交点

2. MVC具有什么样的优势，各个模块之间怎么通信，比如点击 Button 后 怎么通知 Model？

3. UITableView的相关优化

4. KVO、Notification、delegate各自的优缺点，效率还有使用场景

5. 如何手动通知KVO

6. Objective-C 中的copy方法

7. runtime 中，SEL和IMP的区别

8. autoreleasepool的使用场景和原理

9. RunLoop的实现原理和数据结构，什么时候会用到

10. block为什么会有循环引用

11. 使用GCD如何实现这个需求：A、B、C 三个任务并发，完成后执行任务 D。

12. NSOperation和GCD的区别

13. CoreData的使用，如何处理多线程问题

14. 如何设计图片缓存？

15. 有没有自己设计过网络控件？

### 阿里p5二面：

1. 怎么判断某个 cell 是否显示在屏幕上

2. 进程和线程的区别

3. TCP 与 UDP 区别

4. TCP 流量控制

5. 数组和链表的区别

6. UIView 生命周期

7. 如果页面 A 跳转到 页面 B，A 的 viewDidDisappear 方法和 B 的 viewDidAppear 方法哪个先调用？

8. block 循环引用问题

9. ARC 的本质

10. RunLoop 的基本概念，它是怎么休眠的？

11. Autoreleasepool 什么时候释放，在什么场景下使用？

12. 如何找到字符串中第一个不重复的字符

13. 哈希表如何处理冲突

###  搜狗iOS面试题：

1.iOS应用的文件目录都是什么？缓存文件存在哪个文件里？它的上一层是什么？



2.SDWebImage图片处理原理？



3.SDWebImage在iOS9 3dtouch下出现的问题？



4.NSArray和NSMutableArray在Copy和MutableCopy下的内存是怎样的？



5.用户下载一个图片，图片很大，需要分成很多份进行下载，使用GCD应该如何实现？使用什么队列？



6.现有两个人和一张桌子，两个人依次在桌子上放硬币，硬币不能叠放、立着，若一方找不到放的位置则失败。若你在玩这个游戏，设计一个算法必赢。



7.现有n个物品和一个体积为V的包，每件物品的体积是ci，价格是wi，现在请你往包中放，每件物品只能放一次，怎么放能让包的价格最大。

  


### 百度iOS面试题：

1.Delegate 、Notification和KVO比较各自的优缺点

2.在一个UI的正中间实现一个正方形的红色视图有几种方式？

3.手触碰到屏幕的时候，响应机制是怎样的？第一响应者是谁？追问 UIView和UIResponse的关系是什么？

4。UIViewController的生命周期是什么？追问 UIViewController 只alloc而没用到的时候，UIViewController 的view是否加载了？如果没有加载那什么时候加载？

5.直接用UILabel和自己用DrawRect画UILabel，哪个性能好？为什么？哪个占用的内存少？为什么?

6.AFNetworking是否支持ipv6？

7.项目采用64位，为什么要用64位？怎么修改成64位？i386是什么？他们有什么关系?

8.iOS的应用程序有几种状态？追问，退到后台代码是否可以执行？双击home键，代码是否可以执行？

9.一般使用的图标内存为多大？比如200×300的图片，内存应该占用多少比较合理？

10.说说你对内存泄漏的看法，追问，block为什么容易引起内存泄漏？

11.\[object copy\]是浅拷贝还是深拷贝？为什么是浅拷贝？copy是实现了哪个协议？

12.Images.xcassets和直接用图片有什么不一样？



