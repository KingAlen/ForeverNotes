#### OverView
* Google在2019的IO大会上宣布，Kotlin first. So 是时候了解一波Kotlin啦。比起Java，从编程思想到代码细节都有不少变化。 我们要对Kotlin有整体的基本了解，然后去学习和使用，这样才能高效掌握Kotlin语言。

* 1995年Sun发布了Java语言，当时与C相比，Java语言简单，面向对象，稳定，平台无关等优点，打开一个新的世界。但是20多年，虽然有扩展更新，底层设计思想很难改动，导致很难实现一些新的语言特性。例如函数式编程、Lambda表达式、流式API、高阶函数、空指针安全等。(Java8实现了部分特性，但Android还不支持Java8) -> 开发效率/时间是软件公司真正的瓶颈，任何能压缩代码量，提高开发效率的举措，都应该受到重视。

* 相比Java，Kotlin在编写代码时具有如下优势：代码简洁高效、函数式编程、空指针安全、支持lambda表达式、流式API等.
执行效率上：与Java同样的理论速度
兼容性：代码文件可以并存，代码可以互相调用，文件可以互相转换


#### Kotlin了解：从表面到更深层次

* findViewById
```
import kotlinx.android.synthetic.main.activity_main.*
setContentView(R.layout.activity_main)
hello.text = "fuck"
```
虚拟的包，临时创建。编译时自动补充


* ：符号    
Java: 三元运算符；switch case    
kotlin:  变量类型，参数类型，函数返回值类型，类/接口继承
使用Java类： MainActivity::class.java

* 不需要; 不需要new 对象
* kotlin支持类型推断 val name: String = "hello" => val name = "hello"
* 初始化和延迟加载： 必须初始化
* 空指针  ? !!
* 函数定义 fun 方法名(参数名：类型，参数名：类型...):返回类型 {}
* is 取代 instance of， when 取代 switch
* 数据类 data class Client(var id:Long)
* 单例模式： kotlin从语言级别提供了单例，关键词为object. 一个类定义为单例，需要用companion objet
* 为已存在的类扩展方法和属性：无法扩展已存在的方法；扩展是伪装的，只是针对当前的类(IDE和编译器)
* 类家族结构
   * Object取消，，基类改为Any
   * object是Kotlin单例
   * rivate, protect 类似，internal 模块内可见， inner 内部类
   * final 取消，kotlin类默认不能继承，只有open修饰的类能继承
   * static 取消，用company object替换
   * 继承 类加()

#### Kotlin的函数式编程
* 纯函数 输入一定，输出也固定不受影响
* 不变形： x=x+1 非法 不变形的好处：问题好追踪；多线程安全  
* 函数式编程里，没有变量，一切都是函数（就像面向对象编程里，一切都是对象）
* 只能新增变量，不能修改=>消耗内存：没有循环
* 高阶函数：参数为函数或者返回值为函数 的函数
    * lambda可作为一种类型，被定义为val    
    ```
    val printMsg = { msg: String ->
        println(msg)
    }
    fun doPrint(msg: String) {
       printMsg.invoke("hello")
    }
    ```
* 闭包 不是函数，逻辑上是封闭的
* Lambda表达式 


#### 有趣的函数
* it 进一步简化lambda表达式  { value -> value*2}   =>   {it*2}
* let 把负责的对象赋值给it
* apply 可以操作一个对象的任何函数，结合let返回该对象
* run 操作一块儿代码
* with 类似apply, 把对象作为参数传入with函数，然后再代码块中操作



    
