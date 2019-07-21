# MengEr.github.io
#  Class01

- 开发流程
- 编码规范
- 变量
- 3.2 基本数据类型
- 3.3 数据类型的转换
- 3.4 运算符
- 3.5 流程控制
- 备注



###  开发流程

​	javac 编译把.Java文件变成.class文件

​	jvm读取字节码文件，运行在不同的底层操作系统中



###  编码规范

1.类名与文件名必须一致，否则编译不通过 eg:public class main

2.main是程序的入口

3.类是组织代码结构的，类中的其他方法是用来执行具体的业务逻辑的

```java
public class Main {    
    public static void main(String[] args) {
    System.out.println("Hello World!");    
    }
    }
```

- 注释

​	单行注释

 ~~~java
//
 ~~~

​	多行注释

~~~java
/*

*/
~~~

​	文档注释

~~~java
/**
*
*
*/
~~~



###   变量

- 变量名的定义要符合一定的规则：

  1.可以包含数字、字母、下划线、$

  2.不能包含空格，运算符

  3.不能用纯关键字给变量命名

  4.不能以数字开头

大小写可以混用，符合驼峰式命名法：如果变量名是一个单词组成，全部小写，如果由多个单词组成，第一个单词全部小写，后续的单词首字母大写。

~~~ java
String name="张三"
~~~



### 基本数据类型

（相反为引用类型）

​	Java 提供了 8 种基本数据类型：byte short int long float double boolean char

TB GB MB KB

B byte 

1 个字节（byte）是 8 位二进制数 01010101

1KB = 1024 byte

1MB = 1024 KB

1GB = 1024 MB

1TB = 1024 GB

byte 一个字节 

short 两个字节 16 位

int 四个字节 32 位

long 八个字节 64 位 

float 四个字节 32 位

double 八个字节 64 位

char 两个字节 16 位

boolean 1/8 个字节



### 数据类型转换

自动类型转换

强制类型转换

~~~ java
double num = 10.0;
int num2 = (int)num;
~~~

- 小数默认是double类型的 
- 精度小的会自动向精度大的转换，精度大的转向精度小的要强制转换
- float的精度小于double

``` java
float num = 10.0 //会报错
```

``` java
float num = 10.0f 
```



###  运算符

- 除法上自动变换

  int num1 = 10;

  int num2 = 3;

~~~ java
System.out.println(num1/num2) //3
~~~

​	  int num1 = 10;

​	  float num2 = 3;

~~~ java
System.out.println(num1/num2) //3.3333333
~~~

- 自增

~~~ java
int num = 10;
System.out.println(num++); //10
System.out.println(++num); //12
~~~

- equals可以比较字符串，比较堆内存里面存放的东西

~~~ java
 System.out.println(str1.equals(str2));
~~~

- 字符串常量池

```
String str1 = "java";
String str2 = "java";
String str3 = new String("java");
String str4 = new String("java");
System.out.println(str1==str2); //true (字符串常量池)
System.out.println(str3==str4); //false（堆内存）
```

- 逻辑运算符

  &和&&的区别

~~~ java
int x = 8;
int y = 9;
System.out.println((++x!=y)&(++x==y)); //false
System.out.println(x); //10
~~~

~~~java
int x = 8;
int y = 9;
System.out.println((++x!=y)&&(++x==y)); //false
System.out.println(x); //9
~~~

- 位运算符

~~~ java
System.out.println(10&5); //0
System.out.println(10|5); //15
System.out.println(10^3); //9
System.out.println(2<<3); //16
System.out.println(2>>3); //0
~~~

​	用二进制的运算效率高，左移

​		&：按位与

​		|：按位或

​		^：按位异或

​		<<：左移  右移：>>

​		A & B：每一位的数字一一对应，如果都为 1 ，则该位计作1，否则计作 0。

​		A | B：每一位的数字一一对应，只要有一个为 1 ，则该位计作1，否则计作 0。

​		A ^ B：每一位的数字一一对应，相同，则该位计作0，否则计作1。

​		A << B：A 乘以 2 的 B 次方法。

​		A >> B：A 除以 2 的 B 次方法。

#####  运算符的优先级

​		算数运算符>关系运算符>逻辑运算符

###  流程控制

- if else

  if 的嵌套

~~~ java
int score = 85;
if(score>80){
	System.out.println("优秀");
}else{
	if(score>=60){
		System.out.println("中等");
	}else{
			System.out.println("差");
	}
}
~~~

- switch-case

  如果没有break，会把从条件几往后的case全部输出.

  (switch-case只能做等值判断，而if else可以做其他逻辑判断)

  

  ######  循环

  1.循环四要素

  初始化循环变量    循环条件    循环体    更新（迭代）  循环变量

- for

- while

~~~ java
 int i = 0;
 while(i<10){
           System.out.println("123");
           i++;
                } //会进入死循环。如果改成++i，则10次出循环
~~~

- do-while

  注意：不能再do语句里面定义while里的判断的变量，作用域

- ==foreach==































































###  备注

- 强语言 弱语言
- 驼峰式命名法 myUserName
- 基本数据类型存放在==栈==里面，例如汉字则存放在==堆==类型中
- ![](D:\ffm\课件\java\图库\Snipaste_2019-07-18_17-46-13.png)
- public class是类（只有一个  后面和文件名相同）

​       class也是类 多了

​       string是类

- string【】 args是变量名
- static 静态的 (不可以少)
- var 任意的数据类型（Javascrpit的东西）

#### 加号的两个作用：运算符中的加法/拼接字符串

- 如果 + 两边都是数字类型（整形、浮点型）则执行加法运算。
- 如果 + 有一边是字符串，则自动将另一边转换为字符串类型，进行拼接。

```
//拼接字符串  结果为abcd
public class One {
	public static void main(String[] args) {
		String  a="ab";
        String  b="cd";
        System.out.println(a+b);
        }
}
```

```java
//101030
public class One {
    public static void main(String[] args) {
        String  a="10";
        String  b="10";
        int c=15;
        int d=15;
        System.out.println(a+b+(c+d));    
    }
}
//10101515
public class One {
    public static void main(String[] args) {
        String  a="10";
        String  b="10";
        int c=15;
        int d=15;
        System.out.println(a+b+c+d);    
    }
}
```

#### 求和函数的调用

```java
public class Main {
    public static void main(String[] args) {
        int x=Add(10,20);
        System.out.println(x);
    }   
    public static int Add(int a,int b){
        int sum=a+b;
        return sum;
    }
}
```

- 注意

  1.主函数无返回值用void否则会报错

  2.求和函数首字母大写Add

  3.int x=Add(a,b)其中a,b为赋值

