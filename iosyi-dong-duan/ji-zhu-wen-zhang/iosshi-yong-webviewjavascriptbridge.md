```
     之前和同行交流的时候，有些童鞋就表示他们公司已经开始在一些完整的模块里使用RN或者Weex来开发页面，并且页面用起来还很顺滑，瞬间让我感觉别人家的公司好潮流。。这两天刚好手上项目里有个需求，原生页面需要与前端多个延伸的界面进行交互，并且隐藏原生的导航栏。如何让我和前端相互助力呢，这里我们借力的桥梁就是Bridge。所以我选择WebViewJavascriptBridge来处理，安卓的同事也是采用相应的库。GitHub地址：**https://github.com/marcuswestin/WebViewJavascriptBridge **感谢开源作者

    众所周知，UIWebView和WKWebView的性能差异很大。例如我在此项目中分别使用二者打开网页，模拟器的内存消耗如下如所示：
```

![](https://upload-images.jianshu.io/upload_images/1742257-abf6361eaae9ea72?imageMogr2/auto-orient/strip|imageView2/2/w/516)

```
                                   UIWebView加载时所占内存示意图
```

![](https://upload-images.jianshu.io/upload_images/1742257-895e3bbfed226afe?imageMogr2/auto-orient/strip|imageView2/2/w/534)

```
                                   WKWebView加载时所占内存示意图
```

所以现在在开发中我都是选择使用WKWebView。

```
    在使用WebViewJavascriptBridge的时候，我们要先让前端在js中注册监听（例如我们需要在移动端点击web页面中的某个按钮实现返回，那么注册监听的代码就需要写在那里。）并且前端那边需要写两套代码，分别对应iOS端和安卓端。
```

![](https://upload-images.jianshu.io/upload_images/1742257-fc92a61b3ceae750?imageMogr2/auto-orient/strip|imageView2/2/w/700)

![](https://upload-images.jianshu.io/upload_images/1742257-65e658dbcadfb607?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
                                                                       JS注入完整代码
```

iOS端加载web页面、开启日志并给webView建立JS与OC的桥梁

![](https://upload-images.jianshu.io/upload_images/1742257-7b2fe89df4c83948?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
              iOS端创建web页面、开启日志、建立JS与OC的桥梁

    iOS端注册与前端JS中对应的方法，获得回调，然后我们就可以在回调中做我们需要做的操作。
```

![](https://upload-images.jianshu.io/upload_images/1742257-4eaa666aaab56e1a?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
                     收到回调

    最后在dealloc方法调用清除缓存的方法：
```

![](https://upload-images.jianshu.io/upload_images/1742257-872927b989411de3?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
                                 WKWebView清除缓存

    以上就是简单使用WebViewJavascriptBridge的一个实例。这个库的原理大致如下：**分别在OC环境和javascript环境都保存一个bridge对象，里面维持着requestId,callbackId,以及每个id对应的具体实现。**其中一个比较重点的方法如下图所示，它用来判断是普通的跳转还是WebViewJavascriptBridge的跳转，然后再进行下一步操作。
```

![](https://upload-images.jianshu.io/upload_images/1742257-0e4ce6403b618020?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
                                     webView的代理方法

    以前使用UIWebView做的时候没有使用Bridge桥接，而是在其代理方法中进行拦截，然后做我们需要做的操作，示例代码如下图，需要注意的是WKWebView中不能使用下面第二张代码中的方法，WKWebView只能使用WKScriptMessageHandler来做JS交互。
```

![](https://upload-images.jianshu.io/upload_images/1742257-3166b9c474768d07?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
                                拦截url中的关键字段
```

![](https://upload-images.jianshu.io/upload_images/1742257-8abb4d1afc148a5c?imageMogr2/auto-orient/strip|imageView2/2/w/700)

```
                           UIWebView使用JSContext来与JS做交互
```



