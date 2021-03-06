# 13 闭包
闭包是现代编程语言的高级特性，新生的很多语言都支持闭包，如：swift、nim等，C++11标准、Java 8也支持了闭包。闭包是什么？先来看看[维基百科][wiki]上的描述：
>在计算机科学中，闭包（英语：Closure），又称词法闭包（Lexical Closure）或函数闭包（function closures），是 __引用了自由变量的函数__。这个被引用的自由变量将和这个函数一同存在，即使已经离开了创造它的环境也不例外。所以，有另一种说法认为闭包是由函数和与其相关的引用环境组合而成的实体。闭包在运行时可以有多个实例，不同的引用环境和相同的函数组合可以产生不同的实例。<br /><br />
闭包的概念出现于60年代，最早实现闭包的程序语言是Scheme。之后，闭包被广泛使用于函数式编程语言如ML语言和LISP。很多命令式程序语言也开始支持闭包。

[wiki]:https://zh.wikipedia.org/wiki/%E9%97%AD%E5%8C%85_(%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%A7%91%E5%AD%A6)

可以看到，第一句就已经说明了什么是闭包：闭包是引用了自由变量的函数。所以，闭包是一种特殊的函数。

在rust中，函数和闭包都是实现了`Fn`、`FnMut`或`FnOnce`特质（trait）的类型。任何实现了这三种特质其中一种的类型的对象，都是 __可调用对象__ ，都能像函数和闭包一样通过这样`name()`的形式调用，`()`在rust中是一个操作符，操作符在rust中是可以重载的。rust的操作符重载是通过实现相应的`trait`来实现，而`()`操作符的相应`trait`就是`Fn`、`FnMut`和`FnOnce`，所以，任何实现了这三个`trait`中的一种的类型，其实就是重载了`()`操作符。关于`Fn`、`FnMut`和`FnOnce`的说明请看第二节闭包的实现。

本章主要分四节讲述：

* [第一节 概要](13-00-overview.md)
* [第二节 闭包的语法](13-01-syntax.md)
* [第三节 闭包的实现](13-02-implementation.md)
* [第四节 闭包作为参数或返回值](13-03-as_argument_return_value.md)
