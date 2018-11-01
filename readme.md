**面试题：常用的设计模式有哪些？是否了解责任链模式？**

#### 1. 单例模式

单例模式是为了保证一个类在系统运行的过程中只有一个实例对象。

#### 2. 工厂模式

工厂模式是一种常见的实例化对象模式，是用工厂方法代替 new 操作的一种模式。

使用工厂模式可能会多做一些工作，但是会给系统带来更大的扩展性和尽量少的修改量。

工厂模式有简单工厂模式、工厂方法模式、抽象工厂模式三种。

看到[这篇文章](https://www.jianshu.com/p/3f824a91d73b)，觉得挺好的，本项目的工厂模式的代码多来自这里。

#### 3. 装饰者模式

装饰者模式是为了对一个已有的类的功能进行增强。

对一个已有的类的功能进行增强的方式还有继承，可以继承已有类，在已有类的基础上进行功能的增强。

使用继承进行类的增强：**被增强的类是固定的；增强也是固定的**

使用装饰者模式进行类的增强：**被增强的类是可以变化的；增强是固定的**

百度百科上面的释义是：装饰者模式指的是在不必改变原类文件和使用继承的情况下，动态地扩展一个对象的功能。它是通过创建一个包装对象，也就是装饰来包裹真实的对象。

这里举了一个不同口味咖啡的例子。

#### 4. 构建者模式

**构建者模式（Builder Pattern），将一个复杂对象的构建与它的表示分离，使得同样的构建过程可以创建不同的表示。**

这种类型的设计模式属于创建型模式，它提供了一种创建对象的最佳方式。

一个 Builder 类会一步一步构造最终的对象。该 Builder 类是独立于其他对象的。

主要解决：在软件系统中，有时候会面临“一个复杂对象”的创建过程。其通常由各个部分的子对象用一定的算法构成；由于需求的变化，这个复杂对象的各个部分经常面临着剧烈的变化，但是将它们组合在一起的算法却相对稳定。

使用场景：1.需要生成的对象具有复杂的内部结构；2.需要生成的对象内部属性本身相互依赖。

Android中的AlertDialog，开源项目Retrofit都使用了 Builder pattern。

#### 5. 观察者模式

**观察者模式（Observer Pattern），当一个对象发生变化时，会自动通知它的依赖对象。观察者模式属于行为型模式。**

**通俗地讲**：就是发布订阅模式，发布者发布信息，订阅者获取信息，订阅了就能收到信息，没订阅就收不到信息。

**主要解决**：一个对象状态改变给其他对象通知的问题，而且要考虑到易用和低耦合，保证高度的协作。

**何时使用**：一个对象（目标对象）的状态发生改变，所有的依赖对象（观察者对象）都将得到通知，进行广播通知。

Android开发中常用的开源库 RxJava 就是使用的观察者模式。

module中参照网上的示例代码写了一个观察者模式的demo。

#### 6. 责任链模式

为请求创建一个接收者对象的链，对请求的发送者和接收者进行解耦。

**在这种模式中，通常每个接收者都包含对另一个接收者的引用。如果一个对象不能处理该请求，那么它会把相同的请求传给下一个接收者，依此类推。**

有点类似现实中的“击鼓传花”。

优点：<br>
1. 降低耦合度。它将请求的发送者和接收者解耦。
2. 可以动态的改变责任链，删除或添加或改变顺序。
3. 让每个处理者专注于实现自己的职责。

缺点：<br>
1. 不能保证请求一定被接收。
2. 系统性能将受到一定的影响，而且在进行代码调试的时候不太方便，可能会造成循环调用。
3. 可能不容易观察运行时的特征，有碍于除错。

Android 中的 okhttp 开源库的网络请求拦截器就是使用的责任链模式。

module是参照网上的示例代码写的一个简单的demo。

#### 7. 代理模式

代理模式又分为静态代理、动态代理。









