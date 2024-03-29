# Java Development Relevant Resource Collection
我收藏的Java相关技术资料

<br />

- [Java Platform Standard Edition 8 Documentation](https://docs.oracle.com/javase/8/docs/index.html)
- [Java Programming Language Enhancements（从Java SE 5一直到8）](https://docs.oracle.com/javase/8/docs/technotes/guides/language/enhancements.html#javase8)
- [Java Language Changes for Java SE 9](https://docs.oracle.com/javase/9/language/toc.htm#JSLAN-GUID-B06D7006-D9F4-42F8-AD21-BF861747EDCF)
- [Oracle JDK 9 Documentation](https://docs.oracle.com/javase/9/)
- [Java Native Interface Specification Contents](https://docs.oracle.com/javase/9/docs/specs/jni/index.html)
- [Java带标签的break 和带标签的continue](https://www.cnblogs.com/woaixingxing/p/6394952.html)
- [长知识了！Java 关键字 transient 还能这么用](https://www.toutiao.com/i6940997239938548228/)
- [一文带你认识Java8中接口的默认方法](https://www.cnblogs.com/sum-41/p/10878807.html)
- [Java中的Annotation详解和使用 自定义注解](http://blog.csdn.net/tabactivity/article/details/30493641)
- [给编译器看的注释——「注解」](https://www.toutiao.com/i6973546997924037127/)
- [JAVA annotation入门](http://blog.csdn.net/hbcui1984/article/details/4735487)
- [Java注解解析-运行时注解详解(RUNTIME)](https://blog.csdn.net/jsonChumpKlutz/article/details/81747839)
- [夜深了，源代码里突然来了一个新朋友](https://www.toutiao.com/i6911858070146515464/)
- [厉害了！老大利用AOP实现自定义注解，半小时完成我三天工作量](https://blog.csdn.net/u011277123/article/details/104728630)
- [IntelliJ IDEA如何生成可执行jar包](https://jingyan.baidu.com/article/c275f6ba0bbb65e33d7567cb.html)
- [IntelliJ IDEA读取资源文件](https://blog.csdn.net/yanwushu/article/details/43764303)
- [Java中使用Sqlite](https://bitbucket.org/xerial/sqlite-jdbc)
- [Java中用于做JSON解析的json-lib库](http://json-lib.sourceforge.net)
- [commons-lang下载](http://commons.apache.org/proper/commons-lang/index.html)
- [commons-beanutils下载](http://commons.apache.org/proper/commons-beanutils/)
- [commons-collections下载](http://commons.apache.org/proper/commons-collections/)
- [commons-logging下载](https://commons.apache.org/proper/commons-logging/)
- [ezmorph下载](http://ezmorph.sourceforge.net)
- [第六章 感受Mac之美-图文安装Gradle以及包解决下载慢的办法](https://www.toutiao.com/a6812509372137079299/)
- [在Jar包中查找Java类的小工具](https://blog.csdn.net/kongxx/article/details/85753286)
- [图示Java异步编程，清晰易懂，收藏了](https://www.toutiao.com/i6678498547207242253/)
- [IO多路复用学习](https://www.toutiao.com/i6801646973322691085/)
- Java中的原子数据类型：`java.util.concurrent.atomic`
- [为什么说ThreadLocal是线程安全的](https://www.toutiao.com/a6742843066614284807/)
- [多线程编程那些事](https://www.toutiao.com/i6904660632952439310/)
- [关于零拷贝的一点认识](https://www.toutiao.com/a6680353701208523272)
- [死磕 java集合之HashMap源码分析](https://www.toutiao.com/a6688257890353938947)
- [深入理解HashMap](https://www.toutiao.com/a6802089727966052867/)
- [从基础到实践，一文带你看懂HashMap](https://www.toutiao.com/i6875580417248854536/)
- [高并发编程系列：深入探讨ConcurrentHashMap](https://www.toutiao.com/a6680034750784078347/)
- [读源码 | ArrayMap 是如何高效利用内存的？](https://juejin.im/post/6875152386260910087)
- [Stream怎么感觉用的人还是少](https://www.toutiao.com/a6700346920361001483)
- [处理集合还是只会for循环？那你该了解了解Stream API了](https://www.toutiao.com/a6699360552717648388/)
- [java中FileInputStream与InputStream的available()方法的作用](https://blog.csdn.net/weixin_39851884/article/details/78609466)
- [Java 11必掌握的8大特性，完美代码信手拈来](https://www.toutiao.com/a6719656856689574407)
- [反射的深入浅出](https://www.toutiao.com/a6723009453613924872)
- [不懂得hashcode的重要性，程序的性能会大打折扣](https://www.toutiao.com/a6759004326334562823/)
- [JVM：醒醒，你的JVM宕机了！JVM之安全退出](https://www.toutiao.com/a6815757669639389699/)
- [JVM虚拟机：三分钟带你了解玩转“对象访问定位](https://www.toutiao.com/i6807333400010031628/)
- [Java 实例 - 格式化时间（SimpleDateFormat）](https://www.runoob.com/java/date-time-am-pm.html)
- [JAVA中Calendar与Date类型互转](https://blog.csdn.net/fz13768884254/article/details/82422752)
- [JAVA&CORBA详解](https://blog.csdn.net/zacklin/article/details/8207673)（RPC在Java中的实现也叫RMI，即Remote Method Invocation）

<br />

## Java 9新增的语法特性概览

Java 9刚发布不久，新增的Java语法特性并不多，这里笔者感觉比较实用的就是允许在接口中定义私有成员方法，这样可以更方便地实现当前接口的模块性封装。下面我将展示一些简单的代码进行描述。

```java
package com.company;
import org.jetbrains.annotations.Contract;


interface MethodFunction {
    void call(int i);
}

interface MyInterface {
    public void hello();

    @Contract(pure = true)
    private int method(int i) {
        return i + 1;
    }

    final int aa = 200;

    static MyInterface hi(MyInterface mi) {
        int x = aa + mi.method(50);
        System.out.println("Hi, there! x = " + x);
        return mi;
    }
}


public class Main {

    public static void main(String[] args) {
        // write your code here

        MyInterface.hi(new MyInterface() {
            @Override
            public void hello() {
                System.out.println("Hello, world!!");
            }
        }).hello();

        System.out.println("aa = " + MyInterface.aa);

        MethodFunction ref = (i) -> {
            System.out.println("This lambda param is: " + i);
        };

        ref.call(100);

        ref = Main::Hello;
        ref.call(20);

        Main m = new Main();
        ref = m::method;
        ref.call(10);
    }

    private static void Hello(int i) {
        System.out.println("i = " + i);
    }

    private void method(int i) {
        System.out.println("method i = " + i);
    }
}

```

上述代码比较简单，由于接口的私有成员方法只能作用于该接口自身，因此不能直接在实现它的类中进行直接访问。但我们可以通过在此接口中定义一个类方法，以对象传递的方式进行访问，这么一来正好可以形成针对当前接口的一种闭环设计。当然，**`private`** 也能修饰接口中的类方法。


