# java：异常

## 面试题

类ExampleA继承Exception，类ExampleB继承ExampleA。
有如下代码片断：

```java
try {
    throw new ExampleB("b")	//#1
} catch（ExampleA e）{
    System.out.println("ExampleA");
} catch（Exception e）{
    System.out.println("Exception");
}  
```

答：输出：ExampleA。（根据里氏代换原则[能使用父类型的地方一定能使用子类型]，抓取ExampleA类型异常的catch块能够抓住try块中抛出的ExampleB类型的异常）

补充：里氏代换原则：能使用父类型的地方一定能使用子类型

#1：这里异常捕捉通过类型捕捉。按照类加载机制的思路，子类初始化之前会先初始化父类的思路是错误的。

