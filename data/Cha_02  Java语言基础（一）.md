---
typora-copy-images-to: 笔记中有关截图
仅作为Java学习过程中知识点的记录
---

[TOC]

本文是本人观看学习了B站视频《[Java零基础教程视频（适合Java 0基础，Java初学入门）]([Java零基础教程视频（适合Java 0基础，Java初学入门）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Rx411876f?p=23))》第P23 - P31内容所作的笔记。未完全按照视频中内容摘录知识点和代码，稍作修改。就记记，主要是方便自己日后复习吧。基础知识还是比较重要的哈~

## 2.1 标识符

### 2.1.1 标识符的概念

* 程序员可以自定义命名的单词为标识符。
* 标识符可以标识：类名、方法名、变量名、接口名、常量名……

### 2.1.2 标识符的命名规则

命名规则是编程语言的语言，不符合规则，编译器会报错。

* 一个合法的标识符只能由数字（0~9）、字母（A~Z、a~z）、下划线（_）和美元符号（$）组成,不能含有其他特殊符号（空格也是一个符号）。
* 不能以数字开头
* 严格区分大小写
* 关键字（如：public、main等）不能做标识符
* 理论上无长度限制

### 2.1.3 标识符的命名规范

命名规范不属于Java语言语法，不遵守规范，编译器不会报错。

* 命名时最好能见名知意
	```java
	public class UserService{
		public void login(String name,String password){
			
		}
	}
	```
* 遵守驼峰命名法
	如：OuterClass、outerObject、StaticNestedClass、nestedObject等。
* 类名、接口名：首字母大写，后面每个单词首字母大写；
* 变量名、方法名：首字母小写，后面每个单词首字母大写；
* 常量名：全部大写，若为多个单词组成，单词之间用下划线（ _ ）分隔。
	
	```java
	public class IdentifierTest01 //IdentifierTest01 是一个自定义的类名，可修改
	{
		//mian是程序的入口，一般不可以修改，args是变量名
		public static void main(String [] args){
			
		}
	}
	```



---

## 2.2 关键字

### 2.2.1 Java语言中的关键字包括：

#### 		1. 数据类型
​		byte   char   short   int   float   long   double   boolean   class   interface   enum

#### 	2. 常量值

​		true   false   null

#### 		3. 流程控制
​		<u>if  else</u>   <u>do  while</u>   for   <u>switch  case  default</u>   break   continue   return   <u>try  catch  finally</u>   assert

#### 		4. 修饰符
​		public   protected   private   final   void   static   abstract   *strictfp   transient   sychronized   volatile   native*

#### 		5. 动作
​		package   import   throw   throws   extends   implements   this   super   instanceof   new

#### 		6. 保留字
​		goto   const（在Java中无意义，在汇编中有意义）

   <u>*Java中的关键字全部为小写*</u>



---

## 2.3 字面值

### 2.3.1 字面值的概念

字面值，即字面意义上的数据值。在Java中称作字面值，在C语言中称为常量。

- 字面值（const）如：10、3.14、"const"、'a'、true；

- 字面值就是数据；

- 字面值和标识符、关键字为 Java 源程序的组成部分；

### 2.3.2 字面值的分类

- 数据在现实世界中是分门别类的，所以数据在计算机世界中也有区分不同数据类型，如：
  - 整数型字面值：10、-10；
  - 浮点型字面值：3.14；
  - 布尔型字面值：true、false；
  - 字符串型字面值："const"、"字面值"；
  - 字符型字面值：'c'、'值'；
  
- 注意：
  - **字符串**用**半角**的双引号包含起来，如：`"This is a string."`；
  - **字符**是用**半角**的单引号包含起来，且只能是**单个**字符，如：`'This is a char.'`。

### 2.3.3 代码示例

```java
public class ConstTest01{
    public static void main(String [] args){

        //字符串型的字面值要用半角双引号（ " " ）包括起来
        System.out.println("This is a string.");

        //字符型的字面值要用半角单引号（ ' ' ）包括起来，且只能是一个字符，否子编译器会报错
        System.out.println('c');

        //整数型、浮点型和布尔型字面值可以直接写
        System.out.println(111);
        System.out.println(3.14);
        System.out.println(true);
	}
}
```

​	

---

## 2.4 变量

​		数据在计算机中会占用一定内存，每次输出一个数据，都会自动产生一个临时内存空间用来存储这些临时数据。为了持续访问这某一块内存空间，我们需要声明一个变量来创建固定的内存空间。

### 2.4.1 变量的概念

- 变量本质上是一块内存空间，包括 **数据类型**、**名称**和**字面值**（数据）；
- 变量是内存中存储数据的最基本单元。
- 变量中存储的具体的 **数据** 应与变量的 **数据类型 一致**，若不一致，编译会报错。

### 2.4.2 变量的声明与赋值

#### 1. 声明 / 定义变量的语法格式

​		**数据类型 变量名;**
​		**数据类型 变量名1,变量名2,变量名3;**

​	如：`String name,;`、`int age,height;`；

​	变量名应符合**标识符命名规则**

#### 2. 变量赋值的语法格式

​		**变量名 = 字面值;**

​	如：`age=21;`、`name="LHH"`；

​	要求：字面值的数据类型必须和变量的数据类型一致。
​		其中，**=** 是一个运算符，称为 **赋值运算符**。赋值运算符先运行等号左边的表达式，再将计算结果赋值给左边的变量。

#### 3. 声明与赋值可以同时进行

​	如：`String name = "LHH";`、`int age = 21;`；

#### 4. 变量的值可变换

```java
int i=10;
System.out.println(i);//10
int i=100;
System.out.println(i);//100
int i++;
System.out.println(i);//101
```

### 2.4.3 变量的访问

#### 1. 变量访问的方式

* 获取变量中保存的具体数据（get），如：`System.out.println(i);`；
* 修改变量中保存的具体数据（set），如：`i++;`。

#### 2. Java中的变量必须先声明并赋值后才可访问

​		变量在声明时，程序并未为其开辟一个内存空间，所以变量 i 并未初始化，不可直接访问。

#### 3. Java程序中，在一个方法里，严格按照至上而下的顺序执行代码

```java
public class VarTest01{
    public static void main(String [] args){
        
        //声明一个int型的变量，i
        int i;
        
        //直接输出i，编译会报错，因为变量i未进行初始化
        //System.out.println(i);
        
        //给变量i赋值，i在此处完成初始化，内存空间开辟
        i=10;
        System.out.println(i); //10
        
        //变量的值可以改变
        i++;
        System.out.println(11);//10
        
        //可以同时声明多个变量
        int height,weight,age=21;
        
        //编译报错，因为未对变量height初始化
        //System.out.println(height);
        
        //编译报错，因为未对变量height初始化
        //System.out.println(weight);
        
        System.out.println(age);//21
    }
}
```

### 2.4.4 变量的作用域

#### 1. 作用域的概念

- 变量的作用域，是用以描述变量在程序中的有效范围。

- 变量只在其**作用域内可被访问**。

- 在同一个作用域中，变量名**不可重名**；在不同作用域中可重名

#### 2. 代码示例

```java
public class VarTest02{
    //声明了一个int型的类（静态）变量age为21
    // * 用static修饰的变量成为静态变量或类变量，类变量可在类中访问
    static int age=21;
    
	public static void main(String [] args){
		//变量name的作用域为main方法体内，只能在main()中被访问
	    String name="LHH";
	    System.out.println(name);//LHH
	    
	    name="FYY";
	    System.out.println(name);//FYY
	    
	    //同一作用域中，变量名不可重复命名
	    //System.out.println(name);
	    
	    //for循环中，变量的作用域
	    for(int i=0;i<10;i++){
	        //在该for循环中，变量i的作用域为for循环开始直至结束
	    }
	    //无法访问for循环中的变量i
	    //System.out.println(i);
	    
	    int j;//j的作用域为main()方法体内
	    for(j=0;j<10;j++){
	        
	    }
	    System.out.println(j);//输出10
	    
	}
	
	public static void doSomething(){
	    
	    //编译错误，无法访问main()中的name
	    //System.out.println(name);
	    
	    System.out.println(age);
	}
}
```

### 2.4.5 变量的分类

#### 1. 根据变量声明的位置分：

* 局部变量
  在方法体中声明的变量，称为局部变量。
* 成员变量
  在方法体外（类体之内）声明的变量，称为成员变量。
* 成员变量和局部变量的区别：
  成员变量无需赋值也可以访问，计算机会自动给成员变量赋默认值

#### 2. 代码示例

```java
public class VarTest03{
    
    //成员变量，作用域仅在 VarTest03 类体中
    String name = "LHH";
    
    //声明一个成员变量k，并赋初值
    static int k=1000;
    
    //声明一个成员变量f，系统自动赋予默认值，为0
    static int f;
    
    //主方法，程序的入口
    public static void main(String [] args){
        
        //局部变量，作用域仅在 main() 方法体中
        String birthday = "09.17";
        
        //输出主方法中变量birthday的值
        System.out.println(birthday);//09.17
        
        int i;
        
        //System.out.println(i);//编译报错，因为未对局部变量i赋初始值
        System.out.println(k);//1000
        System.out.println(f);//0
        
    }
    
    //成员变量，作用域仅在 VarTest03 类体中
    String birthday="八月二十";
    
    //除声明变量之外，类体中不能直接编写其他Java语句
    //System.out.println(birthday);
    
    public static void doSomething(){
        
        //局部变量，作用域仅在 doSomething() 方法体中
        String birthday="9月17日";
        
        //输出doSomething()方法体总中变量birthday的值
        System.out.println(birthday);//9月17日
        
    } 
    
}
```


