1、String,StringBuffer与StringBuilder的区别

    String 字符串常量；StringBuffer字符串变量（线程安全）；StringBuilder字符串变量（非线程安全）
    String类型和StringBuffer类型的主要性能区别其实在于String是不可变的对象, 因此在每次对String类型进行改变的时候其实都等同于生成了一个新的String对象，然后将指针指向新的String对象
    StringBuffer类则结果就不一样了，每次结果都会对StringBuffer对象本身进行操作，而不是生成新的对象，再改变对象引用。所以在一般情况下我们推荐使用StringBuffer，特别是字符串对象经常改变的情况下

2、 final、finally、finalize区别

    Final用于修饰类、成员变量和成员方法。final修饰的类，不能被继承；Final修饰的方法不能被重写，但是子类可以用父类中final修饰的方法；Final修饰的成员变量是不可变的
    Finally通常和try catch搭配使用，保证不管有没有发生异常，资源都能够被释放（释放连接、关闭IO流）。
    Finalize是object类中的一个方法，子类可以重写finalize()方法实现对资源的回收。垃圾回收只负责回收内存，并不负责资源的回收

3、序列化的方式

    实现了序列化接口Serializable；实现接口Externalizable
    Android中增加Parc