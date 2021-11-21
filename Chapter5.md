# 继承
### 类 超类 子类
- 子类派生自超类,继承了超类的protected级及以上的方法和数据.
### 多态
- 同一种行为或者方法,表现出不同的动作或者表现形式
- 多态的例子
  ```java
  class Animal{
    public void say(){
      System.out.println("I'm Animal");
    } 
  }
  class Dog extends Animal{
    public void say(){
      System.out.println("I'm Dog");
    }
  }
  public class Example{
    public static void main(String[] args){
      Animal a;
      a = new Animal();
      a.say(); // I'm Animal
      a = new Dog();
      a.say(); // I'm Dog
    }
  }
  ```
- 子类数组的引用可以转换成超类数组的引用,但这会出现一些问题,例如下面这个例子:
  ```java
  class Animal{
  }
  class Dog extends Animal{
    public void bark(){
      System.out.println("Bark~Bark!");
    }
  }
  public class Example{
    public static void main(String[] args){
      Dog[] dogs = new Dog[10];
      for (int i = 0; i < 10; i++) {
    	  dogs[i] = new Dog();
      }
      Animal[] animals = dogs;
      animals[1] = new Animal(); // throw ArrayStoreException
    }
  }
### instanceof关键字
- 检查某个对象是否属于或者可转换成一个类的对象, 在转换对象之前,通常应该使用instanceof进行检查,如果直接转换这个对象不成功的话将会抛出ClassCastException.
### 抽象类
- 一个类中包含抽象方法的话,这个类必须被声明成抽象类(使用abstract关键字),同时,除了抽象方法外,抽象类也可以包含具体数据和具体方法.
- 抽象类的子类可以只实现其超类的部分抽象方法,但是这个类必须也被声明成抽象类
- 抽象类不能实例化,但是抽象类的对象变量可以引用非抽象子类的对象.
### protected关键字
- Java中受保护的部分对所有子类以及**同一个包中的其他类**都可见,这与C++中保护机制稍有不同,Java中的protected概念要比C++中的安全性差一些.
### 对象包装器与自动装箱
