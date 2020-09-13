### JAVA 多线程的两种实现方式

#### 继承 Thread 类

java 实现多线程的方法还是很简单的,只需要继承 Thread 类,重写 run() 方法即可,然后调用类的 start() 方法就可以实现了

```java
public class MyThread extends Thread{
    @Override
    public void run(){
        System.out.println("启动线程");
    }
}
```

```java
public class Main{
    public static void main(String[] args){
        MyThread thread = new MyThread();
        thread.start();
    }
}
```

#### 实现 Runnable 接口

由于 java 不允许多继承,所以当你的类已经继承了其他类之后就不能继承 Thread 类来实现多线程,所以 java 提供了 Runnable 接口来实现多线程,在 Runnable 接口中只有一个 run() 方法

```java
public class MyRunnable implements Runnable{
    @Override
    public void run(){
        System.out.println("线程启动");
    }
}
```

```java
public class Run {
    public static void main(String[] args){
        MyRunnable mr = new MyRunnable();
        Thread thread = new Thread(mr);
        thread.start();
    }
}
```

