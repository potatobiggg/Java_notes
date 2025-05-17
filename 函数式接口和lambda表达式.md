**函数式接口** 就是**只包含一个抽象方法**的接口，用来表示“一个函数”。

```java
@FunctionalInterface  //这个注解也可以不加，但加上之后可以帮助你检测是不是只有一个方法
interface MyFunc {
    void doSomething();
}
```

**Lambda表达式本质是一个匿名函数**

作用是实现函数式接口

```java
//无返回值无参数
@FunctionalInterface
interface NoParameterNoReturn {
    void test();
}
//无返回值一个参数
@FunctionalInterface
interface OneParameterNoReturn {
    void test(int a);
}
//无返回值两个参数
@FunctionalInterface
interface MoreParameterNoReturn {
    void test(int a,int b);
}
public class TestDemo {
    public static void main(String[] args) {
        NoParameterNoReturn n = ()->{
            System.out.println("无参数无返回值");
        };
        n.test();

        OneParameterNoReturn o = (a)-> {
            System.out.println("无返回值一个参数"+a);
        };
        o.test(666);
        MoreParameterNoReturn m = (int a,int b)->{
            System.out.println("无返回值两个参数"+a+" "+b);
        };
        m.test(666,999);
    }
}

```

