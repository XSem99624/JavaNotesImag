---
typora-copy-images-to: 笔记中有关截图
仅作为Java学习过程中知识点的记录
---

[TOC]

待更新。。。

---

## 2.5 数据类型

> 相关参考资料见：[JAVA中分为基本数据类型及引用数据类型](https://www.cnblogs.com/dubo-/p/5565677.html)

### 2.5.1 数据类型的概述

#### 1. 数据类型的作用？

- 不同的数据有不同的数据类型，计算机会根据不同的数据类型分配不同大小的内存空间，用以存储数据。

#### 2. Java 数据类型的分类

Java数据类型分为：基本数据类型和引用数据类型。见图如下：
![2.5.2 Java数据类型](C:\Users\chenjn\Desktop\Java程序设计\Java零基础学习笔记（动力节点）\笔记\笔记中有关截图\2.5.2 Java数据类型.png)

##### （1）基本数据类型

- 整数型：byte、short、int、long；
- 浮点型：float、double；
- 布尔型：boolean；
- 字符型：char；

##### （2）引用数据类型

- 字符串型：String
- 类（class）
- 接口（interface）
- 数组（array）

### 2.5.2 基本数据类型

#### 1. 基本数据类型概述

##### （1）基本数据类型的取值范围

| 基本数据类型 | 占用空间大小（单位：byte） |                 取值范围                 | 默认值   |
| :----------: | :------------------------: | :--------------------------------------: | -------- |
|     byte     |        1( = 8 bit )        |                 -128~127                 | 0        |
|    short     |       2 ( = 16 bit )       |               -32768~32767               | 0        |
|     int      |       4 ( = 32 bit )       |          -2147483648~2147483647          | 0        |
|     long     |       8 ( = 64 bit )       |             -2^63 ~ (2^63-1)             | 0L       |
|    float     |       4 ( = 32 bit )       |     ±3.40282347E+38F（有效位数6~7位)     | 0.0f     |
|    double    |       8 ( = 64 bit )       | ±1.79769313486231570E+308 (有效位数15位) | 0.0d     |
|   boolean    |        1( = 8 bit )        |               true / false               | false    |
|     char     |       2 ( = 16 bit )       |           0 ~ 2^15（0~65535）            | '\u0000' |

> 基本数据类型中的整数型和浮点型数据类型有正负之分。1字节在二进制中的最高位为“符号位”，其中“0”，表示正数，“1”表示负数。

> Java语言的数据类型都是有符号的，参考资料见：[java数据类型是有符号的，那与有些无符号的如何区别](https://www.cnblogs.com/huzi007/p/6566567.html)

> Byte 的取值范围用二进制表示的方式与原码、反码、补码有关，见参考资料：[原码, 反码, 补码 详解 ](https://www.cnblogs.com/zhangziqiu/archive/2011/03/30/ComputerCode.html)

##### （2）计算机中数据的存储方式

- 现代计算机底层采用交流电的方式，只有接通和关闭两种状态。相对应的是 0 和 1 ，所以，计算机值识别 0 或1 （二进制）。
- 二进制是一种数据的表现形式，满足满二进一的原则。
> *不同进制之间的转换，参考资料见：[进制转换方法是什么](https://www.php.cn/faq/417579.html)

  ① 十进制转换成 X 进制：用十进制的除以 X 取余直至余数为1，再将余数串连起来。

  ② 十进制或其他进制转换成二进制：将其转换成最接近这个数的2的N次幂累加之和，或转换成二进制比特位。
  如：

  - 17 (10) = 2^4 + 2^0 ；
  - 17 (8) = 00000001 1111111 (2) ；
  - C (16) =  00001111 11111111 (2) ；

  ③ 二进制转换成十进制：将二进制数的每一位数乘以对应的2的次幂相加之和。
  如：10010 (2) = 0 * 2^0 + 1 * 2^1 + 0 * 2^2 + 0 * 2^3 + 1 * 2^4 = 17

  ④ 其他进制（二进制以外）转换成十进制：先转换成二进制，再转换成十进制。
  如：17 (8) = 00000001 1111111 (2) 
  			= 2^9-1 = 511(10)

##### （3）计算机中数据的存储单位

- 字节（Byte）是计算机中最小的存储单位。所有数据以比特（bit）的形式进行存储。其中，1Byte = 8 bit ，1比特位表示一个0或1。
- 常见的计算机存储单位之间的转换如下：
	- 1 B (Byte) = 8 bit；
	- 1KB = 1024 B；
	- 1MB =1024 KB；
	- 1GB = 1024 MB；
	- 1TB = 1024 GB；
> *存储单位之间的转换，见参考资料：[字节转化](https://blog.csdn.net/dalei9243/article/details/106096539)

#### 2. 字符编码

##### （1）字符编码概述

- 字符型（char）数据表示的是现实世界中的文字，通过计算机通过**字符编码**规则将现实世界中的文字转换成计算机中的二进制。
- 计算机最初只支持英文，最早出现的字符编码是：ASCII码
  'a' = 97 =  (01100001)；
  'A' = 65 = (01000001)；
  '0' = 48 = (00110000)；
  'a' >>按照ASCII码解码 >> 01100001；01100001 >>通过ASCII码编码>> 'a' 
- 计算机需采用同一套字典 / 对照表进行编码和解码，才不会出现乱码。
> 关于编码和解码，参见资料：[什么是编码，什么是解码。原理解读]([什么是编码，什么是解码。原理解读_toyijiu的专栏-CSDN博客_什么是编码解码](https://blog.csdn.net/toyijiu/article/details/106102836?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~default-1.pc_relevant_paycolumn_v2&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~default-1.pc_relevant_paycolumn_v2&utm_relevant_index=1))

##### （2）字符编码的发展史

- 随着计算机的发展，后来出现了一种编码方式，是国际化便准组织ISO指定的，这种编码方式支持修语言，向上兼容ASCII码，仍然不支持中文。这种编码是：**ISO-8859-1**，又称**latin-1**。
- 随着计算机向亚洲发展，计算机开始支持中文、日文、韩文等亚洲国家的语言，其中支持简体中文的编码方式：**GB2312 < GBK < GB18030**
- 支持繁体中文：**big5**
- 后来出现了一种编码方式统一了全球左右的文字，容量较大，这种编码方式称为：Unicode。这种编码有多种具体的体现：UTF-8、UTF-16、UTF-32......
- Java语言源代码采用的是Unicode编码方式，所以“标识符”可以写中文。
- 在实际开发中，一般使用UTF-8编码方式较多。

#### 3. 整数型

##### （1）Java语言中的整数型数据类型有：byte、short、int、long

##### （2）Java语言中的 “整数型字面值” 默认当作int型处理。若要表示long型数据，需要在数值后添加“ **l / L** ”（建议使用 L ）。

##### （3）Java语言中的整数型字面值的三种表现形式

- 十进制（默认情况下是十进制）；
- 八进制（编写八进制整数型字面值时，需以**0**开头）；
- 十六进制（编写十六进制整数型字面值时，需以**0x / 0X**开头）。

```java
public class DataTypeTest01{
    public static void main(String[] args){
        
        //三种进制
        
        int a = 10;//十进制的10
        int b = 010;//八进制的10
        int c = 0x10;//十六进制的10
        
        System.out.println(a);//10
        System.out.println(b);//8
        System.out.println(c);//16
        
        System.out.println(a + b + c);
                
        //Java语言中，默认将整数型字面值“123”当作int型，变量i也是int型，将“123”赋值给i时，不存在类型转换。
        int i = 123;
        System.out.println(i);
        
    }
}
```

##### （4）类型转换

> Java语言中的类型转换，见参考资料：[java类型转换](https://blog.csdn.net/hu619016140/article/details/80885026) 和 [Java 类型转换](https://blog.csdn.net/kezhenke/article/details/90286048?ops_request_misc=%7B%22request%5Fid%22%3A%22164266716016780264018151%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=164266716016780264018151&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~sobaiduend~default-1-90286048.nonecase&utm_term=java类型转换&spm=1018.2226.3001.4450)

① **自动类型转换**。
将小容量的整数类型转换成大容量的整数类型。直接赋值。

② **强制类型转换**。

将大容量的整数类型转换成小容量的整数类型。

- 需用强制转换符“**( )**”，将需要转换的类型名写在强制转换符内。但是在程序运行阶段可能**损失精度**。
- 在实际开发中，若整数字面值大小在byte、short、char类型的取值范围内，可直接赋值。
- 强制转换的原理：
  - 原始数据：00000000 00000000 00000000 00000000 00000000 00000000 00000000 01011100 （long类型）
  - 强制转换后的数据：00000000 00000000 00000000 01011100 （int类型）（补码形式）
- *注意：
  - 强制转换的数据的字面值不能超过原类型的取值范围。
  - 计算机中存储数据以补码的形式存储，需将补码转换为原码。


```java
public class DataTypeTest02{
    public static void main(String[] args){
        
        //自动类型转换
        
        // “456”默认为int型字面值，占4个字节
        //x是long型变量，占8个字节
        //将“456”赋值给x，JVM将自动把int型数值转换成long型数值
        long x = 456;
        System.out.println(x);
        
        //“2147483647”字面值是int型，占用4个字节
        //y是long型变量，占用8个字节，自动类型转换
        long y = 2147483647;
        System.out.println(y);
        
        //====================================================
        
        //“2147483648”默认视为int类型，但是超出了int类型的取值范围。
        //long z = 2147483648;//编译报错。
        
        //“2147483648L”表示long型字面值，将long型字面值赋值给long型变量，不存在类型转换
        long z = 2147483648L;
        int k = (int)z;
        System.out.println(z);//精度严重损失，结果为负数（-2147483648）
        
        /*
         * 原始数据：
        00000000 00000000 00000000 00000000 10000000 00000000 00000000 00000000
         * 强制转换后的数据：
        10000000 00000000 00000000 00000000 （补码形式）
         * 计算机中存储数据以补码的形式存储，需将补码转换为原码
        */
        
        //====================================================
        
        
        //强制类型转换
        
        //“100L”是long型字面值，将100L赋值给long型变量y，不存在类型转换
        y = 100L;
        //编译报错，变量 n 是int类型，变量 y 是long类型，不可以直接赋值，需要强制类型转换，
        //int n = y;
        int n = (int)y;
        
    }
}
```

##### （5）计算机二进制的三种表现形式

**① 原码**
**② 反码**
**③ 补码**

- 计算机底层表示和存储数据都采用二进制**补码**形式

- 正数的补码：与原码、反码相同；

- 负数的补码：负数的绝对值对应的二进制码，所有二进制位取反，再加1。
  > byte i = -1;
  > 原码：10000001
  > 反码（符号位不变，其他位取反）：11111110
  > 补码（反码+1）：11111111

  > byte b = (byte)150;
  > 150默认为int类型，它对应的二进制码为：
  > 00000000 00000000 00000000 10010110
  > 强制转换成byte类型后的二进制码为：10010110
  > 补码：10010110
  > 反码：10010101
  > 原码：11101010 (2) = -106

```java
public class DataTypeTest03{
    public static void main(String[] ags){
        
        byte b = (byte)198;
        System.out.println(b);//-58
        /*
        198=128+64+4+2
        原始数据：00000000 00000000 00000000 11000110
        强制转换后的数据：11000110 （补码形式）
        11000110 - 1 = 11000101 
        原码：00111010 = 58
        -58
        */
        
    }
}
```

#### 4. 浮点型

##### （1）Java中表示浮点型的数据类型

① float	单精度（4个字节）

② double	双精度（8个字节）

③ BigDecimal（不属于基础数据类型）

- 涉及到**财务**时，SUN公司在基础SE类库中，为程序员准备了精度更高的类型，**java.Math.BigDecimal**，它属于**引用数据类型**。

*注意： float 和 double 在计算机内部二进制存储时存储的都是**近似值**。

##### （2）Java中的SE类库的字节码、源码存储路径（以我的存储路径为例）

- SE类库字节码：C:\Program Files\Java\jdk1.8.0_144\jre\lib\rt.jar
- SE类库源码：C:\Program Files\Java\jdk1.8.0_144\src.zip
  例如：String.java和String.class。在`main(String[] args)`中的String使用的是String.class字节码文件。

##### （3）Java语言中的“浮点型字面值”默认以double类型处理。若要表示float型数据，需要在数值后添加“ **f / F** ”（建议使用 L ）。

##### （4）精度缺失

> 浮点型数据在使用时，或将浮点型数据强制转换成整型数据时，可能会出现精度缺失。出现这一问题的原因在于，计算机是以**二进制**表示和存储数据的，而计算机**内存**又是**有限**的，所以在对浮点数进行计算时必然是在有限的精度内进行的，这也必然会造成一部分的精度缺失。要解决这一问题，可以使用**java.Math.BigDecimal**进行计算。

> 关于浮点数精度丢失的问题，参考资料见：[浮点数的底层原理和精度损失问题](https://zhuanlan.zhihu.com/p/269619376) 和 [Java 浮点数精度丢失](https://www.cnblogs.com/backwords/p/9826773.html)

```java
public class DataTypeTest04{
    public static void main(String[] args){
        
        //“3.0”默认为double类型，变量d也是double类型，不存在类型转换
        double d = 3.0;
        System.out.println(d);
        
        //float f = 5.1;//编译错误，“5.1”默认为double类型，f为float类型，不可直接赋值
        float f = (float)5.1;
        //或float f = 5.1f;
        System.out.println(f);
        
    }
}
```

#### 5. 布尔型

##### （1）在Java语言中，boolean类型只有两个值：true和false。

##### （2）在底层存储时，boolean类型占用1个字节，其中，0为false，1为true。

##### （3）在实际开发中，boolean类型十分重要。经常用于逻辑运算和条件控制语句中。

```java
public class DataTypeTest05{
    public static void main(String[] args){
        
        //编译错误，不兼容的类型
        boolean flag = 1;
        
        boolean loginSuccess = true;
        
        if(loginSuccess){
            System.out.println("欢迎来到的我小岛！");
        }else{
            System.out.println("登陆失败！");
        }
        
    }
}
```

#### 6. 字符型

##### （1）基本用法

```java
public class DataTypeTest06{
	public static void main(String [] args){
        
        //定义一个char型变量s，并赋初始值'L'
        char s = 'L' ;
        System.out.println(s);//L
        
        //一个中文字符占用2个字节，char类型正好是2个字节
        //所以Java中的char类型变量可以存储一个中文字符。
        char n = '汇';
        System.out.println(n);//汇
        
        
        //编译错误，因为 LH 是字符串，不能用半角单引号包括起来
        //char f = 'LH';
        
        //编译错误，类型不兼容
        //i是char类型变量，"F"是字符串，不能将字符串赋值给char类型变量。
        //char i = "F";
    }
}
```

##### （2）转义字符：“\”

" \ " + 特殊字符 ，会将特殊字符转换成普通字符。

- 常用的转义字符有：
![常用的转义字符](C:\Users\chenjn\Desktop\Java程序设计\Java零基础学习笔记（动力节点）\笔记\笔记中有关截图\常用的转义字符.png)

- 输出语句的区别：
	- System.out.println(); 表示输出并换行；
	- System.out.print(); 表示输出，但不换行；
	- System.out.printf(); 表示按格式输出。

```java
public class DataTypeTest07{
    public static void main(String[] args){
        
        //一个普通的 n 字符
        char c1 = 'n';
        System.out.println(c1);
        
        //转义字符，“\n”表示换行
        char c2 = '\n';
        System.out.println(c2);
        
        //一个普通的 t 字符
        char c3 = 't';
        System.out.println(c3);
        
        //制表符tab，“\t”表示一个tab键
        char c4 = '\t';
        System.out.println(c4);
        
        
        //输出一个反斜杠“\”
        //第一个反斜杠是转义字符，将后面的反斜杠转换成普通字符
        char c5 = '\\';
        System.out.println(c5);
        
        //输出一个单引号“ ' ”
        //char c6 = '';//编译报错，Java程序不允许这样编写程序
        //char c6 = '''; //编译报错，前两个单引号配对，第三个单引号落单
        //反斜杠具有转义功能，可将单引号转换成一个普通字符
        char c6 = '\'';
        System.out.println(c6);
        
        //输出一个双引号“ " ”
        char c7 = '"';//可直接输出一个双引号，双引号前后的单引号配对
        
        System.out.println("You complete me.");//You complete me.
        System.out.println("“You complete me.”");//“You complete me.”
        System.out.println(""You complete me."");//编译报错，前两个和或两个双引号两两成对
        //转义字符“\”加上后面的双引号“ " ”，可将双引号转换成普通字符
        System.out.println("\"You complete me.\"");//"You complete me."
        
    }
}
```

##### （3）中文字符与Unicode编码的转换

JDK中bin目录下的native2ascii.exe命令，可以将文字转换成Unicode编码。
在命令行输入**nativeascii.exe**回车，输入一个中文字符，即可得到对应的Unicode编码（16进制）。如下图：

![中文字符与Unicode编码的转换](C:\Users\chenjn\Desktop\Java程序设计\Java零基础学习笔记（动力节点）\笔记\笔记中有关截图\中文字符与Unicode编码的转换.png)

```java
public class DataTypeTest08{
    public static void main(String[] args){
        
        /* \u 之后的十六进制数表示某个中文字符的Unicode编码
         * “汇”的Unicode编码是6c47
         * 对应二进制数为:
         * 00000000 00111111 00001111 11111111 00000000 00001111 00000000 01111111
         */
        char h = '\u6c47';
        System.out.println(h);//汇
        
    }
}
```
#### 7. 基本数据类型之间的互相转换

##### （1）转换规则

① 八种基本数据类型中，除布尔类型之外剩下7个类型之间都可以互相转换；

② 小容量向大类型转换，称为自动类型转换。容量从小到大排序：![image-20220121005919298](C:\Users\chenjn\Desktop\Java程序设计\Java零基础学习笔记（动力节点）\笔记\笔记中有关截图\image-20220121005919298.png)

* 任何浮点类型容量都比整数型大
* char 和 short 克表示的种类和数量相同，但 char 可以取更大的正整数

③ 大容量转换成小容量，需要进行强制类型转换，但在运行阶段可能会损失精度，谨慎使用。char c = 'a';

④ 当整数字面值没有超出 byte 、short 、int 、char 的取值范围，可以直接赋值给 byte 、short 、int 、char 类型变量。

⑤ byte 、short 、int 、char 类型进行混合运算时，各自先转换成 int 类型再做运算。

⑥ 多种数据类型混合运算，先转换成容量最大的类型再做运算。

```java
public class DataTypeTest09{
    public static void main(String[] args){
        
        //编译错误，“1000”默认为int型，超出了byte类型的取值范围，不可直接赋值
        //byte b1 = 1000;
        
        //20在byte类型的取值范围之内
        byte b2 = 20;
        
        //1000在short的取值范围之内
        short s = 1000;
        
        int i = 1000;
        
        //从int类型转换成long类型，可自动类型转换
        long l1 = i;//1000
        
        //编译错误，大容量转换成小容量会出现精度缺失
        //int e = l1
        //将long类型变量强制转换成int类型，且1000在int类型的取值范围内
        int e = (int)l1;
        
        //10和3默认为int类型，所以“10/3”的结果默认也为int类型
        int f = 10/3;
        
        //自动转换
        long g = 10;
        /*
        变量g是long类型变量，存储的是long类型字面值
        与int类型字面值运算，会先将“3”转换成较大容量的long类型，再运算。
        计算结果为long类型字面值，不能直接赋值给小容量的int类型，会精度丢失*/
        //int h = g/3;
        
        //先将long类型的变量g强制转换成int类型，再与int类型字面值进行运算，结果也为int类型，可以直接赋值给int类型变量h。
        int h = (int)g/3;
        //或将计算结果直接赋值给long类型变量。
        //long h = g/3;
        
        double d = 10/3;
        
    }
}
```


