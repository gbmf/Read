# C Primer Plus

- [ ] 书籍作者：史蒂芬·普拉达
- [ ] 笔记时间：2021.8.11

## 第1章 初识C语言

### 1.1 C语言的起源

- 1972贝尔实验室开发UNIX操作系统设计的C语言，之前是B语言。

### 1.2 选择C语言的理由

- 紧凑、强大控制、高效、可移植性
- 晦涩难懂、指针

### 1.3 C语言的应用范围

### 1.4 计算机能做什么

- 读指令并执行

### 1.5 高级计算机语言和编译器

- 不用机器码表示，不受CPU限制

### 1.6 语言标准

- 最早是K&R，后来UNIX提供实现的库成为标准库
- ANSI在1989发布标准，称为89C或者C90，通常叫它ANSI C。精神很有趣，目的就是高效即使牺牲可移植性。
- C99标准，国际化、弥补缺陷和提高计算的实用性是主要修订目标，尽量与C++兼容。
- C11标准是2011年发布。

### 1.7 使用C语言的7个步骤

- 基本就是软件开发的步骤，简单说 制定目标-编程-调试-维护

### 1.8 编程机制

- 典型的C实现通过编译和链接两个步骤来完成从源代码转为可执行文件。![](images/epub_30440205_11)

- GNU编译器集合和LLVM项目
  - GNU (GNU is not  UNIX)，其编译器GCC。LLVM项目成为cc的另一个替代品。

## 第2章 C语言概述

### 2.1 简单的C程序示例

- ```c
  #include<stdio.h>		// 预处理器指令 
  int main(void){			// 主函数
          printf("A.c  is  used to end a C program  filename..\n");
          return 0;		// 通过＄?可以获取返回值
  }
  ```

### 2.2 示例解释

### 2.3 简单程序的结构

### 2.4 提高程序可读性的技巧

- 缩进，命名规范等

### 2.5 进一步使用C

- 加减乘除

### 2.6 多个函数

- 函数声明后，函数定义，最后调用。

### 2.7 调试程序

### 2.8 关键字和保留标识符

- 函数名，结构名 之类都是

## 第3章 数据和C

### 3.1 示例程序

- ```c
  scanf("%f",&number);	// 
  getchar();				// 阻止程序一闪而过
  ```

### 3.2 变量与常量数据

### 3.3 数据：数据类型关键字

- C90添加了signed，void；C99添加了_Bool， _Complex， _Imaginary
- byte 位，最小存储单位，表示0/1；Byte字节，8位；word字，计算机一次能处理的位数

### 3.4 C语言基本数据类型

- printf当参数个数不对应时候，会打印内存中的后继数值
- 整型没有说明字节占用大小，只说short比int小，long比int大，赋值时候常量加上后缀可以指定
- _Bool只占用1位，C99新增了两个头文件stdint.h和inttypes.h，以确保C语言的类型在各系统中的功能相同。

### 3.5 使用数据类型

### 3.6 参数和陷阱

### 3.7 转义序列示例

- printf 把数据发送到缓冲区，当遇到 换行/缓冲区满/需要输入 就会刷新缓冲区。

## 第4章 字符串和格式化输入/输出

### 4.1 前导程序

- ```c
  #include <string.h>		// 引入字符串
  #define DENSITY 62.4	// 宏定义
  	
  char name[40];			// 数组 等于 字符串
  scanf("%s",name);		// 此处说明数组就是指针
  int len = strlen(name);	// 获取字符长度
  sizeof(name);			// 以字节为单位返回类型或值的大小
  ```

### 4.2 字符串简介

- 没有专门的字符串类型，都是在数组里，结尾带有空字符 `\0`
- 使用当成指针即可
- scanf 遇到空格\制表符\回车自动停止。

### 4.3 常量和C预处理器

- 程序中所有的预编译都会被替换成对应的值。这一过程被称为编译时替换，#define也称为明示常量
- const是C90加入，限定为只读属性。

### 4.4 printf()和scanf()

- 高转低会发生截断，也就是取模。类型不匹配会出现奇怪的错误
- 如果使用字段宽度，scanf()会在字段结尾或第1个空白字符处停止读取，放入普通字符表示输入也要一样

- printf 可以用*修饰符代替字段宽度，参数传入宽度等，scanf表示跳过该项

### 4.5 关键概念

- 最好用#define定义数值常量，用const关键字声明的变量为只读变量。
- 字符数组中，都以一个叫作空字符的隐藏字符结尾。
- 除了%c模式（读取下一个字符），scanf()在读取输入时会跳过非空白字符前的所有空白字符，然后一直读取字符，直至遇到空白字符或与正在读取字符不匹配的字符。

## 第5章 运算符、表达式和语句

### 5.1 循环简介

### 5.2 基本运算符

- 赋值运算符左侧必须引用一个存储位置，称为可修改的左值

### 5.3 其他运算符

- sizeof 可以获取基本类型占用大小

### 5.4 表达式和语句

- 声明创建了名称和类型，并为其分配内存位置

- C语言副作用是对数据对象或文件的修改
- 序列点是程序执行的点，在该点上，所有的副作用都在进入下一步之前发生
- 完整表达式 ，就是指这个表达式不是另一个更大表达式的子表达式。

### 5.5 类型转换

### 5.6 带参数的函数

### 5.7 示例程序

## 第6章 C控制语句：循环

### 6.1 再探while循环

### 6.2 while语句

- 每次循环都被称为一次迭代，循环体支持空语句也就是分号

### 6.3 用关系运算符和表达式比较大小

### 6.4 不确定循环和计数循环

### 6.5 for循环

### 6.6 组合运算符

### 6.7 逗号运算符

- for里面使用

### 6.8 出口条件循环：do while

### 6.9 如何选择循环

- 一般使用for和while已经够用

### 6.10 嵌套循环

### 6.11 数组简介

### 6.12 使用函数返回值的循环示例

## 第7章 C控制语句：分支和跳转

### 7.1 if语句

### 7.2 if else语句

### 7.3 逻辑运算符

- 备选拼写：iso646.h头文件，可代替逻辑运算符的拼写

### 7.4 一个统计单词的程序

- ctype.h头文件中的函数isspace()

### 7.5 条件运算符：?:

### 7.6 循环辅助：continue和break

### 7.7 多重选择：switch和break

### 7.8 goto语句

- 原则上，根本不用在C程序中使用goto语句。

## 第8章 字符输入/输出和输入验证

### 8.1 单字符I/O：getchar()和putchar()

### 8.2 缓冲区

- 立即回显字符属于缓冲输入，缓冲分为两类：完全缓冲I/O和行缓冲I/O。前者需要完全填满才刷新

- ANSI没有提供调用无缓冲输入的标准方式，这意味着是否能进行无缓冲输入取决于计算机系统。

### 8.3 结束键盘输入

- 一些操作系统在文件结尾插入 ctrl-z，另一种方法记录 文件大小。C语言在文件结尾获得到EOF（-1）。

- 一般标准IO通过 ctrl-d 或者 ctrl-z 可以输入EOF

### 8.4 重定向和文件

- 直接使用重定向即可，执行命令的时候
- 程序直接打开文件 fopen，记得调用 fclose

### 8.5 创建更友好的用户界面

- 使用缓冲输入，必须处理换行符，可以使用 getchar 
- 建议使用 getchar 处理字符，scanf 处理数字

### 8.6 输入验证

- scanf 有返回值

### 8.7 菜单浏览

- 基本就是处理输入

## 第9章 函数

### 9.1 复习函数

### 9.2 ANSI C函数原型

- 形参里面数组可以使用指针声明，不定参数用三个点 

### 9.3 递归

- 把递归调用置于函数的末尾，即正好在return语句之前。这种形式的递归被称为尾递归

### 9.4 编译多源代码文件的程序

- ```shell
  gcc file.c f.c ff.o
  ```

- 使用工程管理，头文件引入

### 9.5 查找地址：&运算符

- 一元&运算符给出变量的存储地址，使用%p打印格式

### 9.6 更改主调函数中的变量

### 9.7 指针简介

- 从根本上看，指针（pointer）是一个值为内存地址的变量（或数据对象），* 可以解除引用

## 第10章 数组和指针

### 10.1 数组

- 支持静态初始化，数组长度可以使用变量c99引入。C99增加了一个新特性：指定初始化器

  ```c
  int arr[6] = {[5]=111} //指定第六个元素为111，会覆盖
  ```

- 在C标准中，使用越界下标的结果是未定义的

### 10.2 多维数组

### 10.3 指针和数组

- 数组表示法其实是在变相地使用指针。数组名是首元素地址。
- 指针加一代表增加一个存储单元，也就是下一个元素地址，而不是字节加一。

### 10.4 函数、数组和指针

- 指针大小8字节，int大小4字节

### 10.5 指针操作

- 赋值 解除引用 取址 加减  比较
- 解引用未初始化的指针会发生严重错误，创建一个指针时，系统只分配了存储指针本身的内存，并未分配存储数据的内存

### 10.6 保护数组中的数据

- 数组别无选择，必须传递指针。当不需要修改时候使用const防止意外修改
- 使用非const标识符修改const数据导致的结果是未定义的
- 创建指针时还可以使用const两次，该指针既不能更改它所指向的地址，也不能修改指向地址上的值

### 10.7 指针和多维数组

- 可以多次解引用
- 指针不兼容，除了 void*

### 10.8 变长数组（VLA）

- 变长数组还允许动态内存分配，这说明可以在程序运行时指定数组的大小。

### 10.9 复合字面量

- 字面量是除符号常量外的常量，因为复合字面量是匿名的，所以不能先创建然后再使用它

## 第11章 字符串和字符串函数

### 11.1 表示字符串和字符串I/O

- ```c
  char greeting[50] = "hello , tom !"; // 字面量定义，可以省略50
  // == 此时字符串有两个副本。一个是在静态内存中的字符串字面量，另一个是存储在ar1数组中的字符串 ==
  char* pt = "hello ptr!"; // 使用指针，只是拷贝指针
  // 建议在把指针初始化为字符串字面量时使用const限定符：
  ```

### 11.2 字符串输入

- 首先要分配空间，gets()可以读取一行，可能造成溢出问题。
  - fgets()函数（和fputs()）专门用来处理文件输入，读取不到返回NULL
  - 空字符是一个字符，占1字节；而空指针是一个地址，通常占4字节。
  - C11新增的gets_s()函数（可选）和fgets()类似

### 11.3 字符串输出

- puts()函数打印一行，放入指针即可，遇到空字符停止，缺少空字符会出问题
- fputs 函数需要和fgets 配对使用

### 11.4 自定义输入/输出函数

- 在 getchar 和 putchar 基础上自定义，比如打印之后返回长度等

### 11.5 字符串函数

- ANSI C把这些函数的原型放在string.h头文件中

- | 函数              | 作用                         |
  | ----------------- | ---------------------------- |
  | strlen            | 字符串长度                   |
  | strcat            | 拼接字符串，附加在第一个末尾 |
  | strncat           | 在上者的基础上加了长度限制   |
  | strcmp            | 比较内容，只比空字符前面的   |
  | strncmp           | 限定长度                     |
  | strcpy（有n版本） | 拷贝字符串                   |
  | sprintf           | 写入数组，或者说内存         |

### 11.6 字符串示例：字符串排序

### 11.7 ctype.h字符函数和字符串

- toupper，函数一般是宏实现

### 11.8 命令行参数

- ```c
  int main(int argc,char *argv []) // argc 个数，argv[0]是文件名
  {}
  ```

### 11.9 把字符串转换为数字

- 如果字符串仅以整数开头，atoi()函数也能处理 。包含了stdlib.h头文件，atof()和atol()函数的原型
- 可以转为各种类型，传入转换数组，结束指针，进制即可

## 第12章 存储类别、链接和内存管理

### 12.1 存储类别

- 作用域，一般是块作用域。函数作用域仅用于goto语句的标签
- 链接
  - 具有块作用域、函数作用域或函数原型作用域的变量都是无链接变量
  - 具有文件作用域的变量可以是外部链接或内部链接。外部链接变量可以在多文件程序中使用，内部链接变量只能在一个翻译单元中使用。
- 存储期
  - 静态存储期 -- 程序期间一直存在，static表明链接属性
  - 线程存储期 -- 用于多线程，线程存在期间 
  - 自动存储期 -- 块作用域
  - 动态分配存储期 -- 属于自动存储类别的变量具有自动存储期、块作用域且无链接
- 变量
  - 自动变量不会初始化，主函数里
  - 寄存器变量，添加register即可
  - static变量，只会被初始化一次
  - extern变量，多文件共享 
  - 一共六个 auto、register、static、extern、_Thread_local和typedef

### 12.2 随机数函数和静态变量

### 12.3 掷骰子

### 12.4 分配内存：malloc()和free()

- malloc()分配内存，但是不会为其赋名，使用通用指针接收，可以用于创建动态数组
  - 一定要和free配套使用，否则会产生内存泄漏
-  calloc() 接收两个参数，第二个参数指定单位大小，free也适用

### 12.5 ANSI C类型限定符

- const  volatile restrict _Atomic（C11）

- ```c
  const int * const ptr;//前者表示内容不能改，后者表示指针不能改
  ```

- 可以同时用const和volatile限定一个值

- restrict 用于更好的优化，只能用于指针

## 第13章 文件输入/输出

### 13.1 与文件进行通信

- 文件通常是在磁盘或固态硬盘上的一段已命名的存储区，C把文件看作是一系列连续的字节，每个字节都能被单独读取
  - 由此区分为二进制文件和文本文件，所以也有两类读写模式
- IO级别 -- 底层IO和高级IO，C只提供后者

### 13.2 标准I/O

- 带有缓冲
- fopen 打开文件，传入文件名称和打开模式，返回文件指针
- getc 和 putc 读取和写入一个字符，参数是文件指针 
- 文件结尾是EOF，需要检测。
- fclose 关闭文件，刷新缓冲区

### 13.3 一个简单的文件压缩程序

### 13.4 文件I/O：fprintf()、fscanf()、fgets()和fputs()

- fprintf()和fscanf()函数和标准IO差不多，
- fgets()和fputs() 读写一个字符

### 13.5 随机访问：fseek()和ftell()

- 随机是指可以指定位置开始读写，ftell查看当前位置

-  fgetpos()和fsetpos()函数，默认fseek文件大小限制在long类型能表示的范围内。

### 13.6 标准I/O的机理

- 打开文件 -》输入开辟缓冲区，数据拷贝到缓冲区 -》从缓冲区读取数据

### 13.7 其他标准I/O函数

- int ungetc()函数把c指定的字符放回输入流中

- 调用fflush()函数引起输出缓冲区中所有的未写入数据被发送到fp指定的输出文件。这个过程称为刷新缓冲区

- setvbuf()函数创建了一个供标准I/O函数替换使用的缓冲区。
- fread()和fwrite()二进制数据读写

- feof()和ferror()函数用于区分文件结尾还是读写错误

## 第14章 结构和其他数据形式

### 14.1 示例问题：创建图书目录

### 14.2 建立结构声明

- 简化版的类

### 14.3 定义结构变量

- 可以使用  {.key=value} 进行初始化

### 14.4 结构数组

- 结构存储在栈里，可以扩大栈容量或者使用静态结构，以防栈溢出

### 14.5 嵌套结构

- 使用点语法

### 14.6 指向结构的指针

- 效率更高，使用箭头语法

### 14.7 向函数传递结构的信息

- 把 struct type 看成一种类型
- 默认值传递，会传递副本

- 如果使用malloc()分配内存并使用指针存储该地址，那么在结构中使用指针处理字符串就比较合理

- ```c
  // C99 开始支持复合字面量 和 伸缩型数组成员
  (struct book){"the Idiot","Fyodor Dostoyevsky",6.99}
  // 匿名结构
  ```

### 14.8 把结构内容保存到文件中

- 存储在一个结构中的整套信息被称为记录，单独的项被称为字段
- 使用fread和fwrite可以处理

### 14.9 链式结构

- 链表，树之类

### 14.10 联合简介

- 能在同一个内存空间中存储不同的数据类型，使用箭头语法，只能存储其中一种类型

### 14.11 枚举类型

- 一些特性不适用于C++

- C语言使用名称空间标识程序中的各部分，

### 14.12 typedef简介

- 给类型取别名，由编译器解释，一般用于给复杂结构/联合重命名。

### 14.13 其他复杂的声明

- ```c
  int * risks[10];  //  指针数组
  int (* risks)[10]; // 数组指针
  ```

### 	14.14 函数和指针

- 指向函数的指针中存储着函数代码的起始处的地址。声明一个函数指针时，必须声明指针指向的函数类型

- ```c
  void (*pf) (char *); //pf 是一个指针，指向函数地址
  //函数名就是地址，直接调用即可
  ```

## 第15章 位操作

### 15.1 二进制数、位和字节

- 进制 补码  浮点数等知识

### 15.2 其他进制数

### 15.3 C按位运算符

- 操作无非是 与或非 异或，常见用法 掩码，设置位，移位运算

### 15.4 位字段

- 结构体里面使用

### 15.5 对齐特性（C11）

- C11的对齐特性比用位填充字节更自然，它们还代表了C在处理硬件相关问题上的能力
- _Alignof运算符给出一个类型的对齐要求，在关键字_Alignof后面的圆括号中写上类型名即可：

## 第16章 C预处理器和C库

### 16.1 翻译程序的第一步

- 编译器把源代码中出现的字符映射到源字符集,该过程处理多字节字符和三字符序列
- 定位反斜杠，将多行合并成一行
- 编译器把文本划分成预处理记号序列、空白序列和注释序列

### 16.2 明示常量：#define

- 指令只允许在同一行，由预处理器指令、宏、替换体组成

### 16.3 在#define中使用参数

- 用括号包起来
- #号作为一个预处理运算符，可以把记号转换成字符串
- ##运算符可用于类函数宏的替换部分。而且，##还可用于对象宏的替换部分
- 变参宏：...和 \_\_VA\_ARGS\_\_

### 16.4 宏和函数的选择

- 宏属于内联生成代码，速度快，不用担心变量类型，但是使用不当会有副作用
- 宏名称不允许空格，需要使用括号将替换体包起来，

### 16.5 文件包含：#include

- 当预处理器发现#include指令时，会查看后面的文件名并把文件的内容包含到当前文件中

### 16.6 其他指令

- #undef 取消定义的 #define 指令
- #ifdef #else #endif 条件编译；还有#ifndef 
- #if #elif，用于替代旧的#ifdef

- 预定义宏比如 \_\_FILE\_\_等，双下划线。
- #line 和 #error，#pragma可以使用编译指示
- C11增加了泛型选择表达式，_Generic

### 16.7 内联函数（C99）

- 空间换时间，一般使用较短函数

### 16.8 _Noreturn函数（C11）

- C99新增inline关键字时，它是唯一的函数说明符

- _Noreturn的目的是告诉用户和编译器，这个特殊的函数不会把控制返回主调程序

### 16.9 C库

- 一般自动或者头部引入

### 16.10 数学库

- math.h，三角问题，类型变体，tgmath.h库

### 16.11 通用工具库

- 在stdlib.h头文件中，有 exit，atexitqsort

### 16.12 断言库

- assert.h头文件支持的断言库是一个用于辅助调试程序的小型库

- C11新增了一个特性：_Static_assert声明，可以在编译时检查assert()表达式

### 16.13 string.h库中的memcpy()和memmove()

### 16.14 可变参数：stdarg.h

- stdarg.h头文件为函数提供了一个类似的功能，但是用法比较复杂

## 第17章 高级数据表示

### 17.1 研究数据表示

### 17.2 从数组到链表

### 17.3 抽象数据类型（ADT）

- 在C中，可以提供结构定义和操控该结构的函数原型。

### 17.4 队列ADT

### 17.5 用队列进行模拟

### 17.6 链表和数组

### 17.7 二叉查找树