---
title: Java继承
date: 2021-3-3 16:30:30
tags:
- Core Java Volume学习笔记
---
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
  ```

### instanceof关键字
- 检查某个对象是否属于或者可转换成一个类的对象, 在转换对象之前,通常应该使用instanceof进行检查,如果直接转换这个对象不成功的话将会抛出ClassCastException.

### 抽象类
- 一个类中包含抽象方法的话,这个类必须被声明成抽象类(使用abstract关键字),同时,除了抽象方法外,抽象类也可以包含具体数据和具体方法.
- 抽象类的子类可以只实现其超类的部分抽象方法,但是这个类必须也被声明成抽象类
- 抽象类不能实例化,但是抽象类的对象变量可以引用非抽象子类的对象.

### protected关键字
- Java中受保护的部分对所有子类以及**同一个包中的其他类**都可见,这与C++中保护机制稍有不同,Java中的protected概念要比C++中的安全性差一些.

### 对象包装器与自动拆装箱
- 对象包装器,所有基本类型都有一个对应的包装器,例如Integer类对应基本类型int等,所有对象包装器类还是final修饰的,因此不能定义它的子类.
- 自动装箱的意思是把基本类型自动转换成其对象包装器的过程,例如:
  ```java
  ArrayList<Integer> list = new ArrayList<>();
  list.add(3); // 这里会产生自动装箱,将int基本类型转换成Integer类型
  // 编译器会将这条语句翻译成: list.add(Integer.valueOf(3));
  ```
- 相反地,当将Integer对象赋值给一个int对象时,就会自动地拆箱,例如:
  ```java
  int n = list.get(i); // 编译器会将这条语句翻译成: list.get(i).intValue();
  ```
- 当使用 == 比较两个对象包装器的时候,只会比较两个对象变量的引用值是否相等,可以使得两不同的对象包装器成立,也可以不成立.
- 在自动装箱规范中要求boolean,byte,char<=127,介于-128 ~ 127之间的short和int被包装到固定的对象中,例如下面例子:
  ```java
  Integer a = 127;
  Integer b = 127;
  System.out.println(a == b); // true

  Integer c = 128;
  Integer d = 128;
  System.out.println(c == d); // false
  ```
- 条件表达式中混合使用Integer和Double,Integer会拆箱成int转换成double后再装箱变成Double类型,例如:
  ```java
  Integer n = 1;
  Double d = 2.0;
  System.out.println(true ? n : d); // 1.0
  ```