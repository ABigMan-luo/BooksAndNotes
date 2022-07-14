1.

JDK：java development kit, java 开发工具箱，包含了javac编译器，Java运行时环境，以及各种类库等。

JRE：java runtime enviorment,java运行时环境，用来运行java的字节码文件，包含JVM以及JVM运行的环境。

JVM：java virtual mechinal, java 虚拟机，是JRE的一部分，是整个平台的核心部分，负责运行字节码。

2.

hashCode() 与 equals()之间的关系：

​	每个对象都可以调用hashCode()得到自己的hash值，用于区别不同的对象： hash值相等，不一定是同一个对象；hash值不等，肯定是两个不同对象，如果两个对象相等，hash值一定相等。

​	java的一些集合类实现中，比较两个对象是否相等时，先比较两个对象的hash值，如果不相等，就认为两个对象不相等。然后在比较使用equals()方法。

​	所以在重写equals()方法时，要注意重写hashCode()的生成逻辑与equals()的逻辑一致。

3.

String ,StringBuffer,StringBuilder的区别

​	Stirng是常量，java有字符串不变性的规则，就是一旦创建就不会改变。StringBuffer是可以改变，线程安全。StirngBuilder是可以改变，线程不安全的。单线程环境，StringBuilder效率更高。

4.

