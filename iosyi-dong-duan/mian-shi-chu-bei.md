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

### 搜狗iOS面试题：

1.iOS应用的文件目录都是什么？缓存文件存在哪个文件里？它的上一层是什么？

2.SDWebImage图片处理原理？

3.SDWebImage在iOS9 3dtouch下出现的问题？

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

### **一般面试题**

**1.堆和栈的区别**

> 1.内存管理范围  
> 只有oc对象需要进行内存管理  
> 非oc对象类型比如基本数据类型不需要进行内存管理  
> 2.内存管理本质  
> 因为：Objective-C的对象在内存中是以堆的方式分配空间的,并且堆内存是由你释放的，就是release  
> OC对象存放于堆里面\(堆内存要程序员手动回收\)  
> 非OC对象一般放在栈里面\(栈内存会被系统自动回收\)  
> 堆里面的内存是动态分配的，所以也就需要程序员手动的去添加内存、回收内存  
> 3.内存分配以及管理方式  
> 按分配方式分  
> 堆是动态分配和回收内存的，没有静态分配的堆  
> 栈有两种分配方式：静态分配和动态分配  
> 静态分配是系统编译器完成的，比如局部变量的分配  
> 动态分配是有alloc函数进行分配的，但是栈的动态分配和堆是不同的，它的动态分配也由系统编译器进行释放，不需要程序员手动管理  
> 按管理方式分  
> 对于栈来讲，是由系统编译器自动管理，不需要程序员手动管理  
> 对于堆来讲，释放工作由程序员手动管理，不及时回收容易产生内存泄露  
> 堆：是大家共有的空间，分全局堆和局部堆。全局堆就是所有没有分配的空间，局部堆就是用户分配的空间。堆在操作系统对进程 初始化的时候分配，运行过程中也可以向系统要额外的堆，但是记得用完了要还给操作系统，要不然就是内存泄漏。堆里面一般 放的是静态数据，比如static的数据和字符串常量等，资源加载后一般也放在堆里面。一个进程的所有线程共有这些堆 ，所以对堆的操作要考虑同步和互斥的问题。程序里面编译后的数据段都是堆的一部分。  
> 栈：是个线程独有的，保存其运行状态和局部自动变量的。栈在线程开始的时候初始化，每个线程的栈互相独立，因此 ，栈是　thread safe的。每个c++对象的数据成员也存在在栈中，每个函数都有自己的栈，栈被用来在函数之间传递参数。操作系统在切换线程的时候会自动的切换栈，就是切换ss/esp寄存器。栈空间不需要在高级语言里面显式的分配 和释放。  
> 一句话总结就是  堆：由程序员分配和释放,如果不释放可能会引起内存泄漏  栈：由编译器自动分配和释放，一般存放参数值，局部变量

**2.KVO和KVC**

> KVC，即是指 NSKeyValueCoding\(键值编码\),提供一种机制来间接访问对象的属性。KVC 就是基于KVO技术来实现的。  
> KVO，提供了一种观察者的机制，通过对某个对象的某个属性添加观察者，当该属性改变，就会调用"observeValueForKeyPath:"方法。

**3.OC中创建线程的方法是什么?如果在主线程中执行代码， 方法是什么?如果想延时执行代码、方法是什么?**

> 1、线程创建有三种方法：使用NSThread创建、使用GCD的dispatch、使用子类化的NSOperation,然后将其加入NSOperationQueue;  
> 2、在主线程执行代码，方法是performSelectorOnMainThread:withObject:waitUntilDone:;  
> 3、如果想延时执行代码可以用performSelector:onThread:withObject:waitUntilDone:；

**4.指针与数组名的关系?**

> int arrayName\[4\] = {10, 20, 30, 40};  
> int \*p = \(int \*\)\(&arrayName + 1\);  
> NSLog\(@"%d", \(&arrayName  - 1\)\);  
> 1.\(&arrayName + 1\)：&arrayName是数组的地址（等价于指向arrayName数组的指针）  
> 2.增加 1 会往后移动16个字节，开始是4个字节的位置，移动后就是16个字节后面的位置（也就是目前位置是20个字节）  
> 3.最后又赋值给，int类型的指针p（int类型占4个字节）  
> 4.所以\(p - 1\)就是减去4个字节，变成为16个字节的位置，输出的\(p - 1\)值为40  
> int \*p = \(int \*\)\(&arrayName + 1\);  
> NSLog\(@"%d", \*\(p - 1\)\);//输出结果为 40

**5.\#import 和\#include有 么区别?@class呢?\#import &lt;&gt;和 \#import"" 有 么区别?**

> import是OC导入头文件的关键字,\#include是C/C++导入头文件的关键字  
> 使用\#import只导入一次不会重复导入,相当于\#include和\#pragma once;\(使用\#include可能会出现循环引用,使用\#pragma once消除这种可能\)  
> @class一般用于声明某个字符串作为类名使用,它只是声明了一个类名,没有导入.h文件中的内容,不会引起交叉编译问题  
> import&lt;&gt;代表导入系统自带的框架  
> import" "代表导入我们自己创建的文件,导入的使我们.h文件,也就是头文件

**6.属性readwrite.readonly,assign,retain,copy,nonatomic 什么作用 ? 在哪种情况下 ?**

> readwrite 是可读可写特性；需要生成getter方法和setter方法时（补充：默认属性，将生成不带额外参数的getter和setter方法（setter方法只有一个参数））  
> readonly 是只读特性  只会生成getter方法 不会生成setter方法 ;不希望属性在类外改变  
> assign 是赋值特性，setter方法将传入参数赋值给实例变量；仅设置变量时；  
> retain 表示持有特性，setter方法将传入参数先保留，再赋值，传入参数的retaincount会+1;  
> copy 表示拷贝特性，setter方法将传入对象复制一份；需要完全一份新的变量时。  
> nonatomic 非原子操作，决定编译器生成的setter getter是否是原子操作，atomic表示多线程安全，一般使  
> 用nonatomic

**7.IBOutlet 连出来的视图属性为什么可以被设置成weak?**

> 在 storyboard 中添加一个控件引用关系是这样的\(以 UIbutton 为例\): UIviewController -&gt; UIview -&gt; UIbutton  
> 此时 UIviewController 强引用着 UIview , UIview 强引用着 UIbutton , IBoutlet 连线到控制器的. m 或者. h 中作为视图的属性时用 weak 修饰就可以了, \(觉得用 strong 修饰也可以但是没有必要\)  
> 添加到子控件也是强引用: UIbutton 就是添加到了 UIviewController 的 view 上

**8  预处 指令define 声明 个常数， 以表明  中有多 少秒\(忽 闰 问题\)。**

> define SECONDS\_PER\_YEAR \(60 \* 60 \* 24 \* 365\)UL

**9.重写-个NSString类型的，retain 式声明name属性的 setter和getter 法\(MRC\)**

> 属性的三大特性:语义特性,原子特性,读写特性.  
> 同时重写setter和getter方法,@synchronized name = \_name,关联属性和实例变量  
> 如 -\(void\)setName:\(NSString \*\)name{  
> if\(\_name != name\){  
> \[\_name retain\];  
> \[\_name release\];  
> \_name = name;  
> }  
> }  
> -\(NSString \*\)name{  
> return \[\[\_name retain\]autorelease\]  
> }

**10.分析json、xml 的区别? json、xml 解析 式的底层是如何让处理的**

> \(一\)JSON与XML的区别：  
> （1）可读性方面：基本相同，XML的可读性比较好；  
> （2）可扩展性方面：都具有良好的扩展性；  
> （3）编码难度方面：相对而言，JSON的编码比较容易；  
> （4）解码难度：JSON的解码难度基本为零，XML需要考虑子节点和父节点；  
> （5）数据体积方面：JSON相对于XML来讲，数据体积小，传递的速度比较快；  
> （6）数据交互方面：JSON与javascript的交互更加方便，更容易解析处理，更好的数据交互；  
> （7）数据描述方面：XML对数据描述性比较好  
> （8）传输速度方面：JSON的速度远远快于XML。  
> （二）JSON与XML底层实现原理：  
> 　（1）JSON底层原理：遍历字符串中的字符，最终根据格式规定的特殊字符，比如{}、\[\]、：等进行区分，{}号表示字典，\[\]号表示数组，：号是字典的键和值的分水岭，最终仍是将JSON转化为字典，只不过字典中的值可能是“字典、数组或者字符串而已”。  
> 　　（2）XML底层原理：XML解析常用的解析方法有两种：DOM解析和SAX解析；DOM采用的是树形结构的方式访问XML文档，而SAX采用的是事件模型；DOM解析把XML文档转化为一个包含其内容的树，并可以对树进行遍历，使用DOM解析器的时候需要处理整个XML文档，所以对内存和性能的要求比较高；SAX在解析XML文档的时候可以触发一系列的事件，当发现给定的tag的时候，他可以激活一个回调方法，告诉该方法指定的标签已经找到，SAX对内存的要求通常会比较低，因为他让开发人员自己来决定所要处理的tag，特别是当开发人员只需要处理文档中所包含部分数据时，SAX这种扩展能力得到了更好的体现。

**11.对程序性能的优化你有什么建议?**

> 1.使用复用机制  
> 2.尽可能设置 View 为不透明  
> 3.避免臃肿的 XIB 文件  
> 4.不要阻塞主线程  
> 5.图片尺寸匹配 UIImageView  
> 6.选择合适的容器  
> 7.启用 GZIP 数据压缩  
> 8.View 的复用和懒加载机制  
> 9、缓存  
> 服务器的响应信息（response）。  
> 图片。  
> 计算值。比如：UITableView 的 row heights。  
> 10.关于图形绘制  
> 11.处理 Memory Warnings  
> 在 AppDelegate 中实现 - \[AppDelegate applicationDidReceiveMemoryWarning:\] 代理方法。  
> 在 UIViewController 中重载 didReceiveMemoryWarning 方法。  
> 监听 UIApplicationDidReceiveMemoryWarningNotification 通知。  
> 12.复用高开销的对象  
> 13.减少离屏渲染\(设置圆角和阴影的时候可以选用绘制的方法\)  
> 14.优化 UITableView  
> 通过正确的设置 reuseIdentifier 来重用 Cell。  
> 尽量减少不必要的透明 View。  
> 尽量避免渐变效果、图片拉伸和离屏渲染。  
> 当不同的行的高度不一样时，尽量缓存它们的高度值。  
> 如果 Cell 展示的内容来自网络，确保用异步加载的方式来获取数据，并且缓存服务器的 response。  
> 使用 shadowPath 来设置阴影效果。  
> 尽量减少 subview 的数量，对于 subview 较多并且样式多变的 Cell，可以考虑用异步绘制或重写 drawRect。  
> 尽量优化 - \[UITableView tableView:cellForRowAtIndexPath:\] 方法中的处理逻辑，如果确实要做一些处理，可以考虑做一次，缓存结果。  
> 选择合适的数据结构来承载数据，不同的数据结构对不同操作的开销是存在差异的。  
> 对于 rowHeight、sectionFooterHeight、sectionHeaderHeight 尽量使用常量。  
> 15.选择合适的数据存储方式  
> 在 iOS 中可以用来进行数据持有化的方案包括：  
> NSUserDefaults。只适合用来存小数据。  
> XML、JSON、Plist 等文件。JSON 和 XML 文件的差异在「选择正确的数据格式」已经说过了。  
> 使用 NSCoding 来存档。NSCoding 同样是对文件进行读写，所以它也会面临必须加载整个文件才能继续的问题。  
> 使用 SQLite 数据库。可以配合 FMDB 使用。数据的相对文件来说还是好处很多的，比如可以按需取数据、不用暴力查找等等。  
> 使用 CoreData。也是数据库技术，跟 SQLite 的性能差异比较小。但是 CoreData 是一个对象图谱模型，显得更面向对象；SQLite 就是常规的 DBMS。  
> 16.减少应用启动时间  
> 快速启动应用对于用户来说可以留下很好的印象。尤其是第一次使用时。  
> 保证应用快速启动的指导原则：  
> 尽量将启动过程中的处理分拆成各个异步处理流，比如：网络请求、数据库访问、数据解析等等。  
> 避免臃肿的 XIB 文件，因为它们会在你的主线程中进行加载。重申：Storyboard 没这个问题，放心使用。  
> 注意：在测试程序启动性能的时候，最好用与 Xcode 断开连接的设备进行测试。因为 watchdog 在使用 Xcode 进行调试的时候是不会启动的。  
> 17.使用 Autorelease Pool （内存释放池）  
> 18.imageNamed 和 imageWithContentsOfFile

**12.runloop 和线程有什么关系?**

> runloop与线程是一一对应的，一个runloop对应一个核心的线程，为什么说是核心的，是因为runloop是可以嵌套的，但是核心的只能有一个，他们的关系保存在一个全局的字典里。  
> runloop是来管理线程的，当线程的runloop被开启后，线程会在执行完任务后进入休眠状态，有了任务就会被唤醒去执行任务。  
> runloop在第一次获取时被创建，在线程结束时被销毁。  
> 对于主线程来说，runloop在程序一启动就默认创建好了。  
> 对于子线程来说，runloop是懒加载的，只有当我们使用的时候才会创建，所以在子线程用定时器要注意：确保子线程的runloop被创建，不然定时器不会回调。

**13.介绍下layoutSubview和drawRect**

> layoutSubviews调用情况  
> init初始化UIView不会触发调用  
> addSubview会触发调用  
> 改变view的width和height的时候回触发调用  
> 一个UIScrollView滚动会触发调用  
> 旋转screen会触发调用  
> 改变一个UIView大小的时候会触发superView的layoutSubviews事件  
> 直接调用setLayoutSubviews会触发调用  
> -\(void\)viewWillAppear:\(BOOL\)animated会触发一次调用  
> -\(void\)viewDidAppear:\(BOOL\)animated 看情况，可能有调用  
> drawRect调用情况  
> 如果UIView没有设置frame大小，直接导致drawRect不能被自动调用。  
> drawRect在loadView和viewDidLoad这两个方法之后调用  
> 调用sizeToFit后自动调用drawRect  
> 通过设置contentMode值为UIViewContentModeRedraw。那么每次设置或者更改frame自动调用drawRect。  
> 直接调用setNeedsDisplay或者setNeedsDisplayInRect会触发调用

**14.写个“标准“宏MIN，这个宏输两个参数并返回较小的那个**

> MIN\(A,B\) \(\(A\) &lt;= \(B\) ? \(A\) : \(B\)\)

**15.类别有什么作用**

> 1.扩展已有的类（添加方法）  
> 2.可以通过runtime添加属性

**16.什么是method swizzing?讲 讲你的使 场景以及使  时的注意事项**

> 1.给扩展添加属性  
> 2.替换系统方法的的实现

**17.讲讲iOS事件响应链的原理**

> 1、响应者链通常是由视图（UIView）构成的；  
> 2、一个视图的下一个响应者是它视图控制器（UIViewController）（如果有的话），然后再转给它的父视图（Super View）；  
> 3、视图控制器（如果有的话）的下一个响应者为其管理的视图的父视图；  
> 4、单例的窗口（UIWindow）的内容视图将指向窗口本身作为它的下一个响应者  
> 需要指出的是，Cocoa Touch应用不像Cocoa应用，它只有一个UIWindow对象，因此整个响应者链要简单一点；  
> 5、单例的应用（UIApplication）是一个响应者链的终点，它的下一个响应者指向nil，以结束整个循环。

**18.你在什么场景下会选择使 Category**

> 1.扩展已有的类（添加方法）

**19.UIview 和CAlayer 是什么关系? 你 CLayer做过什么?**

> 首先UIView可以响应事件，Layer不可以.
>
> UIView是CALayer的delegate  3. UIView主要处理事件，CALayer负责绘制就更好 4. 每个 UIView 内部都有一个 CALayer 在背后提供内容的绘制和显示，并且 UIView 的尺寸样式都由内部的 Layer 所提供。两者都有树状层级结构，layer 内部有 SubLayers，View 内部有 SubViews.但是 Layer 比 View 多了个AnchorPoint  
> 创建隐式动画 绘制边框圆角

**20.如何处理UITableVier 中Cell 动态计算高度的问题，都有哪些方案?**

> 1、你的Cell要使用AutoLayout来布局约束这是必须的；  
> 设置tableview的estimatedRowHeight为一个非零值，这个属性是设置一个预估的高度值，不用太精确。  
> 设置tableview的rowHeight属性为UITableViewAutomaticDimension  
> 2.第三方 UITableView+FDTemplateLayoutCell

**21.AutoLayout 中的优先级是什么? UIScrollView 中使用Autolayout 会出现什么问题?**

> 代码计算frame -&gt; autoreszing\(父控件和子控件的关系\) -&gt; autolayout\(任何控件都可以产生关系\) -&gt; sizeclass  
> 可以设置两个看似有冲突的约束，但设置不同的优先级之后就不会有冲突了，当其中一个约束失效之后，另一个优先级比较低的约束就会起作用

**22.NSIRLConnection 和NSLRLSession 的区别是 么? NSURLProtocol是做什么的?**

> 1.下载  
> NSURLConnection下载文件时，先是将整个文件下载到内存，然后再写入到沙盒，如果文件比较大，就会出现内存暴涨的情况。  
> 而使用NSURLSessionUploadTask下载文件，会默认下载到沙盒中的tem文件中，不会出现内存暴涨的情况，但是在下载完成后会把tem中的临时文件删除，需要在初始化任务方法时，在completionHandler回调中增加保存文件的代码  
> 2.请求方法的控制  
> NSURLConnection实例化对象，实例化开始，默认请求就发送\(同步发送\),不需要调用start方法。而cancel可以停止请求的发送，停止后不能继续访问，需要创建新的请求。  
> NSURLSession有三个控制方法，取消\(cancel\)、暂停\(suspend\)、继续\(resume\)，暂停以后可以通过继续恢复当前的请求任务。  
> 使用NSURLSession进行断点下载更加便捷.  
> NSURLSession的构造方法（sessionWithConfiguration:delegate:delegateQueue）中有一个NSURLSessionConfiguration类的参数可以设置配置信息，其决定了cookie，安全和高速缓存策略，最大主机连接数，资源管理，网络超时等配置。NSURLConnection不能进行这个配置，相比较与NSURLConnection依赖与一个全局的配置对象，缺乏灵活性而言，NSURLSession有很大的改进

**23.怎么高效的实现控件的圆角效果**

> 绘制圆角  
> -\(UIImageView \*\)roundedRectImageViewWithCornerRadius:\(CGFloat\)cornerRadius {  
> UIBezierPath \*bezierPath = \[UIBezierPath bezierPathWithRoundedRect:self.bounds cornerRadius:cornerRadius\];  
> CAShapeLayer \*layer = \[CAShapeLayer layer\];  
> layer.path = bezierPath.CGPath;  
> self.layer.mask = layer;  
> return self;  
> }

**24.说说你了解weak属性?**

> weak关键字在OC中属于比较基础的知识此特性表明该属性定义了一种关系“非拥有关系”（nonowning relationship）。为这种属性设置新值得时，设置方法既不保留新值，也不释放旧值。此特性同assign类似，然后在属性所指的对象遭到摧毁时，属性值也会清空（nil out）。  
> 弱引用，不决定对象的存亡。即使一个对象被持有无数个弱引用，只要没有强引用指向它，那么还是会被清除。

**25.假如Controller太臃肿，如何优化?**

> 1.将网络请求抽象到单独的类中  
> 方便在基类中处理公共逻辑；  
> 方便在基类中处理缓存逻辑，以及其它一些公共逻辑；  
> 方便做对象的持久化。  
> 2.将界面的封装抽象到专门的类中  
> 构造专门的 UIView 的子类，来负责这些控件的拼装。这是最彻底和优雅的方式，不过稍微麻烦一些的是，你需要把这些控件的事件回调先接管，再都一一暴露回 Controller。  
> 3.构造 ViewModel  
> 借鉴MVVM。具体做法就是将 ViewController 给 View 传递数据这个过程，抽象成构造 ViewModel 的过程。  
> 4.专门构造存储类  
> 专门来处理本地数据的存取。  
> 5.整合常量

**26.项目中网络层如何做安全处理?**

> 1.判断API的调用请求是否来自于经过授权的APP。如若不是则拒绝请求访问  
> 2.在数据请求的过程中进行URL加密处理：防止反编译，接口信息被静态分析。  
> 3.数据传输加密：对客户端传输数据提供有效的加密方案，以防止网络接口的拦截。  
> 如果可以尽量使用HTTPS，可以有效的避免接口数据在传输中被攻击。

**27.main\(\)之前的过程有哪些?**

> 在iOS中 main.m 是我们所熟悉的程序入口。但是在在此之前其实程序以及做了很多事了。如系统会获取dyld的路径，并加载。加载程序中的依赖库。调用所有的+ load方法，并返回main函数地址。

**其他值得看的总结：**

[见过的最全的iOS面试题](https://link.jianshu.com/?t=http%3A%2F%2Fwww.cnblogs.com%2Flinfenren%2Fp%2F6001139.html)  
[iOS最新面试题汇总](https://www.jianshu.com/p/d7cffbeadc1c)  
[招聘一个靠谱的 iOS](https://link.jianshu.com/?t=https%3A%2F%2Fgithub.com%2FChenYilong%2FiOSInterviewQuestions%2F)

**BAT面试题**

出自：[不懂技术的爱迪生](https://www.jianshu.com/u/37860723842a)

腾讯一面  
1.使用了第三方库, 有看它们是怎么实现的吗？  
2.强连通量算法了解嘛？  
3.遇到tableView卡顿嘛？会造成卡顿的原因大致有哪些？  
4.M、V、C相互通讯规则你知道的有哪些？  
5.NStimer准吗？谈谈你的看法？如果不准该怎样实现一个精确的NSTimer?  
答案详见：[https://www.jianshu.com/p/0e9e7486e1a7](https://www.jianshu.com/p/0e9e7486e1a7)

腾讯二面：  
1.编译过程做了哪些事情；  
2.字典大致实现原理；  
3.block和函数指针的理解；  
4.一般开始做一个项目，你的架构是如何思考的？  
5.你了解的UIKit结构？  
答案详见：[https://www.jianshu.com/p/dd17bdcff9f7](https://www.jianshu.com/p/dd17bdcff9f7)

腾讯三面  
1.OC你了解的锁有哪些？在你回答基础上进行二次提问；  
追问一：自旋和互斥对比？  
追问二：用C/OC/C++，任选其一，实现自旋或互斥？口述即可！  
2.内存泄漏可能会出现的几种原因，聊聊你的看法？  
追问一：非OC对象如何处理？  
追问二：若常用框架出现内存泄漏如何处理？  
3.容错处理你们一般是怎么做的？  
4.项目开始容错处理没做？如何防止拦截潜在的崩溃？  
答案详见：[https://www.jianshu.com/p/3a50d1805655](https://www.jianshu.com/p/3a50d1805655)

阿里  
1.dSYM你是如何分析的？  
2.多线程有哪几种？你更倾向于哪一种？  
3.单例弊端？  
4.如何把异步线程转换成同步任务进行单元测试？  
5.介绍下App启动的完成过程？  
6.比如App启动过慢，你可能想到的因素有哪些？  
7.0x8badf00d表示是什么？  
8.怎么防止反编译？  
9.说说你遇到到的技术难点？  
10.说说你了解的第三方原理或底层知识？  
答案详见：[http://url.cn/5oWSdgZ](http://url.cn/5oWSdgZ)

## **2018.4.17整理**

参考：  
[2017年最新 iOS面试题及答案](https://link.jianshu.com/?t=http%3A%2F%2Fblog.csdn.net%2Ftfy_2425482491%2Farticle%2Fdetails%2F75214148%23t3)  
[2017秋季校园招聘iOS开发岗位面试题集锦](https://link.jianshu.com/?t=http%3A%2F%2Fblog.csdn.net%2FCHENYUFENG1991%2Farticle%2Fdetails%2F53472284)  
[iOS面试题300+](https://www.jianshu.com/p/0d2713164646?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)  
[2017年5月iOS招人心得（附面试题）](https://www.jianshu.com/p/56e40ea56813)  
[2017年iOS面试题总结](https://www.jianshu.com/p/f9eb6b315c08)  
[iOS 面试题集锦](https://link.jianshu.com/?t=https%3A%2F%2Fgithub.com%2FChenYilong%2FiOSInterviewQuestions)

#### 目录

```
一、基础知识点
二、第三方框架
三、算法
四、编码格式（优化细节）
五、其他知识点
```

#### 一、基础知识点

1. _**设计模式是什么？ 你知道哪些设计模式，并简要叙述？**_

   > 设计模式是一种编码经验，就是用比较成熟的逻辑去处理某一种类型的事情。  
   > 1\). MVC模式：Model View Control，把模型 视图 控制器 层进行解耦合编写。  
   > 2\). MVVM模式：Model View ViewModel 把模型 视图 业务逻辑 层进行解耦和编写。  
   > 3\). 单例模式：通过static关键词，声明全局变量。在整个进程运行期间只会被赋值一次。  
   > 4\). 观察者模式：KVO是典型的观察者模式，观察某个属性的状态，状态发生变化时通知观察者。  
   > 5\). 委托模式：代理+协议的组合。实现1对1的反向传值操作。  
   > 6\). 工厂模式：通过一个类方法，批量的根据已有模板生产对象。

2. _**MVC 和 MVVM 的区别**_

   > MVVM是对胖模型进行的拆分，其本质是给控制器减负，将一些弱业务逻辑放到VM中去处理。  
   > MVC是一切设计的基础，所有新的设计模式都是基于MVC进行的改进。  
   > 参考：[iOS MVVM架构总结](https://www.jianshu.com/p/f1d0f7f01130)

3. _**\#import跟 \#include 有什么区别，@class呢，\#import&lt;&gt; 跟 \#import””有什么区别？**_

   > 1\). \#import是Objective-C导入头文件的关键字，\#include是C/C++导入头文件的关键字，使用\#import头文件会自动只导入一次，不会重复导入。  
   > 2\). @class告诉编译器某个类的声明，当执行时，才去查看类的实现文件，可以解决头文件的相互包含。  
   > 3\). \#import&lt;&gt;用来包含系统的头文件，\#import””用来包含用户头文件。

4. _**frame 和 bounds 有什么不同？**_

   > frame指的是：该view在父view坐标系统中的位置和大小。\(参照点是父view的坐标系统\)  
   > bounds指的是：该view在本身坐标系统中的位置和大小。\(参照点是本身坐标系统\)

5. _**Objective-C的类可以多重继承么？可以实现多个接口么？Category是什么？重写一个类的方法用继承好还是分类好？为什么？**_

   > 答：Objective-C的类不可以多重继承；可以实现多个接口（协议）；Category是类别；一般情况用分类好，用Category去重写类的方法，仅对本Category有效，不会影响到其他类与原有类的关系。

6. _**@property 的本质是什么？ivar、getter、setter 是如何生成并添加到这个类中的**_

   > @property 的本质是什么？  
   > @property = ivar + getter + setter;  
   > “属性” \(property\)有两大概念：ivar（实例变量）、getter+setter（存取方法）  
   > “属性” \(property\)作为 Objective-C 的一项特性，主要的作用就在于封装对象中的数据。 Objective-C 对象通常会把其所需要的数据保存为各种实例变量。实例变量一般通过“存取方法”\(access method\)来访问。其中，“获取方法” \(getter\)用于读取变量值，而“设置方法” \(setter\)用于写入变量值。

7. _**@property中有哪些属性关键字？/ @property 后面可以有哪些修饰符？**_

   > 属性可以拥有的特质分为四类:  
   > 1.原子性--- nonatomic 特质  
   > 2.读/写权限---readwrite\(读写\)、readonly \(只读\)  
   > 3.内存管理语义---assign、strong、 weak、unsafe\_unretained、copy  
   > 4.方法名---getter=、setter=  
   > 5.不常用的：nonnull,null\_resettable,nullable

8. _**属性关键字 readwrite，readonly，assign，retain，copy，nonatomic 各是什么作用，在那种情况下用？**_

   > 1\). readwrite 是可读可写特性。需要生成getter方法和setter方法。  
   > 2\). readonly 是只读特性。只会生成getter方法，不会生成setter方法，不希望属性在类外改变。  
   > 3\). assign 是赋值特性。setter方法将传入参数赋值给实例变量;仅设置变量时,assign用于基本数据类型。  
   > 4\). retain\(MRC\)/strong\(ARC\) 表示持有特性。setter方法将传入参数先保留，再赋值，传入参数的retaincount会+1。  
   > 5\). copy 表示拷贝特性。setter方法将传入对象复制一份，需要完全一份新的变量时。  
   > 6\). nonatomic 非原子操作。不写的话默认就是atomic。atomic 和 nonatomic 的区别在于，系统自动生成的 getter/setter 方法不一样。对于atomic的属性，系统生成的 getter/setter 会保证 get、set 操作的完整性，而nonatomic就没有这个保证了。所以，nonatomic的速度要比atomic快。  
   > 不过atomic可并不能保证线程安全。  
   > 参考：[\[爆栈热门 iOS 问题\] atomic 和 nonatomic 有什么区别？](https://www.jianshu.com/p/7288eacbb1a2)

9. _**什么情况使用 weak 关键字，相比 assign 有什么不同？**_

   > 1.在 ARC 中,在有可能出现循环引用的时候,往往要通过让其中一端使用 weak 来解决,比如: delegate 代理属性。  
   > 2.自身已经对它进行一次强引用,没有必要再强引用一次,此时也会使用 weak,自定义 IBOutlet 控件属性一般也使用 weak；当然，也可以使用strong。  
   >   
   > IBOutlet连出来的视图属性为什么可以被设置成weak?  
   > 因为父控件的subViews数组已经对它有一个强引用。  
   >   
   > 不同点：  
   > assign 可以用非 OC 对象，而 weak 必须用于 OC 对象。  
   > weak 表明该属性定义了一种“非拥有关系”。在属性所指的对象销毁时，属性值会自动清空\(nil\)。

10. _**怎么用 copy 关键字？**_

    > 用途：  
    > 1. NSString、NSArray、NSDictionary 等等经常使用copy关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary；  
    > 2. block 也经常使用 copy 关键字。  
    >   
    > 说明：  
    > block 使用 copy 是从 MRC 遗留下来的“传统”,在 MRC 中,方法内部的 block 是在栈区的,使用 copy 可以把它放到堆区.在 ARC 中写不写都行：对于 block 使用 copy 还是 strong 效果是一样的，但写上 copy 也无伤大雅，还能时刻提醒我们：编译器自动对 block 进行了 copy 操作。如果不写 copy ，该类的调用者有可能会忘记或者根本不知道“编译器会自动对 block 进行了 copy 操作”，他们有可能会在调用之前自行拷贝属性值。这种操作多余而低效。

11. _**用@property声明的 NSString / NSArray / NSDictionary 经常使用 copy 关键字，为什么？如果改用strong关键字，可能造成什么问题？**_

    > 答：用 @property 声明 NSString、NSArray、NSDictionary 经常使用 copy 关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary，他们之间可能进行赋值操作（就是把可变的赋值给不可变的），为确保对象中的字符串值不会无意间变动，应该在设置新属性值时拷贝一份。  
    >   
    > 1. 因为父类指针可以指向子类对象,使用 copy 的目的是为了让本对象的属性不受外界影响,使用 copy 无论给我传入是一个可变对象还是不可对象,我本身持有的就是一个不可变的副本。  
    > 2. 如果我们使用是 strong ,那么这个属性就有可能指向一个可变对象,如果这个可变对象在外部被修改了,那么会影响该属性。  
    >   
    > 总结：使用copy的目的是，防止把可变类型的对象赋值给不可变类型的对象时，可变类型对象的值发送变化会无意间篡改不可变类型对象原来的值。

12. _**浅拷贝和深拷贝的区别？**_

    > 浅拷贝：只复制指向对象的指针，而不复制引用对象本身。  
    > 深拷贝：复制引用对象本身。内存中存在了两份独立对象本身，当修改A时，A\_copy不变。

13. _**系统对象的 copy 与 mutableCopy 方法**_

    > 不管是集合类对象（NSArray、NSDictionary、NSSet ... 之类的对象），还是非集合类对象（NSString, NSNumber ... 之类的对象），接收到copy和mutableCopy消息时，都遵循以下准则：  
    > 1. copy 返回的是不可变对象（immutableObject）；如果用copy返回值调用mutable对象的方法就会crash。  
    > 2. mutableCopy 返回的是可变对象（mutableObject）。

```
一、非集合类对象的copy与mutableCopy
      在非集合类对象中，对不可变对象进行copy操作，是指针复制，mutableCopy操作是内容复制；
      对可变对象进行copy和mutableCopy都是内容复制。用代码简单表示如下： NSString *str = @"hello word!"; NSString *strCopy = [str copy] // 指针复制，strCopy与str的地址一样 NSMutableString *strMCopy = [str mutableCopy] // 内容复制，strMCopy与str的地址不一样   NSMutableString *mutableStr = [NSMutableString stringWithString: @"hello word!"]; NSString *strCopy = [mutableStr copy] // 内容复制 NSMutableString *strMCopy = [mutableStr mutableCopy] // 内容复制
```

```
二、集合类对象的copy与mutableCopy (同上)
      在集合类对象中，对不可变对象进行copy操作，是指针复制，mutableCopy操作是内容复制；
      对可变对象进行copy和mutableCopy都是内容复制。但是：集合对象的内容复制仅限于对象本身，对集合内的对象元素仍然是指针复制。(即单层内容复制) NSArray *arr = @[@[@"a", @"b"], @[@"c", @"d"]; NSArray *copyArr = [arr copy]; // 指针复制 NSMutableArray *mCopyArr = [arr mutableCopy]; //单层内容复制 NSMutableArray *array = [NSMutableArray arrayWithObjects:[NSMutableString stringWithString:@"a"],@"b",@"c",nil]; NSArray *copyArr = [mutableArr copy]; // 单层内容复制 NSMutableArray *mCopyArr = [mutableArr mutableCopy]; // 单层内容复制
```

> 【总结一句话】：  
> 只有对不可变对象进行copy操作是指针复制（浅复制），其它情况都是内容复制（深复制）！

1. _**这个写法会出什么问题：@property \(nonatomic, copy\) NSMutableArray \*arr;**_

   > 问题：添加,删除,修改数组内的元素的时候,程序会因为找不到对应的方法而崩溃。  
   > //如：-\[\_\_NSArrayI removeObjectAtIndex:\]: unrecognized selector sent to instance 0x7fcd1bc30460  
   > // copy后返回的是不可变对象（即 arr 是 NSArray 类型，NSArray 类型对象不能调用 NSMutableArray 类型对象的方法）  
   > 原因：是因为 copy 就是复制一个不可变 NSArray 的对象，不能对 NSArray 对象进行添加/修改。

2. _**如何让自己的类用 copy 修饰符？如何重写带 copy 关键字的 setter？**_

   > 若想令自己所写的对象具有拷贝功能，则需实现 NSCopying 协议。如果自定义的对象分为可变版本与不可变版本，那么就要同时实现 NSCopying 与 NSMutableCopying 协议。  
   > 具体步骤：  
   > 1. 需声明该类遵从 NSCopying 协议  
   > 2. 实现 NSCopying 协议的方法。  
   > // 该协议只有一个方法:
   >
   > * \(id\)copyWithZone:\(NSZone \*\)zone;  
   >   // 注意：使用 copy 修饰符，调用的是copy方法，其实真正需要实现的是 “copyWithZone” 方法。

3. _**写一个 setter 方法用于完成 @property \(nonatomic, retain\) NSString \*name，写一个 setter 方法用于完成 @property \(nonatomic, copy\) NSString \*name**_

```
// retain - (void)setName:(NSString *)str {
      [str retain];
      [_name release];
      _name = str;
    } // copy - (void)setName:(NSString *)str {
      id t = [str copy];
      [_name release];
      _name = t;
    }
```

1. _**@synthesize 和 @dynamic 分别有什么作用？**_

   > @property有两个对应的词，一个是@synthesize（合成实例变量），一个是@dynamic。  
   > 如果@synthesize和@dynamic都没有写，那么默认的就是 @synthesize var = \_var;  
   > // 在类的实现代码里通过 @synthesize 语法可以来指定实例变量的名字。\(@synthesize var = \_newVar;\)  
   > 1. @synthesize 的语义是如果你没有手动实现setter方法和getter方法，那么编译器会自动为你加上这两个方法。  
   > 2. @dynamic 告诉编译器，属性的setter与getter方法由用户自己实现，不自动生成（如，@dynamic var）。

2. _**常见的 Objective-C 的数据类型有那些，和C的基本数据类型有什么区别？如：NSInteger和int**_

   > Objective-C的数据类型有NSString，NSNumber，NSArray，NSMutableArray，NSData等等，这些都是class，创建后便是对象，而C语言的基本数据类型int，只是一定字节的内存空间，用于存放数值;NSInteger是基本数据类型，并不是NSNumber的子类，当然也不是NSObject的子类。NSInteger是基本数据类型Int或者Long的别名\(NSInteger的定义typedef long NSInteger\)，它的区别在于，NSInteger会根据系统是32位还是64位来决定是本身是int还是long。

3. _**id 声明的对象有什么特性？**_

   > id 声明的对象具有运行时的特性，即可以指向任意类型的Objcetive-C的对象。

4. _**Objective-C 如何对内存管理的，说说你的看法和解决方法？**_

   > 答：Objective-C的内存管理主要有三种方式ARC\(自动内存计数\)、手动内存计数、内存池。  
   > 1\). 自动内存计数ARC：由Xcode自动在App编译阶段，在代码中添加内存管理代码。  
   > 2\). 手动内存计数MRC：遵循内存谁申请、谁释放；谁添加，谁释放的原则。  
   > 3\). 内存释放池Release Pool：把需要释放的内存统一放在一个池子中，当池子被抽干后\(drain\)，池子中所有的内存空间也被自动释放掉。内存池的释放操作分为自动和手动。自动释放受runloop机制影响。

5. _**Objective-C 中创建线程的方法是什么？如果在主线程中执行代码，方法是什么？如果想延时执行代码、方法又是什么？**_

   > 答：线程创建有三种方法：使用NSThread创建、使用GCD的dispatch、使用子类化的NSOperation,然后将其加入NSOperationQueue;在主线程执行代码，方法是performSelectorOnMainThread，如果想延时执行代码可以用performSelector:onThread:withObject:waitUntilDone:

6. _**Category（类别）、 Extension（扩展）和继承的区别**_

   > 区别：  
   > 1. 分类有名字，类扩展没有分类名字，是一种特殊的分类。  
   > 2. 分类只能扩展方法（属性仅仅是声明，并没真正实现），类扩展可以扩展属性、成员变量和方法。  
   > 3. 继承可以增加，修改或者删除方法，并且可以增加属性。

7. _**我们说的OC是动态运行时语言是什么意思？**_

   > 答：主要是将数据类型的确定由编译时，推迟到了运行时。简单来说, 运行时机制使我们直到运行时才去决定一个对象的类别,以及调用该类别对象指定方法。

8. _**为什么我们常见的delegate属性都用是week而不是retain/strong？**_

   > 答：是为了防止delegate两端产生不必要的循环引用。  
   > @property \(nonatomic, weak\) iddelegate;

9. _**什么时候用delete，什么时候用Notification？**_

   > Delegate\(委托模式\)：1对1的反向消息通知功能。  
   > Notification\(通知模式\)：只想要把消息发送出去，告知某些状态的变化。但是并不关心谁想要知道这个。

10. _**什么是 KVO 和 KVC？**_

    > 1\). KVC\(Key-Value-Coding\)：键值编码 是一种通过字符串间接访问对象的方式（即给属性赋值）  
    > 举例说明：  
    > [stu.name](https://link.jianshu.com/?t=http%3A%2F%2Fstu.name) = @"张三" // 点语法给属性赋值  
    > \[stu setValue:@"张三" forKey:@"name"\]; // 通过字符串使用KVC方式给属性赋值  
    > stu1.nameLabel.text = @"张三";  
    > \[stu1 setValue:@"张三" forKey:@"nameLabel.text"\]; // 跨层赋值  
    > 2\). KVO\(key-Value-Observing\)：键值观察机制 他提供了观察某一属性变化的方法，极大的简化了代码。  
    > KVO只能被KVC触发，包括使用setValue:forKey:方法和点语法。  
    > // 通过下方方法为属性添加KVO观察
    >
    > * \(void\)addObserver:\(NSObject \*\)observer forKeyPath:\(NSString \*\)keyPath options:\(NSKeyValueObservingOptions\)options context:\(nullable void \*\)context;
    >
    >   // 当被观察的属性发送变化时，会自动触发下方方法
    >
    > * \(void\)observeValueForKeyPath:\(NSString \*\)keyPath ofObject:\(id\)object change:\(NSDictionary \*\)change context:\(void \*\)context;
    >
    >   KVC 和 KVO 的 keyPath 可以是属性、实例变量、成员变量。  
    >   [iOS 成员变量，属性变量，局部变量，实例变量，全局变量 详解](https://link.jianshu.com/?t=http%3A%2F%2Fblog.csdn.net%2Fchenshun123%2Farticle%2Fdetails%2F52280564)

11. _**KVC的底层实现？**_

    > 当一个对象调用setValue方法时，方法内部会做以下操作：  
    > 1\). 检查是否存在相应的key的set方法，如果存在，就调用set方法。  
    > 2\). 如果set方法不存在，就会查找与key相同名称并且带下划线的成员变量，如果有，则直接给成员变量属性赋值。  
    > 3\). 如果没有找到\_key，就会查找相同名称的属性key，如果有就直接赋值。  
    > 4\). 如果还没有找到，则调用valueForUndefinedKey:和setValue:forUndefinedKey:方法。  
    > 这些方法的默认实现都是抛出异常，我们可以根据需要重写它们。

12. _**KVO的底层实现？**_

    > KVO基于runtime机制实现。  
    > [探究KVO的底层实现原理](https://www.jianshu.com/p/829864680648)

13. _**ViewController生命周期**_

    > 按照执行顺序排列：  
    > 1. initWithCoder：通过nib文件初始化时触发。  
    > 2. awakeFromNib：nib文件被加载的时候，会发生一个awakeFromNib的消息到nib文件中的每个对象。  
    > 3. loadView：开始加载视图控制器自带的view。  
    > 4. viewDidLoad：视图控制器的view被加载完成。  
    > 5. viewWillAppear：视图控制器的view将要显示在window上。  
    > 6. updateViewConstraints：视图控制器的view开始更新AutoLayout约束。  
    > 7. viewWillLayoutSubviews：视图控制器的view将要更新内容视图的位置。  
    > 8. viewDidLayoutSubviews：视图控制器的view已经更新视图的位置。  
    > 9. viewDidAppear：视图控制器的view已经展示到window上。  
    > 10. viewWillDisappear：视图控制器的view将要从window上消失。  
    > 11. viewDidDisappear：视图控制器的view已经从window上消失。

14. _**方法和选择器有何不同？**_

    > selector是一个方法的名字，方法是一个组合体，包含了名字和实现。

15. _**你是否接触过OC中的反射机制？简单聊一下概念和使用**_

    > 1\). class反射  
    > 通过类名的字符串形式实例化对象。  
    > Class class = NSClassFromString\(@"student"\);  
    > Student \*stu = \[\[class alloc\] init\];  
    > 将类名变为字符串。  
    > Class class =\[Student class\];  
    > NSString _className = NSStringFromClass\(class\);  
    > 2\). SEL的反射  
    > 通过方法的字符串形式实例化方法。  
    > SEL selector = NSSelectorFromString\(@"setName"\);  
    > \[stu performSelector:selector withObject:@"Mike"\];  
    > 将方法变成字符串。  
    > NSStringFromSelector\(@selector_\(setName:\)\);

16. _**调用方法有两种方式：**_

    > 1\). 直接通过方法名来调用。\[person show\];  
    > 2\). 间接的通过SEL数据来调用 。SEL aaa = @selector\(show\); \[person performSelector:aaa\];

17. _**如何对iOS设备进行性能测试？**_

    > 答： Profile-&gt; Instruments -&gt;Time Profiler

18. _**开发项目时你是怎么检查内存泄露？**_

    > 1\). 静态分析 analyze。  
    > 2\). instruments工具里面有个leak可以动态分析。

19. _**什么是懒加载？**_

    > 答：懒加载就是只在用到的时候才去初始化。也可以理解成延时加载。  
    > 我觉得最好也最简单的一个例子就是tableView中图片的加载显示了, 一个延时加载, 避免内存过高,一个异步加载,避免线程堵塞提高用户体验。

20. _**类变量的 @public，@protected，@private，@package 声明各有什么含义？**_

    > @public 任何地方都能访问;  
    > @protected 该类和子类中访问,是默认的;  
    > @private 只能在本类中访问;  
    > @package 本包内使用,跨包不可以。

21. _**什么是谓词？**_

    > 谓词就是通过NSPredicate给定的逻辑条件作为约束条件,完成对数据的筛选。  
    > //定义谓词对象,谓词对象中包含了过滤条件\(过滤条件比较多\)  
    > NSPredicate \*predicate = \[NSPredicate predicateWithFormat:@"age&lt;%d",30\];  
    > //使用谓词条件过滤数组中的元素,过滤之后返回查询的结果  
    > NSArray \*array = \[persons filteredArrayUsingPredicate:predicate\];

22. _**isa指针问题**_

    > isa：是一个Class 类型的指针. 每个实例对象有个isa的指针,他指向对象的类,而Class里也有个isa的指针, 指向meteClass\(元类\)。元类保存了类方法的列表。当类方法被调 用时,先会从本身查找类方法的实现,如果没有,元类会向他父类查找该方法。同时注意的是:元类\(meteClass\)也是类,它也是对象。元类也有isa指针,它的isa指针最终指向的是一个根元类\(root meteClass\)。根元类的isa指针指向本身,这样形成了一个封闭的内循环。

23. _**如何访问并修改一个类的私有属性？**_

    > 1\). 一种是通过KVC获取。  
    > 2\). 通过runtime访问并修改私有属性。

24. _**一个objc对象的isa的指针指向什么？有什么作用？**_

    > 答：指向他的类对象,从而可以找到对象上的方法。

25. _**下面的代码输出什么？**_

    > @implementation Son : Father
    >
    > * \(id\)init {  
    >   if \(self = \[super init\]\) {  
    >   NSLog\(@"%@", NSStringFromClass\(\[self class\]\)\); // Son  
    >   NSLog\(@"%@", NSStringFromClass\(\[super class\]\)\); // Son  
    >   }  
    >   return self;  
    >   }  
    >   @end  
    >   // 解析：  
    >   self 是类的隐藏参数，指向当前调用方法的这个类的实例。  
    >   super是一个Magic Keyword，它本质是一个编译器标示符，和self是指向的同一个消息接收者。  
    >   不同的是：super会告诉编译器，调用class这个方法时，要去父类的方法，而不是本类里的。  
    >   上面的例子不管调用\[self class\]还是\[super class\]，接受消息的对象都是当前 Son \*obj 这个对象。

26. _**写一个完整的代理，包括声明、实现**_

```
// 创建 @protocol MyDelagate @required -(void)eat:(NSString *)foodName; 
    @optional -(void)run;
    @end //  声明 .h @interface person: NSObject


    @end //  实现 .m @implementation person - (void)eat:(NSString *)foodName { NSLog(@"吃:%@!", foodName);
    } 
    - (void)run { NSLog(@"run!");
    }

    @end
```

1. _**isKindOfClass、isMemberOfClass、selector作用分别是什么**_

   > isKindOfClass：作用是某个对象属于某个类型或者继承自某类型。  
   > isMemberOfClass：某个对象确切属于某个类型。  
   > selector：通过方法名，获取在内存中的函数的入口地址。

2. _**delegate 和 notification 的区别**_

   > 1\). 二者都用于传递消息，不同之处主要在于一个是一对一的，另一个是一对多的。  
   > 2\). notification通过维护一个array，实现一对多消息的转发。  
   > 3\). delegate需要两者之间必须建立联系，不然没法调用代理的方法；notification不需要两者之间有联系。

3. _**什么是block？**_

   > 闭包（block）：闭包就是获取其它函数局部变量的匿名函数。

4. _**block反向传值**_

```
*   在控制器间传值可以使用代理或者block，使用block相对来说简洁。

*  在前一个控制器的touchesBegan:方法内实现如下代码。 // OneViewController.m TwoViewController *twoVC = [[TwoViewController alloc] init];
      twoVC.valueBlcok = ^(NSString *str) { NSLog(@"OneViewController拿到值：%@", str); 
      };
      [self presentViewController:twoVC animated:YES completion:nil]; // TwoViewController.h   （在.h文件中声明一个block属性） @property (nonatomic ,strong) void(^valueBlcok)(NSString *str); // TwoViewController.m   （在.m文件中实现方法） - (void)touchesBegan:(NSSet
 *)touches withEvent:(UIEvent *)event { // 传值:调用block if (_valueBlcok) {
            _valueBlcok(@"123456");
        }
    }
```

1. _**block的注意点**_

   > 1\). 在block内部使用外部指针且会造成循环引用情况下，需要用\_\_week修饰外部指针：  
   > \_\_weak typeof\(self\) weakSelf = self;  
   > 2\). 在block内部如果调用了延时函数还使用弱指针会取不到该指针，因为已经被销毁了，需要在block内部再将弱指针重新强引用一下。  
   > \_\_strong typeof\(self\) strongSelf = weakSelf;  
   > 3\). 如果需要在block内部改变外部栈区变量的话，需要在用\_\_block修饰外部变量。

2. _**BAD\_ACCESS在什么情况下出现？**_

   > 答：这种问题在开发时经常遇到。原因是访问了野指针，比如访问已经释放对象的成员变量或者发消息、死循环等。

3. _**lldb（gdb）常用的控制台调试命令？**_

   > 1\). p 输出基本类型。是打印命令，需要指定类型。是print的简写  
   > p \(int\)\[\[\[self view\] subviews\] count\]  
   > 2\). po 打印对象，会调用对象description方法。是print-object的简写  
   > po \[self view\]  
   > 3\). expr 可以在调试时动态执行指定表达式，并将结果打印出来。常用于在调试过程中修改变量的值。  
   > 4\). bt：打印调用堆栈，是thread backtrace的简写，加all可打印所有thread的堆栈  
   > 5\). br l：是breakpoint list的简写

4. _**你一般是怎么用Instruments的？**_

   > Instruments里面工具很多，常用：  
   > 1\). Time Profiler: 性能分析  
   > 2\). Zombies：检查是否访问了僵尸对象，但是这个工具只能从上往下检查，不智能。  
   > 3\). Allocations：用来检查内存，写算法的那批人也用这个来检查。  
   > 4\). Leaks：检查内存，看是否有内存泄露。

5. _**iOS中常用的数据存储方式有哪些？**_

   > 数据存储有四种方案：NSUserDefault、KeyChain、File、DB。  
   > 其中File有三种方式：writeToFile:atomically:、Plist、NSKeyedAchiever（归档）  
   > DB包括：SQLite、FMDB、CoreData

6. _**iOS的沙盒目录结构是怎样的？**_

   > 沙盒结构：  
   > 1. AppName.app 目录：这是应用程序的程序包目录，包含应用程序的本身。由于应用程序必须经过签名，所以您在运行时不能对这个目录中的内容进行修改，否则可能会使应用程序无法启动。  
   > 2. Documents：您应该将所有的应用程序数据文件写入到这个目录下。这个目录用于存储用户数据。iCloud备份目录。（这里不能存缓存文件，否则上架不被通过）  
   > 3. Library 目录：这个目录下有两个子目录：  
   > Preferences 目录：包含应用程序的偏好设置文件。您不应该直接创建偏好设置文件，而是应该使用NSUserDefaults类来取得和设置应用程序的偏好.  
   > Caches 目录：用于存放应用程序专用的支持文件，保存应用程序再次启动过程中需要的信息。  
   > 可创建子文件夹。可以用来放置您希望被备份但不希望被用户看到的数据。该路径下的文件夹，除Caches以外，都会被iTunes备份。  
   > 4. tmp：存放临时文件，不会被备份，而且这个文件下的数据有可能随时被清除的可能。

7. _**iOS多线程技术有哪几种方式？**_

   > 答：pthread、NSThread、GCD、NSOperation

8. _**GCD 与 NSOperation 的区别：**_

   > GCD 和 NSOperation 都是用于实现多线程：  
   > GCD 基于C语言的底层API，GCD主要与block结合使用，代码简洁高效。  
   > NSOperation 属于Objective-C类，是基于GCD更高一层的封装。复杂任务一般用NSOperation实现。

9. _**写出使用GCD方式从子线程回到主线程的方法代码**_

   > 答：dispatch\_sync\(dispatch\_get\_main\_queue\(\), ^{ }\);

10. _**如何用GCD同步若干个异步调用？（如根据若干个url异步加载多张图片，然后在都下载完成后合成一张整图）**_

    > // 使用Dispatch Group追加block到Global Group Queue,这些block如果全部执行完毕，就会执行Main Dispatch Queue中的结束处理的block。  
    > // 创建队列组  
    > dispatch\_group\_t group = dispatch\_group\_create\(\);  
    > // 获取全局并发队列  
    > dispatch\_queue\_t queue = dispatch\_get\_global\_queue\(DISPATCH\_QUEUE\_PRIORITY\_DEFAULT, 0\);  
    > dispatch\_group\_async\(group, queue, ^{ /\*加载图片1 _/ }\);  
    > dispatch\_group\_async\(group, queue, ^{ /_加载图片2 _/ }\);  
    > dispatch\_group\_async\(group, queue, ^{ /_加载图片3 \*/ }\);  
    > // 当并发队列组中的任务执行完毕后才会执行这里的代码  
    > dispatch\_group\_notify\(group, dispatch\_get\_main\_queue\(\), ^{  
    > // 合并图片  
    > }\);

11. _**dispatch\_barrier\_async（栅栏函数）的作用是什么？**_

```
函数定义：dispatch_barrier_async(dispatch_queue_t queue, dispatch_block_t block);
    作用： 1.在它前面的任务执行结束后它才执行，它后面的任务要等它执行完成后才会开始执行。 2.避免数据竞争 // 1.创建并发队列 dispatch_queue_t queue = dispatch_queue_create("myQueue", DISPATCH_QUEUE_CONCURRENT); // 2.向队列中添加任务 dispatch_async(queue, ^{ // 1.2是并行的 NSLog(@"任务1, %@",[NSThread currentThread]);
    }); dispatch_async(queue, ^{ NSLog(@"任务2, %@",[NSThread currentThread]);
    });

    dispatch_barrier_async(queue, ^{ NSLog(@"任务 barrier, %@", [NSThread currentThread]);
    }); dispatch_async(queue, ^{ // 这两个是同时执行的 NSLog(@"任务3, %@",[NSThread currentThread]);
    }); dispatch_async(queue, ^{ NSLog(@"任务4, %@",[NSThread currentThread]);
    }); // 输出结果: 任务1 任务2 ——》 任务 barrier ——》任务3 任务4  // 其中的任务1与任务2，任务3与任务4 由于是并行处理先后顺序不定。
```

1. _**以下代码运行结果如何？**_

```
- (void)viewDidLoad {
    [super viewDidLoad]; NSLog(@"1"); dispatch_sync(dispatch_get_main_queue(), ^{ NSLog(@"2");
    }); NSLog(@"3");
} // 只输出：1。（主线程死锁）
```

_**  
什么是 RunLoop**_

1. > \* 从字面上看，就是运行循环，跑圈  
   > \* 其实它内部就是do-while循环，在这个循环内部不断地处理各种任务（比如Source、Timer、Observer）  
   > \* 一个线程对应一个RunLoop，基本作用就是保持程序的持续运行，处理app中的各种事件。  
   > \* 通过runloop，有事运行，没事就休息，可以节省cpu资源，提高程序性能。  
   >   
   > 主线程的run loop默认是启动的。iOS的应用程序里面，程序启动后会有一个如下的main\(\)函数  
   > int main\(int argc, char \* argv\[\]\) {  
   > @autoreleasepool {  
   > return UIApplicationMain\(argc, argv, nil, NSStringFromClass\(\[AppDelegate class\]\)\);  
   > }  
   > }  
   > [RunLoop学习总结](https://www.jianshu.com/p/9d67e3fd6c61)
2. _**说说你对 runtime 的理解**_

   > Runtime又叫运行时，是一套底层的C语言API，其为iOS内部的核心之一，我们平时编写的OC代码，底层都是基于它来实现的。

1. _**Runtime实现的机制是什么，怎么用，一般用于干嘛？**_

   > 1\). 使用时需要导入的头文件  
   > 2\). Runtime 运行时机制，它是一套C语言库。  
   > 3\). 实际上我们编写的所有OC代码，最终都是转成了runtime库的东西。  
   > 比如：  
   > 类转成了 Runtime 库里面的结构体等数据类型，  
   > 方法转成了 Runtime 库里面的C语言函数，  
   > 平时调方法都是转成了 objc\_msgSend 函数（所以说OC有个消息发送机制）  
   > // OC是动态语言，每个方法在运行时会被动态转为消息发送，即：objc\_msgSend\(receiver, selector\)。  
   > // \[stu show\]; 在objc动态编译时，会被转意为：objc\_msgSend\(stu, @selector\(show\)\);  
   > 4\). 因此，可以说 Runtime 是OC的底层实现，是OC的幕后执行者。  
   >   
   > 有了Runtime库，能做什么事情呢？  
   > Runtime库里面包含了跟类、成员变量、方法相关的API。  
   > 比如：  
   > （1）获取类里面的所有成员变量。  
   > （2）为类动态添加成员变量。  
   > （3）为类动态添加新的方法。  
   > （4）动态改变类的方法实现等。\(Method Swizzling\)  
   > 因此，有了Runtime，想怎么改就怎么改。  
   > [iOS：学习runtime的理解和心得](https://link.jianshu.com/?t=http%3A%2F%2Fwww.cocoachina.com%2Fios%2F20150901%2F13173.html)

2. _**什么是 Method Swizzle（黑魔法），什么情况下会使用？**_

   > 1\). 在没有一个类的实现源码的情况下，想改变其中一个方法的实现，除了继承它重写、和借助类别重名方法暴力抢先之外，还有更加灵活的方法 Method Swizzle。  
   > 2\). Method Swizzle 指的是改变一个已存在的选择器对应的实现的过程。OC中方法的调用能够在运行时通过改变，通过改变类的调度表中选择器到最终函数间的映射关系。  
   > 3\). 在OC中调用一个方法，其实是向一个对象发送消息，查找消息的唯一依据是selector的名字。利用OC的动态特性，可以实现在运行时偷换selector对应的方法实现。  
   > 4\). 每个类都有一个方法列表，存放着selector的名字和方法实现的映射关系。IMP有点类似函数指针，指向具体的方法实现。  
   > 5\). 我们可以利用 method\_exchangeImplementations 来交换2个方法中的IMP。  
   > 6\). 我们可以利用 class\_replaceMethod 来修改类。  
   > 7\). 我们可以利用 method\_setImplementation 来直接设置某个方法的IMP。  
   > 8\). 归根结底，都是偷换了selector的IMP。

3. _**\_objc\_msgForward 函数是做什么的，直接调用它将会发生什么？**_

   > 答：\_objc\_msgForward是 IMP 类型，用于消息转发的：当向一个对象发送一条消息，但它并没有实现的时候，\_objc\_msgForward会尝试做消息转发。

4. _**什么是 TCP / UDP ?**_

   > TCP：传输控制协议。  
   > UDP：用户数据协议。  
   >   
   > TCP 是面向连接的，建立连接需要经历三次握手，是可靠的传输层协议。  
   > UDP 是面向无连接的，数据传输是不可靠的，它只管发，不管收不收得到。  
   > 简单的说，TCP注重数据安全，而UDP数据传输快点，但安全性一般。

5. _**通信底层原理（OSI七层模型）**_

   > OSI采用了分层的结构化技术，共分七层：  
   > 物理层、数据链路层、网络层、传输层、会话层、表示层、应用层。

6. _**介绍一下XMPP？**_

   > XMPP是一种以XML为基础的开放式实时通信协议。  
   > 简单的说，XMPP就是一种协议，一种规定。就是说，在网络上传东西，XMM就是规定你上传大小的格式。

7. _**OC中创建线程的方法是什么？如果在主线程中执行代码，方法是什么？**_

```
// 创建线程的方法 - [NSThread detachNewThreadSelector:nil toTarget:nil withObject:nil]
   - [self performSelectorInBackground:nil withObject:nil];
   - [[NSThread alloc] initWithTarget:nil selector:nil object:nil];
   - dispatch_async(dispatch_get_global_queue(0, 0), ^{});
   - [[NSOperationQueue new] addOperation:nil]; // 主线程中执行代码的方法 - [self performSelectorOnMainThread:nil withObject:nil waitUntilDone:YES];
   - dispatch_async(dispatch_get_main_queue(), ^{});
   - [[NSOperationQueue mainQueue] addOperation:nil];
```

1. _**tableView的重用机制？**_

   > 答：UITableView 通过重用单元格来达到节省内存的目的: 通过为每个单元格指定一个重用标识符，即指定了单元格的种类,当屏幕上的单元格滑出屏幕时，系统会把这个单元格添加到重用队列中，等待被重用，当有新单元格从屏幕外滑入屏幕内时，从重用队列中找看有没有可以重用的单元格，如果有，就拿过来用，如果没有就创建一个来使用。

2. _**用伪代码写一个线程安全的单例模式**_

```
static id _instance;
    + (id)allocWithZone:(struct _NSZone *)zone { static dispatch_once_t onceToken; dispatch_once(
&
onceToken, ^{
           _instance = [super allocWithZone:zone];
       }); return _instance;
    }

    + (instancetype)sharedData { static dispatch_once_t onceToken; dispatch_once(
&
onceToken, ^{
           _instance = [[self alloc] init];
       }); return _instance;
    }

    - (id)copyWithZone:(NSZone *)zone { return _instance;
    }
```

1. _**如何实现视图的变形?**_

   > 答：通过修改view的 transform 属性即可。

2. _**在手势对象基础类UIGestureRecognizer的常用子类手势类型中哪两个手势发生后，响应只会执行一次？**_

   > 答：UITapGestureRecognizer,UISwipeGestureRecognizer是一次性手势,手势发生后,响应只会执行一次。

3. _**字符串常用方法：**_

   > NSString _str = @"abc_123";  
   > NSArray _arr = \[str componentsSeparatedByString:@"_"\]; //以目标字符串把原字符串分割成两部分，存到数组中。@\[@"abc", @"123"\];

4. _**如何高性能的给 UIImageView 加个圆角?**_

    *   不好的解决方案：使用下面的方式会`强制Core Animation提前渲染屏幕的离屏绘制, 而离屏绘制就会给性能带来负面影响`，会有卡顿的现象出现。 self.view.layer.cornerRadius = 5.0f; self.view.layer.masksToBounds = YES; 

        *   正确的解决方案：使用绘图技术

            - (UIImage *)circleImage { // NO代表透明 UIGraphicsBeginImageContextWithOptions(self.size, NO, 0.0); // 获得上下文 CGContextRef ctx = UIGraphicsGetCurrentContext(); // 添加一个圆 CGRect rect = CGRectMake(0, 0, self.size.width, self.size.height); CGContextAddEllipseInRect(ctx, rect); // 裁剪 CGContextClip(ctx); // 将图片画上去 [self drawInRect:rect]; UIImage *image = UIGraphicsGetImageFromCurrentImageContext(); // 关闭上下文 UIGraphicsEndImageContext(); return image;
            } 

        *   还有一种方案：使用了贝塞尔曲线"切割"个这个图片, 给UIImageView 添加了的圆角，其实也是通过绘图技术来实现的。 UIImageView *imageView = [[UIImageView alloc] initWithFrame:CGRectMake(0, 0, 100, 100)];
            imageView.center = CGPointMake(200, 300); UIImage *anotherImage = [UIImage imageNamed:@"image"]; UIGraphicsBeginImageContextWithOptions(imageView.bounds.size, NO, 1.0);
            [[UIBezierPath bezierPathWithRoundedRect:imageView.bounds
                                   cornerRadius:50] addClip];
            [anotherImage drawInRect:imageView.bounds];
            imageView.image = UIGraphicsGetImageFromCurrentImageContext(); UIGraphicsEndImageContext();
            [self.view addSubview:imageView];

1. _**你是怎么封装一个view的**_

```
1）. 可以通过纯代码或者xib的方式来封装子控件 2）. 建立一个跟view相关的模型，然后将模型数据传给view，通过模型上的数据给view的子控件赋值 /**
     *  纯代码初始化控件时一定会走这个方法
     */ - (instancetype)initWithFrame:(CGRect)frame { if(self = [super initWithFrame:frame]) {
            [self setupUI];
        } return self;
    } /**
     *  通过xib初始化控件时一定会走这个方法
     */ - (id)initWithCoder:(NSCoder *)aDecoder { if(self = [super initWithCoder:aDecoder]) {
            [self setupUI];
        } return self;
    }

    - (void)setupUI { // 初始化代码 }
```

1. _**HTTP协议中 POST 方法和 GET 方法有那些区别?**_

   > 1. GET用于向服务器请求数据，POST用于提交数据  
   > 2. GET请求，请求参数拼接形式暴露在地址栏，而POST请求参数则放在请求体里面，因此GET请求不适合用于验证密码等操作  
   > 3. GET请求的URL有长度限制，POST请求不会有长度限制

2. _**请简单的介绍下APNS发送系统消息的机制**_

   > APNS优势：杜绝了类似安卓那种为了接受通知不停在后台唤醒程序保持长连接的行为，由iOS系统和APNS进行长连接替代。  
   > APNS的原理：  
   > 1\). 应用在通知中心注册，由iOS系统向APNS请求返回设备令牌\(device Token\)  
   > 2\). 应用程序接收到设备令牌并发送给自己的后台服务器  
   > 3\). 服务器把要推送的内容和设备发送给APNS  
   > 4\). APNS根据设备令牌找到设备，再由iOS根据APPID把推送内容展示

# 77. ios开发逆向传值的几种方法整理

#### 第一种：代理传值

```
第二个控制器： @protocol WJSecondViewControllerDelegate 
 - (void)changeText:(NSString*)text; @end @property(nonatomic,assign)id
delegate;

  - (IBAction)buttonClick:(UIButton*)sender {
  _str = sender.titleLabel.text;
  [self.delegate changeText:sender.titleLabel.text];
  [self.navigationController popViewControllerAnimated:YES];
  }

  第一个控制器:

  - (IBAction)pushToSecond:(id)sender {
  WJSecondViewController *svc = [[WJSecondViewController alloc]initWithNibName:@"WJSecondViewController" bundle:nil];
  svc.delegate = self;
  svc.str = self.navigationItem.title;
  [self.navigationController pushViewController:svc animated:YES];
  [svc release];
  }
  - (void)changeText:(NSString *)text{ self.navigationItem.title = text;
  }
```

#### 第二种：通知传值

```
第一个控制器： //注册监听通知 [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(limitDataForModel:) name:@"NOV" object:nil];
  - (void)limitDataForModel:(NSNotification *)noti{ self.gamesInfoArray = noti.object;
  }

  第二个控制器： //发送通知 [[NSNotificationCenter defaultCenter]     postNotificationName:@"NOV" object:gameArray];
```

#### 第三种：单例传值

```
Single是一个单例类，并且有一个字符串类型的属性titleName
  在第二个控制器：

  - (IBAction)buttonClick:(UIButton*)sender {
  Single *single = [Single sharedSingle];
  single.titleName = sender.titleLabel.text;
  [self.navigationController popViewControllerAnimated:YES];
  }
  
  第一个控制器：

  - (void)viewWillAppear:(BOOL)animated{
  [super viewWillAppear:animated];
  Single *single = [Single sharedSingle]; self.navigationItem.title = single.titleName;
  }
```

#### 第四种：block传值

```
第二个控制器： @property (nonatomic,copy) void (^changeText_block)(NSString*);
  - (IBAction)buttonClick:(UIButton*)sender {
  _str = sender.titleLabel.text; self.changeText_block(sender.titleLabel.text);
  [self.navigationController popViewControllerAnimated:YES];
  }

  第一个控制器：

  - (IBAction)pushToSecond:(id)sender {
  WJSecondViewController *svc = [[WJSecondViewController alloc]initWithNibName:@"WJSecondViewController" bundle:nil];
  svc.str = self.navigationItem.title;
  [svc setChangeText_block:^(NSString *str) {
      
>
self.navigationItem.title = str;
  }]；
  [self.navigationController pushViewController:svc animated:YES];
  }
```

#### 第五种：extern传值

```
第二个控制器： extern NSString *btn;
  - (IBAction)buttonClick:(UIButton*)sender {
  btn = sender.titleLabel.text;
  [self.navigationController popViewControllerAnimated:YES];
  }
 
  第一个控制器: NSString *btn = nil;
  - (void)viewWillAppear:(BOOL)animated{
  [super viewWillAppear:animated]; self.navigationItem.title = btn;
  }
```

#### 第六种：KVO传值

```
第一个控制器:

  - (void)viewDidLoad {
  [super viewDidLoad];
   _vc =[[SecondViewController alloc]init]; //self监听vc里的textValue属性 [_vc addObserver:self forKeyPath:@"textValue" options:0 context:nil];   
  }

  第二个控制器:

  - (IBAction)buttonClicked:(id)sender { self.textValue = self.textField.text;
  [self.navigationController popViewControllerAnimated:YES];
  }
```

# 78. 浅谈iOS开发中方法延迟执行的几种方式

### Method1. performSelector方法

### Method2. NSTimer定时器

### Method3. NSThread线程的sleep

### Method4. GCD

---

公用延迟执行方法

> - \(void\)delayMethod{ NSLog\(@"delayMethodEnd"\);

---

### Method1: performSelector

    [self performSelector:@selector(delayMethod) withObject:nil/*可传任意类型参数*/ afterDelay:2.0];`
    注：此方法是一种非阻塞的执行方式，未找到取消执行的方法。


    >
     程序运行结束

    >
     2015-08-31 10:56:59.361 CJDelayMethod[1080:39604] delayMethodStart2015-08-31 10:56:59.363 CJDelayMethod[1080:39604] nextMethod2015-08-31 10:57:01.364 CJDelayMethod[1080:39604] delayMethodEnd

### Method2: NSTimer定时器

    NSTimer *timer = [NSTimer scheduledTimerWithTimeInterval:2.0 target:self selector:@selector(delayMethod) userInfo:nil repeats:NO];`
      注：此方法是一种非阻塞的执行方式，
      取消执行方法：`- (void)invalidate;`即可


    >
     程序运行结束

    >
     2015-08-31 10:58:10.182 CJDelayMethod[1129:41106] delayMethodStart2015-08-31 10:58:10.183 CJDelayMethod[1129:41106] nextMethod2015-08-31 10:58:12.185 CJDelayMethod[1129:41106] delayMethodEnd

### Method3: NSThread线程的sleep

```
[NSThread sleepForTimeInterval:2.0];
  注：此方法是一种阻塞执行方式，建议放在子线程中执行，否则会卡住界面。但有时还是需要阻塞执行，如进入欢迎界面需要沉睡3秒才进入主界面时。
  没有找到取消执行方式。

  
>
 程序运行结束
  
>
 2015-08-31 10:58:41.501 CJDelayMethod[1153:41698] delayMethodStart2015-08-31 10:58:43.507 CJDelayMethod[1153:41698] nextMethod
```

### Method4: GCD

```
__block ViewController/*主控制器*/ *weakSelf = self; dispatch_time_t delayTime = dispatch_time(DISPATCH_TIME_NOW, (int64_t)(2.0/*延迟执行时间*/ * NSEC_PER_SEC));

  dispatch_after(delayTime, dispatch_get_main_queue(), ^{
      [weakSelf delayMethod];
  });

  注：此方法可以在参数中选择执行的线程，是一种非阻塞执行方式。没有找到取消执行方式。

  
>
 程序运行结束
  
>
 2015-08-31 10:59:21.652 CJDelayMethod[1181:42438] delayMethodStart2015-08-31 10:59:21.653 CJDelayMethod[1181:42438] nextMethod2015-08-31 10:59:23.653 CJDelayMethod[1181:42438] delayMethodEnd
```

    完整代码参见：


    >
     // 
    >
     // ViewController.m 
    >
     // CJDelayMethod 
    >
     // 
    >
     // Created by 陈杰 on 8/31/15. 
    >
     // Copyright (c) 2015 chenjie. All rights reserved. 
    >
     // 
    >
    >
     # import "ViewController.h" 
    >
    >
     @interface ViewController () 
    >
     @property (nonatomic, strong) NSTimer *timer;

    >
     @end 
    >
     @implementation ViewController* 
    >
    >
      *`- (void)viewDidLoad { `*

    >
    >
     *` [super viewDidLoad]; `*

    >
    >
     *` NSLog(@"delayMethodStart"); `*

    >
    >
     *` [self methodOnePerformSelector];// `* 
    >
    >
     *` [self methodTwoNSTimer];// `* 
    >
    >
     *` [self methodThreeSleep];//`* 
    >
    >
     *` [self methodFourGCD]; `*

    >
    >
     *` NSLog(@"nextMethod");`*

    >
    >
     *`}`*

    >
    >
      *`- (void)methodFiveAnimation{ `*

    >
    >
     *` [UIView animateWithDuration:0 delay:2.0 options:UIViewAnimationOptionAllowUserInteraction animations:^{ } completion:^(BOOL finished) { `*

    >
    >
     *` [self delayMethod]; `*

    >
    >
     *` }];`*

    >
    >
     *`}`

    >
     `- (void)methodFourGCD{ `*

    >
    >
     *` __block ViewController`*`weakSelf = self; dispatch_time_t delayTime = dispatch_time(DISPATCH_TIME_NOW, (int64_t)(2.0 * NSEC_PER_SEC)); dispatch_after(delayTime, dispatch_get_main_queue(), ^{ `

    >
    >
     ` [weakSelf delayMethod]; `

    >
    >
     ` });`

    >
    >
     `}`

    >
    >
      `- (void)methodThreeSleep{ `

    >
    >
     ` [NSThread sleepForTimeInterval:2.0];`

    >
    >
     `}`

    >
    >
      `- (void)methodTwoNSTimer{`

    >
    >
     ` NSTimer *timer = [NSTimer scheduledTimerWithTimeInterval:2.0 target:self selector:@selector(delayMethod) userInfo:nil repeats:NO];`

    >
    >
     `}`

    >
    >
      `- (void)methodOnePerformSelector{`

    >
    >
     ` [self performSelector:@selector(delayMethod) withObject:nil/*可传任意类型参数*/ afterDelay:2.0];`

    >
    >
     `}`

    >
    >
      `- (void)delayMethod{`

    >
    >
     ` NSLog(@"delayMethodEnd");`

    >
    >
     `}`

    >
     `- (void)didReceiveMemoryWarning { `

    >
    >
     ` [super didReceiveMemoryWarning]; `

    >
    >
     ` // Dispose of any resources that can be recreated.` 
    >
    >
     `}`

    >
    >
     `@end`

---

1. _**NSPersistentStoreCoordinator , NSManaged0bjectContext 和NSManaged0bject中的那些需要在线程中创建或者传递**_

   > 答：NSPersistentStoreCoordinator是持久化存储协调者，主要用于协调托管对象上下文和持久化存储区之间的关系。NSManagedObjectContext使用协调者的托管对象模型将数据保存到数据库，或查询数据。

2. _**您是否做过一部的网络处理和通讯方面的工作？如果有，能具体介绍一下实现策略么?**_

   > 答：使用NSOperation发送异步网络请求，使用NSOperationQueue管理线程数目及优先级，底层是用NSURLConnetion，

3. _**你使用过Objective-C的运行时编程（Runtime Programming）么？如果使用过，你用它做了什么？你还能记得你所使用的相关的头文件或者某些方法的名称吗？**_

   > 答：Objecitve-C的重要特性是Runtime（运行时）,在\#import下能看到相关的方法，用过objc\_getClass\(\)和class\_copyMethodList\(\)获取过私有API;使用  
   > Method method1 = class\_getInstanceMethod\(cls, sel1\);  
   > Method method2 = class\_getInstanceMethod\(cls, sel2\);  
   > method\_exchangeImplementations\(method1, method2\);  
   >   
   > 代码交换两个方法，在写unit test时使用到。

4. _**Core开头的系列的内容。是否使用过CoreAnimation和CoreGraphics。UI框架和CA，CG框架的联系是什么？分别用CA和CG做过些什么动画或者图像上的内容。（有需要的话还可以涉及Quartz的一些内容）**_

   > 答：UI框架的底层有CoreAnimation，CoreAnimation的底层有CoreGraphics。  
   > UIKit \|  
   > ------------ \|  
   > Core Animation \|  
   > Core Graphics \|  
   > Graphics Hardware\|  
   > 使用CA做过menu菜单的展开收起（太逊了）

5. _**是否使用过CoreText或者CoreImage等？如果使用过，请谈谈你使用CoreText或者CoreImage的体验。**_

   > 答：CoreText可以解决复杂文字内容排版问题。CoreImage可以处理图片，为其添加各种效果。体验是很强大，挺复杂的。

6. _**自动释放池是什么,如何工作**_

   > 答：当您向一个对象发送一个autorelease消息时，Cocoa就会将该对象的一个引用放入到最新的自动释放.它仍然是个OC的对象，因此自动释放池定义的作用域内的其它对象可以向它发送消息。当程序执行到作用域结束的位置时，自动释放池就会被释放，池中的所有对象也就被释放。

7. _**NSNotification和KVO的区别和用法是什么？什么时候应该使用通知，什么时候应该使用KVO，它们的实现上有什么区别吗？如果用protocol和delegate（或者delegate的Array）来实现类似的功能可能吗？如果可能，会有什么潜在的问题？如果不能，为什么？（虽然protocol和delegate这种东西面试已经面烂了…）**_

   > 答：NSNotification是通知模式在iOS的实现，KVO的全称是键值观察\(Key-value observing\),其是基于KVC（key-value coding）的，KVC是一个通过属性名访问属性变量的机制。例如将Module层的变化，通知到多个Controller对象时，可以使用NSNotification；如果是只需要观察某个对象的某个属性，可以使用KVO。  
   > 对于委托模式，在设计模式中是对象适配器模式，其是delegate是指向某个对象的，这是一对一的关系，而在通知模式中，往往是一对多的关系。委托模式，从技术上可以现在改变delegate指向的对象，但不建议这样做，会让人迷惑，如果一个delegate对象不断改变，指向不同的对象。

8. _**你用过NSOperationQueue么？如果用过或者了解的话，你为什么要使用NSOperationQueue，实现了什么？请描述它和G.C.D的区别和类似的地方（提示：可以从两者的实现机制和适用范围来描述）。**_

   > 答：使用NSOperationQueue用来管理子类化的NSOperation对象，控制其线程并发数目。GCD和NSOperation都可以实现对线程的管理，区别是 NSOperation和NSOperationQueue是多线程的面向对象抽象。项目中使用NSOperation的优点是NSOperation是对线程的高度抽象，在项目中使用它，会使项目的程序结构更好，子类化NSOperation的设计思路，是具有面向对象的优点（复用、封装），使得实现是多线程支持，而接口简单，建议在复杂项目中使用。  
   > 项目中使用GCD的优点是GCD本身非常简单、易用，对于不复杂的多线程操作，会节省代码量，而Block参数的使用，会是代码更为易读，建议在简单项目中使用。

9. _**既然提到G.C.D，那么问一下在使用G.C.D以及block时要注意些什么？它们两是一回事儿么？block在ARC中和传统的MRC中的行为和用法有没有什么区别，需要注意些什么？**_

   > 答：使用block是要注意，若将block做函数参数时，需要把它放到最后，GCD是Grand Central Dispatch，是一个对线程开源类库，而Block是闭包，是能够读取其他函数内部变量的函数。

10. _**对于Objective-C，你认为它最大的优点和最大的不足是什么？对于不足之处，现在有没有可用的方法绕过这些不足来实现需求。如果可以的话，你有没有考虑或者实践过重新实现OC的一些功能，如果有，具体会如何做？**_

    > 答：最大的优点是它的运行时特性，不足是没有命名空间，对于命名冲突，可以使用长命名法或特殊前缀解决，如果是引入的第三方库之间的命名冲突，可以使用link命令及flag解决冲突。

11. _**你实现过一个框架或者库以供别人使用么？如果有，请谈一谈构建框架或者库时候的经验；如果没有，请设想和设计框架的public的API，并指出大概需要如何做、需要注意一些什么方面，来使别人容易地使用你的框架。**_

    > 答：抽象和封装，方便使用。首先是对问题有充分的了解，比如构建一个文件解压压缩框架，从使用者的角度出发，只需关注发送给框架一个解压请求，框架完成复杂文件的解压操作，并且在适当的时候通知给是哦难过者，如解压完成、解压出错等。在框架内部去构建对象的关系，通过抽象让其更为健壮、便于更改。其次是API的说明文档。

# 二、 第三方框架

1. _**AFNetworking 底层原理分析**_

   > AFNetworking主要是对NSURLSession和NSURLConnection\(iOS9.0废弃\)的封装,其中主要有以下类:  
   > 1\). AFHTTPRequestOperationManager：内部封装的是 NSURLConnection, 负责发送网络请求, 使用最多的一个类。\(3.0废弃\)  
   > 2\). AFHTTPSessionManager：内部封装是 NSURLSession, 负责发送网络请求,使用最多的一个类。  
   > 3\). AFNetworkReachabilityManager：实时监测网络状态的工具类。当前的网络环境发生改变之后,这个工具类就可以检测到。  
   > 4\). AFSecurityPolicy：网络安全的工具类, 主要是针对 HTTPS 服务。  
   >   
   > 5\). AFURLRequestSerialization：序列化工具类,基类。上传的数据转换成JSON格式  
   > \(AFJSONRequestSerializer\).使用不多。  
   > 6\). AFURLResponseSerialization：反序列化工具类;基类.使用比较多:  
   > 7\). AFJSONResponseSerializer; JSON解析器,默认的解析器.  
   > 8\). AFHTTPResponseSerializer; 万能解析器; JSON和XML之外的数据类型,直接返回二进  
   > 制数据.对服务器返回的数据不做任何处理.  
   > 9\). AFXMLParserResponseSerializer; XML解析器;

2. _**描述下SDWebImage里面给UIImageView加载图片的逻辑**_

   > SDWebImage 中为 UIImageView 提供了一个分类UIImageView+WebCache.h, 这个分类中有一个最常用的接口sd\_setImageWithURL:placeholderImage:，会在真实图片出现前会先显示占位图片，当真实图片被加载出来后再替换占位图片。  
   >   
   > 加载图片的过程大致如下：  
   > 1.首先会在 SDWebImageCache 中寻找图片是否有对应的缓存, 它会以url 作为数据的索引先在内存中寻找是否有对应的缓存  
   > 2.如果缓存未找到就会利用通过MD5处理过的key来继续在磁盘中查询对应的数据, 如果找到了, 就会把磁盘中的数据加载到内存中，并将图片显示出来  
   > 3.如果在内存和磁盘缓存中都没有找到，就会向远程服务器发送请求，开始下载图片  
   > 4.下载后的图片会加入缓存中，并写入磁盘中  
   > 5.整个获取图片的过程都是在子线程中执行，获取到图片后回到主线程将图片显示出来  
   >   
   > SDWebImage原理：  
   > 调用类别的方法：  
   > 1. 从内存（字典）中找图片（当这个图片在本次使用程序的过程中已经被加载过），找到直接使用。  
   > 2. 从沙盒中找（当这个图片在之前使用程序的过程中被加载过），找到使用，缓存到内存中。  
   > 3. 从网络上获取，使用，缓存到内存，缓存到沙盒。

参考：[SDWebImage内部实现过程](https://www.jianshu.com/p/4eda12661459)

1. _**友盟统计接口统计的所有功能**_

   > APP启动速度，APP停留页面时间等

# 三、算法

1._**不用中间变量,用两种方法交换A和B的值**_

```
// 1.中间变量 void swap(int a, int b) { int temp = a;
       a = b;
       b = temp;
    } // 2.加法 void swap(int a, int b) {
       a = a + b;
       b = a - b;
       a = a - b;
    } // 3.异或（相同为0，不同为1\. 可以理解为不进位加法） void swap(int a, int b) {
       a = a ^ b;
       b = a ^ b;
       a = a ^ b;
    }
```

2._**求最大公约数**_

```
/** 1.直接遍历法 */ int maxCommonDivisor(int a, int b) { int max = 0; for (int i = 1; i 
<
=b; i++) { if (a % i == 0 
&
&
 b % i == 0) {
                max = I;
            }
        } return max;
    } /** 2.辗转相除法 */ int maxCommonDivisor(int a, int b) { int r; while(a % b 
>
 0) {
            r = a % b;
            a = b;
            b = r;
        } return b;
    } // 扩展：最小公倍数 = (a * b)/最大公约数
```

3._**模拟栈操作**_

```
/**
     *  栈是一种数据结构，特点：先进后出
     *  练习：使用全局变量模拟栈的操作
     */ #include 
 #include 
 #include 
 //保护全局变量：在全局变量前加static后，这个全局变量就只能在本文件中使用 static int data[1024];//栈最多能保存1024个数据 static int count = 0;//目前已经放了多少个数(相当于栈顶位置) //数据入栈 push void push(int x){
        assert(!full());//防止数组越界 data[count++] = x;
    } //数据出栈 pop int pop(){
        assert(!empty()); return data[--count];
    } //查看栈顶元素 top int top(){
        assert(!empty()); return data[count-1];
    } //查询栈满 full bool full() { if(count 
>
= 1024) { return 1;
        } return 0; 
    } //查询栈空 empty bool empty() { if(count 
<
= 0) { return 1;
        } return 0;
    } int main(){ //入栈 for (int i = 1; i 
<
= 10; i++) {
            push(i);
        } //出栈 while(!empty()){ printf("%d ", top()); //栈顶元素 pop(); //出栈 } printf("\n"); return 0;
    }
```

  
4._**排序算法**_

```
选择排序、冒泡排序、插入排序三种排序算法可以总结为如下：

    *   都将数组分为已排序部分和未排序部分。 1\. 选择排序将已排序部分定义在左端，然后选择未排序部分的最小元素和未排序部分的第一个元素交换。 2\. 冒泡排序将已排序部分定义在右端，在遍历未排序部分的过程执行交换，将最大元素交换到最右端。 3\. 插入排序将已排序部分定义在左端，将未排序部分元的第一个元素插入到已排序部分合适的位置。 
```

    \*   选择排序 /\*\*       \*  【选择排序】：最值出现在起始端      \*        \*  第1趟：在n个数中找到最小\(大\)数与第一个数交换位置      \*  第2趟：在剩下n-1个数中找到最小\(大\)数与第二个数交换位置      \*  重复这样的操作...依次与第三个、第四个...数交换位置      \*  第n-1趟，最终可实现数据的升序（降序）排列。      \*      \*/ void selectSort\(int \*arr, int length\) { for \(int i = 0; i 

&lt;

 length - 1; i++\) { //趟数 for \(int j = i + 1; j 

&lt;

 length; j++\) { //比较次数 if \(arr\[i\] 

&gt;

 arr\[j\]\) {                     int temp = arr\[i\];                     arr\[i\] = arr\[j\];                     arr\[j\] = temp;                 }             }         }     }      \*   冒泡排序 /\*\*       \*  【冒泡排序】：相邻元素两两比较，比较完一趟，最值出现在末尾      \*  第1趟：依次比较相邻的两个数，不断交换（小数放前，大数放后）逐个推进，最值最后出现在第n个元素位置      \*  第2趟：依次比较相邻的两个数，不断交换（小数放前，大数放后）逐个推进，最值最后出现在第n-1个元素位置      \*   ……   ……      \*  第n-1趟：依次比较相邻的两个数，不断交换（小数放前，大数放后）逐个推进，最值最后出现在第2个元素位置       \*/ void bublleSort\(int \*arr, int length\) { for\(int i = 0; i 

&lt;

 length - 1; i++\) { //趟数 for\(int j = 0; j 

&lt;

 length - i - 1; j++\) { //比较次数 if\(arr\[j\] 

&gt;

 arr\[j+1\]\) {                     int temp = arr\[j\];                     arr\[j\] = arr\[j+1\];                     arr\[j+1\] = temp;                 }             }          }     }

---

参考：  
[8大排序算法图文讲解](https://link.jianshu.com/?t=https%3A%2F%2Fmp.weixin.qq.com%2Fs%3F__biz%3DMzAxMzQ3NzQ3Nw%3D%3D%26mid%3D2654249037%26idx%3D2%26sn%3D4b8512cd8435912df30bbb51272bbdc1%26chksm%3D8061f347b7167a51fa7ef4a42915922c5bdda376859503584ef8b434c0af8683abfee6540677%26scene%3D0%23wechat_redirect)  
[常用算法OC实现](https://www.jianshu.com/p/d093df83979a)

---

5._**折半查找（二分查找）**_

```
/**
     *  折半查找：优化查找时间（不用遍历全部数据）
     *
     *  折半查找的原理：
     *   1
>
 数组必须是有序的
     *   2
>
 必须已知min和max（知道范围）
     *   3
>
 动态计算mid的值，取出mid对应的值进行比较
     *   4
>
 如果mid对应的值大于要查找的值，那么max要变小为mid-1
     *   5
>
 如果mid对应的值小于要查找的值，那么min要变大为mid+1
     *
     */ // 已知一个有序数组, 和一个key, 要求从数组中找到key对应的索引位置  int findKey(int *arr, int length, int key) { int min = 0, max = length - 1, mid; while (min 
<
= max) {
            mid = (min + max) / 2; //计算中间值 if (key 
>
 arr[mid]) {
                min = mid + 1;
            } else if (key 
<
 arr[mid]) {
                max = mid - 1;
            } else { return mid;
            }
        } return -1;
    }
```

# 四、编码格式（优化细节）

参考：[请Review下面的代码，并根据iOS的编码规范做出正确的修改](https://www.jianshu.com/p/21cfbaca7f07)

1._**在 Objective-C 中，enum 建议使用NS\_ENUM和NS\_OPTIONS宏来定义枚举类型。**_

```
//定义一个枚举(比较严密) typedef NS_ENUM(NSInteger, BRUserGender) {
        BRUserGenderUnknown, // 未知 BRUserGenderMale, // 男性 BRUserGenderFemale, // 女性 BRUserGenderNeuter // 无性 }; @interface BRUser : NSObject
 @property (nonatomic, readonly, copy) NSString *name; @property (nonatomic, readonly, assign) NSUInteger age; @property (nonatomic, readonly, assign) BRUserGender gender;

    - (instancetype)initWithName:(NSString *)name age:(NSUInteger)age gender:(BRUserGender)gender; @end //说明： //既然该类中已经有一个“初始化方法” ，用于设置 name、age 和 gender 的初始值: 那么在设计对应 @property 时就应该尽量使用不可变的对象：其三个属性都应该设为“只读”。用初始化方法设置好属性值之后，就不能再改变了。 //属性的参数应该按照下面的顺序排列： （原子性，读写，内存管理）
```

2._**避免使用C语言中的基本数据类型，建议使用 Foundation 数据类型，对应关系如下:**_

> int -&gt; NSInteger  
> unsigned -&gt; NSUInteger  
> float -&gt; CGFloat  
> 动画时间 -&gt; NSTimeInterval

# 五、其它知识点

1. _**HomeKit**_，是苹果2014年发布的智能家居平台。

2. _**什么是 OpenGL、Quartz 2D？**_

   > Quatarz 2d 是Apple提供的基本图形工具库。只是适用于2D图形的绘制。  
   > OpenGL，是一个跨平台的图形开发库。适用于2D和3D图形的绘制。

3. _**ffmpeg框架：**_

   > ffmpeg 是音视频处理工具，既有音视频编码解码功能，又可以作为播放器使用。

4. _**谈谈 UITableView 的优化**_

   > 1\). 正确的复用cell；  
   > 2\). 设计统一规格的Cell；  
   > 3\). 提前计算并缓存好高度（布局），因为heightForRowAtIndexPath:是调用最频繁的方法；  
   > 4\). 异步绘制，遇到复杂界面，遇到性能瓶颈时，可能就是突破口；  
   > 5\). 滑动时按需加载，这个在大量图片展示，网络加载的时候很管用！  
   > 6\). 减少子视图的层级关系；  
   > 7\). 尽量使所有的视图不透明化以及做切圆操作；  
   > 8\). 不要动态的add 或者 remove 子控件。最好在初始化时就添加完，然后通过hidden来控制是否显示；  
   > 9\). 使用调试工具分析问题。

5. _**如何实行cell的动态的行高**_

   > 如果希望每条数据显示自身的行高，必须设置两个属性，1.预估行高，2.自定义行高。  
   > 设置预估行高 tableView.estimatedRowHeight = 200。  
   > 设置定义行高 tableView.estimatedRowHeight = UITableViewAutomaticDimension。  
   > 如果要让自定义行高有效，必须让容器视图有一个自下而上的约束。

6. _**说说你对 block 的理解**_

   > 栈上的自动复制到堆上，block 的属性修饰符是 copy，循环引用的原理和解决方案。  
   >   
   > block的循环引用；block的代码实现；为什么会造成循环引用；block是如何强引用self的；  
   > 参考：[Block 代码块中用到了self引用问题，导致循环引用](https://link.jianshu.com/?t=http%3A%2F%2Fblog.sina.com.cn%2Fs%2Fblog_945590aa0102w77w.html)

7. _**什么是野指针、空指针？**_

   > 野指针：不知道指向了哪里的指针叫野指针。即指针指向不确定，指针存的地址是一个垃圾值，未初始化。  
   > 空指针：不指向任何位置的指针叫空指针。即指针没有指向，指针存的地址是一个空地址，NULL。

8. _**什么是 OOA / OOD / OOP ?**_

   > OOA（Object Oriented Analysis） --面向对象分析  
   > OOD（Object Oriented Design） --面向对象设计  
   > OOP（Object Oriented Programming）--面向对象编程

9. _**多线程是什么**_

   > 多线程是个复杂的概念，按字面意思是同步完成多项任务，提高了资源的使用效率，从硬件、操作系统、应用软件不同的角度去看，多线程被赋予不同的内涵，对于硬件，现在市面上多数的CPU都是多核的，多核的CPU运算多线程更为出色;从操作系统角度，是多任务，现在用的主流操作系统都是多任务的，可以一边听歌、一边写博客;对于应用来说，多线程可以让应用有更快的回应，可以在网络下载时，同时响应用户的触摸操作。在iOS应用中，对多线程最初的理解，就是并发，它的含义是原来先做烧水，再摘菜，再炒菜的工作，会变成烧水的同时去摘菜，最后去炒菜。

10. _**iOS 中的多线程**_

    > iOS中的多线程，是Cocoa框架下的多线程，通过Cocoa的封装，可以让我们更为方便的使用线程，做过C++的同学可能会对线程有更多的理解，比如线程的创立，信号量、共享变量有认识，Cocoa框架下会方便很多，它对线程做了封装，有些封装，可以让我们创建的对象，本身便拥有线程，也就是线程的对象化抽象，从而减少我们的工程，提供程序的健壮性。  
    >   
    > GCD是\(Grand Central Dispatch\)的缩写 ，从系统级别提供的一个易用地多线程类库，具有运行时的特点，能充分利用多核心硬件。GCD的API接口为C语言的函数，函数参数中多数有Block，关于Block的使用参看这里，为我们提供强大的“接口”，对于GCD的使用参见本文  
    >   
    > NSOperation与Queue  
    >   
    > NSOperation是一个抽象类，它封装了线程的细节实现，我们可以通过子类化该对象，加上NSQueue来同面向对象的思维，管理多线程程序。具体可参看这里：一个基于NSOperation的多线程网络访问的项目。  
    >   
    > NSThread  
    >   
    > NSThread是一个控制线程执行的对象，它不如NSOperation抽象，通过它我们可以方便的得到一个线程，并控制它。但NSThread的线程之间的并发控制，是需要我们自己来控制的，可以通过NSCondition实现。  
    >   
    > 参看 iOS多线程编程之NSThread的使用   
    >   
    > 其他多线程  
    >   
    > 在Cocoa的框架下，通知、Timer和异步函数等都有使用多线程，\(待补充\).

11. _**在项目什么时候选择使用GCD，什么时候选择NSOperation?**_

    > 项目中使用NSOperation的优点是NSOperation是对线程的高度抽象，在项目中使用它，会使项目的程序结构更好，子类化NSOperation的设计思路，是具有面向对象的优点\(复用、封装\)，使得实现是多线程支持，而接口简单，建议在复杂项目中使用。  
    >   
    > 项目中使用GCD的优点是GCD本身非常简单、易用，对于不复杂的多线程操作，会节省代码量，而Block参数的使用，会是代码更为易读，建议在简单项目中使用。

12. _**KVO，NSNotification，delegate及block区别**_

    > \* KVO就是cocoa框架实现的观察者模式，一般同KVC搭配使用，通过KVO可以监测一个值的变化，比如View的高度变化。是一对多的关系，一个值的变化会通知所有的观察者。  
    > \* NSNotification是通知，也是一对多的使用场景。在某些情况下，KVO和NSNotification是一样的，都是状态变化之后告知对方。NSNotification的特点，就是需要被观察者先主动发出通知，然后观察者注册监听后再来进行响应，比KVO多了发送通知的一步，但是其优点是监听不局限于属性的变化，还可以对多种多样的状态变化进行监听，监听范围广，使用也更灵活。  
    >   
    > \* delegate 是代理，就是我不想做的事情交给别人做。比如狗需要吃饭，就通过delegate通知主人，主人就会给他做饭、盛饭、倒水，这些操作，这些狗都不需要关心，只需要调用delegate（代理人）就可以了，由其他类完成所需要的操作。所以delegate是一对一关系。  
    >   
    > \* block是delegate的另一种形式，是函数式编程的一种形式。使用场景跟delegate一样，相比delegate更灵活，而且代理的实现更直观。  
    >   
    > \* KVO一般的使用场景是数据，需求是数据变化，比如股票价格变化，我们一般使用KVO（观察者模式）。delegate一般的使用场景是行为，需求是需要别人帮我做一件事情，比如买卖股票，我们一般使用delegate。  
    > Notification一般是进行全局通知，比如利好消息一出，通知大家去买入。delegate是强关联，就是委托和代理双方互相知道，你委托别人买股票你就需要知道经纪人，经纪人也不要知道自己的顾客。Notification是弱关联，利好消息发出，你不需要知道是谁发的也可以做出相应的反应，同理发消息的人也不需要知道接收的人也可以正常发出消息。

13. _**将一个函数在主线程执行的4种方法**_

```
*   GCD方法，通过向主线程队列发送一个block块，使block里的方法可以在主线程中执行。 dispatch_async(dispatch_get_main_queue(), ^{ //需要执行的方法 });
  

    * NSOperation 方法 NSOperationQueue *mainQueue = [NSOperationQueue mainQueue]; //主队列 NSBlockOperation *operation = [NSBlockOperation blockOperationWithBlock:^{ //需要执行的方法 }];
    [mainQueue addOperation:operation];
  

    * NSThread 方法

    [self performSelector:@selector(method) onThread:[NSThread mainThread] withObject:nil waitUntilDone:YES modes:nil];

    [self performSelectorOnMainThread:@selector(method) withObject:nil waitUntilDone:YES];

    [[NSThread mainThread] performSelector:@selector(method) withObject:nil];
    

    *   RunLoop方法

    [[NSRunLoop mainRunLoop] performSelector:@selector(method) withObject:nil];
```

1. _**如何让计时器调用一个类方法**_

   > \* 计时器只能调用实例方法，但是可以在这个实例方法里面调用静态方法。  
   > \* 使用计时器需要注意，计时器一定要加入RunLoop中，并且选好model才能运行。scheduledTimerWithTimeInterval方法创建一个计时器并加入到RunLoop中所以可以直接使用。  
   > \* 如果计时器的repeats选择YES说明这个计时器会重复执行，一定要在合适的时机调用计时器的invalid。不能在dealloc中调用，因为一旦设置为repeats 为yes，计时器会强持有self，导致dealloc永远不会被调用，这个类就永远无法被释放。比如可以在viewDidDisappear中调用，这样当类需要被回收的时候就可以正常进入dealloc中了。

   ```
   [NSTimer scheduledTimerWithTimeInterval:1 target:self selector:@selector(timerMethod) userInfo:nil repeats:YES];

   -(void)timerMethod
   { //调用类方法 [[self class] staticMethod];
   }

   -(void)invalid
   {
       [timer invalid];
       timer = nil;
   }
   ```

2. _**如何重写类方法**_

   * 1、在子类中实现一个同基类名字一样的静态方法

   * 2、在调用的时候不要使用类名调用，而是使用\[self class\]的方式调用。原理，用类名调用是早绑定，在编译期绑定，用\[self class\]是晚绑定，在运行时决定调用哪个方法。

3. _**NSTimer创建后，会在哪个线程运行**_

   * 用scheduledTimerWithTimeInterval创建的，在哪个线程创建就会被加入哪个线程的RunLoop中就运行在哪个线程

   * 自己创建的Timer，加入到哪个线程的RunLoop中就运行在哪个线程。

4. _**id和NSObject＊的区别**_

   * id是一个 objc\_object 结构体指针，定义是

   ```
   typedef struct objc_object *id
   ```

   * id可以理解为指向对象的指针。所有oc的对象 id都可以指向，编译器不会做类型检查，id调用任何存在的方法都不会在编译阶段报错，当然如果这个id指向的对象没有这个方法，该崩溃还是会崩溃的。

   * NSObject \*指向的必须是NSObject的子类，调用的也只能是NSObjec里面的方法否则就要做强制类型转换。

   * 不是所有的OC对象都是NSObject的子类，还有一些继承自NSProxy。NSObject \*可指向的类型是id的子集。

5. _**static关键字的作用**_

* 回答一：

  > 1.在函数体内定义的static他的作用域为该函数体,该变量在内存中只被分配一次,因此,其值在下次调用时仍维持上次的值不变；  
  > 2.在模块内的static全局变量可以被模块内所有函数访问,但是不能被模块外的其他函数访问；  
  > 3.在模块内的staic全局变量可以被这一模块内的其他函数调用,这个函数的使用范围被限制在这个模块内;  
  > 4.在类中的static成员变量属于整个类所拥有,对类的所有对象只有一份拷贝,也就是说只要是该类的对象,那么该对象的中被static修饰的成员变量都指向同一块地址。

* 回答二：

  > 修饰局部变量：  
  > 1.延长局部变量的生命周期,程序结束才会销毁。  
  > 2.局部变量只会生成一份内存,只会初始化一次。  
  > 3.改变局部变量的作用域。  
  >   
  > 修饰全局变量:  
  > 1.只能在本文件中访问,修改全局变量的作用域,生命周期不会改  
  > 2.避免重复定义全局变量

* 在OC中static关键字使用误区

  > 1.使用static修饰实例变量是不被允许的  
  > 2.使用static修饰了方法，也是错误的

参考：  
[如何正确使用const,static,extern](https://www.jianshu.com/p/2fd58ed2cf55)  
[OC中 static 与 const 的作用](https://link.jianshu.com/?t=http%3A%2F%2Fblog.csdn.net%2Fcaoxin406%2Farticle%2Fdetails%2F47109975)

1. _**使用 Swift 语言编程的优缺点**_  
   总的来说，我认为使用 Swift 来作为编程语言的优点还是要远远大于缺点的，而且很多缺点苹果也在逐渐改善。

* ##### 优点:

  > 1、简洁的语法  
  > 2、更强的类型安全  
  > 3、函数式编程的支持  
  >    Swift 语言本身提供了对函数式编程的支持。  
  >    Objc 本身是不支持的，但是可以通过引入 ReactiveCocoa 这个库来支持函数式编程。  
  > 4、编写 OS X 下的自动化脚本
* ##### 缺点

  > 1、App体积变大  
  >     使用Swift 后， App 体积大概增加 5-8 M 左右，对体积大小敏感的慎用。  
  >     体积变大的原因是因为 Swift 还在变化，所以 Apple 没有在 iOS 系统里放入 Swift 的运行库，反而是每个 App 里都要包含其对应的 Swift 运行库。  
  > 2、Xcode 支持不够好  
  >     如果你是使用 Xcode经常卡住或者崩溃想必你是肯定碰到过了，这个是目前使用 Swift 最让人头疼的事情，即使是到现在XCode 9， 有时候也会遇到这种问题，所以要看你的承受力了……  
  > 3、第三方库的支持不够多  
  >     目前确实 Swift 编写的第三方库确实不多，但可以通过桥接的方式来使用 Objc 的三方库，基本上没有太大问题。现在已经改善很多了…  
  > 4、语言版本更新带来的编译问题  
  >    语言本身还在发展，所以每次版本更新后都会出现编译不过的情况（至少到目前为止还是），但是自从 4.0 版本发布后，改动没有 beta 时候那么大了，而且根据 Xcode 提示基本就可以解决语法变动导致的编译问题了。

>



