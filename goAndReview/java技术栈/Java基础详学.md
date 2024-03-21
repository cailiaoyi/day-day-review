## java入门

### Java跨平台的原理

### 三步骤

==编程、编译、运行==。

### 高级语言编译运行方式

- 编译型：翻译整个代码


- 解释型：按行翻译代码


- 混合型：半编译、半解释


​		Java是混合型，先将源文件编译成xxx.class字节码文件之后，将字节码文件运行在虚拟机当中，再逐行进行代码的翻译

### JDK和JRE

- JDK：包含jvm、核心类库、开发工具
  - jvm：Java程序运行的地方
  - 核心类库：Java已经写好的东西，可以直接使用
  - 开发工具：javac、java、jdb、jhat...

- JRE：包含jvm、核心类库、运行工具
- 三者包含关系：JDK包含了JRE、JRE包含了JVM

## java基础概念

### java注释

- //注释信息

- /* 注释信息 */
- /** 注释信息 */

## 数据类型类初始值刷题集

![QQ图片20240101161638](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240101161638.png)

方法内定义的变量没有初始值，必须要进行初始化。 类中定义的变量可以不需要赋予初始值，默认初始值为0。  

### java字面量和数据类型

整数类型默认是int，浮点数类型默认是double

- ==基础类型==（默认boolean为false，其余都是0）
  - 整形---->byte、short、int、long
  - 浮点型---->float、double

```
double d = 3;
double d = 3.0;
Double d = 3.0;
Double d = 3D;
错误写法：Double d = 3;

但是float
float f = 3;
float f = 3.0F;
错误写法：float f = 3.0;
Float f = 3F;
错误写法：Float f = 3;
```



- 字符型---->char
- 布尔型---->boolean
- ==包装类型==（默认值为null）
  - 整形包装---->Byte、Short、Integer、Long
  - 浮点包装---->Double、Float


- 字符包装---->Character
- 布尔包装---->Boolean
- ==引用类型==（默认值为null）
  - 类
  - 数组
  - 接口
- 字面量
  - 基础类型
  - 引用类型
  - 空（null）
  - 制表符（\t）

### 计算机的存储规则

- 存储类型
  - text文本：二进制组成
  - image图片：黑白图、灰度图、彩色图
  - sound声音：音质与采样多少相关

- 常见进制

  - 二进制：==以0b开头==
  - 十进制：
  - 八进制：==以0开头==
  - 十六进制：==以0x开头==

- 进制转换

  - 任意进制转10进制

    公式：系数 * 基数的权次幂

  - 十进制转其他进制

    公式：除基取余法

    ![Screenshot_20231218_104411_tv.danmaku.bilibilihd_](C:\Users\12629\Desktop\笔记截图保存\Screenshot_20231218_104411_tv.danmaku.bilibilihd_.jpg)

### 标识符

概念：给类、方法、变量等起的名称

- 硬性要求： 标识符由**数字、字母、下划线（_）和美元符号（$）**组成

  ​					不能以数字开头、不能是关键字

  ​					区分大小写

- 软性要求：

  - 小驼峰命名法：方法名、变量名

    标识符是一个单词的时候全部小写

    标识符由多个单词组成的时候，第一个单词首字母小写，其他单词首字母大写

  - 大驼峰命名法：类名

    标识符是一个单词的时候首字母大写

​			  标识符由多个单词组成的时候，第一个单词首字母小写，每个单词首字母大写

### 键盘录入Scanner

- 导包：

  ```
  import java.util.Scanner;
  ```

- 创建对象：

  ```
  Scanner sc = new Scanner(System.in);
  ```

  

- 接收数据：

  ```
  sc.nextInt();
  sc.nextLong();
  sc.nextLine();
  ```

### 运算符和表达式

- 运算符：对字面量或者变量进行操作的符号

  - 算术运算符：加减乘除、取模

  - 隐式转换和强制转换

    - 隐式转换：取值范围小的数据->取值范围大的数据

    - 强制转换：取值范围大的数据->取值范围小的数据

    - 取值范围：byte---short---int---long---float---double

      byte、short、char三种类型的数据在运算时都会==直接提升为int==，再进行计算

  - 字符串和字符的加操作

    - "+"操作是字符串的连接符，在连续进行“+”操作时，从左到右逐个执行，并产生一个新的字符串
    - 字符的“+”操作，就是int的“+”操作，字符的数值对应于ASCII码值

  - 自增自减运算符

    ++和--

    a++表示==先用后加==

    ```
    int a = 10;
    int b = a ++;
    // a = 11,b = 10
    ```

    ++a表示==先加后用==

    ```
    int a = 10;
    int b = ++ a;
    // a = 11,b = 11
    ```

  - 赋值运算符

    =

  - 关系运算符

    +=、-=、*=、/=、%=

  - 四种逻辑运算符

    ==&==：逻辑与---->需要将表达式全部执行，且表达式全部为真，结果才是真

    ==|== ：逻辑或---->需要将表达式全部执行，且表达式全部为假，结果才是假

    ==^== ：逻辑异或---->相同为false，不同为true

    ==!==  ：逻辑非---->取反

  - 短路逻辑运算符

    ==&&== ：短路与---->不必将表达式全部执行，左边可以确定结果之后，右边就不用参与运行了

    ==||== ：短路或---->不必将表达式全部执行，左边可以确定结果之后，右边就不用参与运行了

  - 三元运算符

    a>b?a:b，true的话，返回a，false返回b

- 表达式：用运算符把字面量或者变量连接起来的符合java语法的式子

  ​			    不同运算符连接的表达式体现的是不同类型的表达式

### 运算符和表达式类刷题集

![QQ图片20240220125213](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240220125213.png)

|：会将代码全部执行

||：若前面的条件为true。则后面的代码将不在执行

### 三码（原码、反码、补码）

- 原码：十进制的二进制（0000 0000--->+0，1000 0000--->-0）

- 反码：用于处理二进制负数的运算

  运算方法：先将原码取反（符号位不变，数值位取反），再与要操作的数进行运算，运算完成之后再取反

- 补码：只有一种零的表达形式（0000 0000）

  ![Screenshot_20231218_160230](C:\Users\12629\Desktop\笔记截图保存\Screenshot_20231218_160230.jpg)

### 条件和循环

条件、选择语句：if和switch

循环语句：do{}while，while和for

- 条件

  - if

  - if...else...

  - if...else if...else if...else

  - switch...case...

    - 格式1：

    ```
    Scanner sc = new Scanner(System.in);
            int a = sc.nextInt();
            int b = sc.nextInt();
            switch (表达式--->具体值) {
                case 10--->具体值:
                    System.out.println(10);
                    break;
                case 20--->具体值:
                    System.out.println(20);
                    break;
                default:
                    System.out.println("no nums");
            }
    ```

    表达式需要有一个具体值

    取值可以为：char、byte、short、int、枚举、String

    ==取值不能取long==

    

    - 格式2：
    
    ```
    switch(表达式) {
    	case 具体值1 -> {
    		需要执行的代码
    	};
    	case 具体值2 -> {
    		需要执行的代码
    	};
    	case 具体值3 -> {
    		需要执行的代码
    	};
    	default -> {
    		需要执行的代码
    	};
    }
    ```

    - 格式3：
    
    ```
    switch(表达式) {
    	case 具体值1， 具体值2， 具体值3 -> {
    		需要执行的代码
    	};
    	
    	case 具体值4, 具体值5, 具体值6, 具体值7 -> {
    		需要执行的代码
    	};
    	default -> {
    		需要执行的代码
    	};
    }
    ```


## switch类刷题集

switch中的条件判断只支持int及以下的整形，枚举，String；

不支持long、浮点型和boolean

**==为什么不支持long？==**

**原因就是 switch 对应的 JVM 字节码 lookupswitch、tableswitch指令只支持 int 类型**

**byte、short、char类型在编译期默认提升为 int，并使用 int 类型的字节码指令。**

- 循环

  - for
  - while
  - do...while
  - 增强for
  - Iterator迭代器

### 数组

- 数组的定义

  - 一维数组声明方式：

    ```
    必须指定数组初始大小
    int[] a = new int[3];
    
    要么赋值数组元素，要么只能创建一个空数组
    int[] b = new int[]{};
    int[] c = new int[]{1,2,3,4,5};
    
    int[] d = {1,2,3,4,5};（简化的声明方式，完整声明方式还是int[] c = new int[]{1,2,3,4,5};）
    int d[] = {1,2,3,4,5};
    ```
  
  - 一维数组错误声明方式：
  
    ```
    int[] e = new int[];
    int[] e = new int[size]{};
    ```
  
  - 二维数组声明方式：
  
    ```
    int [][] a = new int[][]{};
    int [][] b = new int[row][column];
    int [][] b = new int[row][];
    int [] b [] = new int[row][];
    ```
  
  - 二维数组错误声明方式：
  
    ```
    int[][] a = new int[][];
    int[][] a = new int[][column];
    ```
  
  

#### 数组的内存图

- java内存分配

  - 栈：方法运行时使用的内存，比如main方法运行，进入方法栈中执行
  - 堆：存储对象或者数组，new来创建的，都存储在堆内存当中
  - 方法区：存储可以运行的class文件
  - 本地方法栈：JVM在使用操作系统功能的时候使用，和开发无关
  - 寄存器：给CPU使用

- 两个数组指向同一空间的内存图

  ![Screenshot_20231219_143225](C:\Users\12629\Desktop\笔记截图保存\Screenshot_20231219_143225.jpg)

  总结：

  ​		当两个数组指向同一个小空间时，其中一个数组对小空间中的值发生了改变，那么其他数组再次访问的时候就都是修改之后的结果了

- 一个数组的内存图

  ![Screenshot_20231219_143959](C:\Users\12629\Desktop\笔记截图保存\Screenshot_20231219_143959.jpg)

### Java方法

- 什么是方法、什么时候用到方法、方法有什么好处？

  方法（method）是程序中最小的执行单元

  重复代码、具有独立功能的代码可以抽取到方法中

  可以提高代码的复用性和可维护性

- 方法的定义格式

  - 最简单的方法定义

    ```
    public static void 方法名() {
    	方法体;
    }
    ```

    方法调用

    ```
    方法名();
    ```

    

  - 带参数的方法定义

    ```
    public static void 方法名(类型 形参名1，类型 形参名2，……) {
    	方法体;
    }
    ```

    方法调用

    ```
    方法名(实参1，实参2，……);
    ```

    实参与形参的位置与类型必须一一对应

  - 带返回值的方法定义

    ```
    public static 数据类型 方法名(类型 形参名1，类型 形参名2，……) {
    	方法体;
    	return 返回值;
    }
    ```

    方法调用

    - 直接调用

      ```
      方法名(实参1，实参2，……);
      ```

    - 赋值调用

    ```
    数据类型 计算结果 = 方法名(实参1，实参2，……);
    int result = add(a,b);
    ```

    - 输出调用

      ```
      System.out.println(方法名(实参1，实参2，……));
      ```

- ==方法重载==

  - 方法名称**必须相同**
  - 参数列表**必须不同**（参数个数不同、或参数类型不同、参数排列顺序不同等）。
  - 与方法的返回类型无关。
  - 仅仅返回类型不同，不足以称为方法的重载。
  - ***同一个类中，不允许两个方法的方法名称和参数列表都相同***

- ##### 方法重写

  - 重写方法的==名称、形参列表、返回值类型==必须与父类中的一致

  - 子类重写父类方法时，访问权限子类必须==大于等于父类==（default<protected<public）

  - 子类重写父类方法时，返回值类型子类必须==小于等于父类==

  - 子类重写父类方法时，子类方法抛出的异常必须==小于等于父类==抛出的异常

  - 重写的方法尽量和父类保持一致

  - 只有被添加到虚方法表中的方法才能被重写

#### 方法调用的基本内存原理

- 如果==不new对象==，则变量是存在于==栈内存==当中

  当方法结束之后，变量也随之被系统回收

- 基本数据类型

  基本数据类型是存储在栈内存当中，数据值是存储在自己的空间当中

  ==特点==：赋值给其他变量，也是赋值的真实值，相当于==复制一份==值给其他变量

- 引用数据类型

  数据值是存储在其他空间当中，自己空间当中存储的是地址值

  ==特点==：赋值给其他变量，赋值的地址值

  ​			int arr1 = {1,2,3};

  ​			int arr2 = arr1;

  ​			如果arr2修改堆空间内的数据，则arr1和arr2访问时，都是访问的修改后的数据

- 基本数据类型方法传递的内存原理

  传递基本数据类型时，传递的是真实数据，形参的改变，不影响实际参数的值

- 引用数据类型方法传递的内存原理

  传递引用数据类型时，传递的是地址值，形参的改变，影响实际参数的值

## java面向对象

## 面向对象类刷题集

![image-20240105151020701](C:\Users\12629\AppData\Roaming\Typora\typora-user-images\image-20240105151020701.png)

先比较两个对象的hashcode，如果hashcode相同，则使用equals比较两个对象的内容

如果equals之后的结果为true，则俩对象为同一对象

### Java程序初始化顺序

1. 父类的静态代码块
2. 子类的静态代码块
3. 父类的普通代码块
4. 父类的构造方法
5. 子类的普通代码块
6. 子类的构造方法

### 类和对象

#### 创建对象的五种方法

1、使用 ==new 关键字==（最常用）：ObjectName obj = new ObjectName(); 

2、使用反射的Class类的==newInstance()==方法：ObjectName obj = ObjectName.class.newInstance();

3、使用反射的Constructor类的==newInstance()==方法：ObjectName obj = ObjectName.class.getConstructor.newInstance(); 

4、使用对象克隆==clone()方法==：ObjectName obj = obj.clone(); 

5、使用反序列化（**ObjectInputStream**）的==readObject()==方法：

```
try (  ObjectInputStream ois = new ObjectInputStream(new FileInputStream(FILE_NAME)))  {
	ObjectName obj = ois.readObject();
}
```



- 如何定义类？

  ```
  public class 类名{
  	1.成员变量（代表属性，属性类型可以是其他类，也可以是基本类型的包装类）
  	2.成员方法（代表行为，一个类里面自身定义的方法）
  	3.构造器
  	4.代码块
  	5.内部类
  }
  ```

### 引用数据类型（8种）

面向对象三大特征：封装、继承、多态

### 封装

#### 访问权限修饰符

- private：在同一类内可见。

  ​		使用对象：变量、方法。 注意：不能修饰类（外部类）

- default：在同一包内可见，不使用任何修饰符。

  ​		使用对象：类、接口、变量、方法

- protected：对同一包内的类和所有子类可见。

  ​		使用对象：变量、方法。 注意：不能修饰类（外部类）

- public：对所有类可见。

  ​		使用对象：类、接口、变量、方法

#### 访问权限大小

![QQ图片20231220120040](C:\Users\12629\Desktop\笔记截图保存\QQ图片20231220120040.png)

对象代表什么，就得封装对应的数据，并提供数据对应的行为

## 访问权限类刷题集

![QQ图片20240117181118](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240117181118.png)

## 变量类刷题集

![QQ图片20240103103329](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240103103329.png)

c选项中内部类的参数可以与函数的形参同名

数组和new的对象也属于变量，但存储单元在内存的堆区

![QQ图片20240117181833](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240117181833.png)

值类型的变量，如果是在类A中的值类型的变量，那么作用域也在堆中

变量的实例，就是实例变量，实例变量就是成员变量

![image-20240220145142780](C:\Users\12629\AppData\Roaming\Typora\typora-user-images\image-20240220145142780.png)

成员变量有默认值，局部变量没有默认值，必须赋初值

#### 成员变量和局部变量

- 成员变量

  成员变量又叫做全局变量

  static修饰的全局变量，只在该源文件中可用,存放于静态区，类加载时创建，在类中只有一份； 会跟着类的消失而消失，生存时间较长。

  extern修饰的全局变量,可以被其他类引用，作用于整个工程中

  定义在类里面、方法外面的变量，也称为类的属性，不必赋初始值，有默认值

  若为整型、浮点型：初始值为0

  若为对象、包装类或者字符串：初始值为null

  没有实例化的成员变量放在栈中

  实例化后的对象放在堆中，栈中放的是指向堆中对象的引用地址

- 成员变量的分类

  - 实例变量（对象变量）

    实例对象私有，某一个对象将其值改变，不影响其他对象

  - 静态变量（类变量）

    被所有对象所共有，若被改变，则其余对象拿到的就是改变后的值

- 局部变量

  定义在方法里面的变量，**==必须赋初始值==**

- 代码细节剖析

```
class ts{

	//定义的属性，又叫成员变量
    private String name;

	//无参构造器，创建对象时可以不带属性值（不带成员变量）
    public ts() {
    }

	//有参构造器，若没有无参构造器，创建对象时必须带对应属性的属性值（带成员变量）
    public ts(String name) {
        this.name = name;
    }
    
    //全参构造器，若只有全参构造器，创建对象时必须带全部属性的属性值（带全部成员变量）
	public ts(String name) {
        this.name = name;
    }
	//可以获取外部传入的name值，并返回name
    public String getName() {
        return name;
    }

	//可以在外部设置name值，并将外部设置的name赋值给本类的name
	//可以进行条件判断，用于对数据进行过滤
	//name称为局部变量，this.name称为成员变量
    public void setName(String name) {
        this.name = name;
    }
    
    //成员方法
    public void test() {
        System.out.println("测试");
    }
    public void test(String name){
        System.out.println("我的名字是：" + name);
    }
    
}
```

#### this的作用

this是自身的一个对象，代表对象本身

this的用法大致分为三种：

- 普通的直接引用，相当于直接指向当前对象本身

  ```
  this.name;
  ```

- 形参与成员名字重名，用this来区分

  ```
      
  //可以在外部设置name值，并将外部设置的name赋值给本类的name
  //可以进行条件判断，用于对数据进行过滤
  //name称为局部变量，this.name称为成员变量
  public void setName(String name) {
      this.name = name;
  }
  ```

  

- 引用本类的构造函数(有参构造、无参构造)

  ```
  //有参构造器，若没有无参构造器，创建对象时必须带对应属性的属性值（带成员变量）
  public ts(String name) {
      this.name = name;
  }
  ```

#### 构造方法

- 如果没有定义构造方法，系统将默认给出一个无参构造方法

- 如果定义了构造方法，系统将不会给出一个默认构造方法

- 无参构造

  ```
  public Test(){
  
  }
  ```

  

- 有参构造

  ```
  public Test(Integer id, String name){
  	this.id = id;
  	thsi.name = name;
  }
  ```

  

- 全参构造(包含所有属性)

  ```
  public Test(Integer id, String name, Integer age){
  	this.id = id;
  	thsi.name = name;
  	this.age = age
  }
  ```

- 构造方法的重载

  构造方法名相同，但携带参数不同

- 构造方法的作用

  创建对象的时候，虚拟机会自动调用构造方法，作用是给成员变量进行初始化的

## 构造方法类刷题集

##### ![QQ图片20240101162538](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240101162538.png)识别合法的构造方法

- 构造方法可以被重载，一个构造方法可以通过this关键字调用另一个构造方法，this语句必须位于构造方法的第一行；
- 重载：方法的重载(overload)：重载构成的条件：方法的名称相同，但参数类型或参数个数不同，才能构成方法的重载。
- 当一个类中没有定义任何构造方法，Java将自动提供一个缺省构造方法；
- 子类通过super关键字调用父类的一个构造方法；
- 当子类的某个构造方法没有通过super关键字调用父类的构造方法，通过这个构造方法创建子类对象时，会自动先调用父类的缺省构造方法
- 构造方法只能被访问权限修饰符修饰
- 构造方法不是类的成员方法；
- 构造方法不能被继承。

![QQ图片20240117175936](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240117175936.png)

如果父类没有无参构造器，则子类调用父类成员或方法时，需要使用super关键字



![QQ图片20240220150450](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240220150450.png)

由于父类当中没有无参构造器，所以必须显示的调用父类的有参构造方法

```
public Derived (String s) {
	super(s);
    System.out.print("D");
}
```



### 继承

- 子类和父类

  子类又叫派生类，父类又叫基类或者超类

- 使用继承的好处

  可以把多个子类中的重复代码抽取到父类中，提高代码复用性

  子类可以增加新功能

#### 子类可以继承父类的内容

- 单继承：一个子类只能继承一个父类

- 父类的构造方法不能被子类继承

- 父类的private成员变量可以被继承，但不能被调用
- 父类的非私有成员变量可以被继承，可以被调用

- 父类的成员方法非私有可以被继承
- 父类的成员方法私有不可以被继承

#### 成员变量的访问特点

就近原则：谁离我近，我就用谁

如果局部位置没有这个变量，就去本类位置找；

如果本类位置没有，就去父类位置找；

如果父类也没有，则程序报错。

#### 成员方法的访问特点

##### 方法重写的本质

- 虚方法表：非private、非static、非final
- 方法重写：子类覆盖了父类虚方法表当中同名的方法

##### 方法重写的要求

- 重写方法的==名称、形参列表、返回值类型==必须与父类中的一致
- 子类重写父类方法时，访问权限子类必须==大于等于父类==（default<protected<public）
- 子类重写父类方法时，返回值类型子类必须==小于等于父类==
- 子类重写父类方法时，子类方法抛出的异常必须==小于等于父类==抛出的异常
- 重写的方法尽量和父类保持一致
- 只有被添加到虚方法表中的方法才能被重写

##### 构造方法的访问特点

- 子类不能继承父类的构造方法，但是可以通过super调用
- 子类构造方法的第一行，有一个默认的super()
- 默认先访问父类中无参的构造方法，在执行自己的无参构造
- 如果想要访问父类的有参构造，则需要手动code

##### this与super关键字

- 在子类构造方法中使用super()显示调用父类的构造方法，super()必须写在子类构造方法的第一行，否则编译不予通过

  因为子类可能会用到父类的属性或者方法啥的，所以必须先对父类对象进行初始化操作

- this和super不能出现在同一构造器，且this必须出现在构造函数的第一行

  因为程序运行到构造函数第一行时，如果没有发现this()或者super()，那么就会在第一行自动补齐super()来对父类对象

  进行初始化然后返回子类构造器继续执行。当运行到构造函数的this()时，调用子类对象的构造函数，还会对父类进行初始化

  会造成资源的浪费，以及数据丢失、覆盖等报错

- 无论是super()还是this()，指的都是对象，而static环境中是无法使用非静态变量的

## 重写重载类刷题集

![QQ图片20240220145553](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240220145553.png)

重写要求：

​		方法返回值、方法名、参数与父类完全相同，不然不能称之为重写

​		称之为子类新增的自己的方法

### 多态

- 概念：同类型的事物，表现出来的不同形态

  ​			比如动物，有猫、有狗、有猪等

  自我理解：使用父类型作为参数，可以接受收所有子类对象。

#### 多态调用成员特点

- 变量调用：==编译看左边，运行也看左边==

- 方法调用：==编译看左边，运行看右边==

  - 编译看左边：如果父类没有对应方法，则会在编译时报错；

  - 运行看右边：如果子类对方法进行了重写，则在虚方法表中，

    ​					   子类重写的方法会将虚方法表中父类的方法进行覆盖，

    ​					   所以运行的时候调用的就是子类的成员方法

#### 多态弊端

多态无法调用子类的特有功能

### 多态类刷题集

![QQ图片20240101155142](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240101155142.png)





![QQ图片20240105111922](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240105111922.png)

多态调用方法的时候

编译看左边，运行看右边

编译时先看父类有没有这个方法，有则不报错；

再执行父类的构造方法，因为子类里面已经重写了父类的callName方法

所以会调用子类的callName方法

程序先执行了callName方法，子类的baseName还没来得及赋值

所以子类的变量并没有被初始化，所以打印了个null

![QQ图片20240122145856](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240122145856.png)

  1、子类构造函数调用父类构造函数用super 

  2、子类重写父类方法后，若想调用父类中被重写的方法，用super 

  3、未被重写的非private方法可以直接调用。

#### Java 的类初始化机制

一个类在初始化的时候，按照：

​		父类静态初始化块 -> 子类静态初始化块 -> 父类初始化块 -> 父类构造器 -> 子类初始化块 -> 子类构造器，这样的顺序初始化的。

​		当该子类已经加载过之后再次实例化子类对象时，

​		执行：父类初始化块 -> 父类构造器 -> 子类初始化块 -> 子类构造器。

​		静态初始化块因为在类初次被加载时已经执行过了，所以不会再次执行。

### 抽象

抽象类中的方法，子类必须强制性重写

#### 抽象方法

​		将共性的行为抽象到父类。由于每一个子类执行的内容是不一样的，在父类中不能确定具体的方法体，该方法就可以定义为抽象方法

```
public abstract 返回值类型 方法名（参数列表）;
```

#### 抽象类

​		一个类中存在抽象方法，那么该类就必须声明为抽象类

```
public abstract class 类名{}
```

## 抽象类刷题集

- 涉及知识点：
  - 方法的重载
  - 抽象类
  - 抽象方法

![QQ图片20231228193817](C:\Users\12629\Desktop\笔记截图保存\QQ图片20231228193817.png)

- B选项---必须写在main方法中或非抽象类中

- C选项---方法的返回值类型不能作为方法重载的依据

- D选项---抽象方法没有方法体--->{}，大括号就是方法体

### 接口

接口中不能创建对象

需要实现特定行为的时候就可以继承接口里面的方法，使用implements实现接口

成员变量只能是常量

```
public static final int a = 0;
其中public static final 可以省略
```

成员方法只能是抽象方法，默认修饰符：public abstract

接口和接口之间是继承关系，可以单继承也可以多继承

接口的多实现时，实现最下面的接口的类，需要重写所有接口的抽象方法

```
public abstract 返回值类型 方法名(参数列表);
public abstract 可以省略
```

#### 接口中抽象方法

- 定义格式

  ```
  public abstract 返回值类型 方法名(参数列表){}
  ```

- 注意事项
  - 抽象方法必须强制性重写
  - public abstract 可以省略不写
  - 若多个接口的方法同名，则实现类重写方法时会进行方法的覆盖

#### 接口中默认方法

- 定义格式

  ```
  public default 返回值类型 方法名(参数列表){}
  ```

- 注意事项

  - 默认方法不是抽象方法，所以不被强制重写。若需要重写，则去掉实现类当中的default关键字即可

  - public可以省略，但default不能省略

  - 如果实现了多个接口，多个接口中存在相同名字的默认方法，子类就必须对该方法进行重写

#### 接口中静态方法

- 定义格式

  ```
  public static 返回值类型 方法名（参数列表）{}
  ```

- 注意事项

  - 静态方法只能通过接口名去调用，不能通过实现类或者对象名去调用
  - public可以省略，但static不行

接口中的私有方法（JDK9）

- 普通方法定义格式

  ```
  private 返回值类型 方法名(参数列表){}
  ```

- 静态方法定义格式

  ```
  private static 返回值类型 方法名(参数列表){}
  ```

#### 接口中的多态

```
public interface 运输{}
public void 搬家(运输的接口 c){}
实现接口的类：
	搬家（车的对象）;
	搬家（搬家公司）;

如果一个方法的参数是一个接口，则实现这个接口的类的对象，都可以传递到搬家这个方法里面去
```

#### 工厂模式中的接口

直接就包含了接口下面所有的实现类，传递对应的参数过去，让参数自个儿去找对应的实现类进行操作。就不用一个一个地去写具体类来进行操作了

```
public interface getInterface(Object obj){}
```

### 抽象和接口的异同

####  相同点:

    都位于继承的顶端,用于被其他类实现或继承;
    都不能直接实例化对象;
    都包含抽象方法,其子类都必须覆写这些抽象方法;

####  区别:

-  抽象类为部分方法提供实现,避免子类重复实现这些方法,提高代码重用性;接口只能包含抽象方法;

- 一个类只能继承一个直接父类(可能是抽象类),却可以实现多个接口;(接口弥补了Java的单继承)
- 抽象类中的成员变量可以是各种类型的，而接口中的成员变量只能是public static final类型的

-  抽象类是这个事物中应该具备的内容, 继承体系是一种 is..a关系
-  接口是这个事物中的额外内容,继承体系是一种 like..a关系

#### 二者的选用:

    优先选用接口,尽量少用抽象类;
    需要定义子类的行为,又要为子类提供共性功能时才选用抽象类;

## 接口和抽象类刷题集

![QQ图片20240105143553](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240105143553.png)

抽象类可以有构造函数，只是不能实例化



抽象类不可以多继承，但是接口可以多继承

jdk1.8之前，接口中的方法没有方法体，jdk1.8以及之后，使用static或default关键字修饰的方法可以有方法体

static修饰的方法，可以直接使用类名进行方法的调用

default修饰的方法，实现类不必强制重写接口当中使用default关键字修饰的方法

![QQ图片20240117171809](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240117171809.png)

jdk1.8中可以使用static来修饰接口中的方法

接口不能使用protected来修饰

### 内部类

#### 成员内部类

- 该类像是外部类的一个成员，可以无条件的访问外部类的所有成员方法和成员属性（包括private成员和静态成员）

- 成员内部类拥有与外部类同名的成员变量时，会发生隐藏现象，即默认情况下是访问成员内部类中的成员。如果要访问外部类中的成员，需要以下形式访问：

  外部类.this.成员变量    或    外部类.this.成员方法

- 在外部类中如果要访问成员内部类的成员，必须先创建一个成员内部类的对象，再通过指向这个对象的引用来访问

- 成员内部类是依附外部类而存在的，也就是说，如果要创建成员内部类的对象，前提是必须存在一个外部类的对象

#### 四大访问权限

内部类可以拥有四大访问权限：

- 1：private访问权限

- 2：protected访问权限

- 3：public访问权限

- 4：包访问权限。

- 如果成员内部类用private修饰，则只能在外部类的内部访问
- 如果成员内部类用public修饰，则任何地方都能访问
- 如果成员内部类用protected修饰，则只能在同一个包下或者继承外部类的情况下访问
- 如果成员内部类用default修饰，则只能在同一个包下访问
- 外部类只能被public和包访问两种权限修饰



#### 局部内部类

- 局部内部类是定义在一个方法或者一个作用域里面的类，它和成员内部类的区别在于局部内部类的访问仅限于方法内或者该作用域内
- 局部内部类就像是方法里面的一个局部变量一样，是不能有public、protected、private和static修饰符的



#### 匿名内部类

- 一般使用匿名内部类的方法来编写事件监听代码
- 匿名内部类是不能有访问修饰符和static修饰符的
- 匿名内部类是唯一一种==没有构造器==的类
- 匿名内部类用于继承其他类或是实现接口，并不需要增加额外的方法，只是对继承方法的实现或者是重写

![image-20240220150246832](C:\Users\12629\AppData\Roaming\Typora\typora-user-images\image-20240220150246832.png)

#### 静态内部类

- 静态内部类是不需要依赖于外部类的，这点和类的静态成员属性有点儿类似
- 不能使用外部类的非static成员变量或者方法

```
package org.InnerClass;

public class statisClass {
    public static void main(String[] args) {
        //创建静态内部类
        System.out.println("创建静态内部类：");
        Outer.StaticInner staticInner = new Outer.StaticInner();
        staticInner.visit();

        //创建成员内部类
        System.out.println("创建成员内部类：");
        Outer outer = new Outer();
        Outer.MemberInner memberInner = outer.new MemberInner();
        memberInner.visit();
        //局部内部类
        System.out.println("局部内部类：");
        outer.testFunctionClass();
        Outer.testStaticFunctionClass();

        //匿名内部类
        System.out.println("匿名内部类：");
        Service service = i -> {
            for (int j = 0; j < i; j++) {
                System.out.println("匿名内部类");
            }
        };
        service.method(5);


        System.out.println(Runtime.getRuntime().availableProcessors());
    }
}

class Outer {
    //定义私有变量
    private static int param1 = 1;
    private int param2 = 2;
    private int OUT_PARAM2 = 10;
    private static int STATIC_PARAM1 = 20;

    //局部内部类
    //非静态
    public void testFunctionClass() {
        int INNER_PARAM3 = 30;
        class Inner {
            private void fun() {
                System.out.println(OUT_PARAM2);
                System.out.println(STATIC_PARAM1);
                System.out.println(INNER_PARAM3);
            }
        }
        //方法外创建实例，调用方法
        Inner inner = new Inner();
        inner.fun();
    }

    //局部内部类
    //静态
    public static void testStaticFunctionClass() {
        int PARAM = 300;
        class Inner {
            private void fun() {
                System.out.println(STATIC_PARAM1);
                System.out.println(PARAM);
            }
        }
        Inner inner = new Inner();
        inner.fun();
    }

    //成员内部类
    class MemberInner {
        public void visit() {
            System.out.println("visit outer static variable: " + param1);
            System.out.println("visit outer variable: " + param2);
        }
    }

    //静态内部类
    static class StaticInner {
        public void visit() {
            System.out.println("visit outer static variable: " + param1);
        }
    }
}

```



```
package org.InnerClass;

public class statisClass {
    public static void main(String[] args) {
        //创建静态内部类
        System.out.println("创建静态内部类：");
        Outer.StaticInner staticInner = new Outer.StaticInner();
        staticInner.visit();

        //创建成员内部类
        System.out.println("创建成员内部类：");
        Outer outer = new Outer();
        Outer.MemberInner memberInner = outer.new MemberInner();
        memberInner.visit();
        //局部内部类
        System.out.println("局部内部类：");
        outer.testFunctionClass();
        Outer.testStaticFunctionClass();

        //匿名内部类
        System.out.println("匿名内部类：");
        Service service = i -> {
            for (int j = 0; j < i; j++) {
                System.out.println("匿名内部类");
            }
        };
        service.method(5);


        System.out.println(Runtime.getRuntime().availableProcessors());
    }
}

class Outer {
    //定义私有变量
    private static int param1 = 1;
    private int param2 = 2;
    private int OUT_PARAM2 = 10;
    private static int STATIC_PARAM1 = 20;

    //局部内部类
    //非静态
    public void testFunctionClass() {
        int INNER_PARAM3 = 30;
        class Inner {
            private void fun() {
                System.out.println(OUT_PARAM2);
                System.out.println(STATIC_PARAM1);
                System.out.println(INNER_PARAM3);
            }
        }
        //方法外创建实例，调用方法
        Inner inner = new Inner();
        inner.fun();
    }

    //局部内部类
    //静态
    public static void testStaticFunctionClass() {
        int PARAM = 300;
        class Inner {
            private void fun() {
                System.out.println(STATIC_PARAM1);
                System.out.println(PARAM);
            }
        }
        Inner inner = new Inner();
        inner.fun();
    }

    //成员内部类
    class MemberInner {
        public void visit() {
            System.out.println("visit outer static variable: " + param1);
            System.out.println("visit outer variable: " + param2);
        }
    }

    //静态内部类
    static class StaticInner {
        public void visit() {
            System.out.println("visit outer static variable: " + param1);
        }
    }
}

```

```
package org.InnerClass;

public interface Service {
    void method(final int i);
}

```

## 内部类类刷题集

![QQ图片20240122152253](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240122152253.png)

## 泛型

### 泛型好处

- 统一数据类型

- 把运行时期的问题提前到编译期间，避免了强制类型转换可能出现的异常

  因为在编译阶段数据类型就能确定下来

### 泛型的细节

- 泛型当中不能写基本数据类型
- 制定泛型的具体类型后，传递参数时，可以传入该类类型或者其子类类型

- 如果不写泛型，类型默认是Object

### 泛型使用

#### 使用在类上

泛型类

格式

```
修饰符 class 类名<类型> {}
public class ArrayList<E>{}
```

此处的E用来记录数据的类型，一旦限定住数据类型时，集合里面就不能装入其他类型了

#### 使用在接口上

泛型接口

```
public interface List<E>{}
```

##### 使用泛型接口

- 实现类时给出具体类型

```
public class add implements List<String> {}
```

- 实现类时延续泛型，类就变成了泛型类，创建对象时再确定

#### 使用在方法上

泛型方法

格式

```
public static<E> void add(ArrayList<E> list){}
```

可变参数：E...e

#### 泛型的通配符

方法的泛型虽然不确定类型，但我们希望以后只传递固定的数据类型

此时就可以用到泛型的通配符：

​		？--->？也表示不确定的类型，可以==对类型进行限定==

​		？ extends E：表示可以传递E或E的所有子类类型

​		？ super E：表示可以传递E或者E的所有父类类型

#### 泛型通配符应用场景

- 如果咱在定义类、方法、接口的时候，如果类型不确定，就可以定义泛型类、泛型方法、泛型接口

- 如果类型不确定，但是能知道以后只能传递某个继承体系中的，就可以使用泛型通配符的方法



## String字符串

==字符串内容不可变==

```
public final class String{}
```

==字符串有length()方法==

==数组有length属性==

怎样判断字符串重新赋值之后，是不是创建了新对象？

答：

### 获取字符串对象

- 当使用双引号直接赋值时，系统会检查该字符串在字符串常量池中是否存在

  不存在：创建新的字符串对象

  存在：复用已经存在的字符串对象

- 如果是使用new来创建字符串对象，则堆内存中会产生一个对象，字符串常量池中会产生一个对象，一共两个对象

### 字符串的比较

- equals方法

   比较字符串对象中内容是否完全相等

- ==方法

​		基本数据类型比较的是数据值

​		引用数据类型比较的是地址值

### StringBuilder

- 可以将StringBuilder看作是一个容器，创建之后里面的内容是可变的

  可以提高字符串的操作效率，还可以节约空间

- StringBuilder打印对象的时候不是地址值而是属性值

- StringBuilder是一个工具，工具用完之后还是得转为String才合理 

### StringJoiner

- 可以更加快速的进行字符串的拼接
- 可以指定间隔符号，开始符号，结束符号

### 字符串拼接的底层原理

- 如果没有变量参与，都是字符串直接相加，编译之后就是拼接之后的结果，恢复用串池中的字符串
- 如果有变量参与，每一行拼接的代码，都会放在内存中创建新的字符串，浪费内存

### StringBuilder提高效率原理

所有需要拼接的内容都会往StringBuilder中放，不会创建很多无用的空间，极大地节约了内存

### StringBuilder源码分析

默认容量为==16==

默认扩容机制是：默认容量*2 + 2

如果超出了34个字符，则按照实际的长度来创建字符数组进行添加

## 字符串类刷题集

- 涉及知识点：
  - 字符串的存储方式
  - 字面值与引用变量
  - String不可变

![image-20231228191846086](C:\Users\12629\AppData\Roaming\Typora\typora-user-images\image-20231228191846086.png)

因为String==字符串不可变==（使用了final修饰），所以change方法传入的参数，实际上是传入了str的副本，真正的str并未被改变

**String是一个特殊的包装类数据，可以用用以下两种方式创建：**  

**String str = new String(“abc”)；第一种创建方式是用new()来新建对象的，它会存放于堆中。每调用一次就会创建一个新的对象。**  

**String str = “abc”; 第二种创建方式先在栈中创建一个对String类的对象引用变量str，然后在栈中查找有没有存放值为”abc”的地址，如果没有，则开辟一个存放字面值为”abc”的地址，接着创建一个新的String类的对象o，并将o的字符串值指向这个地址，而且在栈中这个地址旁边记下这个引用的对象o。如果已经有了值为”abc”的地址，则查找对象o，并返回o的地址,最后将str指向对象o的地址。**  

**值得注意的是，一般String类中字符串值都是直接存值的。但像String str = “abc”；这种场合下，其字符串值却是保存了一个指向存在栈中数据的引用！** 





![QQ图片20240105103330](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240105103330.png)

```
String的split这个方法默认返回一个数组，如果没有找到分隔符，会把整个字符串当成一个长度为1的字符串数组，然后返回结果
```





![QQ图片20240105105246](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240105105246.png)



![image-20240108142007350](C:\Users\12629\AppData\Roaming\Typora\typora-user-images\image-20240108142007350.png)

在基础类型当中，“==”比较的是真实值；

在引用类型当中，“==”比较的是地址值。



## 集合

### 集合与数组

- 数组
  - 长度开始时必须指定，一旦指定长度之后，就不能更改了
  - 保存的数据必须为同一类型的元素
  - 使用数组时增加或者删除元素的时候比较麻烦
- 集合
  - 可以动态的保存任意多个元素
  - 提供了一系列方便操作对象的方法：add，set，get，remove等
  - 使用集合进行元素的增删更加简洁
  - 限定类型<类型>不能存储基本数据类型
  - 打印的不是地址值，而是集合中存储的数据内容
  - 增（add）、删（remove）、改（set）、查（get）、长度（size） 

### 集合的框架体系图

![2](C:\Users\12629\Desktop\笔记截图保存\2.png)

### Collection接口和常用方法

- ### Collection接口实现类的特点

  public interface Collection<E> extends Iterable<E>

  - Collection实现子类可以存放多个元素，每个元素可以是Object
  - 有些Collection的实现子类可以存放重复的元素，有些则不行
  - 有些Collection的实现子类是有序的（List），有些是无序的（Set）
  - Collection接口没有直接的实现子类，是通过他的子接口Set和List来实现的

- ### Collection接口常用方法（ArrayList子类）

  - add：添加单个元素
  - remove：删除指定元素
  - contains：是否包含某元素
  - size：集合元素个数
  - isEmpty：集合是否为空
  - clear：清空整个集合
  - addAll：添加多个元素
  - containsAll：查找多个元素是否全都存在
  - removeAll：删除多个元素

- ### 遍历集合

  - 迭代器遍历

  ```
  //通过迭代器遍历集合
      Iterator iterator = collection.iterator();
      while (iterator.hasNext()) {
          System.out.println(iterator.next());
      }
  快速创建while循环的方法：
  	itit
  ```

  ```
  显式所有快捷键的快捷键：Ctrl + j
  ```

  

  - 增强for循环遍历

  ```
  //增强for遍历集合
  //增强for就是迭代器的简化版
      for (Object book : collection) {
          System.out.println(book);
      }
  ```

### List接口方法

- ### 小知识

  ```
  /*List list是编译类型
  * new ArrayList()是运行类型
  * */
  ```

  

- ### List接口实现类的特点

  - List集合类中==元素有序==（添加顺序和取出顺序一致），并且元素可以==重复==
  - List集合中的每个元素都有其对应的顺序==索引==，可以插入元素
  - List容器中的元素都对应一个整数型的序号来记载其在容器中的位置，可以根据序号存取容器中的元素
  - List接口的常用实现类：
    - ArrayList
    - LinkedList
    - Stack
    - Vector
    - CopyOnWriteArrayList

- ### List接口常用方法

  - void add(int index, Object ele)：在index位置插入ele元素
  - boolean add(E e)：将指定的元素追加到此列表的末尾（可选操作）
  - boolean addAll(int index, Collection eles)：从index位置开始将eles中的所有元素添加进来
  - Object get(int index)：获取指定index位置的元素
  - int indexOf(Object obj)：返回obj在集合中首次出现的位置
  - int lastIndexOf(Object obj)：返回obj在集合中末次出现的位置
  - Object remove(int index)：移除指定index位置的元素，并返回此元素
  - Object set(int index, Object ele)：设置指定index位置的元素为ele，相当于是替换
  - List subList(int fromIndex, int toIndex)：返回从fromIndex到toIndex位置的子集合

### ArrayList底层

- ### ArrayList注意事项

  - 可以加入多个null元素
  - ArrayList基于数组来存储数据
  - ArrayList基本等同于Vector，但ArrayList线程不安全，Vector线程安全，但是ArrayList执行效率更高
  - 线程安全的List
    - Collections.synchronizedList(new ArrayList<>());
    - new CopyOnWriteArrayList();
    - new Vector<>();

- ### ArrayList扩容机制

  - ArrayList中维护了一个Object类型的数组elementData--->transient Object[] elementData;
  - 当创建对象时，如果使用的是无参构造器，则初始elementData容量为0（jdk7是10）

  - 当添加元素时，先判断是否需要扩容，如果需要扩容，则调用grow方法，否则直接添加元素到合适位置
  - 如果使用的是无参构造器，如果第一次添加，需要扩容的话，则扩容elementData为10，如果需要再次扩容的话，则扩容为elementData的1.5倍

  ```
  	无参构造器：new ArrayList<>();
  ```

  - 如果使用的是指定容量(capacity)的构造器，则初始elementData容量为capacity

  ```
  	有参构造器：new ArrayList<>(int capacity);
  ```

  - 如果使用的是指定容量(capacity)的构造器，如果需要扩容，则直接扩容elementData为1.5倍

- ### ArrayList底层源码分析

  - 无参构造时，ArrayList扩容原理
  - 有参构造类似


```
	#创建空数组
	public ArrayList() {
        this.elementData = DEFAULTCAPACITY_EMPTY_ELEMENTDATA;
    }
```

```
	#add方法
	public boolean add(E e) {
        ensureCapacityInternal(size + 1);
        
        /*先确认是否要扩容*/
        
        elementData[size++] = e;
        
        /*然后再进行赋值操作*/
        
        return true;
    }
```

```
    private void ensureCapacityInternal(int minCapacity) {
        ensureExplicitCapacity(calculateCapacity(elementData, minCapacity));
        
        //起初通过无参构造创建了ArrayList集合，初始大小size为0;
        //minCapacity = size + 1 = 1，初始的minCapacity大小为1
        
    }
    
    private static int calculateCapacity(Object[] elementData, int minCapacity) {
        if (elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA) {
        
        //DEFAULTCAPACITY_EMPTY_ELEMENTDATA：默认容量为空数组
        //由于size = 0，所以此时elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA
        
            return Math.max(DEFAULT_CAPACITY, minCapacity);
            
        //返回两者中较大的值
        //DEFAULT_CAPACITY=10，minCapacity=1
        }
        return minCapacity;
    }
```

```
private void ensureCapacityInternal(int minCapacity) {
        ensureExplicitCapacity(calculateCapacity(elementData, minCapacity));
        
        //calculateCapacity(elementData, minCapacity)==10
    }
```

```
	//此时才是真正决定是否需要扩容的时候
	private void ensureExplicitCapacity(int minCapacity) {
	
	//此时minCapacity==10
	
        modCount++;
		//用于记录当前集合被修改的次数
		
        // overflow-conscious code
        if (minCapacity - elementData.length > 0)
        	//如果minCapacity需要的最小容量，减去，elementData.length目前实际容量，大于0的话
        	//表示实际容量太小了，则需要进行扩容，则进入grow方法
            grow(minCapacity);
    }
```

```
private void grow(int minCapacity) {
        // overflow-conscious code
        int oldCapacity = elementData.length;
        //此时elementData.length==0；
        
        int newCapacity = oldCapacity + (oldCapacity >> 1);
        //此时newCapacity==0
        
        if (newCapacity - minCapacity < 0)
            newCapacity = minCapacity;
        //此时newCapacity==10    
            
        if (newCapacity - MAX_ARRAY_SIZE > 0)
            newCapacity = hugeCapacity(minCapacity);
        // minCapacity is usually close to size, so this is a win:
        elementData = Arrays.copyOf(elementData, newCapacity);
        //使用Arrays.copyOf的方法对elementData进行扩容
        //copyOf会保留原有数据，在此基础上，再额外增加空间
    }
```

- ### 总结

  - 创建ArrayList无参构造对象时，第一次扩容直接扩容到10，第二次开始扩容为前一次的1.5倍
  - 创建ArrayList有参构造对象时，第一次扩容扩容初始大小的1.5倍

## ArrayList类刷题集

### **ArrayList怎么序列化呢？**

ArrayList通过两个方法**readObject**、**writeObject**自定义序列化和反序列化策

实际直接使用两个流**ObjectOutputStream**和 **ObjectInputStream**来进行序列化和反序列化

###   Vector底层

- 若使用无参构造，则第一次扩容时扩容为10，第二次扩容开始，按照2倍大小进行扩容
- 若使用有参构造，则直接按照2倍进行扩容
- 扩容机制与ArrayList类似

```
	//确认是否需要扩容
	private void ensureCapacityHelper(int minCapacity) {
        // overflow-conscious code
        if (minCapacity - elementData.length > 0)
            grow(minCapacity);
    }
```

### LinkedList底层分析

- ### LinkedList小知识

  - LinkedList底层实现了双向链表和双端队列的特点
  - 可以添加任意元素（元素可以重复），包括null
  - 线程不安全，没有实现同步机制

- ### LinkedList底层结构

  - #### 创建linkedlist对象时

    - 容量大小size==0
    - first==null
    - last==null

  - #### 执行add方法时

  ```
  	public boolean add(E e) {
          linkLast(e);
          return true;
      }
  ```

  ```
  	void linkLast(E e) {
          final Node<E> l = last;
          //此时last（l）为空
          
          final Node<E> newNode = new Node<>(l, e, null);
          last = newNode;
          if (l == null)
              first = newNode;
          else
              l.next = newNode;
          //first和last都指向这个newNode
          size++;
          modCount++;
      }
  ```

  ![3](C:\Users\12629\Desktop\笔记截图保存\3.png)

  - #### 执行remove()方法时

```
    private E unlinkFirst(Node<E> f) {
        // assert f == first && f != null;
        final E element = f.item;
        final Node<E> next = f.next;
        f.item = null;
        f.next = null; // help GC
        first = next;
        if (next == null)
            last = null;
        else
            next.prev = null;
        size--;
        modCount++;
        return element;
    }
```

![](C:\Users\12629\Desktop\笔记截图保存\4.png)

### ArrayList与LinkedList比较

|            | 底层结构 |      增删效率       | 改查效率 |
| :--------: | :------: | :-----------------: | :------: |
| ArrayList  | 可变数组 |   较低---数组扩容   |   较高   |
| LinkedList | 双向链表 | 较高---通过链表追加 |   较低   |



### Set集合底层分析

- ### HashSet小知识

  - ==不==能存放==重复==的元素
  - 可以添加一个null
  - set集合存放集合是==无序==的，没有索引
  - 遍历方式为迭代器或者增强for

- ### HashSet底层分析

  - #### HashSet底层：HashMap

    ```
    	public HashSet() {
            map = new HashMap<>();
        }
    ```

  - #### HashSet底层说明

    - HashSet底层是HashMap，维护了一个数组+单向链表的结构
    - 添加一个元素时，先得到Hash值，后面会转成索引值
    - 找到存储数据表table，看这个索引位置是否已经存放得有元素
    - 如果没有，则直接加入
    - 如果有，调用equals进行比较
    - 如果相同，就放弃添加
    - 如果不同，则添加到最后
    - 在java8中，如果一条链表的元素个数达到TREEIFY_THRESHOLD（默认是8）
    - 并且table大小 >= MIN_TREEIFY_CAPACITY（默认64）
    - 将会转化为红黑树

  - #### HashSet源码解读

    - ##### HashSet底层实现了一个HashMap

    ```
    	public HashSet() {
            map = new HashMap<>();
        }
    ```

    - ##### 执行add方法

    ```
    	public boolean add(E e) {
            return map.put(e, PRESENT)==null;
        } 
        //PRESENT：
        private static final Object PRESENT = new Object();
        //作用：
        	//保证value可放任意类型的值
        	//如果没有放入value值，则PRESENT为默认的value值
    ```

    - ##### 执行put方法

    ```
    	public V put(K key, V value) {
            return putVal(hash(key), key, value, false, true);
        }
    ```

    - ##### 主看hash方法

    ```
    	static final int hash(Object key) {
            int h;
            return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
        }
    	//如果key为空，则返回0；如果不为空，则调用key.hashCode()方法生成hash码
    	//h >>> 16，将hash码无符号右移16位
    ```

    - ##### 深入理解putVal方法

    ```
    final V putVal(int hash, K key, V value, boolean onlyIfAbsent,
                       boolean evict) {
            Node<K,V>[] tab;
            Node<K,V> p;
            int n, i;
            //tab, p, n, i都是定义出来的临时变量
            
            if ((tab = table) == null || (n = tab.length) == 0)
            //如果当前tab数组为空，或者它的大小为0，就执行下面的resize方法进行扩容
            
                n = (tab = resize()).length;
                //resize方法讲解
                
            if ((p = tab[i = (n - 1) & hash]) == null)
            //&：按位与操作--->首先按位与操作(&)，就是将两个操作数转换成2进制，根据1 1 = 1 ，1 0 = 0， 0 0 = 0的规则进行计算
    
                tab[i] = newNode(hash, key, value, null);
            else {
                Node<K,V> e; K k;
                if (p.hash == hash && ((k = p.key) == key || (key != null && key.equals(k))))
                //p.hash:当前节点的hash值；hash:下一个节点的hash值；
                //新旧节点的key对象相等或者   （key不为空并且新旧节点的内容相同）
                    e = p;
                    
                //如果上面的if语句为假，再判断p是不是一颗红黑树，如果是，则调用putTreeVal方法进行红黑树的添加
                else if (p instanceof TreeNode)
                    e = ((TreeNode<K,V>)p).putTreeVal(this, tab, hash, key, value);
                else {
                //如果table对应的索引位置，已经是一个链表，就使用for循环进行比较
                	//（1）如果依次和该链表的每一个元素比较后都不相同，则加入到该链表的最后
                	//（2）如果依次和该链表的每一个元素比较过程中，如果有相同的元素，就直接break退出
                	//（3）在每次把元素添加到链表后，立即判断该链表是否已经达到了8个节点
                		  如果达到了8个节点，就调用treeifyBin(tab, hash)，把当前链表转化为红黑树
                		  在转成红黑树时，不会马上进行树化，当hash表的容量小于64时，不会树化，会接着进行扩容
                    for (int binCount = 0; ; ++binCount) {
                        if ((e = p.next) == null) {
                            p.next = newNode(hash, key, value, null);
                            if (binCount >= TREEIFY_THRESHOLD - 1) // -1 for 1st
                                treeifyBin(tab, hash);
                            break;
                        }
                        if (e.hash == hash &&
                            ((k = e.key) == key || (key != null && key.equals(k))))
                            break;
                        p = e;
                    }
                }
                if (e != null) { // existing mapping for key
                    V oldValue = e.value;
                    if (!onlyIfAbsent || oldValue == null)
                        e.value = value;
                    afterNodeAccess(e);
                    return oldValue;
                }
            }
            ++modCount;
            if (++size > threshold)
                resize();
            afterNodeInsertion(evict);
            return null;
        }
    ```

    - ##### 深入理解resize方法

    ```
    final Node<K,V>[] resize() {
            Node<K,V>[] oldTab = table;
            //第一次执行时，table==null
            
            int oldCap = (oldTab == null) ? 0 : oldTab.length;
            //此时的oldTab==0
            
            int oldThr = threshold;
            int newCap, newThr = 0;
            if (oldCap > 0) {
                if (oldCap >= MAXIMUM_CAPACITY) {
                    threshold = Integer.MAX_VALUE;
                    return oldTab;
                }
                else if ((newCap = oldCap << 1) < MAXIMUM_CAPACITY &&
                         oldCap >= DEFAULT_INITIAL_CAPACITY)
                    newThr = oldThr << 1; // double threshold
            }
            else if (oldThr > 0) // initial capacity was placed in threshold
                newCap = oldThr;
                
            //oldTab==0时，走else语句
            else {               // zero initial threshold signifies using defaults
                newCap = DEFAULT_INITIAL_CAPACITY;
                //DEFAULT_INITIAL_CAPACITY默认大小是16
                
                newThr = (int)(DEFAULT_LOAD_FACTOR * DEFAULT_INITIAL_CAPACITY);
                //DEFAULT_LOAD_FACTOR：默认加载因子--->0.75
                //newThr:临界值（此处为12），当所存元素超过临界值时，就得考虑扩容了
                
            }
            if (newThr == 0) {
                float ft = (float)newCap * loadFactor;
                newThr = (newCap < MAXIMUM_CAPACITY && ft < (float)MAXIMUM_CAPACITY ?
                          (int)ft : Integer.MAX_VALUE);
            }
            threshold = newThr;
            @SuppressWarnings({"rawtypes","unchecked"})
            Node<K,V>[] newTab = (Node<K,V>[])new Node[newCap];
            table = newTab;
            if (oldTab != null) {
                for (int j = 0; j < oldCap; ++j) {
                    Node<K,V> e;
                    if ((e = oldTab[j]) != null) {
                        oldTab[j] = null;
                        if (e.next == null)
                            newTab[e.hash & (newCap - 1)] = e;
                        else if (e instanceof TreeNode)
                            ((TreeNode<K,V>)e).split(this, newTab, j, oldCap);
                        else { // preserve order
                            Node<K,V> loHead = null, loTail = null;
                            Node<K,V> hiHead = null, hiTail = null;
                            Node<K,V> next;
                            do {
                                next = e.next;
                                if ((e.hash & oldCap) == 0) {
                                    if (loTail == null)
                                        loHead = e;
                                    else
                                        loTail.next = e;
                                    loTail = e;
                                }
                                else {
                                    if (hiTail == null)
                                        hiHead = e;
                                    else
                                        hiTail.next = e;
                                    hiTail = e;
                                }
                            } while ((e = next) != null);
                            if (loTail != null) {
                                loTail.next = null;
                                newTab[j] = loHead;
                            }
                            if (hiTail != null) {
                                hiTail.next = null;
                                newTab[j + oldCap] = hiHead;
                            }
                        }
                    }
                }
            }
            return newTab;
        }
    ```

- ### LinkedHashSet底层分析

  - #### LinkedHashSet底层说明

    - LinkedHashSet是HashSet的子类
    - LinkedHashSet底层是LinkedHashMap，底层维护了一个数组+双向链表的结构
    - LinkedHashSet根据元素的hashCode值来决定元素存储的位置，同时使用双向链表维护元素的次序，这使得元素看起来是以插入顺序来进行保存的
    - LinkedHashSet不允许添加重复的元素

  - #### LinkedHashSet如何有序？

    - 在LinkedHashSet中维护了一个hash表和双向链表（LinkedHashSet有head和tail）

    - 每一个节点有before和after属性，这样可以形成双向链表

    - 在添加一个元素时，先求hash值再求索引。确定该元素在table中的位置，然后将添加的元素加入到双向链表（如果已经存在，则不用添加）

    - 示例代码

      ```
      tail.next = newElement
      newElement.pre = tail
      tail = newElement
      ```

    - 如此，在遍历LinkedHashSet的时候，也可以确保插入顺序和遍历顺序一致

  - #### LinkedHashSet底层源码

    - 第一次添加元素时，直接将数组table扩容到16，存放的节点类型是LinkedHashMap$Entry

    - table数组是HashMap$Node[]类型，存放的元素是LinkedHashMap$Entry类型

      ```
      static class Entry<K,V> extends HashMap.Node<K,V> {
              Entry<K,V> before, after;
              Entry(int hash, K key, V value, Node<K,V> next) {
                  super(hash, key, value, next);
              }
          }
      ```


### Map接口和常用方法(底层复杂)

- ### JDK8Map接口实现类的特点

  - Map与Collection并列存在，用于保存具有映射关系的数据：key-value

  - Map中的key和value可以是任何引用类型的数据，会封装到HashMap$对象中

  - Map中的key不允许重复，原因和HashSet一样

  - 如果key重复，那么新的key-value键值对将替换旧的key-value键值对

  - Map中的value可以重复

  - Map的key只能有一个为null，但value可以有多个为null

  - 常使用String类作为Map的key

  - key和value之间存在单向一对一的关系，即通过指定的key总能找到对应的value

  - key-value为了方便程序员遍历，创建了一个EntrySet集合，该集合存放的元素的类型Entry，而一个Entry里面存放着Key-Value键值对

    EntrySet<Entry<K, V>>
  
  - HashMap默认初始值大小为16，源码中是1<<4

## Map类刷题合集

![image-20231228200757551](C:\Users\12629\AppData\Roaming\Typora\typora-user-images\image-20231228200757551.png)

### hashMap和hashtable

- 关于HashMap的一些说法：

  - HashMap实际上是一个“链表散列”的数据结构，即数组和链表的结合体。HashMap的底层结构是一个数组，数组中的每一项是一条链表。 

  - HashMap的实例有俩个参数影响其性能： “初始容量” 和 装填因子。

  - HashMap实现不同步，线程不安全。 HashTable线程安全。

  - HashMap中的key-value都是存储在Entry中的。

  - HashMap可以存null键和null值，不保证元素的顺序永久不变，它的底层使用的是数组和链表，通过hashCode()方法和equals方法保证键的唯一性。

  - 解决冲突主要有三种方法：定址法，拉链法，再散列法。

  - HashMap是采用拉链法解决哈希冲突的。

    ​		注： 链表法是将相同hash值的对象组成一个链表放在hash值对应的槽位；

  - 用开放定址法解决冲突的做法是：当冲突发生时，使用某种探查(亦称探测)技术在散列表中形成一个探查(测)序列。 沿此序列逐个单元地查找，直到找到给定的关键字，或者碰到一个开放的地址(即该地址单元为空)为止（若要插入，在探查到开放的地址，则可将待插入的新结点存人该地址单元）。

  - 拉链法解决冲突的做法是： 将所有关键字为同义词的结点链接在同一个单链表中 。若选定的散列表长度为m，则可将散列表定义为一个由m个头指针组成的指针数 组T[0..m-1]。凡是散列地址为i的结点，均插入到以T[i]为头指针的单链表中。T中各分量的初值均应为空指针。在拉链法中，装填因子α可以大于1，但一般均取α≤1。拉链法适合未规定元素的大小。

- Hashtable和HashMap的区别：

  - 继承不同。

    public class Hashtable extends Dictionary implements Map

    public class HashMap extends AbstractMap implements Map

  - Hashtable中的方法是同步的，而HashMap中的方法在缺省情况下是非同步的。在多线程并发的环境下，可以直接使用Hashtable，但是要使用HashMap的话就要自己增加同步处理了。

  - Hashtable 中， key 和 value 都不允许出现 null 值。

     在 HashMap 中， null 可以作为键，这样的键只有一个；可以有一个或多个键所对应的值为 null 。

    当 get() 方法返回 null 值时，即可以表示 HashMap 中没有该键，也可以表示该键所对应的值为 null 。

    因此，在 HashMap 中不能由 get() 方法来判断 HashMap 中是否存在某个键， 而应该用 containsKey() 方法来判断。

  - 两个遍历方式的内部实现上不同。Hashtable、HashMap都使用了Iterator。而由于历史原因，Hashtable还使用了Enumeration的方式 。

  - 哈希值的使用不同，HashTable直接使用对象的hashCode。而HashMap重新计算hash值。

  - Hashtable和HashMap它们两个内部实现方式的数组的初始大小和扩容的方式。

    HashTable中hash数组默认大小是11，增加的方式是old*2+1。

    HashMap中hash数组的默认大小是16，而且一定是2的指数。 

    注：  HashSet子类依靠hashCode()和equal()方法来区分重复元素。

    ​		  HashSet内部使用Map保存数据，即将HashSet的数据作为Map的key值保存，这也是HashSet中元素不能重复的原因。而Map中保存key值的,会去		  判断当前Map中是否含有该Key对象，内部是先通过key的hashCode,确定有相同的hashCode之后，再通过equals方法判断是否相同。

### **为什么HashMap的容量是2的倍数呢？**

- 第一个原因是为了方便哈希取余

  计算机底层是二进制形式，将元素放在table数组上面，是用hash值%数组大小定位位置；

  而HashMap的元素存放位置是取决于hash值&（数组长度-1）

  而数组长度减一，就可以保证数组大小的二进制减一后数字全为1，按位与操作比求余操作效率更高

  使得添加的元素能够更加均匀的散列在map上，减少hash碰撞

- 第二个原因就是扩容时

  方便转移产生碰撞的hashmap元素到扩容后的数组当中去

​	   当数组元素个数达到负载因子（0.75）*数组大小时，就会按照原数组大小2倍进行扩容

### **jdk1.8对HashMap主要做了哪些优化呢？为什么？**

主要有四点优化：

- 数据结构改变

  原：数组+链表

  现：数组+链表+红黑树

- 链表元素插入方式

  头插法变为尾插法

  头插法扩容时，头插法会使链表发生反转，多线程环境下会产生环，导致死循环

- 扩容HashMap

  没有产生hash冲突的元素不需要移动

  产生hash冲突的元素，新的位置为当前索引位置+新增容量大小

- 扩容时机

  jdk1.7时，先判断扩容，再进行插入

  jdk1.8时，先进行插入，再判断扩容

### **HashMap 是线程安全的吗？多线程下会有什么问题？**

- 多线程的 put 可能导致元素的丢失

  当几个线程计算到的hash值相同时，会导致值的覆盖，就会丢失hash值

- put 和 get 并发时，可能导致 get 为 null

  元素还没put成功时，get此时的值为null

  当HashMap发生扩容时，get得到的值也可能为null

### **有什么办法能解决HashMap线程不安全的问题呢？**

- HashTable
- Collections.synchronizedMap(new HashMap)
- ConcurrentHashMap
- 在同步代码块中实现HashMap

### **HashMap 内部节点是有序的吗？**

HashMap是无序的，根据 hash值随机插入。如果想使用有序的Map，可以使用LinkedHashMap或者TreeMap

## set和list的区别

1、set是无序的，取出元素的时候不会按照存入元素的顺序取出；

​	  list是有序的，取出元素的顺序就是存入元素的顺序

2、set只能使用iterator迭代器来进行遍历获取元素

​	  list可以使用迭代器，可以使用for、foreach、while循环、使用get方法来获取元素

3、set元素不可重复，且只能允许一个null值

​	  list元素可以重复，可以允许多个null值



## static

### javabean类

​		用来描述一类事物的类。

### 测试类

​		用来检查其他类是否书写正确，带有main方法的类，是程序的入口

### 工具类

​		不是用来描述一类事物的，而是帮我们做一些事情的类

###  static静态变量

- 被static修饰的变量

  特点：

  - 被该类所有对象共享
  - 不属于对象，属于类
  - 随着类的加载而加载，优先于对象存在

  调用方式：

  - 类名调用（推荐）
  - 对象名调用

###  static静态方法

- 静态方法、静态变量只能访问静态的

- 静态方法不能访问非静态方法
- 静态方法不能调用实例变量（也就是对象）
- 静态方法不能调用非静态的成员方法

### static内存图

![Screenshot_20231221_143828](C:\Users\12629\Desktop\笔记截图保存\Screenshot_20231221_143828.jpg)

### static详解

- 被static修饰的变量称为静态成员变量，也称为类变量；

- 类变量的生命周期和类相同，在整个应用程序执行期间都有效。

- static修饰的全局变量，只在该源文件中可用,存放于静态区，类加载时创建，在类中只有一份；
- 非静态方法可以调用非静态和静态变量；静态方法只能调用静态变量，否则编译会报错

- static用途
  - 方便在没有创建对象的情况下进行调用(方法/变量)

- static不能修饰局部变量

## static类刷题集

### 下面这段代码的输出结果是什么？

```
public class Test extends Base{

    static{
        System.out.println("test static");
    }

    public Test(){
        System.out.println("test constructor");
    }

    public static void main(String[] args) {
        new Test();
    }
}

class Base{

    static{
        System.out.println("base static");
    }

    public Base(){
        System.out.println("base constructor");
    }
}


输出结果为：
base static
test static
base constructor
test constructor
```

代码分析：

- 找到main方法入口，main方法是程序入口，但在执行main方法之前，要先加载Test


- 加载Test类的时候，发现Test类继承Base类，于是先去加载Base类


- 加载Base类的时候，发现Base类有static块，而是先执行static块，输出base static结果


- Base类加载完成后，再去加载Test类，发现Test类也有static块，而是执行Test类中的static块，输出test static结果


- Base类和Test类加载完成后，然后执行main方法中的new Test()，调用子类构造器之前会先调用父类构造器


- 调用父类构造器，输出base constructor结果


- 然后再调用子类构造器，输出test constructor结果



### 这段代码的输出结果是什么？

```
public class Test {
    Person person = new Person("Test");
    static{
        System.out.println("test static");
    }


    public Test() {
        System.out.println("test constructor"); 
    }

    public static void main(String[] args) {
        new MyClass();
    }
}


class Person{
    static{
        System.out.println("person static");
    }
    public Person(String str) {
        System.out.println("person "+str);
    }
}


class MyClass extends Test {
    Person person = new Person("MyClass");
    static{
        System.out.println("myclass static");
    }

    public MyClass() {
        System.out.println("myclass constructor");
    }
}


输出结果：
test static
myclass static
person static
person Test
test constructor
person MyClass
myclass constructor
```

后面自行分析（这题是做对了的）



![QQ图片20240109105658](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240109105658.png)

D选项需要考虑在A类通过类名访问B类的静态成员变量时，B类的静态成员变量必须public修饰；访问其他类的类方法：类名.类方法

![QQ图片20240117174257](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240117174257.png)

类变量---->静态变量

类方法---->静态方法

访问其他类的类方法：类名.类方法

## final

- 修饰方法：不能被重写
- 修饰类：不能被继承
- 修饰变量：变为常量，只能被赋值一次

  - **成员变量：**final修饰的**成员变量必须在声明的时候初始化或者在构造器中初始化**，否则就会报编译错误；

  - **局部变量：**final修饰的**局部变量必须声明时赋值**，如果不赋值，虽然声明是不会出错，但调用时会编译出错；
  - final关键字修饰变量，（常量）要求全部的字母大写
- 修饰引用数据类型：记录的地址值不会发生改变，内部的属性值可以改变
- byte、short、char在进行计算时都会提升为int类型，运算中的所有值都被final修饰时结果才不会改变类型
- **final不能用来修饰抽象类：**因为抽象类需要被继承才有作用，而final修饰的类不能被继承
- **final不能用来修饰构造器：**因为构造方法既不能被继承，也不能被重写，用final修饰毫无意义
- final变量可以安全地在**多线程环境下共享**，而不需要额外的同步开销

###  final类刷题集

![QQ图片20240101163348](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240101163348.png)

final变量如果是基本数据类型

则其数值一旦初始化后就不能被改变。

如果是引用类型的变量，则对其初始化后，便不能再指向另一个对象，但是其里面的值是可以改变的。

引用变量所指向的对象中的内容是可以改变的。

B选项是访问修饰符所决定的

## lambda表达式

###  标准格式

```
() -> {

}

()	对应着方法的形参
->	固定格式
{}	对应着方法的方法体
```

### 注意事项

- lambda表达式可以用来简化匿名内部类的书写
- lambda表达式只能简化函数式接口的匿名内部类的写法

### 省略写法

- 参数类型可以省略不写

- 如果只有一个参数，参数类型可以省略，同时（）也可以省略

- 如果lambda表达式的方法体只有一行

  大括号、分号、return都可以省略不写

  但三者需要同时省略

## Stream流

### stream流使用步骤

- 先得到一条stream流，放入数据
- 使用中间方法对流中数据进行操作
- 使用最终方法对流中数据进行操作



### 单列集合使用Stream流

```
package cn.itcast.demo.test;

import java.sql.SQLOutput;
import java.util.*;
import java.util.stream.Stream;

public class test{
    public static void main(String[] args){
        ArrayList<String> list = new ArrayList<>();
        list.add("张无忌");
        list.add("周芷若");
        list.add("赵敏");
        list.add("张强");
        list.add("张三丰");

        list.stream().forEach(s -> {System.out.println(s);});

        System.out.println("==========");
        HashMap<Integer, String> hashMap = new HashMap<>();
        hashMap.put(1, "张无忌");
        hashMap.put(2, "周芷若");
        hashMap.put(3, "赵敏");
        hashMap.put(4, "张强");
        hashMap.put(5, "张三丰");

        // 获取key的Stream流
        hashMap.keySet().stream().forEach(s -> System.out.println(s));

        System.out.println("==========");
        hashMap.entrySet().stream().forEach(s -> System.out.println(s));

        System.out.println("==========");
        // 数组的Stream流
        int[] arr = new int[]{1,2,3,4,5,6,7,8,9};
        Arrays.stream(arr).forEach(s -> System.out.print(s + " "));
        System.out.println();
        System.out.println("==========");
        // 零散数据的Stream流
        Stream.of(1,2,3,4,5).forEach(s -> System.out.println(s));

        // 如果将零散数据装入数组，且数据是基本数据类型时，打印结果将会变为地址值
        // 可以传递引用类型的数组
        Stream.of(arr).forEach(s -> System.out.println(s));
    }
}
```

### stream流的中间方法

```
package cn.itcast.demo.test;

import java.util.*;
import java.util.stream.Stream;

public class test{
    public static void main(String[] args){
        ArrayList<String> list = new ArrayList<>();
        list.add("张无忌-15");
        list.add("周芷若-45");
        list.add("赵敏-56");
        list.add("张强-24");
        list.add("张三丰-76");
        list.add("张三丰-90");
    }
}

```

#### filter（过滤）

```
		list.stream()
                .filter(s->s.startsWith("张"))
                .forEach(System.out::println);
```



#### limit（获取前几个元素）

```
        list.stream()
                .limit(6)
                .skip(3)
                .forEach(System.out::println);
```



#### skip（跳过前几个元素）

```
        list.stream()
                .limit(6)
                .skip(3)
                .forEach(System.out::println);
```



#### distinct（元素去重，依赖hashcode和equals方法）

```
        list.stream()
                .distinct()
                .forEach(System.out::println);
    }
```



#### concat（合并a和b两个流为一个流）

```
Stream.concat(list.stream(), list.stream())
                .forEach(System.out::println);
```



#### map（转换流中的数据类型）

```
list.stream().map(
                s -> Integer.parseInt(s.split("-")[1])
        ).forEach(System.out::println);
```



### stream流的终止方法

#### forEach（遍历）

#### count（计数）

#### toArray（转数组）

```
String[] array = list.stream().toArray(value -> new String[value]);
System.out.println(Arrays.toString(array));
        
String[] array1 = list.toArray(new String[0]);// new String[0]会创建一个与集合大小一致的空数组，空间利用率和时间利用率更高效
System.out.println(Arrays.toString(array1));
```

#### collect（转集合）

- 转list或set集合

```
list.stream()
                .filter(s -> "男".equals(s.split("-")[1]))
                .collect(Collectors.toList())
                .forEach(System.out::println);
```

- 转map集合

```
		list.stream()
                .filter(s->"男".equals(s.split("-")[1]))
                .collect(Collectors.toMap(键的规则, 值的规则));

        /*
        * 键的规则当中，new Function<String, String>()
        *   第一个泛型是流里面数据的类型
        *   第二个泛型是map集合当中键的类型
        *
        * 值的规则当中，new Function<String, Integer>()
        *   第一个泛型是流里面数据的类型
        *   第二个泛型是map集合当中值的类型
        * */
//        list.stream()
//                .filter(s->"男".equals(s.split("-")[1]))
//                .collect(Collectors.toMap(new Function<String, String>() {
//                                              @Override
//                                              public String apply(String s) {
//                                                  return s.split("-")[0];
//                                              }
//                                          },
//                        new Function<String, Integer>() {
//                            @Override
//                            public Integer apply(String s) {
//                                return Integer.parseInt(s.split("-")[2]);
//                            }
//                        }));

        Map<String, Integer> map = list.stream()
                .filter(s->"男".equals(s.split("-")[1]))
                .collect(Collectors.toMap(
                        s -> s.split("-")[0], s -> Integer.parseInt(s.split("-")[2])));
        System.out.println(map);

```



## 文件File

### File的三种构造器

- File(String pathName)

  根据文件路径创建文件对象

  作用：把字符串表示的路径变成file对象

- File(String parent, String child)

  根据父路径名字符串和子路径名字符串创建文件对象

  作用：把父级路径和子级路径进行拼接

- File(File parent, String child)

  根据父路径对应文件对象和子路径名字符串创建文件对象

​	   作用：把父级路径和子级路径进行拼接

### listFiles方法！！！

public File[] listFiles()：获取当前该路径下所有内容

- 当调用者File表示的路径不存在时，返回null
- 当调用者File表示的路径是文件时，返回null
- 当调用者File表示的路径是空文件夹时，返回一个长度为0的数组
- 当调用者File表示的路径是一个有内容的文件夹时，将里面所有的文件和文件夹路径放在File数组中返回
- 当调用者File表示的路径是一个有隐藏文件的文件夹时，将里面所有的文件和文件夹路径放在File数组中返回，包括隐藏文件
- 当调用者File表示的路径是需要权限才能访问的文件夹时，返回null

## IO流字节流

### IO流的分类

#### 流的方向

- 输入流-----inputstream

- 输出流-----outputstream

#### 文件类型

- 全部类型的文件----字节流
- 纯文本文件-----字符流

纯文本文件：能用记事本打开且不乱码的文件

### FileOutputStream

往本地文件当中写入数据

#### 写数据时字节输出流的细节

##### 创建字节输出流对象

- 参数是字符串表示的路径或者是File对象都是可以的
- 如果文件不存在，会创建一个新的文件，但是要保证父级路径是存在的
- 如果文件已经存在，则会清空文件的数据，然后写入程序中预写入的数据

##### 写入数据

- write方法的参数是整数，但是实际上写到本地文件的是ASCII上对应的字符
- 可以使用getBytes方法，此方法会返回一个byte数组，用于快速输入数据

##### 释放资源

- 不管什么流，每次使用完之后都需要释放资源

#### 换行写数据时字节输出流的细节

- 再次写个换行符

  windows：\r\n

  linux：\n

  mac：\r

#### 续写数据时字节输出流的细节

- 打开续写开关即可
- 续写开关默认是false，改为true时，就可以进行续写而不覆盖原有数据

### FileInputStream

#### 读取文件单个数据的细节

##### 创建字节输入流

- 如果文件不存在，直接报错

##### 读取数据

- 一次读取一个字节，读出来的是ASCII对应的数字
- 如果想要显示字符，需要强转成char类型
- 读到文件末尾时，read方法返回-1

##### 释放资源

- 不管什么流，每次使用完之后都需要释放资源

#### 循环读取文件数据的细节

```
FileInputStream fileInputStream = new FileInputStream("C:\\Users\\12629\\Desktop\\txt.txt");
int b；
while ((b = fileInputStream.read()) != -1) {
	sout((char)b);
}
fileInputStream.close;
```

- 需要定义一个变量，用来存储当前读到的单个数据
- 每次执行read时，指针都会往后移动一次

### 文件拷贝

- 小文件拷贝

```
FileInputStream inputStream = new FileInputStream("C:\\Users\\12629\\Desktop\\秦成加--开题报告.doc");
FileOutputStream outputStream = new FileOutputStream("D:\\copy.doc");
int b = 0;
while ((b = inputStream.read()) != -1) {
    outputStream.write(b);
}
outputStream.close();
inputStream.close();
```

- 大文件拷贝

```
long start = System.currentTimeMillis();
FileInputStream fis = new FileInputStream
	("C:\\Users\\12629\\Documents\\Virtual Machines\\CentOS 7 64 位\\CentOS 7 64 位-000002-s002.vmdk");
FileOutputStream fos = new FileOutputStream("D:\\copy.vmdk");
byte[] bytes = new byte[1024*1024];
int len = 0;
while ((len = fis.read(bytes)) != -1) {
    fos.write(bytes, 0, len);
}
fos.close();
fis.close();
long end = System.currentTimeMillis();
System.out.println(end - start);
```

FileInputStream：往控制台输入数据

FileOutputStream：控制台向文件输出数据

## 编码和解码

### 编码

- 默认方式

  getBytes()

- 指定方式

  getBytes(String charsetName)

### 解码

UTF-8编码方式：1一个英文一个字节，一个中文3个字节

GBK编码方式：1个英文一个字节，一个中文2个字节

- 默认方式

  String(byte[] bytes)

- 指定方式

  String(byte[] bytes, String charsetName)

## 字符流

字符流：字节流+字符集

### FileReader字符输入流

#### 空参的read方法

```
FileReader fr = new FileReader("C:\\Users\\12629\\Desktop\\学习笔记\\mybatis笔记.md");
int ch;
while ((ch = fr.read())!= -1) {
    System.out.print((char) ch);
}
```

- 字符流的底层也是字节流，默认也是一个字节一个字节地读取
- 如果遇到中文会一次读多个，GBK编码一次读两个字节，UTF-8一次读3个字节
- 读取之后，read方法的底层会进行解码并转成10进制，最终将这个十进制的值作为返回值
- 如果想看到原文，则将结果再次强转为char类型就行

#### 带参的read方法

合并了空参+强转的步骤

```
char[] bytes = new char[1024];
int len;
while ((len = fr.read(bytes)) != -1) {
    System.out.print(new String(bytes, 0 ,len));
}
fr.close();
```

FileReader底层会创建一个8192字节的缓冲区，调用read方法时，会尽量填满缓冲区，此时调用FileWriter时，会将文件内容清空，就读不到后面的数据了，但写入缓冲区的数据会保留

### FileWriter字符输出流

FileWriter关联文件的会清空文件当中的数据

FileWriter底层也会创建一个缓冲区，将要输入的数据保存到8192字节的缓冲区

- 当缓冲区满时，会自动写入数据到文件
- 当调用flush方法时，会将数据写入到文件
- 当调用close方法时，会将数据写入到文件

## 引用类型

### **一，强引用**  

   Object obj = new Object(); //只要obj还指向Object对象，Object对象就不会被回收 obj = null; //手动置null  

   只要强引用存在，垃圾回收器将永远不会回收被引用的对象，哪怕内存不足时，JVM也会直接抛出OutOfMemoryError，不会去回收。如果想中断强引用与对象之间的联系，可以显示的将强引用赋值为null，这样一来，JVM就可以适时的回收对象了  

### **二，软引用**  

   软引用是用来描述一些非必需但仍有用的对象。**在内存足够的时候，软引用对象不会被回收，只有在内存不足时，系统则会回收软引用对象，如果回收了软引用对象之后仍然没有足够的内存，才会抛出内存溢出异常**。这种特性常常被用来实现缓存技术，比如网页缓存，图片缓存等。  

   在 JDK1.2 之后，用java.lang.ref.SoftReference类来表示软引用。  

### **三，弱引用**  

   弱引用的引用强度比软引用要更弱一些，**无论内存是否足够，只要 JVM 开始进行垃圾回收，那些被弱引用关联的对象都会被回收**。在 JDK1.2 之后，用 java.lang.ref.WeakReference 来表示弱引用。  

### **四，虚引用**  

   虚引用是最弱的一种引用关系，如果一个对象仅持有虚引用，那么它就和没有任何引用一样，它随时可能会被回收，在 JDK1.2 之后，用 PhantomReference 类来表示，通过查看这个类的源码，发现它只有一个构造函数和一个 get() 方法，而且它的 get() 方法仅仅是返回一个null，也就是说将永远无法通过虚引用来获取对象，虚引用必须要和 ReferenceQueue 引用队列一起使用。  



## 异常

### Error

系统级别错误

### RuntimeException（运行时异常）

RuntimeException及其子类，编译阶段都不会出现异常提醒，但会在运行时出现异常提醒

### 其他异常（编译时异常）

编译阶段就会出现异常提醒



## 异常类刷题集

![QQ图片20240105144835](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240105144835.png)

try和catch中的return语句，都会在finally执行之前执行，但这个时候不会返回结果，而是将结果存放于一个局部变量当中，

当finally中的代码执行完毕之后，再执行try和catch中的return语句



如果try或catch和finally当中均有return语句，执行顺序还是刚才的顺序，但返回结果则会执行finally当中的return语句



System.exit(status)：停掉整个虚拟机的运行

System.exit（0）:正常退出，程序正常执行结束退出

System.exit(1):是非正常退出，就是说无论程序正在执行与否，都退出



![QQ图片20240108142356](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240108142356.png)



![QQ图片20240108142253](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240108142253.png)

error是系统错误，catch无法解决

## 方法引用

### 方法引用要求

- 引用处需要是函数式接口
- 被引用的方法必须是已经存在了的
- 被引用方法的形参和返回值需要跟抽象方法的形参和返回值保持一致
- 被引用方法的功能需要满足当前的需求

Integer::parseInt====================Integer.ParseInt()

### 类::静态方法

OneClass类的concatString()方法的参数列表，和ImTheOne接口的handleString()方法参数列表必须一致，才能用方法引用，否则编译报错。

```

@FunctionalInterface
public interface ImTheOne {
    String handleString(String a, String b);
}
class OneClass {
    public static String concatString(String a, String b) {
        return a + b;
    }
}
 
public class Test {
    public static void main(String[] args) {
        ImTheOne theOne = OneClass::concatString;
        String result = theOne.handleString("abc", "def");
        System.out.println(result);
 
        //相当于以下效果，直接把类的静态方法写在Lambda体里
        ImTheOne theOne2 = (a, b) -> OneClass.concatString(a, b);
        String result2 = theOne2.handleString("123", "456");
        System.out.println(result2);
 
    }
}

————————————————
版权声明：本文为CSDN博主「lkforce」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/lkforce/article/details/99682885
```

### 对象::实例方法

与         类::静态方法类似，只不过需要先创建对象，使用对象来进行方法的引用

若是本类的：this::方法名

若是父类的：super::方法名

```
@FunctionalInterface
public interface ImTheOne {
    String handleString(String a, String b);
}
class OneClass {
    public String concatString(String a, String b) {
        return a + b;
    }
}
 
public class Test {
    public static void main(String[] args) {
        OneClass oneClass = new OneClass();
        ImTheOne theOne = oneClass::concatString;
        String result = theOne.handleString("abc", "def");
        System.out.println(result);
 
        //相当于以下效果
        OneClass oneClass2 = new OneClass();
        ImTheOne theOne2 = (a, b) -> oneClass2.concatString(a, b);
        String result2 = theOne2.handleString("123", "456");
        System.out.println(result2);
 
    }
}
————————————————
版权声明：本文为CSDN博主「lkforce」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/lkforce/article/details/99682885
```

### 类::new

引用构造方法，创建相应对象

```
public static void main(String[] args) {
    ArrayList<String> list = new ArrayList<>();
    Collections.addAll(list, "张无忌，15","周芷若，14","赵敏，13","张强，15","张翠山，18");

    // 要求：封装成Student对象并存储在List集合当中
    List<Student> studentList = list.stream().map(Student::new).toList();
    System.out.println(studentList);
}

public class Student {
    private String name;
    private Integer age;

    public Student(String name, Integer age) {
        this.name = name;
        this.age = age;
    }

    public Student(String stream) {
        this.name = stream.split("，")[0];
        this.age = Integer.parseInt(stream.split("，")[1]);
    }

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```

### 类::成员方法

## 反射

### 反射的概念

反射允许对成员变量，成员方法和构造方法的信息进行编程访问

### 获取对象的三种方式

- Class.forName("全类名");

  最为常用

```
Class<?> c2 = Class.forName("org.reflection.getClass.Student");
System.out.println(c2);
System.out.println(c2.hashCode());
```

- 类名.class

  一般更多是当做参数被传递

```
Class<Student> c3 = Student.class;
System.out.println(c3);
System.out.println(c3.hashCode());
```

- 对象.getClass();

  只有当有了这个类的对象时，才能使用这种方法

```
Person person = new Student();

Class<? extends Person> c1 = person.getClass();
System.out.println(c1);
System.out.println(c1.hashCode());
```

### 反射获取构造方法

- getConstructors()

  获取所有公共的构造方法

```
Class<?> aClass = Class.forName("org.reflection.getClass.Student");
Constructor<?>[] constructors = aClass.getConstructors();
for (Constructor<?> constructor : constructors) {
    System.out.println(constructor);
}
```



- getDeclaredConstructors()

  获取全部访问修饰符的构造方法

```
Class<?> aClass = Class.forName("org.reflection.getClass.Student");
Constructor<?>[] declaredConstructors = aClass.getDeclaredConstructors();
for (Constructor<?> declaredConstructor : declaredConstructors) {
    System.out.println(declaredConstructor);
}
```



- getConstructor()

  里面可以传递若干数量的数据类型的类名（String.class）

  此类名需要与类中构造方法的参数类型保持一致

  只能获取公共的构造方法

```
Class<?> aClass = Class.forName("org.reflection.getClass.Student");
Constructor<?> constructor = aClass.getConstructor(Integer.class);
System.out.println(constructor);
```



- getDeclaredConstructor()

  里面可以传递若干数量的数据类型的类名（String.class）

  此类名需要与类中构造方法的参数类型保持一致

  可以获取全部访问修饰符的构造方法

```
Class<?> aClass = Class.forName("org.reflection.getClass.Student");
Constructor<?> declaredConstructor = aClass.getDeclaredConstructor();
System.out.println(declaredConstructor);
```

### 反射获取访问权限修饰符

![QQ图片20240120071106](C:\Users\12629\Desktop\笔记截图保存\QQ图片20240120071106.png)

```
Class<?> aClass = Class.forName("org.reflection.getClass.Student");
Constructor<?> declaredConstructor = aClass.getDeclaredConstructor();
int modifiers = declaredConstructor.getModifiers();
System.out.println(modifiers);
```

扩展知识：

​		java在调用构造函数的时候为什么知道这个方法是不能调用的呢？

答：通过反射来获取到每一个访问权限修饰符所对应的整形号码，就能够知道哪些构造函数能调用，哪些不能了 

### 反射获取成员变量

getFields()：返回所有公共成员变量的对象的数组

getDeclaredFields()：返回所有成员变量对象的数组

getField(String name)：返回单个公共成员变量对象

getDeclaredField(String name)：返回单个成员变量对象

```
Class<?> clazz = Class.forName("org.reflection.reflectionGetMember.Student");
Field field = clazz.getDeclaredField("age");

// 获取权限修饰符
field.setAccessible(true);
int modi = field.getModifiers();
System.out.println(modi);

// 获取成员变量的名字
String name = field.getName();
System.out.println(name);

// 获取成员变量的数据类型
Class<?> type = field.getType();
System.out.println(type);

// 获取成员变量获取的值
Student student = new Student("zhangsan", 24, "男");
field.setAccessible(true);
Integer o = (Integer) field.get(student);
System.out.println(o);

// 修改对象里面记录的值
field.set(student, 20);
System.out.println(student);
```



### 反射获取成员方法

getMethods()：返回所有公共成员方法的对象的数组，包括继承的

getDeclaredMethods()：返回所有成员方法对象的数组，不包括继承的	

getMethod(String name)：返回单个公共成员方法对象

getDeclaredMethod(String name)：返回单个成员方法对象

```
Class<?> clazz = Class.forName("org.reflection.reflectionGetMember.Student");
// 获取所有的成员方法(只能获取公共的)，也包括父类当中的
Method[] methods = clazz.getMethods();
for (Method method : methods) {
    System.out.println(method);
}

System.out.println("----------------");

// 获取所有的成员方法，不包括父类
Method[] methods1 = clazz.getDeclaredMethods();
for (Method method : methods1) {
    System.out.println(method);
}

System.out.println("--------------------");

// 获取指定的单一方法
Method eat = clazz.getDeclaredMethod("eat", String.class);
System.out.println(eat);

// 获取方法的修饰符
int modifiers = eat.getModifiers();
System.out.println(modifiers);

// 获取方法的名字
String name = eat.getName();
System.out.println(name);

// 获取方法的形参
Parameter[] parameters = eat.getParameters();
for (Parameter parameter : parameters) {
    System.out.println(parameter);
}

// 方法运行：invoke(Object obj, Object... args)方法
System.out.println("---------");
Student student = new Student();
eat.setAccessible(true);
eat.invoke(student, "hanbaobao");
```



### 反射创建对象

- 创建private修饰的构造器的对象

```
Constructor<?> constructor1 = aClass.getDeclaredConstructor(Integer.class,String.class);
System.out.println(constructor1);
constructor1.setAccessible(true);
Student o = (Student) constructor1.newInstance(22, "qcj");
System.out.println(o);
```

## 枚举

- 若仅获取枚举中的常量，则枚举属性值设置为private
- 若还需获取常量中的属性值，则枚举属性值不可设置为private，其他封装类型均可
- 属性值最好设置为final常量，因为枚举里面的量都是常量

## 内存分配策略

### 静态分配

静态存储分配是指在编译时就==能确定==每个数据目标在运行时刻的==存储空间需求==，因而在==编译时==就可以给他们分配==固定的内存空间==。这种分配策略要求程序代码中==不允许==有==可变数据结构==(比如可变数组)的存在，也==不允许====有嵌套或者递归==的结构出现,因为它们都会导致编译程序无法计算准确的存储空间需求。  

### 栈式分配

栈式存储分配也可称为动态存储分配，是由一个类似于堆栈的运行栈来实现的。和静态存储分配相反，在栈式存储方案中，程序对数据区的需求在==编译时是完全未知==的，只有到==运行==的时候才能够==知道==，但是规定在运行中进入一个程序模块时，==必须知道该程序模块所需的数据区大小==才能够为其分配内存。和我们在数据结构所熟知的栈一样，栈式存储分配按照==先进后出==的原则进行分配。  

### 堆式分配

静态存储分配要求在==编译时==能知道==所有变量==的存储要求，栈式存储分配要求在过程的==入口处==必须知道所有的存储要求，而堆式存储分配则专门负责在编译时或运行时==模块入口处==都无法确定存储要求的数据结构的内存分配，比如可变长度串和对象实例。堆由大片的可利用块或空闲块组成，堆中的内存可以按照任意顺序分配和释放。

## 序列化和反序列化

一、基本概念

1、序列化和反序列化的定义：

(1)Java序列化就是指把Java对象转换为字节序列的过程

​    Java反序列化就是指把字节序列恢复为Java对象的过程。

(2)序列化最重要的作用：在传递和保存对象时.保证对象的完整性和可传递性。对象转换为有序字节流,以便在网络上传输或者保存在本地文件中。

   反序列化的最重要的作用：根据字节流中保存的对象状态及描述信息，通过反序列化重建对象。

   总结：核心作用就是对象状态的保存和重建。（整个过程核心点就是字节流中所保存的对象状态及描述信息）

 

2、json/xml的数据传递：

 在数据传输(也可称为网络传输)前，先通过序列化工具类将Java对象序列化为json/xml文件。

在数据传输(也可称为网络传输)后，再将json/xml文件反序列化为对应语言的对象

 

3、序列化优点：

 ①将对象转为字节流存储到硬盘上，当JVM停机的话，字节流还会在硬盘上默默等待，等待下一次JVM的启动，把序列化的对象，通过反序列化为原来的对象，并且序列化的二进制序列能够减少存储空间（永久性保存对象）。

 ②序列化成字节流形式的对象可以进行网络传输(二进制形式)，方便了网络传输。

 ③通过序列化可以在进程间传递对象。

 

4、序列化算法需要做的事：

  ① 将对象实例相关的类元数据输出。

  ② 递归地输出类的超类描述直到不再有超类。

  ③ 类元数据输出完毕后，从最顶端的超类开始输出对象实例的实际数据值。

  ④ 从上至下递归输出实例的数据。

 

二、Java实现序列化和反序列化的过程

   1、实现序列化的必备要求：

       只有实现了Serializable或者Externalizable接口的类的对象才能被序列化为字节序列。（不是则会抛出异常） 

   2、JDK中序列化和反序列化的API：

      ①java.io.ObjectInputStream：对象输入流。
    
          该类的readObject()方法从输入流中读取字节序列，然后将字节序列反序列化为一个对象并返回。
    
     ②java.io.ObjectOutputStream：对象输出流。
    
          该类的writeObject(Object obj)方法将将传入的obj对象进行序列化，把得到的字节序列写入到目标输出流中进行输出。

 3、实现序列化和反序列化的三种实现：

  ①若Student类仅仅实现了Serializable接口，则可以按照以下方式进行序列化和反序列化。

             ObjectOutputStream采用默认的序列化方式，对Student对象的非transient的实例变量进行序列化。 
             ObjcetInputStream采用默认的反序列化方式，对Student对象的非transient的实例变量进行反序列化。

  ②若Student类仅仅实现了Serializable接口，并且还定义了readObject(ObjectInputStream in)和writeObject(ObjectOutputSteam out)，则采用以下方式进行序列化与反序列化。

           ObjectOutputStream调用Student对象的writeObject(ObjectOutputStream out)的方法进行序列化。 
           ObjectInputStream会调用Student对象的readObject(ObjectInputStream in)的方法进行反序列化。

  ③若Student类实现了Externalnalizable接口，且Student类必须实现readExternal(ObjectInput in)和writeExternal(ObjectOutput out)方法，则按照以下方式进行序列化与反序列化。

           ObjectOutputStream调用Student对象的writeExternal(ObjectOutput out))的方法进行序列化。 
           ObjectInputStream会调用Student对象的readExternal(ObjectInput in)的方法进行反序列化。

4、序列化和反序列化代码示例

```
public class SerializableTest {
        public static void main(String[] args) throws IOException, ClassNotFoundException {
            //序列化
            FileOutputStream fos = new FileOutputStream("object.out");
            ObjectOutputStream oos = new ObjectOutputStream(fos);
            Student student1 = new Student("lihao", "wjwlh", "21");
            oos.writeObject(student1);
            oos.flush();
            oos.close();
            //反序列化
            FileInputStream fis = new FileInputStream("object.out");
            ObjectInputStream ois = new ObjectInputStream(fis);
            Student student2 = (Student) ois.readObject();
            System.out.println(student2.getUserName()+ " " +
                    student2.getPassword() + " " + student2.getYear());
    }
}
```

​                                                                          

    public class Student implements Serializable{                             
        private static final long serialVersionUID = -6060343040263809614L;   
    
        private String userName;                                              
        private String password;                                              
        private String year;                                                  
                                                                          
    public String getUserName() {                                         
        return userName;                                                  
    }                                                                     
                                                                          
    public String getPassword() {                                         
        return password;                                                  
    }                                                                     
                                                                          
    public void setUserName(String userName) {                            
        this.userName = userName;                                         
    }                                                                     
                                                                          
    public void setPassword(String password) {                            
        this.password = password;                                         
    }                                                                     
                                                                          
    public String getYear() {                                             
        return year;                                                      
    }                                                                     
                                                                          
    public void setYear(String year) {                                    
        this.year = year;                                                 
    }                                                                     
                                                                          
    public Student(String userName, String password, String year) {       
        this.userName = userName;                                         
        this.password = password;                                         
        this.year = year;                                                 
    }                                                                     
}                                                                         
 ①序列化图示

②反序列化图示

三、序列化和反序列化的注意点：

①序列化时，只对对象的状态进行保存，而不管对象的方法；

②当一个父类实现序列化，子类自动实现序列化，不需要显式实现Serializable接口；

③当一个对象的实例变量引用其他对象，序列化该对象时也把引用对象进行序列化；

④并非所有的对象都可以序列化，至于为什么不可以，有很多原因了，比如：

安全方面的原因，比如一个对象拥有private，public等field，对于一个要传输的对象，比如写到文件，或者进行RMI传输等等，在序列化进行传输的过程中，这个对象的private等域是不受保护的；

资源分配方面的原因，比如socket，thread类，如果可以序列化，进行传输或者保存，也无法对他们进行重新的资源分配，而且，也是没有必要这样实现；

⑤声明为static和transient类型的成员数据不能被序列化。因为static代表类的状态，transient代表对象的临时数据。

⑥序列化运行时使用一个称为 serialVersionUID 的版本号与每个可序列化类相关联，该序列号在反序列化过程中用于验证序列化对象的发送者和接收者是否为该对象加载了与序列化兼容的类。为它赋予明确的值。显式地定义serialVersionUID有两种用途：

在某些场合，希望类的不同版本对序列化兼容，因此需要确保类的不同版本具有相同的serialVersionUID；

在某些场合，不希望类的不同版本对序列化兼容，因此需要确保类的不同版本具有不同的serialVersionUID。

⑦Java有很多基础类已经实现了serializable接口，比如String,Vector等。但是也有一些没有实现serializable接口的；

⑧如果一个对象的成员变量是一个对象，那么这个对象的数据成员也会被保存！这是能用序列化解决深拷贝的重要原因；

