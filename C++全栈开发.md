# C++基础入门

## 1. C++初识

### 1.1 编写第一个C++ 程序

四个步骤：

创建项目

创建文件

编写代码

运行程序

```c++
#include <iostream>;


using namespace std;

int main(void) {

	cout << "hello world!" << endl;

	system("pause");
	return 0;
}
```

### 1.2 单行注释和多行注释

```c++
 //单行注释

 /*
 	多行注释
 */
```

### 1.3 变量

变量存在的意义：方便我们管理内存空间

**变量创建的语法**： 数据类型  变量名 = 变量初始值；

​								int  a  =  10;

```c++
#include <iostream>;


using namespace std;

int main(void) {


	//定义变量

	int a = 10;
	cout << "a = " << a << endl;

	system("pause");
	return 0;
}
```

### 1.4 常量

**作用**：用于记录程序中不可更改的数据

C++定义常量的两种方法：

​	1.**#define**宏常量：	#define 常量名 常量值

​		通常在文件上方定义

​	2.**const**修饰的变量

```c++
#include <iostream>;

//定义常量的两种方式：
// 
//1.
#define Day 7

using namespace std;

int main(void) {

	//2.
	const int month = 30;
	cout << "一周有" << Day<<"天，一个月有"<<month<<"天" << endl;

	system("pause");
	return 0;
}
```



### 1.5 关键字

**作用**：关键字是C++中预先保留的单词（标识符）。



## 2. 数据类型

###  2.1 sizeof关键字

**作用**：统计数据类型所占内存大小

**语法**：sizeof(数据类型/变量)

```c++
//数据类型
coun<<"short类型所占内存空间为："<<sizeof(short)<<endl;
//变量
int num = 10;
coun<<"short类型所占内存空间为："<<sizeof(num)<<endl;
//short_2字节	int_4字节 long_4字节 long long_8字节
```

### 2.2 所有数据类型

|          | 数据类型         |        占用空间         | 取值范围                |
| -------- | ---------------- | :---------------------: | ----------------------- |
| 整型     | short            |          2字节          | -2^15~2^15-1            |
| 整型     | int              |          4字节          | -2^31~2^31-1            |
| 整型     | long             | 4字节(linux64位为8字节) | -2^31~2^31-1            |
| 整型     | long long        |          8字节          | -2^63~2^63-1            |
| 实型     | float（单精度）  |          4字节          | 7位有效数字             |
| 实型     | double（双精度） |          8字节          | 15~16位有效数字         |
| 字符型   | char             | 1字节（单引号  ‘  ’  ） | ASCII码  a-97 A-65      |
|          | 转义字符         |            /            | 常用：\n 换行  \t制表   |
| 布尔类型 | bool             |          1字节          | true/false（本质是1/0） |
| 输入类型 | cin              |                         | 语法：cin>>变量         |

*注1*：编译器会默认输入的小数为**double类型**的数，如:

```c++
float f1 = 3.14;	//其中3.14为double类型，系统会先把3.14这个double数据类型转换成float，再赋值。良好的定义float数据类型的方法是在小数后面加代表float数据类型的字母f，如：
float f2 = 3.14f;
```

*注2*：C++中**字符串类型**的两种定义形式：

```c++
#include <string> // 用C++输出字符串要包含此头文件


// 1.C风格字符串  char 字符串名[] = "XXX"
char A[] = "hello world!"
cout<<A<<endl;

// 2.C++风格字符串 要包含<string>头文件
string str = "hello world!"
```

*注3*：各种数据类型的**输入**：

```c++
int main(){
    //1.整型
    int a = 0;
    cout<<"please input:"<<endl;
    cin>>a;
    cout<<"a is:"<<a<<endl;
    //2.浮点型
    //3.字符型
    //  同上
    //4.字符串型（注意引入头文件<string>）
    //布尔类型（输入0为假，非0皆为真）
    
}
```

## 3.运算符

### 3.1算数运算符

“ + - * / % ++ --”

### 3.2赋值运算符

“= += -= *= /= %=”

### 3.3 比较运算符

“== != < > <= >=”

###  3.4 逻辑运算符

“! && ||”

## 4.程序流程结构

C/C++ 支持最基本的三种程序运行结构：顺序结构，选择结构，循环结构

### 4.1 选择结构

#### 4.1.1 if语句

**作用**：执行满足条件的语句

单行if，多行if，多条件if，嵌套if

#### 4.1.2 三目运算符

**作用**：通过三目运算符实现简单的判断

**语法**：

```c++
表达式1 ? 表达式2 : 表达式3
```

#### 4.1.3 switch语句

**作用**：执行多条件分支语句

**语法**：

```c++
switch(表达式):{
    case 结果1:
    	执行语句；
        break;
    case 结果2:
		执行语句;
    	break;
    ...
    default:
    	执行语句;
    	break;
}
```

### 4.2 循环结构

#### 4.2.1 while语句

```c++
while(循环条件){
    循环语句;
}
```

#### 4.2.2 do...whild语句

```c++
do{
    循环语句;
}while(循环条件);
```



#### 4.2.3 for循环语句

**作用**：满足循环条件，执行循环语句

**语法**：for(起始表达式；条件表达式；末尾循环体){循环语句;}



### 4.3 跳转语句 break,continue,goto

#### 4.3.1 break语句

**作用**：跳出选择结构或者循环结构

break使用的时机：

​		出现在switch条件语句中，作用是**终止case并跳出switch**

​		出现在循环语句中，作用是**跳出当前的循环语句**

​		出现在嵌套循环中，跳出**最近的内层循环语句**

#### 4.3.2 continue语句

**作用**：在**循环语句**中，**跳出本次循环**中尚未执行的语句，继续执行下一次循环

#### 4.3.3 goto语句

**作用**：可以无条件跳转语句

**语法**：```goto 标记;```

解释：如果标记的名称存在，执行到goto语句时，会跳转到标记的位置

**示例**：

```C++
int main(){
    cout<< "1.XXX"<<endl;
    goto FLAG;
    cout<< "2.XXX"<<endl;
    cout<< "3.XXX"<<endl;
    FLAG;
    cout<< "4.XXX"<<endl;
    /*
    输出：
    1.XXX
    4.XXX
    */
} 
```

*PS:goto向上跳转可以实现循环，加上if可以写循环语句，但不建议使用goto*

## 5.数组

### 5.1 概述

所谓数组，就是一个集合，里面存放了**相同类型**的数据元素

**特点1**：数组中每个数据元素都是**相同的数据类型**

**特点2**：数组是由**连续的内存位置**组成的

### 5.2 一维数组

#### 5.2.1 一维数组定义方式

一维数组定义的三种形式：

1.```数据类型 数组名[数组长度];```  **常用**

2.```数据类型 数组名[数组长度]={值1，值2，...};```

3.```数据类型 数组名[]={值1，值2，...};```

#### 5.2.2 一维数组数组名

**用途1**.可以统计**数组在内存中的长度**		```sizeof(arr)```

**用途2**.可以获取数组在**内存中的首地址**	例：```cout<<arr<<endl;```,打印地址如 0x0000

​				   获取任意元素的地址```cout<<&arr[x]<<<endl;``` 可以取数组下标为x的元素的地址。**取地址符&**

### 5.3 二维数组

#### 5.3.1 二维数组定义方式

二维数组的四种定义方式：

1.```数据类型 数组名[行数][列数];```

2.```数据类型 数组名[行数][列数]={{数据1,数据2,...},{数据3,数据4,...},...};```	直观，推荐

3.```数据类型 数组名[行数][列数]={数据1,数据2,数据3,数据4,...};```		*不直观，但是理解计算是行优先*

4.```数据类型 数组名[][列数]={数据1,数据2,数据3,数据4,...};```    *计算机会拿数据除列数计算行数*

#### 5.3.2 二维数组数组名

用途同一维数组(5.2.2)。

## 6. 函数

### 6.1 概述

**作用**：将常用的代码封装起来，减少重复代码

一个较大的程序，一般分为若干程序块，每个模块实现特定的功能

###  6.2 函数的定义

函数的定义一般有以下五个步骤：

1.返回值类型

2.函数名

3.参数列表

4.函数体语句

5.return表达式

例：

```c++
//函数定义
int add(int a,int b){
    int sum = a + b;
    return sum;
}
```

### 6.3函数的调用

**功能**：使用定义好的函数

**语法**：```函数名(参数)```

### 6.4 值传递

值传递是函数调用时实参将数值传入给形参

值传递时，如果形参发生改变，不会影响实参

### 6.5 函数声明

**作用**：告诉编译器函数名称及如何调用函数。函数的实际主体可以单独定义。

函数的**声明可以多次**，但是函数的**定义只能有一次**

### 6.6函数的分文件编写

**作用**：让代码结构更加清晰

函数分文件编写一般有4个步骤：

1.创建后缀名为.h的头文件

2.创建后缀名为.cpp的源文件

3.在头文件中写函数的声明

4.在源文件中写函数的定义

示例：

主程序:main.cpp,要先引用头文件

```c++
#include <iostream>
//引用头文件
#include "swap.h"
using namespace std;

int main() {
    
	int a = 10;
	int b = 20;
    
    swap(a,b);
    
    return 0;
}
```

头文件：swap.h，创建名为swap.h的头文件并在头文件中写函数的声明

```c++
#include <iostream>;
using namespace std;


void swap(int a, int b);

```

源文件：swap.cpp，创建名为swap.cpp的源文件并在源文件中写函数的定义

```c++
#include <iostream>;
using namespace std;

void swap(int a, int b) {
	int temp = a;
	a = b;
	b = temp;
}
```



## 7. 指针

### 7.1 指针的基本概念

**作用**：可以通过指针间接访问内存

内存编号是从0开始记录的，一般用十六进制数字表示

可以利用指针变量保存地址

### 7.2 指针变量的定义和使用

指针变量定义语法：```数据类型 *变量名```

```c++
#include <iostream>
using namespace std;

int main() {
	int a = 10;
	
	//1.定义指针
	int *p;
    
	//2.让指针P记录变量a的地址
	p = &a;			//其中&为取地址符
	cout << "a的地址为：" << p << endl;

	//3.指针的使用
	//可以通过解引用的方式来找到指针指向的内存
	//指针前加 * 代表解引用，找到指针指向的内存中的数据
	*p = 100;	//此时指针p记录的是变量a的地址，*指向地址p中的数据，即a的数据

	cout << "a的值为：" << a << endl;
	cout << "p指针地址中的值为:" << *p << endl;

	return 1;
}
```

### 7.3 指针所占内存空间

32位：4字节  （4*8bite = 32）指针保存的是地址

64位：8字节

### 7.4 空指针和野指针

**空指针**：指针变量指向内存中编号为0的空间

**用途**：初始化指针变量

**注**：空指针指向的内存是不可访问的

示例1： 空指针

```c++
int main(){
    //指针变量p指向内存地址编号为0的空间
    int * p = NULL;
    
    //访问空指针报错
    //内存编号0~255为系统占用内存，不允许用户访问
    
    cout << *p <<endl;//此时会报错，因为NULL指针不允许访问
    
    return 0;
}
```

**野指针**：指针变量指向非法的内存空间（未申请的地址空间）

```c++
int * p = (int *)001100
```

###  7.5 const 修饰指针

const修饰指针有三种情况：

1.const修饰指针 —— 常量指针（常量的指针）

2.const修饰常量 —— 指针常量（指针是常量）

3.const既修饰指针，又修饰常量

 **常量指针**：

```c++
const int *p = &a;
```

特点：指针的指向可以修改，但是指针指向的值不可以修改  

```c++
int a = 10;
const int * p = &a;

*p = 20; //错误，指针指向的值不可以修改
p = &b;  //正确，指针指向可以修改
```

**指针常量**：（理解记忆：const 修饰的是p的值，也就是地址，因此指针的指向（指针地址）不能修改）

```c++
int * const p = &a;
```

特点：指针地址不可以修改，指针指向的值可以改

```c++
int a = 10;
int * const p = &a;

*p = 20; //正确，指针指向的值可以修改
p = &b;  //错误，指针指向不可以修改
```

 ### 7.6 指针和数组

**作用**：利用指针访问数组中的元素

示例：

```c++
#include<iostream>
using namespace std;

int main() {
	//指针和数组
	//利用指针访问数组中的元素

	int arr[10];

	for(int i = 0; i < 10; i++ ){
		arr[i] = i;
	}

	int* p = arr;  //数组的名称arr就是数组首地址

	cout << arr << endl;
	//打印数组arr中首元素的值
	cout << *p << endl;

	p = p + 1;
	cout << *p << endl;
	return 0;
}
```

*ps:指针在定义时int \* p,其中（int \*）表示，定义的p为int类型的指针，而后面打印的\*p表示p地址指向的内容*

即：

```c++
int* p = &a;
//等价于
int* p;
p = &a;
```

### 7.7 指针和函数(地址传递)

**作用**：利用指针**做函数参数**，可以**修改实参的值**

```c++
#include<iostream>
using namespace std;
//值传递
void swap1(int a,int b){
    int temp = a;
    a = b;
    b = temp;
}
//地址传递
void swap(int* p1;int* p2){
    int temp = *p1;
    *p1 = *p2;
    *p2 = temp;
}

int main(){
    int a =10;
    int b =20;
    swap(&a,&b);
    cout<<a<<b<<endl;	//会发现a,b的值发生了改变
    return 0;
}
```

### 7.8 指针、数组和函数

**案例描述**： 封装一个函数，利用冒泡排序，实现对整形数组的升序排序，并打印出来

例如数组： int arr[10]={4,3,6,9,1,2,10,8,7,5}

示例：

```c++
//冒泡排序
#include<iostream>
using namespace std;

void buubleSort(int* arr, int len) {	// int  *arr 也可以写成int arr[] 
	for (int i = 0; i < len-1; i++) {
		for (int j = 0; j < len - i-1; j++) {
			if (arr[j] > arr[j + 1]) {
				int temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}
}

void printArray(int* arr, int len) {
	for (int i = 0; i < len; i++) {
		cout << arr[i] << "\t";
	}
}

int main() {
	//指针和数组
	//利用指针访问数组中的元素

	int arr[10] = { 4,3,6,9,1,2,10,8,7,5 };
	int len = sizeof(arr) / sizeof(arr[0]);

	buubleSort(arr, len);
	
	printArray(arr, len);
	return 0;

}

```

## 8. 结构体

### 8.1结构体基本概念

结构体是用户自定义的数据类型，允许用户存储不同的数据类型

### 8.2 结构体定义和使用

**语法**：```struct 结构体名 {结构体成员列表};```

例：

```c++
//结构体定义(自定义的数据类型，一些类型组合成的类型)
struct student{
    string name;
    int age;
    float score;
}
```



通过**结构体创建变量**的方式有三种：

1.struct 结构体名 变量名

2.struct 结构体明 变量名 = {成员1值，成员2值,...}

3.定义结构体时顺便创建变量

```c++
创建变量的方式
//1.struct 结构体名 变量名 (struct 关键字可以省略)
struct student s1;  // 或 student s1;
s1.name = "小红";
s1.age = 19;
s1.score = 480;
//2.struct 结构体明 变量名 = {成员1值，成员2值,...}
struct student s2 = {"小明",18,500}
//3.定义结构体时顺便创建变量
struct student{
    string name;
    int age;
    float score;
}s3;
s3.name = "小王";
s3.age = 20;
s3.score = 490;
```

**总结**：1.定义结构体时的关键字是struct，不可以省略

​			2.创建结构体变量时，关键字struct可以省略

​			3.结构体变量利用操作符“.”访问成员

### 8.3 结构体数组

**作用**：将自定义的结构体放到数组中方便维护

**语法**：```struct 结构体名 数组名[元素个数]={{结构体变量1元素}，{结构体变量2元素},...}

例如：

```c++
//1.定义结构体
struct student{
    string name;
    int age;
    float score;
}
//2.创建结构体数组
struct student students[3]={
    {"小明",18,500},
    {"小王",19,490},
    {"小红",17,480}
};

//3.给结构体数组中的元素赋值（或修改）
students[1].name = "小张";

//4.遍历结构体数组
for(int i = 0;i<3;i++){
    cout<<"姓名:"<<students[i].name
        <<"年龄:"<<students[i].age
        <<"分数:"<<students[i].score<<endl;
}
```

### 8.4 结构体指针

**作用**：通过指针访问结构体中的成员

​	利用操作符```->``可以通过结构体指针访问结构体属性

例：

```c++
//假设已经定义好结构体student
struct student s1;
s1.name = "小红";
s1.age = 19;
s1.score = 480;

//通过指针指向结构体变量(这里指针类型应该和要指向的结构体变量的类型一致)
student* p = &s1;

//通过指针访问结构体变量中的数据
cout<<"姓名："<<p->name<<"年龄："<<p->age<<"分数："<<p->score<<endl;
```

总结：结构体指针可以通过->操作符来访问结构体中的成员

### 8.5 结构体嵌套结构体

**作用**：结构体中的成员可以是另一个结构体

**例如**：每个老师辅导一个学员，一个老师结构体中，记录了其辅导的学生结构体

**示例**：

```c++
struct student{
    string name;
    int age;
    float score;
}

//结构体嵌套结构体
struct techer{
    int ID;
    string name;
    int age;
    struct student stu;		//辅导的学生
}

// 创建老师
techer t;
t.ID = 0001;
t.name = "老王";
t.age = 50;
t.stu.name = "小明";
t.stu.age = 18;
t.stu.score = 500;
```

总结：在结构体中可以定义另一个结构体作为成员，用来解决实际问题

### 8.6结构体做函数参数

**作用**：将结构体作为参数向函数中传递

传递的方式有两种：1.**值传递**；2.**地址传递**

**示例**：(打印学生身上所有信息)

```c++
//学生结构体定义
struct student
{
    //成员列表
    string name;
    int age;
    int score;
}
// 值传递参数为结构体类型变量
void printinf1(struct student s){
    cout<<s.name<<s.age<<s.score<<endl;
	return;
}

// 地址传递参数为结构体类型的指针
void printinf2(struct student* s){
    cout<<s->name<<s->age<<s->score<<endl;
    return;
}

int main(){
	//创建结构体变量
    struct student S;
    //值传递
   	printinf1(S);
    //地址传递
    printinf2(&S);
    
	return 0;
}
```

### 8.7 结构体中const使用场景

**作用**：用const防止误操作

示例：

```c++
//将函数中的形参改为指针，可以减少内存空间，不会复制新的副本出来
void printinf2(const student* s){
    s->age = 100; //会报错，const就是防止在调用原结构体变量时修改其中的值
    cout<<s->name<<s->age<<s->score<<endl;
    return;
}
```



### 8.8案例

设计一个英雄的结构体，包括成员姓名，团战伤害；创建结构体数组，数组中存放五名英雄。通过冒泡排序算法，将数组中的英雄按照造成的团战伤害进行排序，并最终打印排序后的结果。

```c++
{"刘备",1145},
{"张飞",140},
{"貂蝉",4396},
{"关羽",0},
{"赵云",9999}
```

```c++
#include <iostream>
#include <string>
using namespace std;

//英雄结构体
struct heros{
    string name;
    int score;
};

//冒泡排序
void bubbleSort(heros* H){
    for(int i=0;i<5-1;i++){
        for(int j=0;j<5-i-1;j++){
            if(H[j].score<H[j+1].score){
                heros temp = H[j];
                H[j] = H[j+1];
                H[j+1]=temp;
            }
        }
    }
    return;
}

//打印英雄
void printHero(heros* H){
    for(int i=0;i<5;i++){
        cout<<H[i].name<<"\t"<<H[i].score<<endl;
    }
    return;
}

int main(){
    heros hs[5]={
        {"刘备",1145},
        {"张飞",140},
        {"貂蝉",4396},
        {"关羽",0},
        {"赵云",9999}
    };


    bubbleSort(hs);
    printHero(hs);
    return 1;

}
```



## 基础阶段项目：通讯录管理系统

### 1.系统需求

通讯录是一个可以记录亲人，好友信息的工具

本教程主要利用C++来实现一个通讯录管理系统

系统中需要实现的功能如下：

* 添加联系人：向通讯录中添加新人，信息包括（姓名、性别、年龄、联系电话、家庭住址）最多纪录1000人
* 显示联系人：显示通讯录中所有联系人信息
* 删除联系人：按照姓名进行删除指定联系人
* 查找联系人：按照姓名查看指定联系人信息
* 修改联系人：按照姓名重新修改指定联系人
* 清空联系人：清空通讯录中所有信息
* 退出通讯录：退出当前使用的通讯录



# C++核心编程(面向对象)

本阶段主要针对C++面向对象编程技术做详细讲解，探讨C++中的核心和精髓；



## 1.内存分区模型

C++程序在执行时，将内存大方向划分为**4个区域**

* 代码区：存放函数体的二进制代码，由操作系统进行管理
* 全局区：存放全局变量和静态变量以及常量
* 栈区：由编译器自动分配释放，存放程序的参数值，局部变量等
* 堆区：由程序员分配和释放，若程序员不释放，程序结束时由操作系统回收



**内存四区的意义**：

不同区域存放不同数据，赋予不同的生命周期，给我们更大的灵活编程的空间。



### 1.1 程序运行前

在程序编译后，生成了exe可执行程序，**未执行该程序前**分为两个区域

**代码区**：共享、只读

​			存放CPU执行的机器指令

​			代码区是**共享**的，共享的目的是对于频繁被执行的程序，只需要在内存中有一份代码即可；（例如：很多.exe可以被重复打开）

​			代码区是**只读**的，其只读的原因是防止程序意外地修改了它的指令

**全局区**

​		全局变量和静态变量存放在此

​		全局区还包含了常量区，字符串常量和其他常量也存放在此（const修饰的全局常量也在全局区）

​		该区域的数据在程序结束后由操作系统释放

```c++
#include<iostream>
using namespace std;

//全局变量
int g_a = 10;
int g_b = 10;
//const修饰的全局变量——全局常量
const c_g_a = 10;
const c_g_b = 10;

int main() {
	// 全局区
	// 全局变量、静态变量、常量

    //静态变量 在普通变量前面加static，属于静态变量
	statice int s_a = 10;
    statice int s_b = 10;
    
    //常量 —— 字符串常量和const修饰的变量
    //字符串常量
    string a = "hello world!"
    //const修饰的变量++const可以修饰全局变量和局部变量
        
        
    //注注注注注注注注注注注注注注注注注注注注注注注注注注注注注注注注注注
    //const修饰的局部变量++++++++++++++++++++++局部常量 不在全局区
    const int c_l_a = 10;
    const int c_l_b = 10;
     
    
    // 全局变量的地址
	cout << &g_a << endl;
	cout << &g_b << endl;
	/*
	输出
	00007FF66759C010
	00007FF66759C014
	*/
        
	// 创建普通局部变量
	int a = 10;
	int b = 10;

	// 局部变量的地址

	cout << &a << endl;
	cout << &b << endl;
	/*
	输出
	000000D66DEFF594
	000000D66DEFF5B4
	*/

	return 1;
}
```

**总结**：**全局变量**、static修饰的**静态变量**、常量中的**字符串常量**、const修饰的**全局常量**在全局区

​			**局部变量**和const修饰的**局部常量**不在全局区

### 1.2 程序运行后

**栈区**：

​	由编译器**自动分配和释放**，存放函数的参数值，局部变量等

​	注意事项：不要返回局部变量的地址，栈区开辟的数据由编译器自动释放

```c++
#include<iostream>
using namespace std;

//栈区数据注意事项 ——不要返回局部变量的地址
//栈区的数据由编译器管理开辟和释放


//返回值类型是int型的指针
int* func(){
    int a = 10;//局部变量	存放在栈区，栈区的数据在函数执行完后自动释放
    
    return &a;	//返回局部变量的地址，错误行为
}

int main(){
    //接收func函数的返回值
    int* p = func();
    
    //10
    cout <<*p<<endl;  //第一次可以打印正确的数字是因为编译器做了保留
    
    //乱码
    cout <<*p<<endl;	//第二次这个数据就不再保留了
}
```



**堆区**：

​	由程序员分配释放，若程序员不释放，程序结束时由操作系统回收

​	在C++中主要利用new在堆区中开辟内存

```c++
#include<iostream>
using namespace std;

int* func(){
    //利用new关键字  可以将数据开辟到堆区
    
    //new 返回一个开辟的堆区地址，可以用指针接收
    int* p = new int(10);
    return p;
}

int main(){
    //在堆区开辟数据
    int* p = func();
    cout<<*p<<endl;
    return 0;
    
}
```

**总结**：堆区数据由程序员管理开辟和释放

​			堆区数据利用new关键字进行开辟内存

### 1.3 new操作符

C++中利用**new**操作符在堆区开辟数据  (各种数据类型或者数组)

堆区开辟的数据，由程序员手动开辟，手动释放，释放利用操作符**delete**

**语法**：`new 数据类型`

```c++
#include<iostream>
using namespace std;
//1.new的基本语法
int* func(){
    //在堆区创建整数类型
    //new 返回的是 该数据类型的指针（地址）
    int* p = new  int(10);
    return p;
}
void test01(){
    int* p =func();
    cout <<*p<<endl;
    cout <<*p<<endl;
    cout <<*p<<endl;
    //堆区的数据由程序员管理开辟，程序员管理释放
    //如果想释放堆区的数据，利用关键字delete
    delete p;
    
    cout <<*p<<endl;//报错。内存已经被释放，再次访问就是非法操作，会报错
}

//2.在堆栈利用new开辟数组
void test02(){
    //创建10个整型数据的数组，在堆区
    int* arr = new int[10];
   	for(int i=0;i<10;i++){
        arr[i] = i+100;
    }
    
    for(int i=0;i<10;i++){
        cout<<arr[i]<<endl;
    }
    
    //释放堆区数组
    //释放数组的时候，要加[]才可以
    delete[] arr;
}
int main(){
    test01();
    return 0;
}
```

## 2. 引用

### 2.1引用的基本使用

**作用**：给变量取别名

**语法**： `数据类型 &别名 = 原名；`

*其实也就是把原名a所在的内存地址也给了别名b，a,b同时指向同一片地址空间*



### 2.2 引用的注意事项

* 引用必须初始化
* 引用在初始化后，不可以改变

1.引用必须初始化

```c++
int a = 10;
int &b = a;
//对

int &b;
//错，引用必须初始化，即一开始就得有个地址供引用指向
```

2.引用在初始化后，不可以改变

```c++
b = c;
//错，引用在初始化后不亏改变
```



### 2.3 引用做函数参数

**作用**：函数传参时，可以利用引用的技术让形参修饰实参？（即，形参发生改变，实参也会发生改变）

**优点**：可以简化指针修改实参

```c++
//三种函数传递方式

//1.值传递
void swap1(int a,int b){
    int temp = a;
    a = b;
    b = temp
}

//2.地址传递
void swap2(int* a,int* b){
    int temp = *a;
    *a = *b;
    *b = temp;
}

//3.引用传递
void swap3(int &a,int &b){
    int temp = a;
    a = b;
    b = temp;
}

//主函数
int main(){
    a=10;
    b=20;
    
    swap1(a,b);
    swap2(&a,&b);
    
    //引用传递，形参发生改变，实参也会发生改变
    swap3(a,b);
    return 0; 
}
```

**引用的原理**：形参中的参数作为实参的别名，和实参共同指向一片地址空间，所以形参发生改变，即该地址空间中保存的数据发生改变，实参因此也发生改变。

### 2.4 引用做返回值类型

**作用**：引用是可以作为函数 的返回值存在的

注意：不要返回局部变量引用

用法：函数调用作为左值

```c++
//引用作为函数的返回值
//1.不要返回局部变量的引用
int& test01(){
    int a = 10;
    return a;//局部变量保存在栈区，在test01函数运行结束后，系统会自动释放a的内存空间
}

//2.函数的调用可以作为左值
int& test02(){
    static int a = 10;//静态变量，存放在全局区，全局区上的数据在整个程序结束后才会释放空间
    return a;
}

int main(){
    int &ref2 = test02();
    cout<<"ref2="<<ref2<<endl;
    //ref2输出为10
    
    //函数调用可以作为左值
    test02 = 1000;//如果函数的返回值是引用，这个函数调用可以作为左值
    //引用作为返回值类型表示返回的那个地址的值，此时再给他赋值表示将该地址的值赋新的值。
    cout<<"ref2="<<ref2<<endl;
    //ref2输出为1000
    return 1;
}
```

### 2.5 引用的本质

**本质**：引用的本质在C++内部实现是一个指针常量（指针是常量）

![image-20230718230833586](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230718230833586.png)

### 2.6 常量引用

**作用**：常量引用主要用来修饰形参，防止误操作（原理：常量指针常量，指针指向的地址不可以更改，指针地址中的值也不能修改）

在函数形参列表中，可以加const修饰形参，防止形参改变实参

```c++
void showValue(int& val){
    val = 10;//此时内部val和外部b的指向的内存地址中的值发生了改变。
}
//常量引用
void showValue2(cost int& val){
    val = 10;//报错，常量引用。指向的内存地址中的值不可以修改
}

int main(){
    //常量引用
    //使用场景：用来修饰形参，防止误操作
    
    int a = 10;
    int& ref =10;//错误。引用代表的是一个固定的合法的内存地址中的值，而10是个常量，不能被引用。
    
    const int& ref = 10;//正确。加上const之后，编译器将代码修改为：
    					//int temp = 10; const int& ref = temp；
    ref = 20;//错误，加入const之后变为只读，不可以修改
    
    
    int b = 100;
    showValue(b);
    
    return 1;
}
```

**PS**:为什么不用值传递呢？值传递会开辟大量地址空间，造成浪费。因此在以后的开发中，如果不想让调用函数内部改变外部变量的值，可以用**常量引用**。

## 3. 函数提高

### 3.1 函数默认参数

在c++中，函数的形参列表中的形参是可以有默认值的。

语法:`返回值类型 函数名（参数 = 默认值）{}`

示例：

```c++
//1.如果某个位置参数有默认值，那么从这个位置往后，都必须要有默认值
int func(int a,int b = 10,int c = 10){
    return a+b+c;
}


//2.如果函数声明有默认值，函数实现的时候就不能有默认参数(否则重定义了默认参数，二义性)
//声明和实现只能有一个有默认参数
int func2(int a = 10,int b = 20);
int func2(int a ,int b){
    return a+b;
}
```

### 3.2 函数占位参数

C++中函数的形参列表里可以有占位参数，用来占位，调用函数时必须填补该位置

**语法**：`返回值类型 函数名（数据类型）{}`

```c++
//函数占位参数，占位参数也可以有默认参数
void func(int a,int){
    cout<<"func"<<endl;
}

int main(){
    func(10,20); //此时，20传递给占位参数int,但是我们不能在函数中使用传进来的20
	return 0;	 //目前阶段占位参数用不到
    
}

//占位参数也可以有默认参数
void func2(int a =10,int = 10){
    ......
}
```

### 3.3 *函数重载

#### 3.3.1 函数重载概述

**作用**：函数名可以相同，提高复用性

**函数重载满足条件**

* 同一个作用域下
* 函数名称相同
* 函数参数**类型不同**或者**个数不同**或者**顺序不同**

**注意**：函数的返回值不可以作为函数重载的条件



**示例**：

```c++
//函数重载需要函数在同一个作用域下
void func(){
    cout<<"func 的调！"<<endl;
}
void func(int a){ //重载，函数名相同，但函数参数类型不用或者个数不同或顺序不同
    cout<<"func(int a)的调用"<<endl;
}
void func(double a){
    ......;
}

void func(double a,int b){
    ......;
}
void func(int a,double b){
    ......;
}

int main(){
    func(10);//参数个数不同
    func(3.14);//参数类型不同
    func(10,3.14);//参数顺序不同
    
    return 0;
}

//注意事项：
//仅函数的返回值类型不同的函数不能重载
//如
int func(){
    ......;
	return 0;
}
void func(){
    ......;
}
//不能重载
```

#### 3.3.2 函数重载注意事项

* 引用作为重载条件
* 函数重载碰到函数默认参数

**示例**：

```c++
//函数重载的注意事项
//1.引用作为重载的条件
void func(int &a){	//为什么func(10)不走这条：int &a=10 不合法
    cout <<"func(int &a)调用"<<endl;
}

void func(const int &a){//const int &a = 10;
    					//此时编译器内部：int temp = 10;
    					//			   const int &a = temp;(故合法)
    cout <<"func(const int &a)调用"<<endl;
}


//2.函数重载碰到默认参数
void func2(int a){
    ......;
}
void func2(int a,int b = 10){
    ......;
}

int main(){
    int a = 10;
    func(a);//调用没有加const的重载函数
   	func(10);//调用加const的重载函数
    
    func2(10);
    //此函数重载同时满足func2(int a)和void func2(int a,int b = 10)，出现二义性，会报错。需要尽量避免。
    //因此写函数重载时尽量避免默认参数

        
    return 1;
}
```

**注**：参数类型为常量引用和对应基本参数类型的函数不能重载，有二义性。

```c++
void func(int a) {
}
void func(const int& a) {
}
```

## 4. 类和对象

C++面向对象的三大特性为：**封装、继承、多态**

C++认为**万事万物都皆为对象**,对象上有其属性和行为



**例如**：人可以作为对象，

​			属性有姓名、年龄、身高、体重......，

​			行为有走、跑、跳、吃饭......，

​			车可以作为对象，

​			属性有轮胎、方向盘、车灯......，

​			行为有载人、放音乐、开空调......。	

​			

​			具有相同性质的**对象**，我们可以抽象称为**类**，人属于人类，车属于车类

### 4.1 封装

#### 4.1.1 封装的意义

封装是c++面向对象三大特性之一

封装的意义：

* 将属性和行为作为一个整体，表现生活中的事物
* 将属性和行为加以权限控制

**封装的意义一**：

​	在设计类的时候，属性和行为写在一起，表现事物

**语法**：`class 类名{访问权限： 属性/行为};



**示例1**：设计一个圆类，求圆的周长

**示例代码**：

```c++
#include <iostream>
#include <string>
#define PI  3.14
using namespace std;

//设计一个圆类，求圆的周长
//圆求周长的公式： 2 * PI * 半径；
class Circle{
	//访问权限
public://公共权限

	//属性(变量表示)
	int m_r;
    
	//行为(用函数表示)
	//获取圆的周长
	double calculateZC() {
		return 2 * PI * m_r;
	}
};
int main() {

	//通过圆类创建具体的圆（对象）
    //实例化：通过一个类创造一个对象的过程。
	Circle c1;
	//给圆对象的属性进行复制
	c1.m_r = 10;
	cout << "圆的周长：" << c1.calculateZC() << endl;
	return 1;
}
```



**示例2** 设计一个学生类，属性有姓名和学号，可以给姓名和学号赋值，可以显示学生的姓名和学号

```c++
#include<iostream>
#include<string>
using namespace std;
//设计一个学生类，属性有姓名和学号
//可以给姓名和学号赋值，可以显示学生的姓名和学号

class Student{
public:
    //类中的属性和行为统一称为： 成员
    //属性（成员属性、成员变量）
    string m_Name;
    int m_ID;
    
    //行为：（成员函数、成员方法）
    void printStudent(){
        cout<<"name"<<m_Name<<"ID"<<m_ID<<endl;
    }
    //给姓名赋值
    void setName(name){
        m_Name = name;
    }
}

int main(){
    //创建一个学生对象，实例化对象
    Student s1;
    s1.name = "张三";
    s1.ID = 001;
  	s1.printStudent();
    
    Student s2;
    //设置s2的名字
    s2.setname("张三");//通过set行为给对象的属性赋值
    s2.ID = 001;
  	s2.printStudent();
    
    return 0;
}
```

**封装的意义二**：

类在设计时，可以把属性和行为放在不同的权限下，加以控制

**访问权限**有三种：

* public			公共权限		成员类内可以访问	类外可以访问
* protected     保护权限        成员类内可以访问     类外不可以访问    子类可以访问父类中的保护内容
* private          私有权限        成员类内可以访问     类内不可以访问    子类不可以访问父类的私有内容

示例：

```c++
#include<iostream>
#include<string>
using namespace std;

class Person {
public:		//公共权限
    string m_Name;
protected:	//保护权限
    string m_Car;
private:	//私有权限
    int m_Password;

public:
    void func() {
        m_Name = "张三";			//类内可以访问
        m_Car = "宝马";			//类内可以访问
        m_Password = 123456;	 //类内可以访问
    }
};

int main() {

    //实例化对象
    Person p1;
    p1.m_Name = "张三";		//类外可以访问
    p1.m_Car = "奔驰";        //报错，类外不能访问
    p1.m_Password = 666666;   //报错，类外不能访问
    return 0;
}
```

#### 4.1.2 struct和class区别

在c++中struct和class 唯一的**区别**就在于**默认的访问权限不同**

区别：

* struct默认访问权限为 公有 public
* class 默认访问权限为  私有 private

#### 4.1.3 成员属性私有化

**优点1**：将成员属性设置为私有，可以自己控制读写权限

**优点2**：对于写权限，我们可以检测数据的有效性

示例：

```c++
#include <iostream>
#include<string>
using namespace std;



//成员属性设置为私有
//1.可以自己控制读写权限
//2.对于写可以检测数据有效性

//设计人类
class Person {

public:
	void setName(string name) {
		m_Name = name;
	}
	string getName() {
		return m_Name;
	}
	int getAge(){
		m_Age = 0;
		return m_Age;
	}
	void setLover(string lover) {
		m_Lover = lover;
	}
	void setScore(int score) {
		if (score < 100 && score>0) {
			m_Score = score;
			return;
		}
		m_Score = -1;
		cout << "成绩不合法！" << endl;
	}
	int getScore() {

		return m_Score;
	}
private:
	//姓名 可读可写 
	string m_Name;
	//年龄 只读
	int m_Age;
	//爱人 只写
	string m_Lover;
	//成绩 可读可写（如果想修改，成绩的范围必须是0-100之间）
	int m_Score;
};

int main() {
	Person p;
	//p.m_Name = "张三";//错误，私有，类外无法访问

	//可以读写
	p.setName("张三");
	cout << p.getName() << endl;

	//只读
	cout << p.getAge() << endl;

	//只写
	p.setLover("张骞");

	//检测数据有效性
	p.setScore(-100);
	cout << p.getScore() << endl;
	return 1;
}
```

#### 4.1.4 练习案例1：设计立方体类

设计立方体类（Cube）

求出立方体的面积和体积

分别用全局函数和**成员函数**判断两个立方体是否相等



**思路**：

立方体类：

​	成员变量：长、宽、高

​	成员方法：求面积、求体积

实现：

```c++
#include <iostream>
#include<string>
using namespace std;


class Cube {
private:
	float m_L;
	float m_W;
	float m_H;

public:
	void setL(float L) {
		m_L = L;
	}
	float getL() {
		return m_L;
	}

	void setW(float W) {
		m_W = W;
	}
	float getW() {
		return m_W;
	}

	void setH(float H) {
		m_H = H;
	}
	float getH() {
		return m_H;
	}

	float getS() {
		return 2 * (m_L * m_W + m_W * m_H + m_L * m_H);
	}
	float getV() {
		return m_L * m_W * m_H;
	}

	//利用成员函数判断两个立方体是否相等(因为他在调用时，已经有了一个立方体对象的属性，因此参数列表只用传递另一个立方体的属性)
	bool isSameByClass(Cube& c) {
		if (m_L == c.getL() && m_W == c.getW() && m_H == c.getH()) {
			cout << "两个立方体相等" << endl;
			return 1;
		}
		cout << "两个立方体不相等" << endl;
		return 0;
	}
};

void same_Cube(Cube& c1, Cube& c2);
int main() {
	Cube c1;
	c1.setH(10);
	c1.setW(5);
	c1.setL(4);
	cout << c1.getS() << endl;
	cout << c1.getV() << endl;
	Cube c2;
	c2.setH(10);
	c2.setW(5);
	c2.setL(6);
	Cube c3;
	c3.setH(10);
	c3.setW(5);
	c3.setL(6);

	//利用全局函数判断两个立方体是否相等
	same_Cube(c1, c2);

	//利用成员函数判断两个立方体是否相等
	c1.isSameByClass(c2);
	c2.isSameByClass(c3);


	return 0;
}

void same_Cube(Cube& c1, Cube& c2) {
	if (c1.getH() == c2.getH() && c1.getW() == c2.getW() && c1.getL() == c2.getL()) {
		cout << "两个立方体相等" << endl;
		return;
	}
	cout << "两个立方体不相等" << endl;
	return;
}
```

#### 4.1.5 练习案例2：点和圆的位置关系

设计一个圆形类(Circle)，和一个点类(Point)，计算点和圆的关系

点和圆关系判断：

​	圆类：

​			半径

​			圆心（属于点类）

​			点和圆位置判断

​					点到圆心的距离 == 半径 点在圆上

​					点到圆心的距离  <  半径 点在圆内

​					点到圆心的距离  >  半径 点在圆外

​	点类：

​			点的坐标

​			点和点的距离

```c++
#include <iostream>
#include<string>
using namespace std;

//点类
class point {
private:
	float m_X;
	float m_Y;
public:
	void setX(float x) {
		m_X = x;
	}
	float getX() {
		return m_X;
	}
	void setY(float y) {
		m_Y = y;
	}
	float getY() {
		return m_Y;
	}
    //点与点之间距离计算 =====  点的成员方法
	float distance(point& p) {
		return (m_X - p.getX())*(m_X - p.getX()) + (m_Y - p.getY())*(m_Y - p.getY());
	}
};

//圆类
class Circle
{
public:
	void setR(float r) {
		m_R = r;
	}
	float getR() {
		return m_R;
	}
    //设置圆心(是个点)
	void setCenter(point& p) {
		m_Center = p;
	}
    //得到圆心(是个点)
	point getCenter() {

		return m_Center;
	}

    //点和圆的位置判断 ===== 圆的成员方法
	void locationRelat(point& p) {
		if (m_Center.distance(p) > m_R * m_R) {
			cout << "点在圆外" << endl;
			return;
		}
		else if(m_Center.distance(p) == m_R * m_R) {
			cout << "点在圆上" << endl;
			return;
		}
		cout << "点在圆内" << endl;
		return;
	}
private:
    
    //在类中可以让另一个类作为为本类中的成员
	point m_Center;
	float m_R;
};


int main() {

	Circle c;
	point center;
	center.setX(0);
	center.setY(0);
	c.setCenter(center);
	c.setR(1);

	point p;
	p.setX(1);
	p.setY(1);

	c.locationRelat(p);

	return 0;
}
```

#### 4.1.5 续 类的分文件编写

**步骤**：

* 1.在.h头文件中定义类及类中成员变量和成员方法的声明
* 2.在.cpp源文件中引用.h头文件，在其中只写成员方法的实现（**注**:需要用`类名::方法名()`表示该方法的作用域，即表达他是该类的一个成员方法）
* 3.在main.cpp中引用.h头文件即可
* **注**：在定义一个类时如果需要调用其他类，只需要在该类的头文件中调用其他类的.h头文件即可

示例：（上述案例修改为分文件编写）:

1.创建"point.h"头文件，并在其中定义Point类，声明其中的成员变量和成员方法:

```c++
#pragma once   //防止头文件重复包含
#include <iostream>

using namespace std;

class Point {
private:
	float m_X;
	float m_Y;
public:
	void setX(float x);
	float getX();
	void setY(float y);
	float getY();
	//点与点之间距离计算 =====  点的成员方法
	float distance(Point& p);
};
```

2.创建"point.cpp"源文件，在其中引用"point.h"头文件，并写成员方法的实现（用`Point::`标识该方法的作用域）

```c++
#pragma once
#include <iostream>
#include "point.h"
using namespace std;

//在.cpp文件中:
//1.添加.h头文件
//2.只保留所有实现，
//同时在函数名称前加作用域如：Point::表示该函数是Point作用域下的成员函数

void Point::setX(float x) {
	m_X = x;
}
float Point::getX() {
	return m_X;
}
void Point::setY(float y) {
	m_Y = y;
}
float Point::getY() {
	return m_Y;
}
float Point::distance(Point& p) {
	return (m_X - p.getX()) * (m_X - p.getX()) + (m_Y - p.getY()) * (m_Y - p.getY());
}
```

3.创建"circle.h"头文件，因为Circle类中要用到Point类，因此在代码头要引用"point.h"头文件

```c++
#pragma once
#include <iostream>
#include "point.h"		//要在一个类中调用另一个类，只需要在头文件中加入该类的头文件
using namespace std;

class Circle
{
public:
	void setR(float r);
	float getR();
	void setCenter(Point& p);
	Point getCenter();

	void locationRelat(Point& p);
private:
	Point m_Center;
	float m_R;
};
```

4.创建"circle.cpp"源文件

```c++
#pragma once
#include <iostream>
#include "circle.h"
using namespace std;


void Circle::setR(float r) {
	m_R = r;
}
float Circle::getR() {
	return m_R;
}
void Circle::setCenter(Point& p) {
	m_Center = p;
}
Point Circle::getCenter() {

	return m_Center;
}

void Circle::locationRelat(Point& p) {
	if (m_Center.distance(p) > m_R * m_R) {
		cout << "点在圆外" << endl;
		return;
	}
	else if (m_Center.distance(p) == m_R * m_R) {
		cout << "点在圆上" << endl;
		return;
	}
	cout << "点在圆内" << endl;
	return;
}
```

5.创建“main.cpp”主源文件，并在代码头引用"point.h"和"circle.h"头文件，以调用Point类和Circle类

```c++
#include <iostream>
#include<string>
#include"point.h"
#include"circle.h"
using namespace std;


int main() {

	Circle c;
	Point center;
	center.setX(0);
	center.setY(0);
	c.setCenter(center);
	c.setR(1);

	Point p;
	p.setX(1);
	p.setY(1);

	c.locationRelat(p);

	return 0;
}
```

### 4.2 对象的初始化和清理

* 生活中我们买的电子产品都会有出厂设置，在某一天不用的时候也会删除一些自己的信息数据保证安全
* C++中的面向对象来源于生活，每个对象也都会有初始设置以及对象销毁前的清理数据的设置



#### 4.2.1 构造函数和析构函数

对象的**初始化和清理**也是两个非常重要的安全问题

​		一个对象或者变量没有初始状态，对其使用后果是未知的

​		同样，使用完一个对象或变量，没有及时清理，也会造成一定的安全问题

C++利用了**构造函数**和**析构函数**解决上述问题，这两个函数将会被编译器自动调用，完成对象初始化和清理工作。

对象的初始化和清理工作是编译器强制要求我们做的事情，因此如果**我们不要提供构造和析构，编译器会提供，编译器提供的构造函数和析构函数是空实现。**



**构造函数语法**：`类名(){}`

1.构造函数没有返回值也不写void

2.构造函数名称与类名必须相同

3.构造函数可以有参数，因此可以发生重载

4.程序在创建对象时会自动调用构造，无需手动调用，而且只会调用一次

**析构函数语法**: `~类名(){}`

1.构造函数没有返回值也不写void

2.构造函数名称与类名必须相同,在名称前

3.析构函数不可以有参数，因此不能发生重载

4.程序在对象销毁前会自动调用析构，无需手动弄调用，而且只会调用一次

```c++
#include <iostream>
using namespace std;

//对象的初始化和清理
//1.构造函数 进行初始化操作

class Person
{
public:

	//构造函数
	Person() {
		cout << "构造函数" << endl;
	}
	//析构函数
	~Person() {
		cout << "析构函数" << endl;
	}

private:
};


void test01() {
	//构造函数在对象创建时会自动调用
	Person p;
	cout << 1 << endl;
}
int main() {

	test01();
	//析构函数在对象销毁时会自动调用，test01创建在栈取，代码行结束后会销毁其中的内容
	cout << 2 << endl;
	
	Person p;
	cout << 3 << endl; 
	system("pause");
	return 0;
}
```

#### 4.2.2 构造函数的分类和调用

两种分类方式：

​		按参数分：有参构造和无参构造

​		按类型分：普通构造和拷贝构造

三种调用方式：

​		括号法

​		显示法

​		隐式转换法



**示例**：

```c++
#include<iostream>
#include<string>
using namespace std;


// 1.构造函数的分类及调用
//分类
//按照参数分类    无参构造（默认构造）  和  有参构造


class Person {
public:
	
	//构造函数
	Person() {
		cout << "Person的无参构造函数调用" << endl;
	}
	Person(int a) {
		age = a;
		cout << "Person的有参构造函数调用" << endl;
	}

	//拷贝构造函数
	Person(const Person &p) {
		//将传入的对象身上所有的属性拷贝到要构造的对象身上
		age = p.age;
		cout << "Person的拷贝构造函数调用" << endl;
	}

	~Person() {
		cout << "Person的析构函数调用" << endl;
	}

	int age;
};

int main() {

	//调用构造函数的方法
	//括号法
	Person p1;//调用无参构造
	Person p2(10);//调用有参构造
	Person p3(p2);//调用拷贝构造
	//注意事项：
	//调用无参构造（默认构造）时，不要加( );
	Person p10();
	//上面代码不运行，因为编译器会认为是一个函数的声明，不会认为在创建对象。
	


	//显示法
	Person p4;//调用无参构造
	Person p5 = Person(10);//调用有参构造
	Person P6 = Person(p5);//调用拷贝构造
	//分析，在显示法中：
	Person(10);//为匿名对象， 特点：在当前行执行结束后，系统会自动销毁该匿名对象
	//注意事项2：
	//不要利用拷贝构造函数初始化匿名对象，如：
	//Person(p5);   编译器会认为Person(p3)==Person p3; 对象的声明，重定义了

	//隐式转换法 
	Person p7 = 10;//调用有参构造   相当于 写了 Person p7 = Person(10);
	Person p8 = p7;//调用拷贝构造
	system("pause");

	return 0;
}
```

#### 4.2.3 拷贝构造函数调用时机

C++ 中拷贝构造函数调用时机通常有三种情况：

* 使用一个已经创建完毕的对象来初始化一个新对象；
* 值传递的方式给函数参数传值
* 以值传递方式返回局部对象

```c++
#include<iostream>
#include<string>
using namespace std;

class Person {
public:
	Person() {
		age = 10;
		name = "张三";
		cout << "无参构造" << endl;
	}
	Person(int a,string n) {
		age = a;
		name = n;
		cout << "有参构造" << endl;
	}
	Person(const Person& p) {
		age = p.age;
		name =  p.name;
		cout << "拷贝构造" << endl;
	}
	~Person() {
		cout << "析构函数" << endl;
	}

	string getName() {
		return name;
	}
private:
	int age;
	string name;

};

//使用一个已经创建完毕的对象来初始化一个新对象
void test01() {
	Person p1;
	Person p2(p1);
}

//值传递的方式给函数传值
void doWork(Person p_0) {
	
}
void test02() {
	Person p;
	doWork(p);//将创建好的p对象通过值传递拷贝给doWork里的p_0对象
}

//值方式返回局部变量
Person doWork2() {
	Person p2(10, "小王");
	return p2;
}

int main() {


	//test01();
	//test02();
	Person p3 = doWork2(); //通过拷贝构造将doWork2()的返回值p2对象拷贝给P3
	//在C++11 优化过了，此时不会进行拷贝构造，而是会把地址传递给p3
	
	system("pause");

	return 0;
}
```

####  4.2.4 构造函数调用的规则

默认情况下,c++编译器至少给一个类添加以下三个函数：

* 默认构造函数(无参，函数体为空)
* 默认析构函数(无参，函数体为空)
* 默认拷贝构造函数，对对象的属性进行值的拷贝



构造函数调用规则如下：

* 如果用户定义有参构造函数，c++不会再提供无参构造，但是会提供默认拷贝构造
* 如果用户定义拷贝构造函数，C++不会再提供其他构造函数



#### 4.2.5 *深拷贝与浅拷贝

深拷贝与浅拷贝是面试经典问题，也是常见的一个坑

浅拷贝：简单的赋值拷贝操作

深拷贝：在堆区重新申请空间，进行拷贝操作

*ps：析构函数存在的意义就是将堆区开辟的数据做释放操作（堆区数据在整个程序关闭之前不会自动释放）*

**浅拷贝带来的问题：堆区的内存重复释放** 两个m_Height都指向同一片地址空间

![image-20230722144713792](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230722144713792.png)

解决办法：深拷贝。重新开辟一片堆区保存数据

```c++
#include<iostream>
#include<string>
using namespace std;

class Person {
public:
	Person() {
		age = 10;
		name = "张三";
		cout << "无参构造" << endl;
	}
	Person(int a,int h,string n) {
		age = a;
		height = new int(h);//在堆区开辟一片空间，并用指针指向他，保存对象的身高信息。
		name = n;
		cout << "有参构造" << endl;
	}

	//自己实现拷贝构造函数，解决浅拷贝带来的问题
	Person(const Person& p) {
			age = p.age;
			name =  p.name;
			// height = p.height;编译器默认实现，会带来浅拷贝问题。
			//深拷贝对于堆区的数据做的改动，重新开辟一片堆区内存，保存堆区数据
			height = new int(*p.height);
			cout << "拷贝构造" << endl;
	}

	~Person() {
		//析构代码，将堆区开辟的数据做释放操作
		if (height != NULL) {
			delete height;
			height = NULL;
		}
		cout << "析构函数" << endl;
	}


	int age;
	int* height;
	string name;

};

void test01() {
	Person p1(10,160,"小明");
	cout << "p1的姓名为:" << p1.name <<"   身高为:"<< *p1.height << endl;
	Person p2(p1);
	cout << "p2的姓名为:" << p2.name << "   身高为:" << *p2.height << endl;
}


int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结**：如果属性有在堆区开辟的，一定要自定义深拷贝构造函数，防止浅拷贝带来的问题。



#### 4.2.6 初始化列表

**作用**：C++提供了初始化列表语法，用来初始化属性

**语法**：`构造函数():属性1(值1),属性2(值2)...{}`

```c++
#include<iostream>
#include<string>
using namespace std;

class Person {
public:
	int m_A;
	int m_B;
	int m_C;

	//传统方式赋初值
	/*
	Person(int a, int b, int c) {
		m_A = a;
		m_B = b;
		m_C = c;
	}
	*/

	/*
	//初始化列表赋初值(固定初值)
	Person() :m_A(10), m_B(20), m_C(30) {
		
	}
	*/
	//初始化列表赋初值
	Person(int a,int b,int c) :m_A(a), m_B(b), m_C(c) {

	}
};

void test01() {
	//传统方式
	//Person p1(10, 20, 30);
	//初始化列表赋初值(a,b,c写死了)
	//Person p2;

	//初始化列表赋初值（不写死版）
	Person p3(10, 20, 30);
	cout << "m_C" << p3.m_C << endl;
}

int main() {

	test01();
	system("pause");

	return 0;
}
```

*ps:这么做的好处是减少机器开销*

#### 4.2.7 其他类的对象作为类成员

c++中类的成员可以是另一个类的对象，我们称该成员为**对象成员**(和结构体中可以定义另一个结构体的变量类似)

**语法**

```c++
class A{}
class B{
    A a;
}
```

B类中有对象A作为成员，A为对象成员



**问题**：当B对象创建时，A与B的构造和析构的顺序是谁先谁后？析构时呢？

```c++
#include<iostream>
#include<string>
using namespace std;

class Phone {
public:
	string pinpai;
	string xinghao;
	float* price;

	Phone() :pinpai("小米"), xinghao("11pro") {
		price = new float(2999.99);
		cout << "Phone的构造函数" << endl;
	}

	Phone(const Phone& p):pinpai("小米"),xinghao("11pro") {
		price = new float(*p.price);
		cout << "Phone的有参数构造函数" << endl;
	}

	~Phone() {
		if (price != NULL) {
			delete price;
			float* price = NULL;
		}
		cout << "Phone的析构函数" << endl;
	}
};

class Person {
public:
	string name;
	Phone phone;
	Person(string n,Phone p) :name(n), phone(p) {
		cout << "Person的构造函数" << endl;
	}
	~Person() {
		cout << "Person的析构函数" << endl;
	}
};

//看看成员对象他们谁先创建，谁先销毁
void test01() {
	Phone phone1;
	Person("小秦",phone1);
}
int main() {

	test01();
	system("pause");

	return 0;
}
```

**总结**:

当其他类对象作为本类成员，

构造先构造其他类对象，再构造自身对象。

析构先析构其自身类的对象，再析构其他类对象。（析构的顺序与构造相反）

#### 4.2.8 静态成员

静态成员就是在成员变量或成员函数前加上关键字static，称为静态成员

静态成员变量分为：

* 静态成员变量：
  * 所有对象共享同一份数据（同一个该属性的值）
  * 在编译阶段分配内存（全局区）
  * 类内声明，类外初始化（必须有个初始值）
  * 静态成员变量不属于任何对象，因此其拥有两种访问方式：
    * **`类名::静态成员变量;`**和`对象名.静态成员变量;`
  * 静态成员变量也是有访问权限的

```c++
#include <iostream>
#include <string>

using namespace std;

class Person {
public:
	//所有变量都共享同一份数据
	//编译阶段就分配内存
	//类内声明，类外初始化
	static int m_A;
private:
	static int m_B;
};

//必须有初始化值，Person::表示是Person作用域下的m_A
int Person::m_A = 10;
int Person::m_B = 20;

void test01() {
	Person p;
	cout << p.m_A << endl;

	Person p2;
	p2.m_A = 100;
	//所有变量都共享同一份数据,P2修改值，P1中的值也发生改变
	cout << p.m_A << endl;

	cout << Person::m_A << endl;
	//cout << Person::m_B << endl;报错，私有静态成员变量不可以类外访问（但是类外初始化）
}


int main() {
	
	test01();
	return 0;
}
```



* 静态成员函数：
  * 所有对象共享同一个函数
  * 静态成员函数只能访问静态成员变量
    * 原因：静态成员函数在程序中只有一份，而非静态成员变量每个对象都不一样，有很多份，静态成员函数不知道该访问哪一份变量。
  * 静态成员方法(静态成员函数)不属于任何对象，因此也有两种访问方式：
    * **`类名::静态成员函数()`**和`对象名.静态成员函数()`
  * 静态成员函数也是有访问权限的

```c++
#include <iostream>
#include <string>

using namespace std;

class Person {
public:
	static int m_A;

	int m_B;

	static void func() {
		//静态成员函数能访问静态成员变量
		m_A = 100;

		//m_B = 10;报错，静态成员函数不能访问非静态成员变量
		//原因：静态成员函数在程序中只有一份，而非静态成员变量每个对象都不一样，有很多份，静态成员函数不知道该访问哪一份变量。
		cout << "静态成员函数的调用" << endl;
	}

private:
	//静态成员函数也是有访问权限的
	static void func2() {
	}
};

int Person::m_A = 10;
void test01() {
	Person p;
	 
	//静态成员函数的两种调用方式
	p.func();
	Person::func();
}
int main() {

	return 0;
}
```

### 4.3 C++对象模型和this指针

#### 4.3.1成员变量和成员函数分开存储

在c++中，类内的成员变量和成员函数是分开存储的

只有非静态成员变量才属于类的对象

```c++
#include <iostream>
using namespace std;

//成员变量和成员函数分开存储
class Person
{
	int m_A;//非静态成员变量，属于类的对象上（占用相应大小的地址空间）
	static int m_B;//静态成员变量，不属于类的对象（不占用相应大小的地址空间）
	void func();//非静态成员函数，不属于类的对象
	static void func2();//静态成员函数，不属于类的对象
};


void test01() {

	Person p;
	//空对象占用内存空间为：1
	//c++编译器会给每个空对象也分配一个字节空间，是为了区分空对象占内存的位置
	//为了每个空对象都有一个独一无二的地址空间
}

void test02() {
	Person p;
	cout << "size of p = " << sizeof(p) << endl;
}
int main() {

	test02();
	 
	system("pause");
	return 0;
}
```

#### 4.3.2 this指针概念

通过上节，C++中成员变量和成员函数是分开存储的

每个非静态成员函数只有一份函数实例，多个对象会共用一块代码

问题：这一块代码是如何区分是哪个对象调用自己的呢？



C++通过提供特殊的对象指针**this指针**，解决上述问题。利用**this指针指向被调用的成员函数所属的对象**



this指针是隐含在每一个非静态成员函数内的一种指针

this指针不需要定义，直接使用即可



this指针的用途：

* 当形参和成员变量同名时，可以用this指针来区分
* 在类的非静态成员函数中**返回对象本身**，可以使用**return *this**

```c++
#include <iostream>
using namespace std;

class Person {
public:
	Person(int age) {
		//this指针指向被调用的成员函数所属的对象（谁调用它就指向谁）
		this->age = age;//解决同名问题
	}


	//引用传递：（不能用值传递）
	//不加引用的话，返回值会调用拷贝函数，创建新的对象拷贝P2对象的属性进行后续运算。
	Person& PersonAddAge(Person& p) {
		age += p.age;
		//this是指向p2的指针，而*this是这个指针指向的p2对象本体
		return *this;//返回这个指针指向的Person类型的数p1
	}
	int age;
};


void test01() {
	Person p(18);
	cout << "年龄:" <<p.age<< endl;
}

void test02() {
	Person p1(10);
	Person p2(10);
	//链式编程
	p2.PersonAddAge(p1).PersonAddAge(p1);
	cout << "年龄:" << p2.age << endl;
	cout << "年龄:" << p2.age << endl;
	

}
int main() {

	test02();
	system("pause");
	return 0;
}
```

#### 4.3.3 空指针访问成员函数

c++中空指针也是可以调用成员函数，但是也要注意到有没有用到this指针

如果用到this指针，则要加以判断保证代码的健壮性

```c++
#include <iostream>
using namespace std;

class Person {
public:
	void showClass() {
		cout << "Class" << endl;
	}
	void showAGE() {
		//提高健壮性
		if (this==NULL) {
			return;
		}

		//报错的原因是因为传入的指针是NULL
		cout << age << endl;//非静态成员变量前默认有this->age
	}
	int age;
};

void test01() {
	Person* p = NULL;
	p->showClass();
	//p->showAGE();报错，该函数体内有指向该对象的this指针，而我们创建的p指针指向NULL，是一个空对象
}
int main() {

	test01();
	system("pause");
	return 0;
}
```

#### 4.3.4 const修饰成员函数

**常函数**：

* 成员函数后加const称之为**常函数**(注意const修饰的位置)
  * 如：`void func() const{}`
* 常函数内不可修改成员属性
* 成员属性声明时加关键字mutable后，在常函数中依然可以修改

**常对象**：

* 声明对象前加const称该对象为常对象
* 常对象只能调用常函数 

```c++
#include <iostream>
using namespace std;

class Person {
public:

	//this指针的本质是指针常量 指针的指向是不可以修改的，加const之后变为了常量指针常量
	//在成员函数后面加const,修饰的是this指针，让指针指向的值也不能修改
	void showPerson() const {
		//m_A = 100;
		//等价于  this->m_A = 100;

	}
	void func() {
		
	}

	int m_A;
	mutable int m_B;//关键字 mutable 。特殊变量，即使在常函数中，也可以修改这个值
};

void test02() {
	const Person p;//在对象前加const,变为常对象
	//p.m_A = 100;常对象下不能修改变量的值
	p.m_B = 100;//m_B是特殊值，在常对象下也可以修改
	p.showPerson();//常对象只能调用常函数
	// p.func();//报错，常对象不可以调用普通的成员函数，因为普通成员函数可以修改属性
	
}
int main() {

	system("pause");
	return 0;
}
```

### 4.4 友元

生活中你家有客厅(Public),有你的卧室(Private)

客厅所有客人都可以进去，但卧室是私有的，也就是只有你能进去

但是你可以允许你的好朋友进去



在程序里，有些私有属性，也想让类外的一些特殊的函数或者类进行访问，就需要用到友元技术



友元的目的就是让一个函数或者类，访问另一个类中私有成员

友元的关键字为 friend



友元的三种实现：

* 全局函数做友元
* 类做友元
* 成员函数做友元

#### 4.4.1 全局函数做友元

```c++
#include <iostream>
using namespace std;

class Building {
    /********************
	//利用关键字friend告诉编译器goodGay 全局函数是Building好朋友，可以访问Building中私有成员
	********************/
	friend void goodGay(Building* building);
public:
	string m_SittingRoom;//客厅
private:
	string m_BedRoom;

public:
	Building() {
		m_BedRoom = "卧室";
		m_SittingRoom = "客厅";
	}
};

//全局函数
void goodGay(Building *building){
	cout << "好基友全局函数 正在访问:" << building->m_SittingRoom << endl;
	// cout << "好基友全局函数 正在访问:" << building->m_BedRoom << endl;//私有的。普通成员函数不能访问私有成员变量
	cout << "好基友全局函数 正在访问:" << building->m_BedRoom << endl;//
}

void test01() {
	Building building;
	goodGay(&building);
}

int main() {

	test01();
	system("pause");
	return 0;
}
```

#### 4.4.2 类做友元

```c++
#include <iostream>
#include <string>;

using namespace std;

class Building{
    //用关键字friend告诉编译器 Gay类是Building类的好朋友，可以访问其私有成员
    ******************************************
	friend class Gay;
	******************************************
public:
	string m_SettingRoom;

	Building() {
		m_SettingRoom = "客厅";
		m_BedRoom = "卧室";
	}

private:
	string m_BedRoom;
};

class Gay {
public:
	Building* building;
	

	Gay(){
		building = new Building;//在堆区开辟空间存储Building对象，并用building指针指向它。
	}

	void visit() {
		cout << "好基友正在访问:" << building->m_SettingRoom << endl;
		//cout << "好基友正在访问:" << building->m_BedRoom << endl;//报错，私有成员变量类外不可访问
		cout << "好基友正在访问:" << building->m_BedRoom << endl;//在Building类里面用friend关键字标明Gay类即可访问
	}
};


void test01(){
	Building b1;
	Gay gay;
	gay.visit();
}

int main() {

	test01();
	return 0;
}
```

#### 4.4.3 成员函数做友元

```c++
#include <iostream>
#include <string>;

using namespace std;

class Building;
class Gay {
public:
	Gay();

	//类中成员函数做友元的使用场景：
	void visit();//使visit函数可以访问Building中的私有成员
	//void visit2();//使visit2函数不可以访问Building中的私有成员

	Building* building;
};


class Building {
    **********************************************
	friend void Gay::visit();
    **********************************************
public:
	string m_SittingRoom;

private:
	string m_BedRoom;
public:
	Building() {
		m_SittingRoom = "客厅";
		m_BedRoom = "卧室";
	}
};

void test() {
	Gay gg;
	gg.visit();
}


int main() {
	test();
	return 0;
}


void Gay::visit() {
	cout << "好基友正在访问：" << building->m_SittingRoom << endl;//非私有成员变量正常访问
	//cout << "好基友正在访问：" << building->m_BedRoom << endl;//报错，私有成员变量不允许类外访问
	cout << "好基友正在访问：" << building->m_BedRoom << endl;//利用关键字friend即可访问
}
/*
void Gay::visit2() {
	cout << "好基友正在访问：" << building->m_SittingRoom << endl;//非私有成员变量正常访问
	//cout << "好基友正在访问：" << building->m_BedRoom << endl;//报错，私有成员变量不允许类外访问
	cout << "好基友正在访问：" << building->m_BedRoom << endl;
}

*/
Gay::Gay() {
	building = new Building;
}

```

### 4.5 运算符重载

运算符重载概念：对于已有的运算符重新进行定义，赋予其另一种功能，以适应不同的数据类型

对于内置数据类型，编译器知道如何进行运算：如int ,float,bool等

#### 4.5.1 加号运算符重载

作用：实现两个自定义数据类型相加的运算

之前的做法：

```c++
#include <iostream>
#include <string>;

using namespace std;

//自己实现两个对象中各变量相加，返回新的对象

class Person {
public:
	int m_A;
	int m_B;

	Person(int a, int b): m_A(a),m_B(b){

	}
	//定义一个add成员函数，并返回新的对象
	Person&  add(Person& p) {
		int a_add = m_A + p.m_A;
		int b_add = m_B + p.m_B;
		Person p3(a_add, b_add);
		return p3;
	}

};

void test() {
	Person p1(10, 20);
	Person p2(5, 5);
	Person p3 = p2.add(p1);
	cout << p3.m_A << p3.m_B << endl;
}

int main() {
	test();

	return 0; 
}
```

编译器给这种**自定义的运算符函数**起了个**通用名称**：**operator操作符(){}**如 operator+();

本例中：		Person& add(Person& p ){}

**可以写成：    Person& operator+(Person& p){}**

因此调用:	   Person p3 = p2.add(p1)；

可以写成:       Person p3 = p2.operator+(p1);

**可以写成：    Person p3 = p2+p1;**

最终形态：p4

```c++
#include <iostream>
#include <string>;

using namespace std;

//自己实现两个对象中各变量相加，返回新的对象

class Person {
public:
	int m_A;
	int m_B;

	Person(int a, int b): m_A(a),m_B(b){

	}


	//通过成员函数重载+号实现（全局函数照样可以重载+号）
	Person&  operator+(Person& p) {
		int a_add = m_A + p.m_A;
		int b_add = m_B + p.m_B;
		Person p3(a_add, b_add);
		return p3;
	}

};


void test() {
	Person p1(10, 20);
	Person p2(5, 5);
	Person p3 = p2.operator+(p1);
	Person p4 = p1 + p2;//最终形态
	cout << p3.m_A << p3.m_B << endl;
	cout << p4.m_A << p4.m_B << endl;
}

int main() {
	test();

	return 0;
}
```



#### 4.5.2 左移运算符重载

作用：可以**输出自定义数据类型**

```c++
#include <iostream>
#include <string>

using namespace std;

class Person {
	friend ostream& operator<<(ostream& cout, Person& p);
public:


	Person(int a, int b) :m_A(a), m_B(b) {
	}
	//利用成员函数重载 左移运算符 p.operator<<(cout)  简化版本 p<<cout
	//错误，不能利用成员函数重载<<运算符，因为无法实现cout在左侧

private:
	int m_A;
	int m_B;
};


//只能利用全局函数重载左移运算符
//cout本质是标准输出流ostream类的一个对象,该对象只能有一个，因此调用时要加引用，保证不创建副本
ostream& operator<<(ostream& cout, Person& p) //本质 Operator<<(cout,p) 简化cout <<p;
{
	cout << p.m_A << p.m_B;
	return cout;
}


void test01() {
	Person p(10, 20);
	//cout << p << endl; 报错，对象不能直接输出
	//重载左移运算符后
	cout << p;
	cout << p << endl;
	//第一个左移运算符，重载的是自定义的左移运算符，第二个左移运算符，重载的是系统定义的左移运算符。要注意返回值是cout。
}

int main() {

	test01();
	return 0;
}
```

总结：左移运算符配合友元(自定义数据类型一般是私有)可以实现输出自定义数据类型 

#### 4.5.3 递增运算符重载

作用：通过重载自增运算符++，实现自己的整形数据



```c++
递增运算符重载++
int a = 10;
cout << ++a <<endl; //11
int b = 10;
cout << b++ <<endl; //10
```



注：前置++ 和后置++的区别：

* 前置++返回引用，后置++返回值
* 后置++需要在参数列表中加**占位符int**以和前置++区分

```c++
#include <iostream>
#include <string>

using namespace std;

class MyInteger {
	friend ostream& operator<<(ostream& cout, MyInteger myint);
public:
	MyInteger() {
		m_Num = 0;
	}

	//重载前置++运算符  返回引用是为了对同一个对象进行运算
	MyInteger& operator++() {
		++m_Num;
		return *this;
	}

	//重载后置++运算符 int代表占位参数，用于区分前置和后置递增
	//注意后置递增返回的是值，因为局部对象temp不能作为引用返回
	MyInteger operator++(int) {
		//先记录当前结果
		MyInteger temp = *this;
			
		//后递增
		m_Num++;
		//再讲记录的结果返回
		return temp;
	}
private:
	int m_Num;
};

ostream& operator<<(ostream& cout,MyInteger myint){
	
	cout << myint.m_Num;
	return cout;
}

void test01() {
	MyInteger myint;
	cout << myint++ << endl;
}

int main() {

	test01();
	return 0;
}
```

练习：自减

```c++
#include <iostream>
#include <string>
using namespace std;

class MyInt {
public:
	int m_a;
	MyInt() {
		m_a = 1;
	}
	//前置自减
	MyInt& operator--() {
		--m_a;
		return *this;
	}
	//后置自减
	MyInt operator--(int) {
		MyInt temp = *this;
		m_a--;
		return temp;
	}
};
ostream& operator<<(ostream& cout,MyInt mi) {
	cout << mi.m_a;
	return cout;
}

void test01() {
	MyInt mi;
	cout << --mi << endl;
	cout << mi-- << endl;
	cout << mi << endl;
}

int main() {
	test01();
	return 0;
}
```



#### 4.5.4 赋值运算符重载

C++编译器至少给一个类添加四个函数

* 1.默认构造函数
* 2.默认析构函数
* 3.默认拷贝构造函数
* 4.赋值运算符operator= 对属性进行值拷贝（默认浅拷贝，因此需要重载赋值运算符提供深拷贝）

如果类中有属性指向堆区，做赋值操作时也会出现深浅拷贝的问题

```c++
#include <iostream>
#include <string>

using namespace std;

class Person {
	//friend ostream& operator<<(ostream& cout, Person p);
public:
	int* m_Age;

	Person(int age) {
		m_Age = new int(age);
	}
	~Person() {
		if (m_Age != NULL) {
			delete m_Age;
			m_Age = NULL;
		}
	}

	//该返回值类型是为了链式操作
    //重载 赋值运算符   提供深拷贝
	Person& operator=(Person& p) {
		if (m_Age != NULL) {
			delete m_Age;
			m_Age = NULL;
		}
		m_Age = new int(*p.m_Age);
		return *this;
	}

};

ostream& operator<<(ostream& cout,Person& p) {
	cout << *p.m_Age;
	return cout;
}


void test01() {
	Person p1(18);
	cout << p1 << endl;
	Person p2(20);
	cout << p2 << endl;
	Person p3(10);
	//p2.operator=(p1);//赋值操作
	p3 = p2 = p1;//赋值操作
	cout << p3 << endl;
}	
int main() {

	test01();
	return 0;
}
```

#### 4.5.5 关系运算符重载

作用：重载关系运算符，可以让两个自定义类型对象进行比对操作

```c++
#include <iostream>
#include <string>

using namespace std;

class Person {
public:
	int age;
	string name;

	Person() {
		age = 18;
		name = "张三";
	}
	Person(int a, string n) :age(a), name(n) {
	}

	bool operator==(Person& p) {
		if (name == p.name && age == p.age) {
			return true;
		}

		return false;
	}
	bool operator!=(Person& p) {
		if (name != p.name || age != p.age) {
			return true;
		}
		return false;
	}
};

void test01() {
	Person p1;
	Person p2(18,"张骞");
	if (p1 == p2) {
		cout << "是一个人" << endl;
		return;
	}
	cout << "不是一个人" << endl;
}
void test02() {
	Person p1;
	Person p2(18, "张骞");
	if (p1 != p2) {
		cout << "不是一个人" << endl;
		return;
	}
	cout << "是一个人" << endl;
}
int main() {
	test01();
	test02();
	return 0;
}
```

#### 4.5.6 函数调用运算符重载（仿函数  stl常用）

* 函数调用运算符()也可以发生重载
* 由于重载后的使用方式非常像函数的调用，因此称为仿函数
* 仿函数没有固定写法，很灵活

```c++
#include <iostream>
#include <string>

using namespace std;

//函数调用运算符重载
class MyPrint {
public:
	void operator()(string test) {
		cout << test << endl;
	}
};

class MyAdd {
public:
	int operator()(int a, int b) {
		return a + b;
	}

};
void test01(){
	MyPrint myprint;
	myprint("hello world");//由于使用起来非常类似函数调用，因此称为仿函数
}

void test02() {
	MyAdd myadd;
	cout << myadd(10, 20) << endl;
	cout << MyAdd()(100, 100) << endl;
	//其中	MyAdd()创建了一个匿名对象(当前行执行完自动释放)，并重载了()仿函数，因此称为匿名函数对象
}
int main() {
	test01();
	test02();
	return 0;
}
```





### 4.6  继承

**继承是面向对象三大特性之一**

有些类与类之间存在特殊的关系

如:

​	      	动物

​         猫			   狗

布偶猫   缅因猫    ........

父类有一些子类共有的功能。可以用到继承。

```c++
#include <iostream>
#include <string>

using namespace std;

//继承实现页面
//公共页面类
class BasePage {
public:
	void head() {
		cout << "头部信息" << endl;
	}
	void down(){
		cout << "底部信息" << endl;
	}
	void left() {
		cout << "左侧信息" << endl;
	}
	void right(){
		cout << "右侧信息" << endl;
	}
};

//java页面继承公共页面类中的信息
class Java :public BasePage {
public:
	void content() {
		cout << "java学科视频" << endl;
	}
};

class CPP :public BasePage {
public:
	void content() {
		cout << "CPP学科视频" << endl;
	}
};
int main() {
	CPP c1;
	c1.content();
	c1.head();
	c1.down();

	return 0;
}
```

**继承的好处：减少重复代码**

**语法**：`class 子类 : 继承方式 父类`

子类也称为派生类 父类也称为基类

#### 4.6.2 继承方式

**语法**：`class 子类 : 继承方式 父类`

**继承方式**一共有三种：

* 公共继承
* 保护继承
* 私有继承

![image-20230725235859374](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230725235859374.png)

```c++
#include <iostream>
#include <string>

using namespace std;
//继承方式：公共继承，保护继承，私有继承
class Futher {
public:
	int m_A;
protected:
	int m_B;
private:
	int m_C;
};

//公共继承(不改变父类的权限)
class Son1 :public Futher {
public:
	void func() {
		m_A = 10;//父类中的公共权限成员，到子类中仍然是公共权限
		m_B = 10;//父类中的保护权限成员，到子类中仍然是保护权限
		m_C = 10;//父类中的私有权限成员 子类访问不到
	}
};
//保护继承（把父类除私有权限的成员变为保护权限）
class Son2 :protected Futher {
public:
	void func() {
		m_A = 10;//父类中的公共权限成员，到子类中变为保护权限
		m_B = 10;//父类中的保护权限成员，到子类中仍然是保护权限
		m_C = 10;//父类中的私有权限成员 子类访问不到
	}
};
//私有继承（把父类所有成员变为私有权限）
class Son3 :private Futher {
public:
	void func() {
		m_A = 10;//父类中的公共权限成员，到子类中变为私有权限
		m_B = 10;//父类中的保护权限成员，到子类中变为私有权限
		m_C = 10;//父类中的私有权限成员，子类访问不到
	}

};

int main() {
	

	Son1 son1;
	son1.m_A;//可以访问
	son1.m_B;//保护权限，类外不可以访问
	son1.m_C;//父类私有权限，子类根本不可以访问

	Son2 son2;
	son2.m_A;//保护权限，类外不可以访问
	son2.m_B;//保护权限，类外不可以访问
	son2.m_C;//父类私有权限，子类根本不可以访问


	Son3 son3;
	son3.m_A;//私有权限，类外不可以访问
	son3.m_B;//私有权限，类外不可以访问
	son3.m_C;//父类私有权限，子类根本不可以访问

	
	return 0;
}
```

#### 4.6.3 继承中的对象模型

**问题**：从父类继承过来的成员，哪些属于子类对象中？

**示例**：

```c++
#include <iostream>
#include <string>
using namespace std;

class Base {
public:
	int m_A;
protected:
	int m_B;
private:
	int m_C;
};

class Son :public Base {
public:
	int m_D;
};
void test01() {
	//16
	//父类中所有非静态成员属性都会被子类继承下去
	//父类中私有成员属性是被编译器隐藏了，因此访问不到，但确实继承了
	cout << "size of Son = " << sizeof(Son) << endl;
}

int main() {
	test01();
	return 1;
}
```

![image-20230725235833774](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230725235833774.png)

利用开发人员命令提示工具查看对象模型

跳转盘符

跳转文件路径

查看明明

cl /d1 reportSingleClassLayout类名 文件名

#### 4.6.4 继承构造和析构顺序

子类继承父类后，当创建子类对象， 也会调用父类的构造函数

问题：父类和子类的构造和析构顺序是谁先谁后？

继承的构造函数和析构函数顺序如下：

构造：先构造父类，再构造子类

析构：先析构子类，再析构父类 

**示例**：

```c++
#include <iostream>
#include <string>
using namespace std;

class Base {
public:
	Base() {
		cout << "Base构造函数！" << endl;
	}
	~Base() {
		cout << "Base析构函数！" << endl;
	}
};

class Son :public Base {
public:
	Son() {
		cout << "Son构造函数！" << endl;
	}

	~Son() {
		cout << "Son析构函数！" << endl;
	}
};

void test() {
	Son s;
}
int main() {
	test();
	return 1;
}
```

#### 4.6.5 继承同名成员处理方式

问题：当子类与父类出现同名的成员，如何通过子类对象，访问到子类或父类同名中的数据呢？

* 访问子类同名成员，直接访问即可
* 访问父类同名成员。需要加作用域
* 如果子类中出现和父类同名的成员函数，子类的同名成员会隐藏掉父类中所有同名成员函数(包括各种重载)，只要名称相同就隐藏

```c++
#include <iostream>
#include <string>
using namespace std;

class Base {
public:
	Base() {
		m_A = 100;
	}
	void func() {
		cout << "父类同名函数" << endl;
	}
	void func(int) {
		cout << "父类同名函数重载" << endl;
	}
	int m_A;
};

class Son :public Base {
public:
	Son() {
		m_A = 10;
	}
	void func() {
		cout << "子类同名函数" << endl;
	}
	int m_A;
};


void test() {
	Son s;
	//子类中同名成员直接访问
	cout << "子类中的m_A:" << s.m_A << endl;
	//父类中同名成员加作用域即可
	cout << "父类中的m_A:" << s.Base::m_A << endl;
}
void test2() {
	Son s1;
	//如果子类中出现和父类同名的成员函数，子类的同名成员会隐藏掉父类中所有同名成员函数(包括各种重载)，只要名称相同就隐藏
	// 如果想访问到父类中被隐藏的同名成员函数，需要加作用域
	//s1.func(10);报错
	s1.Base::func(10);
}
int main() {
	test();
	test2();
	return 1;
}
```

#### 4.6.6 继承同名静态成员处理方式

问题：继承中同名的静态成员在子类对象上如何进行访问？

静态成员和非静态成员出现同名，处理方式一致。

* 访问子类同名成员，直接访问即可
* 访问父类同名成员。需要加作用域

```c++
class Base{
public:
    static int m_A;
    static func(){}
};
class Son{
public:
	static int m_A;
    static func(){}
}
Base::m_A = 10;
Son::m_A = 100;

//1.通过对象访问
//子类下的m_A
cout<<s.m_A<<endl;
//父类下的m_A
cout<<s.Base::m_A<<endl;

//2.通过类名访问
//子类下的m_A
cout<<Son::m_A<<endl;
//父类下的m_A(但是通过子类调用版)
cout<<Son::Base::m_A<<endl;
//第一个::代表通过类名的方式进行访问  第二个::代表访问父类作用域下

//静态成员函数
//通过对象
s.func();//子类
s.Base::func();//父类
//通过类名
Son::func();//子类
Son::Base::func();//父类

```

#### 4.6.7 多继承语法

c++允许**一个类继承多个父类**

语法:`class 子类:继承方式 父类1,继承方式 父类2`

多继承可能会引发父类中有同名成员出现，需要加作用域区分

**c++实际开发中不建议使用多继承**

#### 4.6.8 菱形继承

**菱形继承概念**：

​	两个派生类继承同一个基类

​    又有某个类同时继承两个派生类

​	这种继承被称为菱形继承，又叫钻石继承

**典型的菱形继承案例：**

![image-20230726000008326](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230726000008326.png)

**菱形继承问题：**

​	1.羊继承了动物的数据，驼也同样继承了动物的数据，当羊驼使用数据时，就会产生二义性

​	2.羊驼继承自动物的数据继承了两份，其实这份数据我们只需要一份即可。

问题案例：

​	普通继承的话会导致数据集成两份，造成空间浪费



![image-20230726002005151](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230726002005151.png)

解决办法：利用关键字virtual实现虚继承

```c++
#include <iostream>
#include <string>;

using namespace std;

class Animal {
public:
	int m_age;

};


//利用虚继承 解决菱形继承问题
// 继承之前 加上关键字virtual变为虚继承
// 此时基类Animal称为虚基类
//羊类
class Sheep :virtual public Animal {

};
class Tuo :virtual public Animal {

};

class YangTuo :public Sheep,public Tuo{
};

void test01() {
	YangTuo yt;
	//yt.m_Age = 18;//继承了两份m_age，需要明确是继承自谁的m_Age
	yt.Sheep::m_age = 18;
	yt.Tuo::m_age = 28;
	cout << "羊驼继承自羊的年龄：" << yt.Sheep::m_age << endl;
	cout << "羊驼继承自驼的年龄：" << yt.Tuo::m_age << endl;
	cout << yt.m_age << endl;
	//这份数据我们知道，只要有一份就可以，菱形继承导致数据有两份，造成资源浪费。
}
int main() {

	test01();
	return 0;
}
```

![image-20230726002712168](C:\Users\Windows11\AppData\Roaming\Typora\typora-user-images\image-20230726002712168.png)

**虚函数实现原理**：

​	羊驼类中继承羊类和驼类分别提供的虚基指针vnptr分别指向羊类和驼类的虚基类表vbtable，同时虚基类表中记录了虚基类的成员偏移地址，之后通过偏移地址即可找到共同的m_Age属性。（读不懂的话看图）

**总结**：

* 菱形继承带来的主要问题是子类继承了两份相同的数据，导致资源浪费并且毫无意义
* 利用虚继承(virtual)可以解决菱形继承的问题

### 4.7 多态

#### 4.7.1 多态的基本概念

多态是C++面向对象三大特性之一

多态分为两种：

* 静态多态：函数重载和运算符重载属于静态多态，复用函数名
* 动态多态：派生类和虚函数实现运行时多态

静态多态和动态多态的区别：

* 静态多态的函数地址早绑定 ——编译阶段确定函数地址
* 动态多态的函数地址晚绑定——运行阶段确定函数地址

案例：

```c++
#include <iostream>
#include <string>

using namespace std;


class Animal {
public:
	//virtual 虚函数
	virtual void speak() {
		cout << "动物在说话" << endl;
	}
};

class Cat : public Animal {
public:
	void speak(){
		cout << "小猫在说活" << endl;
	}
};

class Dog : public Animal {
public:
	void speak() {
		cout << "小狗在说活" << endl;
	}
};

//执行说话的函数
//地址早绑定 在编译阶段确定函数地址
//如果想执行让猫说话，那么这个函数的地址就不能提前绑定，需要在运行阶段进行绑定，地址晚绑定
void doSpeak(Animal& animal) {// Animal& animal = cat;//父类引用指向子类对象
	animal.speak();
}


//动态多态满足条件
//1.有继承关系
//2.子类重写父类虚函数    重写： 函数函返回值类型 函数名 参数列表 完全相同
//动态多态使用：
//父类指针或引用指向子类对象
void test01() {
	Cat cat;
	doSpeak(cat);//到底是谁在说话：动物在说活
				 //doSpeak()加入关键字virtual修饰后变成虚函数，小猫在说话
	Dog dog;
	doSpeak(dog);
}

int main() {
	
	test01();
	return 0;
}
```

动态多态满足条件
	1.有继承关系
	2.子类重写父类虚函数    重写： 函数函返回值类型 函数名 参数列表 完全相同
动态多态使用：
	父类指针或引用指向子类对象

重写：函数函返回值类型 函数名 参数列表 完全相同

原理：![6dfb5c57a106a7afc97d1f998b21e4b](C:\Users\WINDOW~1\AppData\Local\Temp\WeChat Files\6dfb5c57a106a7afc97d1f998b21e4b.jpg)

![4580e6faca189ba6b267a00687e609a](C:\Users\WINDOW~1\AppData\Local\Temp\WeChat Files\4580e6faca189ba6b267a00687e609a.jpg)

#### 4.7.2 多态案例——计算器类

案例描述：

分别利用普通写法和多态技术，设计实现两个操作数进行运算的计算器类

多态的优点：

* 代码组织结构清晰
* 可读性强
* 利于前期和后期的扩展和维护

```c++
#include <iostream>
#include <string>

using namespace std;

//普通写法
class Calculator {
public:
	int getResult(string oper) {
		if (oper == "+") {
			return m_Num1 + m_Num2;
		}
		else if (oper == "-") {
			return m_Num1 + m_Num2;
		}
		else if (oper == "*") {
			return m_Num1 + m_Num2;
		}
		//如果想扩展新的功能，需要修改源码
		//在真实的开发中 提倡 开闭原则
		//开闭原则：对扩展提供开放，对修改提供关闭
	}
	int m_Num1;
	int m_Num2;
};
//利用多态实现计算器
//实现计算器抽象类
class AbstractCalculator {
public:
	//虚函数，等待子类重写
	virtual int getResult() {
		return 0;
	}
	int m_A;
	int m_B;
};
class AddCalculator :public AbstractCalculator {
public:
	int getResult() {
		return m_A + m_B;
	}
};
class MulCalculator :public AbstractCalculator {
public:
	int getResult() {
		return m_A * m_B;
	}
};


void test01() {
	//创建计算器对象
	Calculator c;
	c.m_Num1 = 10;
	c.m_Num2 = 5;
	cout << c.getResult("+") << endl;
}

void test02() {
	//多态使用条件：
	//父类指针或者引用指向子类对象
	//乘法运算
	//在堆区中开辟一片空间创建一个乘法对象，并用父类指针abc指向他
	AbstractCalculator* abc = new MulCalculator;
	abc->m_A = 10;
	abc->m_B = 20;
	cout << abc->getResult() << endl;
	//用完记得销毁(销毁的是堆栈里的数据，抽象类指针abc还在)
	delete abc;

	abc = new AddCalculator;
	abc->m_A = 20;
	abc->m_B = 10;
	cout << abc->getResult() << endl;
	delete abc;
}

int main() {
	
	//test01();
	test02();
	return 0;
}
```

#### 4.7.3 纯虚函数与抽象类

在多态中，通常父类中的虚函数实现是毫无意义的，主要都是调用子类重写的内容

因此可以将虚函数改写为**纯虚函数**

语法：**`virtural 返回值类型 函数名(参数列表) = 0;`**

当类中有了纯虚函数，这个类也称为了**抽象类**

**抽象类特点**:

* 无法实例化对象
* 子类必须重写抽象类中的纯虚函数，否则也属于抽象类(否则无法实例化对象)

```c++
#include <iostream>
#include <string>

using namespace std;

//抽象类与纯虚函数
class Base {
public:
	//重写纯虚函数
	virtual void func() = 0;
};

class Son : public Base{
public:
	//重写纯虚函数func
	void func() {
		cout << "子类中的func" << endl;
	}
};


void test01() {
	//Base b; 报错，抽象类无法实例化对象
	//Base* b = new(Base); 报错，抽象类无法实例化对象

	Son s;//必须重写父类中的抽象类，否则无法实例化
	//多态：
	Base* base = new Son;
	base->func();

}

int main() {
	
	test01();
	return 0;
}
```

#### 4.7.3 多态案例二——制作饮品

**案例描述**：

制作饮品的大致流程为：煮水-冲泡-倒入杯中-加入辅料



利用多态技术实现本案例，提供抽象制作饮品基类，提供子类制作咖啡和茶叶

咖啡类：

	煮水-冲泡咖啡-倒入咖啡杯-加糖和牛奶

茶叶类：

	煮水-冲泡茶叶-倒入茶杯-加柠檬

```c++
#include <iostream>
#include <string>

using namespace std;

class Drink {
public:

	void shaoWater() {
		cout << "煮水" << endl;
	}


	virtual void chongPao() = 0;
	virtual void pull() = 0;
	virtual void addSomething() = 0;
	void makeDrink() {
		shaoWater();
		chongPao();
		pull();
		addSomething();
	}
};

class Coofe :public Drink{
	void chongPao() {
		cout << "冲泡咖啡" << endl;
	}
	void pull() {
		cout << "倒入咖啡杯中" << endl;
	}
	void addSomething() {
		cout << "加糖和牛奶" << endl;
	}
};

class Tee :public Drink {
	void chongPao() {
		cout << "冲泡茶叶" << endl;
	}
	void pull() {
		cout << "倒入茶杯中" << endl;
	}
	void addSomething() {
		cout << "加柠檬" << endl;
	}
};


void test01() {
	Drink* tee = new Tee;
	Drink* coofe = new Coofe;
	
	tee->makeDrink();
	cout << "==============================================" << endl;
	coofe->makeDrink();
	//makeDrink 一个接口调用出来是多种形态 这就是多态

	delete tee;
	delete coofe;
}
int main() {
	
	test01();
	return 0;
}
```

#### 4.7.5 虚析构和纯虚析构

多态使用时，如果子类中有属性开辟到堆区，那么父类指针在释放时无法调用到子类的析构代码

(父类指针无法释放子类对象)

解决办法：将父类中的析构函数改为**虚析构**或**纯虚析构**



虚析构和纯虚析构共性：

* 都可以解决父类指针释放子类对象
* 都需要有具体的函数实现

虚析构和纯虚析构区别：

* 如果是纯虚析构，该类属于抽象类，无法实例化对象

虚析构语法：

`virtual ~类名(){}`

纯虚析构语法

`virtual ~类名() = 0; `

``

示例：

```c++
#include <iostream>
#include <string>;

using namespace std;

class Animal {
public:
	Animal(){
		cout << "Animal构造函数" << endl;
	}
	//为了解决父类指针不能删除子类对象堆区数据的问题，引入   虚析构     关键字 virtual
	//virtual ~Animal() {
	//	cout << "Animal析构函数" << endl;
	//}
	//纯虚析构
	virtual ~Animal() = 0; //直接使用会报错，因为父类可能也有指针需要析构函数释放，因此程序默认会走父类的析构函数，不能只声明
	virtual void speak() = 0;
};

//纯虚析构需要类外定义
//有了纯虚析构之后，这个类也属于抽象类，无法实例化对象
Animal::~Animal() {
	cout << "Animal纯虚析构函数" << endl;
}

class Cat:public Animal {
public:
	Cat(string name) {
		m_Name = new string(name);
		cout << "Cat构造函数" << endl;
	}
	void speak() {
		cout << "小猫在叫" << endl;
	}
	~Cat() {
		if (m_Name != NULL) {
			cout << "Cat析构函数" << endl;
			delete m_Name;
			m_Name = NULL;
		}
	}

	string* m_Name;//出现了Cat对象的堆区数据，而父类指针cat不能直接删除子类对象的堆区数据.因此引入虚析构或纯虚析构
};

void test01() {
	Animal* cat = new Cat("Tom");
	cat->speak();
	delete cat;//父类指针在析构的时候 不会调用子类中的析构函数，导致子类如果有堆区属性，会出现内存泄漏情况。
}	

int main() {

	test01();
	return 0;
}
```

**总结**：

​	1.虚析构或纯虚析构就是用来解决通过父类指针释放子类对象

​	2.如果子类中没有堆区数据，可以不写虚析构或纯虚析构

​	3.拥有纯虚析构函数的类也属于抽象类

#### 4.7.6 多态案例三——电脑组装

**案例描述**：

​	电脑主要组成部分CPU，显卡，内存条

​    需求;

​		将每个零件封装成抽象基类，并且提供不同的厂商生产不同的零件，如Intel厂商和Lenovo厂商

​		创建电脑类提供电脑工作的函数，并且调用每个零件工作的接口

​		测试时组装三台不同的电脑进行工作

```c++
#include <iostream>
#include <string>;

using namespace std;


//抽象出每个零件的类
class CPU {
public:
	virtual void calculate() = 0;
	virtual ~CPU() {
	}
};

class VideoCard {
public:
	virtual void display() = 0;
	virtual ~VideoCard() {
	}
};

class Memory {
public:
	virtual void storage() = 0;
	virtual ~Memory() {}
};

class Intel :public CPU, public VideoCard, public Memory {
public:
	Intel() {
		m_Name = new string("Inter");
	}
	void calculate() {
		cout << *m_Name << "家CPU提供计算" << endl;
	}
	void display() {
		cout << *m_Name << "家显卡提供处理图像" << endl;
	}
	void storage() {
		cout << *m_Name << "家内存条提供存储" << endl;
	}

	~Intel() {
		if (m_Name != NULL) {
			delete m_Name;
			m_Name = NULL;
		}
	}

	string* m_Name;
};

class Dell :public CPU, public VideoCard, public Memory {
public:
	Dell() {
		m_Name = new string("Dell");
	}
	void calculate() {
		cout << *m_Name << "家CPU提供计算" << endl;
	}
	void display() {
		cout << *m_Name << "家显卡提供处理图像" << endl;
	}
	void storage() {
		cout << *m_Name << "家内存条提供存储" << endl;
	}

	~Dell() {
		if (m_Name != NULL) {
			delete m_Name;
			m_Name = NULL;
		}
	}

	string* m_Name;
};


class Lenovo :public CPU, public VideoCard, public Memory {
public:
	Lenovo() {
		m_Name = new string("Lenovo");
	}
	void calculate() {
		cout << *m_Name << "家CPU提供计算" << endl;
	}
	void display() {
		cout << *m_Name << "家显卡提供处理图像" << endl;
	}
	void storage() {
		cout << *m_Name << "家内存条提供存储" << endl;
	}

	~Lenovo() {
		if (m_Name != NULL) {
			delete m_Name;
			m_Name = NULL;
		}
	}

	string* m_Name;
};


class Computer {
public:

	string m_Name;
	CPU* cpu;
	VideoCard* vc;
	Memory* me;
	Computer(string name,CPU* p1,VideoCard* p2,Memory* p3) {
		m_Name = name;

		cpu = p1;
		vc = p2;
		me = p3;
	}
	void makeUp() {
		cout << m_Name << "的电脑配置如下：" << endl;
		cpu->calculate();
		vc->display();
		me->storage();
		delete cpu;
		delete vc;
		delete me;

	}
};

void test01() {
	Computer p1("低端机",new Intel,new Dell,new Dell);
	p1.makeUp();

}

int main() {
	test01();
	return 0;
}
```

**进化版本**（把三个厂商抽象为工厂）

```c++
#include <iostream>
#include <string>;

using namespace std;


//抽象出每个零件的类
class CPU {
public:
	virtual void calculate() = 0;
	virtual ~CPU() {
	}
};

class VideoCard {
public:
	virtual void display() = 0;
	virtual ~VideoCard() {
	}
};

class Memory {
public:
	virtual void storage() = 0;
	virtual ~Memory() {}
};

//抽象出每个工厂类
class Factory :public CPU, public VideoCard, public Memory {
public:
	void calculate() {
		cout << *m_Name << "家CPU提供计算" << endl;
	}
	void display() {
		cout << *m_Name << "家显卡提供处理图像" << endl;
	}
	void storage() {
		cout << *m_Name << "家内存条提供存储" << endl;
	}

	virtual ~Factory() {}

	string* m_Name;
};

class Dell :public Factory {
public:
	Dell() {
		m_Name = new string("Dell");
	}


	~Dell() {
		if (m_Name != NULL) {
			delete m_Name;
			m_Name = NULL;
		}
	}
};


class Lenovo :public Factory {
public:
	Lenovo() {
		m_Name = new string("Lenovo");
	}

	~Lenovo() {
		if (m_Name != NULL) {
			delete m_Name;
			m_Name = NULL;
		}
	}

};


class Computer {
public:

	string m_Name;
	CPU* cpu;
	VideoCard* vc;
	Memory* me;
	Computer(string name,CPU* p1,VideoCard* p2,Memory* p3) {
		m_Name = name;

		cpu = p1;
		vc = p2;
		me = p3;
	}
	void makeUp() {
		cout << m_Name << "的电脑配置如下：" << endl;
		cpu->calculate();
		vc->display();
		me->storage();
		delete cpu;
		delete vc;
		delete me;

	}
};

void test01() {
	Computer p1("低端机",new Lenovo,new Dell,new Dell);
	p1.makeUp();

}

int main() {
	test01();
	return 0;
}
```

## 5. 文件操作

程序运行时产生的数据都属于临时数据，程序一旦运行结束都会被释放

通过**文件可以将数据持久化存储**

C++中对文件操作需要包含头文件**`<fstream>`**



文件类型分为两种：

1.**文本文件**——文件已文本的**ASCII码**形式存储在计算机中

2.**二进制文件**——文件以文本的**二进制**形式存储在计算机中，用户一般不能直接读懂他们



操作文件的三大类：

1.ofstream:	  写操作

2.ifstream:	   读操作

3.fstream:		读写操作

### 5.1 文本文件

#### 5.1.1 写文件

写文件步骤如下：

1.包含头文件

​	#include <fstream>

2.创建流对象

​	ofstream ofs;

3.打开文件

​	ofs.open("文件路径",打开方式);

4.写数据

​	ofs.<<"写入的数据";

5.关闭文件

​	ofs.close();



文件打开方式：

| 打开方式    | 解释                         |
| ----------- | ---------------------------- |
| ios::in     | 为读文件而打开文件           |
| ios::out    | 为写文件而打开文件           |
| ios::ate    | 初始位置：文件尾             |
| ios::app    | 追加方式写文件               |
| ios::trunc  | 如果文件存在，先删除，再创建 |
| ios::binary | 二进制方式                   |

**注意**：文件打开方式可以配合使用，利用   **|**   操作符

**例如**：用二进制方式写文件`ios::out|ios::binary`

```c++
#include <iostream>
#include <fstream>
#include <string>

using namespace std;
void test01(){
    //1.包含头文件 fstream
    
    //2.创建流对象
    ofstream ofs;
    
    //3.指定打开方式
    ofs.open("test.txt",ios::out);
    
    //4.写内容
    ofs<<"姓名：张三"<<endl;
    ofs<<"性别：男"<<endl;
    ofs<<"年龄：18"<<endl;
    
    //5.关闭文件
    ofs.close();
}
int main(){
    test01();
    return 0;
}
```

#### 5.1.2 读文件

读文件与写文件步骤相似，但是读取方式相对于比较多



读文件步骤如下：

1.包含头文件

​	#include<fstream>

2.创建流对象

​	ifstream ifs;

3.打开文件并判断文件是否打开成功

​	ifs.open("文件路径",打开方式);

4.读数据

​	四种方式读取

5.关闭文件

​	ifs.close();

```c++
#include <iostream>
#include <fstream>
#include <string>

using namespace std;

//文本文件 读文件
void test01(){
    //1.包含头文件
    
    //2.创建流对象
    ifstream ifs;
    
    //3.打开文件，并判断是否打开成功
    ifs.open("test.txt",ios::in);
    //打开文件类里面自带判断是否打开成功的函数，返回的是一个布尔类型的数
	if(!ifs.is_open()){
        cout<<"打开失败"<<endl;
        return;
    }
    //4.读数据
    //第一种	利用字符数组存储
    char buf[1024] = {0};
    while (ifs>>buf)//按行读数据，读到空行返回false
    {
        cout<<buf<<endl;
    }	
    //第二种	利用字符数组存储
    char buf[1024] = {0};//初始化char数组
    while(ifs.getline(buf,sizeof(buf))){
        cout<<buf<<endl;
    } 
    
    //第三种	读到string里
	string buf;
    //getline(数据流对象，读到的string对象)
    while(getline(ifs,buf)){
        cout<<buf<<endl;
    }
    
    //第四种	逐字符读（不推荐）
    char c;
    while((c=ifs.get())!=EOF)//EOF end of file 文件尾标志
    {
        cout<<c;
    }
    
    //5.关闭文件
    ifs.close();
}

int main(){
    test01();
    return 0;
    
}
```

### 5.2 二进制文件

以二进制方式对文件进行读写操作

打开方式要指定为ios::binary

#### 5.2.1 写文件

二进制方式写文件主要利用流对象调用成员函数write

函数原型：`ostream& write(const char * buffer,int len);`

参数解释：字符指针buffer指向内存中的一段存储空间，len是读写的字节数

示例：

```c++
#include<iostream>
#include<fstream>
using namespace std;
//二进制文件 写文件
class Person{
public:
    char m_Name[64];//姓名 要写二进制文件最好不要用string，会出问题
    int m_Age;
};

void test01(){
    //1.包含头文件
    
    //2.创建流对象
    ofstream ofs;
    
    //3.打开文件
    ofs.open("person.txt,ios::out|ios::binary")
        
    //2、3两步可以合为一步
    ofstream ofs("person.txt,ios::out|ios::binary");
    
    //4.写文件
    Person p = {"张三"，18}；
    ofs.write((const char*)&p,sizeof(Person));
    //5.关闭文件
    ofs.close（）;
  
}
int main{
    test01();
    return 0;
}

```

#### 5.2.2 读二进制文件

二进制方式读文件主要利用流对象调用成员函数read

函数原型：`istream& read(char *buffer,int len);`

示例：

```c++
#include <iostream>
#include <fstream>
using namespace std;

class Person{
public:
    char m_Name[64];//姓名
    int m_Age;//年龄
};

//二进制文件 读文件
void test01(){
    //1.包含头文件
    
    //2.创建流对象
    ifstream ifs;
    
    //3.打开文件，判断文件是否打开成功
    ifs.open("Person.txt",ios::in|ios::binary);
    if(!ifs.is_open()){//文件打开失败
        return;
    }
    //4.读文件
    Person p;
    ifs.read((char*)&p,sizeof(Person));
    cout<<p.m_Name<<p.m_Age<<endl;
    
    //5.关闭文件
   	ifs.close();
}


```

## 核心阶段项目：职工管理系统



职工管理系统可以用来管理公司内所有员工的信息

本节主要利用C++来实现一个基于多态的职工管理系统



公司中职工分为三类：普通员工、经理、老板，显示信息时，需要显示职工编号，职工姓名、职工岗位、以及职责

普通员工职责：完成经理交给的任务

经理职责：完成老板交给的任务，并下发任务给员工

老板职责：管理公司所有事物



管理系统中需要实现的功能如下:

* 退出管理系统
* 增加职工信息：实现批量添加职工功能，将信息导入到文件中，职工信息为：职工编号、姓名、部门编号
* 显示职工信息：显示公司内部所有职工的信息
* 删除离职员工：按照编号删除指定的职工
* 修改职工信息：按照编号修改职工个人信息
* 查找职工信息：按照职工的编号或者职工的姓名进行查找相关的人员信息
* 按照编号排序：按照职工编号，进行排序，排序规则由用户指定
* 清空所有文档：清空文件中记录的所有职工信息（请空前需要再次确认，防止误删）



# C++提高: C++标准库——体系结构与内核分析

体系结构：六大部件
内核分析：结构如何实现
**目标**：

* Level0:使用C++标准库
* level1:认识C++标准库（胸中自有丘壑）
* level2:**良好**使用C++标准库
* level3:扩充C++标准库（难）

本阶段主要针对C++**泛型编程**和**STL**技术做详细讲解，探讨C++更深层的使用

## 序1. 模板
### 1.1 模板的概念
  1.模板不能直接使用，只是个框架
  2.模板的通用型不是万能的
### 1.2 函数模板
* C++另一种编程思想称为**泛型编程**，主要利用的技术就是模板
* C++提供两种模板机制：**函数模板** 和 **类模板**

#### 1.2.1 函数模板语法
函数模板作用：
建立一个通用函数，其函数返回值类型和形參类型可以不具体制定，用一个**虚拟的类型**来表示

语法：
```c++
template<typename T>//typename可以替换为class
函数声明或定义
```
解释：
template —- 声明创建模板
typename —- 表明其后面的符号是一种数据类型，可以用class代替
T —- 通用数据类型，名称可以替换，通常为大写
```c++
template<typename T>
void mySwap(T &a,T &b){
    T temp = a ;
    a = b;
    b = temp;
}
//利用函数模板交换
//两种方式使用函数模板
//1.自动类型推导
//例：
//int a = 10;
//int b = 20;
//mySwap(a,b);
//mySwap<int>(a,b);
```
总结：
* 函数模板利用关键字template
* 使用函数模板有两种方式：自动类型推导、显示指定类型
* 模板的目的是为了提高复用性，将类型参数化
#### 1.2.2 函数模板注意事项
注意事项：
* 自动类型推导，必须推导出一致的数据类型T，才可以使用

* 模板必须要确定出T的数据类型，才可以使用
  **示例：**

  ```c++
  //模板必须要确定出T的数据类型，才可以使用
  template<class T>
  void func(){			
      cout<<"func 调用"<<endl;
  }
  
  func();//报错，确定不了T的数据类型
  
  func<int>();//正确，必须确定T的数据类型1.2.3 函数模板案例
  ```

#### 1.2.3 函数模板案例

案例描述：

* 利用函数模板封装一个排序函数，可以对不同数据类型的数组进行排序
* 排序规则从大到小，排序算法为**交换排序**
* 分别用char数组和int数组进行测试

```c++
#include <iostream>

using namespace std;

template <class T>
void sort(T a1[],int len) {
	for (int i = 0; i < len; i++) {
		for (int j = 0; j < len - i-1; j++) {
			if (a1[j + 1] < a1[j]) {
				T temp = a1[j];
				a1[j] = a1[j + 1];
				a1[j + 1] = temp;
			}
		}
	}
}

int main() {
	int a[] = { 5,3,4,1,6,2,7 };
	int len = 7;
	sort(a,len);

	for (int i = 0; i < len; i++)
		cout << a[i] << "\t";

	char b[] = { 'c','b','e','a','f' };
	int len1 = 5;
	sort(b, len1);
	for (int i = 0; i < len; i++)
		cout << b[i] << "\t";
	return 0;
}
```

#### 1.2.4 普通函数与函数模板的区别

**区别**：

* 普通函数调用时可以发生自动类型转换（隐式类型转换）
* 函数模板调用时，如果利用自动类型推导，不会发生隐式类型转换
* 如果利用显示指定类型的方式，可以发生隐式类型转换

```c++
//普通函数
int myAdd01(int a, int b){
    return a+b;
}

test01(){
    int a = 10;
    char b = 'a';
    myAdd01(a,b);//正确，将b自动类型转换为了其ASCII码
}

//函数模板
template <class T>
T myAdd02(T a, T b){
    return a+b;
}
test02(){
    int a = 10;
    cha b = 'a';
    myAdd02(a,b);//报错，函数模板利用自动类型推导，不会发生隐式类型转换
    myAdd02<int>(a,b);//正确，函数模板指定参数类型，可以发生隐式类型转换
}
```

#### 1.2.5 普通函数与函数模板的调用规则

调用规则如下：

1.如果函数模板和普通函数都可以实现，**优先调用普通函数**

2.可以通过**空模板参数类表**来强制调用函数模板

3.函数模板也可以发生重载

4.如果函数模板可以产生更好的匹配，优先调用函数模板

```c++

void myprint(int a){
    cout<<"普通函数"<<a<<endl;
}

template<class T>
void myprint(T a){
    cout<<"函数模板"<<a<<endl;
}

//函数模板可以发生重载
template<class T>
void myprint(T a,T b){
    cout<<"函数模板重载"<<a<<b<<endl;
}

void test01(){
    int a = 10;
    int b = 10;
    myprint(a);//一般情况下优先调用普通函数
    
    myprint<>(a);//利用空模板参数列表，强制调用函数模板
    
    myprint(a,b);//调用函数模板重载（自动类型推导）
    
    char c1 = 'a';
	myprint(c1);//此时调用函数模板，因为c1类型为char，普通函数参数列表为int类型，该函数调用和函数模板有更好的匹配
}
//通过空模板参数列表，强制调用函数模板
```

#### 1.2.6 模板的局限性

局限性：

* 模板的通用性不是万能的

```c++
//模板局限性：
//模板并不是万能的，有些特定数据类型，需要用具体化方式做特定实现

//对比两个数据是否相等的函数
class Person{
private:
    string m_name;
    int m_age;
public:
    Person(string name,int age){
        m_name = name;
        m_age = age;
    }
};

template<class T>
bool myCompare(T &a, T &b){
    return a==b;
}

//对于Person类的对象，重载函数模板myCompare
template<> bool myCompare(Person &p1,Person &p2){
    if(p1.name == p2.name && p1.age==p2.age){
        return true;
    }
    return false;
}

void test01(){
    int a = 10;
    int b = 20;
    myCompare(a,b);
}

void test02(){
    Person p1("小张",18);
    Person p2("小张";18);
    
    myCompare(p1,p2);//报错，函数模板自动类型转换转换不了对象。
    //解决方法：
    //1.运算符重载，重载"==";
    //2.利用具体化Person 的版本实现代码，具体化优先调用

}
```

总结：

* 利用具体化的模板，可以解决自定义类型的通用化
* **学习模板并不是为了写模板，而是在STL能够运用系统提供的模板**



### 1.3 类模板

#### 1.3.1 类模板语法

类模板作用：

* 建立一个通用类，类中的成员 数据类型可以不具体制定，用一个**虚拟的类型**代替

```c++
//类模板定义
template <class NameType,class AgeType>
class Person{
public:
	NameType m_Name;
    AgeType m_Age;
    Person(NameType name,AgeType age){
        m_Name = name;
        m_Age = age;
    }
};

void test01(){
    //类模板的使用
    Person<string,int> p1("小明",18);
}
```

#### 1.3.2 类模板和函数模板的区别

**区别**：

1.类模板没有自动类型推导的使用方式

2.类模板在模板参数列表中可以有默认参数

**示例**：

```c++
//类模板
//类模板在参数列表中可以有默认参数
template <class NameType,class AgeType = int>
class Person{
public:
	NameType m_Name;
    AgeType m_Age;
    Person(NameType name,AgeType age){
        m_Name = name;
        m_Age = age;
    }
};

void test01(){
    //错误，类模板没有自动类型推导
    Person p1("小明",18);
}

//2.类模板在参数列表中可以有默认参数
void test02(){
    Person<string> p2("小明",18);
    //此时，age的数据类型为默认的int，可以在定义对象时不添加age的数据类型
}
```

#### 1.3.3 类模板中成员函数创建时机

类模板中的成员函数和普通类中的成员函数创建时机是有区别的：

* 普通类中的成员函数**运行时创建**
* 类模板中的成员函数在**调用时创建**

**原因**：因为类模板中的成员函数不完整，只有调用的时候指定了参数类型才完整

```c++
class Person1{
public:
    void showPerson1(){
        cout<<"调用Person1"<<endl;
    }
};

class Person2{
public:
  void showPerson2(){
      cout<<"调用Person2"<<endl;
  }  
};

template<class T>
class Myclass{
public:
    T obj;
    
    //类模板中的成员函数
    void func1(){
        obj.showPerson1();
    }
    
    void func2(){
        obj.showPerson2();
    }
    //可以编译成功，在编译的时候编译器不知道obj的数据类型，因此不能判断类模板中的成员函数的数据类型是否正确，不能完成创建
}

void test01(){
	Myclass<Person1> m;
    m.func1();
    m.func2();//报错,此时确定了成员对象obj的数据类型为Person1对象，因此只能调用Person1中的成员方法，对于Person2中的成员方法 调用失败，此时也说明了类模板中的成员函数已经创建。
    
    Myclass<Person2> m2;
    m.func2();//正确
}
```

#### 1.3.4 类模板对象做函数参数

学习目标：

* 类模板实例化出的对象，向函数传参的方式

传递方式：

​	1.指定传入类型

​	2.参数模板化

​	3.整个类模板化

```c++
#include <iostream>
#include <string>
using namespace std;



template<class T1,class T2>
class Person
{
public:
	Person(T1 name, T2 age) {
		m_Name = name;
		m_Age = age;
	};
	
	void showPerson() {
		cout << "姓名" << m_Name << "年龄" << m_Age << endl;
	}
	T1 m_Name;
	T2 m_Age;
};


//类模板对象做函数参数
//1.指定传入类型
void printPerson1(Person<string,int>&p) {
	p.showPerson();
}

void test01() {
	Person<string, int> p1("小明", 18);
}


//2.参数模板化(即，指定传入的模板类对象中的参数类型和之前定义的参数类型一致，都是T1，T2)
template<class T1,class T2>
void printPerson2(Person<T1,T2>&p2) {
	p2.showPerson();
	//如果想看T1,T2是什么类型的
	cout << typeid(T1).name << endl; 
}

void test02() {
	Person<string, int> p2("小张", 16);
}


//3.整个类模板化（函数模板）
template<class T>
void printPerson3(T &p3) {
	p3.showPerson();
}

void test03() {
	Person<string, int> p3("小秦", 20);
	printPerson3(p3);
}


int main() {
	test03();
	return 0;
}
```

总结：比较广泛的是第一种：指定传入类型。







## 序2.STL初识
### 2.1 STL的诞生

* 长久以来，软件界一直希望建立一种可重复利用的东西
* C++的**面向对象和泛型编程**思想，目的就是为了**提升复用性**
* 大多数情况下，数据结构和算法都未有一套标准，导致被迫从事大量重复工作
* 为了建立数据结构和算法的一套标准，诞生了**STL**

### 2.2 STL基本概念
* STL（standard template library，标准模板库）
* STL从广义上分为：**容器(container)算法(algorithm)迭代器(itrator)**
* **容器**和**算法**之间通过**迭代器**进行无缝连接
* STL几乎所有的代码都采用了模板类或者模板函数

### 2.3 STL六大组件
SL大体分为六大组件：分别是：**容器、算法、迭代器、仿函数、适配器、空间配置器**

1.容器：各种数据结构，如vector、list、deque、set、map等用来存放数据
2.算法：各种常用的算法，如sort、find、copy、for_each等
3.迭代器：扮演了容器与算法之间的粘合剂
4.仿函数：行为类似函数，可作为算法的某种策略
5.适配器：一种用来修饰容器或者仿函数或迭代器接口的东西
6.空间配置器：负责空间的配置与管理

### 2.4 STL中容器、算法、迭代器
STL**容器**就是将应用**最广泛的一些数据结构**实现出来
常用的数据结构：数组、链表、树、栈、队列、集合、映射等
这些容器分为**序列式容器**和**关联式容器**两种：
    **序列式容器** ：强调值的排序，序列式容器中每个元素均有固定的位置。
    **关联式容器**：二叉树结构，各元素之间没有严格的物理上的顺序关系。

**算法**：有限的步骤，解决逻辑或数学上的问题，这一门学科我们叫做算法（Algorithms）
算法分为**质变算法**和**非质变算法**。区别在于运算过程中是肉会更改区间内的元素的内容。例如拷贝、替换、删除（质变），查找、计数、遍历（非质变）
**迭代器**：容器和算法之间的黏合剂。
提供一种方法，使之能够依序访问容器内所含的各个元素，而又无需暴露该容器的内部表示方式。
每个容器都有自己专属的迭代器。
迭代器使用非常类似于指针。



## 第一讲：C++STL标准库与泛型编程(Generic Programming)

泛型编程(GP)：使用template（模板）为主要工具来编写程序。而STL就是泛型编程(GP)最成功的 作品。

C++标准库>STL(标准模板库)

标准库以header files形式呈现：

* C++标准库的header files不带副档名.h,例如#include<vector>
* 新式headers内的组件封装于namespace “std”，using namespace std。

重要网页：
CPlusPlus.com
CppReference.com
bcc.gnu.org

### 1.1 STL六大部件

容器
分配器
算法
迭代器
适配器
仿函数
六大部件之间的关系：

![image](images\releshape.jpg)

泛型编程与面向对象编程思想上不同：面向对象中讲究封装，习惯将属性和方法(对属性的操作)封装在一起形成类。泛型编程提供一种“模板” ，如容器和算法(一些对容器的操作)分开存放。

```c++
#include <vector>
#include <algorithm>
#include <functional>
#include <iostream>

using namespace std;

int main(){
    int ia[6]= {27,210,12,47,109,83};
    vector<int,allocator<int>> vi(ia,ia+6);
  // 容器	      分配器                  仿函数适配器(下)
cout<<count_if(vi.begin(),vi.end(),not1(bind2nd(less<int>(),40)));
  //   算法        迭代器         算法适配器       仿函数
    return 0;   
}
```

**“前闭后开”区间** [)

![image](images\jiliguala.jpg)

**tips:c++11一个新特性(for 循环)**:

```c++
for (decl:coll){
    statement;
}

//例
for(int i : {2,3,4,5,6,7,8,9}){
    cout<<i<<endl;
}

//例2
std::vector<double> vec;
...
//auto c++11新特性：自动类型推导
for (auto elem : vec){
    cout<<elem<<endl;
}

for (auto &elem : vec){
    elem *= 3;
}
```

### 1.2 基本容器一览

![images](images\image-20230906115336553.png)

**Sequence Containers（顺序式容器）：**

* Array:数组，内存中一片连续的固定的地址空间

* Vector：空间不够的时候会自动扩充（单向）（ps：每次扩充原大小的两倍）

* Deque：双端队列。 分段连续，对++重载让程序员感觉是连续的（ps：每次扩充一个buffer）
  * queue
  * stack

​		![ ](images\image-20230906154010211.png)

* List：链表。(双向链表) （每次扩充一个节点）

* Forward-List：单向链表。只提供头插法（猜测：有头指针，头插快，尾插很慢）

**Associative Containers（关联式容器）：**

* set/Multiset:基于红黑树，高度平衡二叉树。  
* Map/multimap：基于红黑树，高度平衡二叉树，分为Key和value两个部分，可以用Key查找。

* multi-：元素的内容可以重复。

**Unordered Containers:**

​	最右边的图：HashTable：哈希表（Separate Chaining实现的最好用——拉链法）

## 第二讲 容器

源码之前，了无秘密

### 2.1 基础知识

**OOP(面向对象编程) VS GP(泛型编程)**

**OOP**企图将Datas和methods关联在一起

**GP**却是将Datas和methods分开

​	采用**GP：**

	*  Containers和Algorithms团队可以闭门造车，其间以Iterator贯通即可
	*  Algorithms通过Iterators确定操作范围，并通过Iterators取用Container元素



**泛化、特化和偏特化**

特化：模板对于某些数据类型有更好的实现，可以采用特化

偏特化：个数偏特化、范围偏特化



### 2.2 分配器 allocators

VC6，BC5，GNU2.9（C++编译器）调用分配器过程 ：

allocate---->调用operator new---->调用malloc		 申请内存

deallocate---->调用operator delete---->调用free 	 清空内存



ps: malloc开辟内存空间时有固定的额外开销，因此申请的空间越小，额外开销所占的比例越大。



### 2.3 vector容器

**功能**：vector数据结构和**数组非常相似**，也称为**单端数组**

**vector与普通数组区别**：

* 不同之处在于数组是静态空间，而vector可以**动态扩展**（每次扩展为原空间的两倍）

#### 2.3.1 vector 存放内置数据类型

```c++
#include <iostream>
using namespace std;
#include <vector> //vector容器头文件，用什么容器就要引用什么容器的头文件
#include <algorithm>//STL 中算法的头文件，记住


void myPrint(int val) {
	cout << val << endl;
}

//vector容器存放内置数据类型

void test01() {
	//创建一个vector容器，数组
	vector<int> v;

	//向容器中插入数据
	v.push_back(10);
	v.push_back(20);
	v.push_back(30);

	//通过迭代器访问容器中的数据

	/*
	//遵循左闭右开
	vector<int>::iterator itBegin = v.begin();//起始迭代器，指向容器中第一个元素的位置
	vector<int>::iterator itEnd = v.end();//结束迭代器 指向容器中最后一个元素的下一个位置

	//第一种遍历方式
	while (itBegin != itEnd) {
		cout << *itBegin << endl;
		itBegin++;
	}
	
	//第二种遍历方式
	for (vector<int>::iterator itBegin = v.begin(); itBegin != v.end(); itBegin++) {
		cout << *itBegin << endl;
	}
	*/

	//第三种遍历方式,利用STL中的遍历算法
	for_each(v.begin(), v.end() , myPrint);		//底层第三个参数是Func(*p);   p是算法中当前指向的该元素的迭代器，解引用p
}

int main() {
	test01();
	return 0;
}
```



#### 2.3.2 vector 存放自定义数据类型



1.存放自定义数据类型；

如例子中的`	vector<Person> v;`

```c++
#include <iostream>
#include <vector>
#include <algorithm>
#include <string>

using namespace std;


class Person {
public:
	string m_Name;
	int m_Age;

	Person(string name,int age) {
		m_Name = name;
		m_Age = age;
	}

	void func() {
		cout << "是个人就会呼吸" << endl;
	}
};


//方式1 
ostream& operator<<(ostream& cout, Person& p) {
	cout << p.m_Name << p.m_Age;
	p.func();
	return cout;
}


//方式2
void myPrint(Person& p) {
	cout << p;
}


void test01() {
	vector<Person> v;
	v.push_back(Person("小明", 18));
	v.push_back(Person("小张", 20));
	v.push_back(Person("小秦", 22));

//方式1 遍历
	for (vector<Person>::iterator it = v.begin(); it != v.end(); it++) {
		cout << *it;
	}

//方式2 遍历
	for_each(v.begin(), v.end(), myPrint);
}
int main() {
	test01();
	return 0;
}
```



2.存放指向自定义数据类型的指针(减少vector容器的空间开销，指针只有四字节大小(32位操作系统中))；

如例子中的`	vector<Person> v;`

```c++
#include <iostream>
#include <vector>
#include <algorithm>
#include <string>

using namespace std;


class Person {
public:
	string m_Name;
	int m_Age;

	Person(string name,int age) {
		m_Name = name;
		m_Age = age;
	}

	void func() {
		cout << "是个人就会呼吸" << endl;
	}
};


//方式1
ostream& operator<<(ostream& cout, Person& p) {
	cout << p.m_Name << p.m_Age;
	p.func();
	return cout;
}


//方式2
void myPrint(Person* p) {
	cout << *p;
}


void test01() {
	vector<Person*> v;
	Person p1("小秦", 22);
	v.push_back(&p1);




//方式1
    //请注意：此时迭代器it是指向  指向Person数据类型的指针  的指针
	for (vector<Person*>::iterator it = v.begin(); it != v.end(); it++) {
		cout << **it;
	}

//方式2
	for_each(v.begin(), v.end(), myPrint);
}
int main() {
	test01();
	return 0;
}
```



#### 2.3.3 Vector容器嵌套容器

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;
//容器嵌套容器

void func2(int i) {
	cout << i << " ";
}
void func1(vector<int> p) {
	for_each(p.begin(), p.end(), func2);
	cout << endl;
}


void test01() {
	//vector容器内嵌套了一个vector容器
	vector<vector<int>> v;

	//创建小容器
	vector<int> v1;
	vector<int> v2;
	vector<int> v3;

	//向小容器中添加数据
	for (int i = 0; i < 3; i++) {
		v1.push_back(i);
		v2.push_back(i + 3);
		v3.push_back(i + 6);
	}

	//向大容器中添加小容器
	v.push_back(v1);
	v.push_back(v2);
	v.push_back(v3);



	//第一种：遍历容器v中的内容
	for (vector<vector<int>>::iterator i = v.begin(); i < v.end(); i++) {
		for (vector<int>::iterator j = (*i).begin(); j < (*i).end(); j++) {
			cout << *j << " ";
		}
		cout << endl;
	}



	//第二种：遍历容器v中的内容
	for_each(v.begin(), v.end(), func1);

}

int main() {
	test01();
	return 0;
}
```



#### 2.3.4 vector构造函数

功能描述：创建vector容器

**函数原型**：

* `vector<T> v;`											//默认构造函数
* `vector(v.begin(),v.end());`		      //将v[begin(),end())区间汇总的元素拷贝
* `vector(n,elem); `                                      //构造函数将n个elem拷贝
* `vector(const vector &vec)`                 //拷贝构造函数



**示例**：

```c++
	//默认构造函数
	vector<int> v1;

	//通过区间的方式进行构造,把v1区间中的数据传递给v2（左闭右开区间）
	vector<int> v2(v1.begin(), v1.end());

	//n个elem方式构造函数，构造含有n个elem的vector
	vector<int> v3(10, 100);

	//拷贝构造
	vector<int> v4(v3);
```



#### 2.3.5 vector赋值操作

功能描述：给vector容器进行赋值

```c++
	vector<int> v1;

	for (int i = 0; i < 10; i++) {
		v1.push_back(i);
	}

	//赋值  重载=号
	vector<int> v2;
	v2 = v1;

	//赋值 assign
	vector<int> v3;
	v3.assign(v1.begin(), v1.end());

	//n个elem方式赋值
	vector<int> v4;
	v4.assign(10, 100);
```



#### 2.3.6 vector容量和大小操作

功能描述：对vector容器的容量和大小进行操作

**函数原型**：

* `empty();`							//判断容器是否为空

* `capacity();               `                      //容器的容量

* `size();          `                               //返回容器中元素的个数

* `resize(int mun);`            //重新指定容器的长度为num，若容器变长，则以默认值填充新位置。

  ​                                               //若容器变短，则末尾超出容器长度的元素被删除。

* `resize(int mun,elem);`  //重新指定容器的长度为num，若容器变长，则以elem填充新位置。

  ​                                               //若容器变短，则末尾超出容器长度的元素被删除。

注：resize()变短，容器的capacity不变，resize()变长，容器的capacity可能会变长。取决于重新指定的容器长度有没有超过当前capacity。



#### 2.3.7 vector插入和删除操作

功能描述：对vector容器进行插入、删除操作

**函数原型：**

* `push_back(ele);`                                         //尾部插入元素ele
* `pop_back();`                                                //删除最后一个元素
* `insert(const_iterator pos, ele);`        //迭代器指向位置pos插入元素ele
* `insert(const_iterator pos, int count,ele);`//迭代器指向位置pos插入count个元素ele
* `erase(const_iterator pos);`                     //删除迭代器指向的元素
* `erase(const_iterator start, const_iterator end);`//删除迭代器从start到end之间的元素
* `clear();`                                                        //删除容器中所有元素

```c++
vetcor<int> v1;
v1.push_back(10);
v1.pop_back();
insert(v1.begin(),20);
vector<int>::iterator i = v.begin()+1;
v1.insert(i,10,100);//向迭代器i指向的位置后插入10个一百
v1.erase(i);//删除i位置的元素
v1.erase(i,v1.end());//删除从i位置到末尾位置的元素
```

#### 2.3.8 vector数据存取

功能描述：对vector中的数据进行存取操作

**函数原型：**

* `at(int idx); `     //返回索引idx所指的数据
* `operator[]; `       //返回索引idx所指的数据
* `front(); `            //返回容器中第一个数据元素
* `back();`              //返回容器中最后一个数据元素

```c++
vector<int> v1;
v1.push_back(10);
v1.push_back(20);
v1.push_back(30);

cout<<v1.at(1)<<endl;//输出：20
//vector提供了对[]的重载
cout<<v1[1]<<endl;//输出：20
cout<<v1.front()<<endl;//输出：10 v1.fornt() == *(v1.begin())
cout<<v1.back()<<endl;//输出：30  v1.back() == *(v1.end()-1)
```

**总结**：除了用迭代器获取vector容器中的元素，[]和at也可以



#### 2.3.9 vector容器互换

功能描述：实现两个容器内元素互换

**函数原型：**

* `swap(vec);`  // 将vec与本身的元素互换

**使用场景**：巧用swap()收缩空间：

如:

```c++
vector<int> v;
for(int i=0;i<100000000;i++){
    v.push_back(i);
}
v.resize(10);//此时v的容量 >= 100000000 但是有效元素只有十个

vector<int>(v).swap(v);//巧妙地将v的容量减少到了10
```

底层逻辑：

```
vector<int>(v)//创建了个匿名对象，并将v里面的元素拷贝给了该匿名对象
后面：
.swap(V)//将匿名对象与v容器进行交换。此时匿名对象变成了一个容量>=1000000000的vector，v变成了含有十个元素并且容量为10的vector，并且由于匿名对象的特点，会在此行语句执行完系统自动回收空间，巧妙地进行了v的空间收缩。
```

#### 2.3.10 vector预留空间

功能描述：减少vector在动态扩展容量时的扩展次数

**函数原型**：

* `reserve(int len);`//容器预留len个元素长度，预留位置不初始化，元素不可访问。

如果数据量较大，可以一开始利用reserve预留空间。

### 2.4 deque容器

#### 2.4.1 deque容器基本概念



**功能：**

* 双端数组，可以对头端进行插入删除操作



**deque与vector区别：**

* vector对于头部的插入删除效率低，数据量越大，效率越低
* deque相对而言，对头部的插入删除速度回比vector快
* vector访问元素时的速度会比deque快,这和两者内部实现有关



**deque内部工作原理:**

deque内部有个**中控器**，维护每段缓冲区中的内容，缓冲区中存放真实数据

中控器维护的是每个缓冲区的地址，使得使用deque时像一片连续的内存空间

![image](/images/clip_image002-1547547896341.jpg)

#### 2.4.2 deque构造函数

**功能描述：**

* deque容器构造

**函数原型：**

* `deque<T>` deqT;                      //默认构造形式
* `deque(beg, end);`                  //构造函数将[beg, end)区间中的元素拷贝给本身。
* `deque(n, elem);`                    //构造函数将n个elem拷贝给本身。
* `deque(const deque &deq);`   //拷贝构造函数

**总结：**deque容器和vector容器的构造方式几乎一致，灵活使用即可



#### 2.4.3 deque赋值操作

**功能描述：**

* 给deque容器进行赋值



**函数原型：**

* `deque& operator=(const deque &deq); `         //重载等号操作符


* `assign(beg, end);`                                           //将[beg, end)区间中的数据拷贝赋值给本身。
* `assign(n, elem);`                                             //将n个elem拷贝赋值给本身。



#### 2.4.4 deque大小操作

**功能描述：**

* 对deque容器的大小进行操作



**函数原型：**

* `deque.empty();`                       //判断容器是否为空

* `deque.size();`                         //返回容器中元素的个数

* `deque.resize(num);`                //重新指定容器的长度为num,若容器变长，则以默认值填充新位置。

  ​			                             //如果容器变短，则末尾超出容器长度的元素被删除。

* `deque.resize(num, elem);`     //重新指定容器的长度为num,若容器变长，则以elem值填充新位置。

  ​                                                     //如果容器变短，则末尾超出容器长度的元素被删除。

**总结：**

* deque没有容量的概念
* 判断是否为空   --- empty
* 返回元素个数   --- size
* 重新指定个数   --- resize

#### 2.4.5 deque 插入和删除

**功能描述：**

* 向deque容器中插入和删除数据



**函数原型：**

两端插入操作：

- `push_back(elem);`          //在容器尾部添加一个数据
- `push_front(elem);`        //在容器头部插入一个数据
- `pop_back();`                   //删除容器最后一个数据
- `pop_front();`                 //删除容器第一个数据

指定位置操作：

* `insert(pos,elem);`         //在pos位置插入一个elem元素的拷贝，返回新数据的位置。

* `insert(pos,n,elem);`     //在pos位置插入n个elem数据，无返回值。

* `insert(pos,beg,end);`    //在pos位置插入[beg,end)区间的数据，无返回值。

* `clear();`                           //清空容器的所有数据

* `erase(beg,end);`             //删除[beg,end)区间的数据，返回下一个数据的位置。

* `erase(pos);`                    //删除pos位置的数据，返回下一个数据的位置。


**总结：**

* 插入和删除提供的位置是迭代器！
* 尾插   ---  push_back
* 尾删   ---  pop_back
* 头插   ---  push_front
* 头删   ---  pop_front



#### 2.4.6 deque数据存取

**功能描述：**

* 对deque 中的数据的存取操作

**函数原型：**

- `at(int idx); `     //返回索引idx所指的数据
- `operator[]; `      //返回索引idx所指的数据
- `front(); `            //返回容器中第一个数据元素
- `back();`              //返回容器中最后一个数据元素



### 2.5 案例-评委打分

#### 2.5.1 案例描述

有5名选手：选手ABCDE，10个评委分别对每一名选手打分，去除最高分，去除评委中最低分，取平均分。

```c++
#include <iostream>
#include <vector>
#include <deque>
#include <string>
#include <algorithm>

using namespace std;

void test01() {
	vector<double> v;
	for (int i = 0; i < 5; i++) {
		cout << "请评委们给第" << i << "位选手打分:" << endl;
		deque<double> s;
		for (int j = 0; j < 10; j++) {
			double score;
			cin >> score;
			s.push_back(score);
		}
		sort(s.begin(),s.end());
		s.pop_front();
		s.pop_back();
		double score_m = 0;
		for (int p = 0; p < s.size(); p++) {
			score_m += s[p];
		}
		score_m = score_m / s.size();
		v.push_back(score_m);

	}
	
	for (int q = 0; q < 5; q++) {
		cout << "第" << q << "位选手的平均成绩为:" << v[q] << endl;
	}

}

int main() {

	test01();
	return 0;
}
```

### 2.6 stack容器

#### 2.6.1 stack 基本概念



**概念：**stack是一种**先进后出**(First In Last Out,FILO)的数据结构，它只有一个出口

栈中只有顶端的元素才可以被外界使用，因此栈不允许有遍历行为

栈中进入数据称为  --- **入栈**  `push`

栈中弹出数据称为  --- **出栈**  `pop`





#### 2.6.2 stack 常用接口

功能描述：栈容器常用的对外接口



构造函数：

* `stack<T> stk;`                                 //stack采用模板类实现， stack对象的默认构造形式
* `stack(const stack &stk);`            //拷贝构造函数

赋值操作：

* `stack& operator=(const stack &stk);`           //重载等号操作符

数据存取：

* `push(elem);`      //向栈顶添加元素
* `pop();`                //从栈顶移除第一个元素
* `top(); `                //返回栈顶元素

大小操作：

* `empty();`            //判断堆栈是否为空
* `size(); `              //返回栈的大小



总结：

* 入栈   --- push
* 出栈   --- pop
* 返回栈顶   --- top
* 判断栈是否为空   --- empty
* 返回栈大小   --- size



### 2.7 queue容器

#### 2.7.1 queue 基本概念



**概念：**Queue是一种**先进先出**(First In First Out,FIFO)的数据结构，它有两个出口



队列容器允许从一端新增元素，从另一端移除元素

队列中只有队头和队尾才可以被外界使用，因此队列不允许有遍历行为

队列中进数据称为 --- **入队**    `push`

队列中出数据称为 --- **出队**    `pop`



#### 2.7.2 queue 常用接口



功能描述：栈容器常用的对外接口



构造函数：

- `queue<T> que;`                                 //queue采用模板类实现，queue对象的默认构造形式
- `queue(const queue &que);`            //拷贝构造函数

赋值操作：

- `queue& operator=(const queue &que);`           //重载等号操作符

数据存取：

- `push(elem);`                             //往队尾添加元素
- `pop();`                                      //从队头移除第一个元素
- `back();`                                    //返回最后一个元素
- `front(); `                                  //返回第一个元素

大小操作：

- `empty();`            //判断堆栈是否为空
- `size(); `              //返回栈的大小

总结：

- 入队   --- push
- 出队   --- pop
- 返回队头元素   --- front
- 返回队尾元素   --- back
- 判断队是否为空   --- empty
- 返回队列大小   --- size

### 2.8 list容器

#### 2.8.1 list基本概念

**功能**：将数据进行链式存储

**链表**(list)是一种物理存储单元上非连续的存储结构，数据元素的逻辑顺序是通过链表中的指针链接实现的



链表的组成：链表由一系列**结点**组成



结点的组成：一个是存储数据元素的**数据域**，另一个是存储下一个结点地址的**指针域**



STL中的链表是一个双向循环链表

由于链表的存储方式并不是连续的内存空间，因此链表list中的迭代器只支持前移和后移，属于**双向迭代器**



list的优点：

* 采用动态存储分配，不会造成内存浪费和溢出
* 链表执行插入和删除操作十分方便，修改指针即可，不需要移动大量元素

list的缺点：

* 链表灵活，但是空间(指针域) 和 时间（遍历）额外耗费较大



List有一个重要的性质，插入操作和删除操作都不会造成原有list迭代器的失效，这在vector是不成立的。



总结：STL中**List和vector是两个最常被使用的容器**，各有优缺点



#### 2.8.2 list构造函数

**功能描述：**

* 创建list容器



**函数原型：**

* `list<T> lst;`                               //list采用采用模板类实现,对象的默认构造形式：
* `list(beg,end);`                           //构造函数将[beg, end)区间中的元素拷贝给本身。
* `list(n,elem);`                             //构造函数将n个elem拷贝给本身。
* `list(const list &lst);`            //拷贝构造函数。

#### 2.8.3 list 赋值和交换

**功能描述：**

* 给list容器进行赋值，以及交换list容器

**函数原型：**

* `assign(beg, end);`            //将[beg, end)区间中的数据拷贝赋值给本身。
* `assign(n, elem);`              //将n个elem拷贝赋值给本身。
* `list& operator=(const list &lst);`         //重载等号操作符
* `swap(lst);`                         //将lst与本身的元素互换。



#### 2.8.4 list 大小操作

**功能描述：**

* 对list容器的大小进行操作



**函数原型：**

* `size(); `                             //返回容器中元素的个数

* `empty(); `                           //判断容器是否为空

* `resize(num);`                   //重新指定容器的长度为num，若容器变长，则以默认值填充新位置。

  ​					    //如果容器变短，则末尾超出容器长度的元素被删除。

* `resize(num, elem); `       //重新指定容器的长度为num，若容器变长，则以elem值填充新位置。



#### 2.8.5 list 插入和删除

**功能描述：**

* 对list容器进行数据的插入和删除



**函数原型：**

* push_back(elem);//在容器尾部加入一个元素
* pop_back();//删除容器中最后一个元素
* push_front(elem);//在容器开头插入一个元素
* pop_front();//从容器开头移除第一个元素
* insert(pos,elem);//在pos位置插elem元素的拷贝，返回新数据的位置。
* insert(pos,n,elem);//在pos位置插入n个elem数据，无返回值。
* insert(pos,beg,end);//在pos位置插入[beg,end)区间的数据，无返回值。
* clear();//移除容器的所有数据
* erase(beg,end);//删除[beg,end)区间的数据，返回下一个数据的位置。
* erase(pos);//删除pos位置的数据，返回下一个数据的位置。
* remove(elem);//删除容器中所有与elem值匹配的元素。



#### 2.8.6 list 数据存取

**功能描述：**

* 对list容器中数据进行存取



**函数原型：**

* `front();`        //返回第一个元素。
* `back();`         //返回最后一个元素。
* list容器中不可以通过[]或者at方式访问数据



#### 2.8.7 list 反转和排序

**功能描述：**

* 将容器中的元素反转，以及将容器中的数据进行排序



**函数原型：**

* `reverse();`   //反转链表
* `sort();`        //链表排序



### 2.9 set/multiset容器

#### 2.9.1 set基本概念

**简介：**

* 所有元素都会在插入时自动被排序





**本质：**

* set/multiset属于**关联式容器**，底层结构是用**二叉树**实现。





**set和multiset区别**：

* set不允许容器中有重复的元素

* multiset允许容器中有重复的元素

  

#### 2.9.2 set构造和赋值

构造：

* `set<T> st;`   //默认构造函数;
* `set(const set &st);`     //拷贝构造函数

赋值：

* `set& operator=(const set &st);`   //重载等号赋值



总结：

* set容器插入数据时用insert
* set容器插入数据的数据会自动排序

#### 2.9.3 set大小和交换

**功能描述：**

* 统计set容器大小以及交换set容器



**函数原型：**

* `size();`          //返回容器中元素的数目
* `empty();`        //判断容器是否为空
* `swap(st);`      //交换两个集合容器



#### 2.9.4 set插入和删除

**功能描述：**

* set容器进行插入数据和删除数据

**函数原型：**

* `insert(elem);`           //在容器中插入元素。
* `clear();`                    //清除所有元素
* `erase(pos);`              //删除pos迭代器所指的元素，返回下一个元素的迭代器。
* `erase(beg, end);`    //删除区间[beg,end)的所有元素 ，返回下一个元素的迭代器。
* `erase(elem);`            //删除容器中值为elem的元素。

总结：

* 插入   --- insert
* 删除   --- erase
* 清空   --- clear



#### 2.9.5 set查找和统计

**功能描述：**

* 对set容器进行查找数据以及统计数据



**函数原型：**

* `find(key);`                  //查找key是否存在,若存在，返回该键的元素的迭代器；若不存在，返回set.end();

```c++
//如何判断找到了？
set<int>::iterator pos = s1.find(30);
if(pos!=s1.end()){
    cout<<"找到了"<<endl;
}
else{
    cout<<"没找到"<<endl;
}
```



* `count(key);`                //统计key的元素个数 对于set只能是0或者1 因为set不允许重复元素

#### 2.9.6 set和multiset区别

**学习目标：**

* 掌握set和multiset的区别



**区别：**

* set不可以插入重复数据，而multiset可以

* **set插入数据的同时会返回插入结果，表示插入是否成功**

  ```c ++
  set<int>s;
  pair<set<int>::iterator,bool>ret = s.insert(10);//set插入时是有返回值的，有两部分组成，一部分是指向插入位置的指针，一部分是返回是否插入成功了
  if(ret.second){
      cout<<"插入成功了"<<endl;
  }
  else{
      cout<<"插入失败了"<<endl;
  }
  ```

  

* **multiset不会检测数据，因此可以插入重复数据**

​			multiset 插入时返回的只有迭代器，没有bool值

#### 2.9.7 pair对组创建

**功能描述：**

* 成对出现的数据，利用对组可以返回两个数据

**两种创建方式**：

* `pair<type,type> p(value1,value2);`
* `pair<type,type> p = make_pair(value1,value2);`



```c++
//pair 对组创建
void test01(){
    //第一种方式;
    pair<string,int> p1("Tom",20);
    
    //第二种方式；
	pair<string,int> p2 = make_pair("Jerry",18);
    
    cout<<p1.first<<endl;//利用此方法访问对组中的某一元素
}
```

#### 2.9.8 set容器排序

学习目标：

* set容器默认排序规则为从小到大，掌握如何改变排序规则



主要技术点：

* 利用仿函数，可以改变排序规则





**示例一**   set存放内置数据类型

```C++
#include <set>

class MyCompare 
{
public:
	bool operator()(int v1, int v2) {
		return v1 > v2;
	}
};
void test01() 
{    
	set<int> s1;
	s1.insert(10);
	s1.insert(40);
	s1.insert(20);
	s1.insert(30);
	s1.insert(50);

	//默认从小到大
	for (set<int>::iterator it = s1.begin(); it != s1.end(); it++) {
		cout << *it << " ";
	}
	cout << endl;

	//指定排序规则
	set<int,MyCompare> s2;
	s2.insert(10);
	s2.insert(40);
	s2.insert(20);
	s2.insert(30);
	s2.insert(50);

	for (set<int, MyCompare>::iterator it = s2.begin(); it != s2.end(); it++) {
		cout << *it << " ";
	}
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

总结：利用仿函数可以指定set容器的排序规则



**示例二** set存放自定义数据类型

```C++
#include <set>
#include <string>

class Person
{
public:
	Person(string name, int age)
	{
		this->m_Name = name;
		this->m_Age = age;
	}

	string m_Name;
	int m_Age;

};
class comparePerson
{
public:
	bool operator()(const Person& p1, const Person &p2)
	{
		//按照年龄进行排序  降序
		return p1.m_Age > p2.m_Age;
	}
};

void test01()
{
	set<Person, comparePerson> s;

	Person p1("刘备", 23);
	Person p2("关羽", 27);
	Person p3("张飞", 25);
	Person p4("赵云", 21);

	s.insert(p1);
	s.insert(p2);
	s.insert(p3);
	s.insert(p4);

	for (set<Person, comparePerson>::iterator it = s.begin(); it != s.end(); it++)
	{
		cout << "姓名： " << it->m_Name << " 年龄： " << it->m_Age << endl;
	}
}
int main() {

	test01();

	system("pause");

	return 0;
}
```

总结：

对于自定义数据类型，set必须指定排序规则才可以插入数据



### 2.10 map/multimap容器

#### 2.10.1map基本概念

**简介：**

* map中所有元素都是pair
* pair中第一个元素为**key（键值）**，起到索引作用，第二个元素为**value（实值）**
* 所有元素都会根据元素的**键值**自动排序



**本质：**

* map/multimap属于**关联式容器**，底层结构是用二叉树实现。



**优点：**

* 可以根据key值快速找到value值



map和multimap**区别**：

- map不允许容器中有重复key值元素
- multimap允许容器中有重复key值元素



#### 2.10.2  map构造和赋值

**功能描述：**

* 对map容器进行构造和赋值操作

**函数原型：**

**构造：**

* `map<T1, T2> mp;`                     //map默认构造函数: 
* `map(const map &mp);`             //拷贝构造函数



**赋值：**

* `map& operator=(const map &mp);`    //重载等号操作符



#### 2.10.3 map大小和交换

**功能描述：**

* 统计map容器大小以及交换map容器





函数原型：

- `size();`          //返回容器中元素的数目
- `empty();`        //判断容器是否为空
- `swap(st);`      //交换两个集合容器



#### 2.10.4 map插入和删除

**功能描述：**

- map容器进行插入数据和删除数据





**函数原型：**

- `insert(elem);`           //在容器中插入元素。
- `clear();`                    //清除所有元素
- `erase(pos);`              //删除pos迭代器所指的元素，返回下一个元素的迭代器。
- `erase(beg, end);`    //删除区间[beg,end)的所有元素 ，返回下一个元素的迭代器。
- `erase(key);`            //删除容器中值为key的元素。



#### 2.10.5 map查找和统计

**功能描述：**

- 对map容器进行查找数据以及统计数据



**函数原型：**

- `find(key);`                  //查找key是否存在,若存在，返回该键的元素的迭代器；若不存在，返回set.end();
- `count(key);`                //统计key的元素个数



#### 2.10.6 map容器排序

**学习目标：**

- map容器默认排序规则为 按照key值进行 从小到大排序，掌握如何改变排序规则





**主要技术点:**

- 利用仿函数，可以改变排序规则





**示例：**

```C++
#include <map>

class MyCompare {
public:
	bool operator()(int v1, int v2) {
		return v1 > v2;
	}
};

void test01() 
{
	//默认从小到大排序
	//利用仿函数实现从大到小排序
	map<int, int, MyCompare> m;

	m.insert(make_pair(1, 10));
	m.insert(make_pair(2, 20));
	m.insert(make_pair(3, 30));
	m.insert(make_pair(4, 40));
	m.insert(make_pair(5, 50));

	for (map<int, int, MyCompare>::iterator it = m.begin(); it != m.end(); it++) {
		cout << "key:" << it->first << " value:" << it->second << endl;
	}
}
int main() {

	test01();

	system("pause");

	return 0;
}
```

总结：

* 利用仿函数可以指定map容器的排序规则
* 对于自定义数据类型，map必须要指定排序规则,同set容器

### 2.11 案例-员工分组

#### 2.11.1 案例描述

* 公司今天招聘了10个员工（ABCDEFGHIJ），10名员工进入公司之后，需要指派员工在那个部门工作
* 员工信息有: 姓名  工资组成；部门分为：策划、美术、研发
* 随机给10名员工分配部门和工资
* 通过multimap进行信息的插入  key(部门编号) value(员工)
* 分部门显示员工信息





#### 2.11.2 实现步骤

1. 创建10名员工，放到vector中
2. 遍历vector容器，取出每个员工，进行随机分组
3. 分组后，将员工部门编号作为key，具体员工作为value，放入到multimap容器中
4. 分部门显示员工信息



实现：

```c++
#include <iostream>
#include <vector>
#include <map>
#include <string>
#include <cmath>

using namespace std;

class Workers {
public:
	string name;
	int post;
	int wages;
	Workers(string temp_name, int temp_post, int temp_wages) {
		name = temp_name;
		post = temp_post;
		wages = temp_wages;
	}
};

void input_workers(vector<Workers> &p) {
	cout << "请输入员工的姓名：" << endl;
	string temp_name;
	cin >> temp_name;
	int temp_post = rand()%3+1;
	int temp_wages = rand() % 10000 + 10000;
	p.push_back(Workers(temp_name, temp_post, temp_wages));
}

void recute_workers(vector<Workers> &w) {

	for (int i = 0; i < 10; i++) {
		input_workers(w);
	}
}

void test01() {
	vector<Workers> w;
	recute_workers(w);
	multimap<int, Workers> w_sort;
	for (vector<Workers>::iterator p = w.begin(); p != w.end(); p++) {
		w_sort.insert(make_pair(p->post, *p));
	}
	
	for (multimap<int, Workers>::iterator q = w_sort.begin(); q != w_sort.end(); q++) {
		cout << (*q).first << (*q).second.name << (*q).second.wages << endl;
	}
}

int main() {
	test01();
	return 0;
}
```

## 3. STL函数对象

### 3.1 函数对象

#### 3.1.1 函数对象的概念

**概念**：

* 重载**函数调用操作符**的类，其对象称之为**函数对象**
* **函数对象**使用重载的()时，其行为类似函数调用，也叫作**仿函数**

**本质**：

函数对象(仿函数)是一个**类**，不是一个函数

#### 3.1.2 函数对象使用

**特点**：

* 函数对象在使用时，可以像普通函数那样调用，可以有参数，可以有返回值
* 函数对象超出普通函数的概念，函数对象可以有自己的状态
* 函数对象可以作为参数传递

```c++
#include <iostream>
#include <string>
using namespace std;

class MyAdd {
public:
	int operator()(int v1,int v2){
		return v1 + v2;
	}
};

//2.函数对象超出普通函数的概念，函数对象可以有自己的状态
class MyPrint {
public:
	MyPrint() {
		this->count = 0;
	}
	void operator() (string test){
		cout << test << endl;
		count++;
	}

	int count;//函数对象内部可以用成员属性记录自己的状态
};

//1.函数对象在使用时，可以像普通函数那样调用，可以有参数，可以有返回值
void test01() {
	MyAdd myAdd;
	cout << myAdd(10, 10) << endl;
}

void test02() {
	MyPrint myPrint;
	myPrint("hello world!");
	myPrint("hello world!");
	myPrint("hello world!");
	myPrint("hello world!");
	cout << "调用次数：" << myPrint.count << endl;
}

//3.函数对象可以作为参数传递
void doPrint(MyPrint& mp, string test) {
	mp(test);
}
void test03() {
	MyPrint myPrint;
	doPrint(myPrint, "hello world!");
}
int main() {
	test01();
	test02();
	test03();
	return 0;
}
```

### 3.2 谓词

#### 3.2.1 谓词概念

**概念**：

* 返回bool类型的仿函数称为**谓词**
* 如果operator()接受一个参数，叫做一元谓词
* 如果operator()接受两个参数，叫做二元谓词



#### 3.2.2 一元谓词

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

//仿函数 返回值类型是bool数据类型，称为谓词

class GreaterFive{
public:
    //一元谓词
    bool operator()(int val) { 
        return val > 5;
    }

};
void test01() {
    vector<int>v;
    for (int i = 0; i < 10; i++) {
        v.push_back(i);
    }

    //查找容器中有没有大于5的数字
    vector<int>::iterator it =  find_if(v.begin(), v.end(),GreaterFive());//第三个参数：匿名函数对象
    cout << *it << endl;
}

int main() {
    test01();
    return 0;
}

```

#### 3.2.3 二元谓词

```c++
#include<iostream>
using namespace std;
#include<vector>
#include<algorithm>

//二元谓词
class MyCompare {
public:
	bool operator()(int val1, int val2) {
		return val1 > val2;
	}

};

void  test01() {
	vector<int> v;
	v.push_back(10);
	v.push_back(30);
	v.push_back(20);
	v.push_back(40);

	sort(v.begin(),v.end());
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++) {
		cout << *it << endl;
	}

	cout << endl;

	sort(v.begin(), v.end(), MyCompare());
	for (vector<int>::iterator it = v.begin(); it != v.end(); it++) {
		cout << *it << endl;
	}

}

int main() {
	test01();
	return 0;
}
```

### 3.3 内建函数对象

#### 3.3.1 内建函数对象意义

**概念**：

* STL内建了一些函数对象

**分类**：

* 算数仿函数
* 关系仿函数
* 逻辑仿函数

**用法**：

*  这些仿函数所产生的对象，用法和一般函数完全相同
* 使用内建函数对象。需要引入头文件`#include<functional>`



#### 3.3.2 算数仿函数

**功能描述：**

* 实现四则运算
* 其中negate是一元运算，其他都是二元运算



**仿函数原型：**

* `template<class T> T plus<T>`                //加法仿函数
* `template<class T> T minus<T>`              //减法仿函数
* `template<class T> T multiplies<T>`    //乘法仿函数
* `template<class T> T divides<T>`         //除法仿函数
* `template<class T> T modulus<T>`         //取模仿函数
* `template<class T> T negate<T>`           //取反仿函数



**示例：**

```C++
#include<iostream>
#include<functional> //内建函数对象头文件
using namespace std;

//内建函数对象 算数仿函数

//negate 一元仿函数 取反仿函数
void test01() {
	negate<int>n;//模板类
	cout << n(50) << endl;
}

void test02() {
	plus<int> m;
	cout << m(10, 20) << endl;
}

int main() {
	test01();
	test02();
	return 0;
}
```

总结：使用内建函数对象时，需要引入头文件 `#include <functional>`



#### 3.3.3 关系仿函数

**功能描述：**

- 实现关系对比



**仿函数原型：**

* `template<class T> bool equal_to<T>`                    //等于
* `template<class T> bool not_equal_to<T>`            //不等于
* `template<class T> bool greater<T>`                      //大于
* `template<class T> bool greater_equal<T>`          //大于等于
* `template<class T> bool less<T>`                           //小于
* `template<class T> bool less_equal<T>`               //小于等于



**示例：**

```C++
#include <functional>
#include <vector>
#include <algorithm>

class MyCompare
{
public:
	bool operator()(int v1,int v2)
	{
		return v1 > v2;
	}
};
void test01()
{
	vector<int> v;

	v.push_back(10);
	v.push_back(30);
	v.push_back(50);
	v.push_back(40);
	v.push_back(20);

	for (vector<int>::iterator it = v.begin(); it != v.end(); it++) {
		cout << *it << " ";
	}
	cout << endl;

	//自己实现仿函数
	//sort(v.begin(), v.end(), MyCompare());
	//STL内建仿函数  大于仿函数
	sort(v.begin(), v.end(), greater<int>());

	for (vector<int>::iterator it = v.begin(); it != v.end(); it++) {
		cout << *it << " ";
	}
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

总结：关系仿函数中最常用的就是greater<>大于



#### 3.3.4 逻辑仿函数

**功能描述：**

- 实现逻辑运算



**函数原型：**

* `template<class T> bool logical_and<T>`              //逻辑与
* `template<class T> bool logical_or<T>`                //逻辑或
* `template<class T> bool logical_not<T>`              //逻辑非



**示例：**

```C++
#include <vector>
#include <functional>
#include <algorithm>
void test01()
{
	vector<bool> v;
	v.push_back(true);
	v.push_back(false);
	v.push_back(true);
	v.push_back(false);

	for (vector<bool>::iterator it = v.begin();it!= v.end();it++)
	{
		cout << *it << " ";
	}
	cout << endl;

	//逻辑非  将v容器搬运到v2中，并执行逻辑非运算
	vector<bool> v2;
	v2.resize(v.size());
	transform(v.begin(), v.end(),  v2.begin(), logical_not<bool>());
	for (vector<bool>::iterator it = v2.begin(); it != v2.end(); it++)
	{
		cout << *it << " ";
	}
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

总结：逻辑仿函数实际应用较少，了解即可

## 4 STL- 常用算法



**概述**:

* 算法主要是由头文件`<algorithm>` `<functional>` `<numeric>`组成。



* `<algorithm>`是所有STL头文件中最大的一个，范围涉及到比较、 交换、查找、遍历操作、复制、修改等等
* `<numeric>`体积很小，只包括几个在序列上面进行简单数学运算的模板函数
* `<functional>`定义了一些模板类,用以声明函数对象。





### 4.1 常用遍历算法

**学习目标：**

* 掌握常用的遍历算法



**算法简介：**

* `for_each`     //遍历容器
* `transform`   //搬运容器到另一个容器中





#### 4.1.1 for_each

**功能描述：**

* 实现遍历容器

**函数原型：**

* `for_each(iterator beg, iterator end, _func);  `

  // 遍历算法 遍历容器元素

  // beg 开始迭代器

  // end 结束迭代器

  // _func 函数或者函数对象



**示例：**

```C++
#include <algorithm>
#include <vector>

//普通函数
void print01(int val) 
{
	cout << val << " ";
}
//函数对象
class print02 
{
 public:
	void operator()(int val) 
	{
		cout << val << " ";
	}
};

//for_each算法基本用法
void test01() {

	vector<int> v;
	for (int i = 0; i < 10; i++) 
	{
		v.push_back(i);
	}

	//遍历算法
	for_each(v.begin(), v.end(), print01);
	cout << endl;

	for_each(v.begin(), v.end(), print02());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**for_each在实际开发中是最常用遍历算法，需要熟练掌握









#### 4.1.2 transform

**功能描述：**

* 搬运容器到另一个容器中

**函数原型：**

* `transform(iterator beg1, iterator end1, iterator beg2, _func);`

//beg1 源容器开始迭代器

//end1 源容器结束迭代器

//beg2 目标容器开始迭代器

//_func 函数或者函数对象



**示例：**

```C++
#include<vector>
#include<algorithm>

//常用遍历算法  搬运 transform

class TransForm
{
public:
	int operator()(int val)
	{
		return val;
	}

};

class MyPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int>v;
	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}

	vector<int>vTarget; //目标容器

	vTarget.resize(v.size()); // 目标容器需要提前开辟空间

	transform(v.begin(), v.end(), vTarget.begin(), TransForm());

	for_each(vTarget.begin(), vTarget.end(), MyPrint());
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：** 搬运的目标容器必须要提前开辟空间，否则无法正常搬运







### 4.2 常用查找算法

学习目标：

- 掌握常用的查找算法





**算法简介：**

- `find`                     //查找元素
- `find_if`               //按条件查找元素
- `adjacent_find`    //查找相邻重复元素
- `binary_search`    //二分查找法
- `count`                   //统计元素个数
- `count_if`             //按条件统计元素个数




#### 4.2.1 find

**功能描述：**

* 查找指定元素，找到返回指定元素的迭代器，找不到返回结束迭代器end()



**函数原型：**

- `find(iterator beg, iterator end, value);  `

  // 按值查找元素，找到返回指定位置迭代器，找不到返回结束迭代器位置

  // beg 开始迭代器

  // end 结束迭代器

  // value 查找的元素





**示例：**

```C++
#include <algorithm>
#include <vector>
#include <string>
void test01() {

	vector<int> v;
	for (int i = 0; i < 10; i++) {
		v.push_back(i + 1);
	}
	//查找容器中是否有 5 这个元素
	vector<int>::iterator it = find(v.begin(), v.end(), 5);
	if (it == v.end()) 
	{
		cout << "没有找到!" << endl;
	}
	else 
	{
		cout << "找到:" << *it << endl;
	}
}

class Person {
public:
	Person(string name, int age) 
	{
		this->m_Name = name;
		this->m_Age = age;
	}
	//重载==
	bool operator==(const Person& p) 
	{
		if (this->m_Name == p.m_Name && this->m_Age == p.m_Age) 
		{
			return true;
		}
		return false;
	}

public:
	string m_Name;
	int m_Age;
};

void test02() {

	vector<Person> v;

	//创建数据
	Person p1("aaa", 10);
	Person p2("bbb", 20);
	Person p3("ccc", 30);
	Person p4("ddd", 40);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);

	vector<Person>::iterator it = find(v.begin(), v.end(), p2);
	if (it == v.end()) 
	{
		cout << "没有找到!" << endl;
	}
	else 
	{
		cout << "找到姓名:" << it->m_Name << " 年龄: " << it->m_Age << endl;
	}
}
```

总结： 利用find可以在容器中找指定的元素，返回值是**迭代器**













#### 4.2.2 find_if

**功能描述：**

* 按条件查找元素

**函数原型：**

- `find_if(iterator beg, iterator end, _Pred);  `

  // 按值查找元素，找到返回指定位置迭代器，找不到返回结束迭代器位置

  // beg 开始迭代器

  // end 结束迭代器

  // _Pred 函数或者谓词（返回bool类型的仿函数）



**示例：**

```C++
#include <algorithm>
#include <vector>
#include <string>

//内置数据类型
class GreaterFive
{
public:
	bool operator()(int val)
	{
		return val > 5;
	}
};

void test01() {

	vector<int> v;
	for (int i = 0; i < 10; i++) {
		v.push_back(i + 1);
	}

	vector<int>::iterator it = find_if(v.begin(), v.end(), GreaterFive());
	if (it == v.end()) {
		cout << "没有找到!" << endl;
	}
	else {
		cout << "找到大于5的数字:" << *it << endl;
	}
}

//自定义数据类型
class Person {
public:
	Person(string name, int age)
	{
		this->m_Name = name;
		this->m_Age = age;
	}
public:
	string m_Name;
	int m_Age;
};

class Greater20
{
public:
	bool operator()(Person &p)
	{
		return p.m_Age > 20;
	}

};

void test02() {

	vector<Person> v;

	//创建数据
	Person p1("aaa", 10);
	Person p2("bbb", 20);
	Person p3("ccc", 30);
	Person p4("ddd", 40);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);

	vector<Person>::iterator it = find_if(v.begin(), v.end(), Greater20());
	if (it == v.end())
	{
		cout << "没有找到!" << endl;
	}
	else
	{
		cout << "找到姓名:" << it->m_Name << " 年龄: " << it->m_Age << endl;
	}
}

int main() {

	//test01();

	test02();

	system("pause");

	return 0;
}
```

总结：find_if按条件查找使查找更加灵活，提供的仿函数可以改变不同的策略















#### 4.2.3 adjacent_find

**功能描述：**

* 查找相邻重复元素



**函数原型：**

- `adjacent_find(iterator beg, iterator end);  `

  // 查找相邻重复元素,返回相邻元素的第一个位置的迭代器

  // beg 开始迭代器

  // end 结束迭代器

  



**示例：**

```C++
#include <algorithm>
#include <vector>

void test01()
{
	vector<int> v;
	v.push_back(1);
	v.push_back(2);
	v.push_back(5);
	v.push_back(2);
	v.push_back(4);
	v.push_back(4);
	v.push_back(3);

	//查找相邻重复元素
	vector<int>::iterator it = adjacent_find(v.begin(), v.end());
	if (it == v.end()) {
		cout << "找不到!" << endl;
	}
	else {
		cout << "找到相邻重复元素为:" << *it << endl;
	}
}
```

总结：面试题中如果出现查找相邻重复元素，记得用STL中的adjacent_find算法









#### 4.2.4 binary_search

**功能描述：**

* 查找指定元素是否存在



**函数原型：**

- `bool binary_search(iterator beg, iterator end, value);  `

  // 查找指定的元素，查到 返回true  否则false

  // 注意: 在**无序序列中不可用**

  // beg 开始迭代器

  // end 结束迭代器

  // value 查找的元素





**示例：**

```C++
#include <algorithm>
#include <vector>

void test01()
{
	vector<int>v;

	for (int i = 0; i < 10; i++)
	{
		v.push_back(i);
	}
	//二分查找
	bool ret = binary_search(v.begin(), v.end(),2);
	if (ret)
	{
		cout << "找到了" << endl;
	}
	else
	{
		cout << "未找到" << endl;
	}
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**二分查找法查找效率很高，值得注意的是查找的容器中元素必须的有序序列









#### 4.2.5 count

**功能描述：**

* 统计元素个数



**函数原型：**

- `count(iterator beg, iterator end, value);  `

  // 统计元素出现次数

  // beg 开始迭代器

  // end 结束迭代器

  // value 统计的元素





**示例：**

```C++
#include <algorithm>
#include <vector>

//内置数据类型
void test01()
{
	vector<int> v;
	v.push_back(1);
	v.push_back(2);
	v.push_back(4);
	v.push_back(5);
	v.push_back(3);
	v.push_back(4);
	v.push_back(4);

	int num = count(v.begin(), v.end(), 4);

	cout << "4的个数为： " << num << endl;
}

//自定义数据类型
class Person
{
public:
	Person(string name, int age)
	{
		this->m_Name = name;
		this->m_Age = age;
	}
	bool operator==(const Person & p)
	{
		if (this->m_Age == p.m_Age)
		{
			return true;
		}
		else
		{
			return false;
		}
	}
	string m_Name;
	int m_Age;
};

void test02()
{
	vector<Person> v;

	Person p1("刘备", 35);
	Person p2("关羽", 35);
	Person p3("张飞", 35);
	Person p4("赵云", 30);
	Person p5("曹操", 25);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);
	v.push_back(p5);
    
    Person p("诸葛亮",35);

	int num = count(v.begin(), v.end(), p);
	cout << "num = " << num << endl;
}
int main() {

	//test01();

	test02();

	system("pause");

	return 0;
}
```

**总结：** 统计自定义数据类型时候，需要配合重载 `operator==`

















#### 4.2.6 count_if

**功能描述：**

* 按条件统计元素个数

**函数原型：**

- `count_if(iterator beg, iterator end, _Pred);  `

  // 按条件统计元素出现次数

  // beg 开始迭代器

  // end 结束迭代器

  // _Pred 谓词

  

**示例：**

```C++
#include <algorithm>
#include <vector>

class Greater4
{
public:
	bool operator()(int val)
	{
		return val >= 4;
	}
};

//内置数据类型
void test01()
{
	vector<int> v;
	v.push_back(1);
	v.push_back(2);
	v.push_back(4);
	v.push_back(5);
	v.push_back(3);
	v.push_back(4);
	v.push_back(4);

	int num = count_if(v.begin(), v.end(), Greater4());

	cout << "大于4的个数为： " << num << endl;
}

//自定义数据类型
class Person
{
public:
	Person(string name, int age)
	{
		this->m_Name = name;
		this->m_Age = age;
	}

	string m_Name;
	int m_Age;
};

class AgeLess35
{
public:
	bool operator()(const Person &p)
	{
		return p.m_Age < 35;
	}
};
void test02()
{
	vector<Person> v;

	Person p1("刘备", 35);
	Person p2("关羽", 35);
	Person p3("张飞", 35);
	Person p4("赵云", 30);
	Person p5("曹操", 25);

	v.push_back(p1);
	v.push_back(p2);
	v.push_back(p3);
	v.push_back(p4);
	v.push_back(p5);

	int num = count_if(v.begin(), v.end(), AgeLess35());
	cout << "小于35岁的个数：" << num << endl;
}


int main() {

	//test01();

	test02();

	system("pause");

	return 0;
}
```

**总结：**按值统计用count，按条件统计用count_if













### 4.3 常用排序算法

**学习目标：**

- 掌握常用的排序算法

**算法简介：**

- `sort`             //对容器内元素进行排序
- `random_shuffle`   //洗牌   指定范围内的元素随机调整次序
- `merge `           // 容器元素合并，并存储到另一容器中
- `reverse`       // 反转指定范围的元素





#### 4.3.1 sort

**功能描述：**

* 对容器内元素进行排序





**函数原型：**

- `sort(iterator beg, iterator end, _Pred);  `

  // 按值查找元素，找到返回指定位置迭代器，找不到返回结束迭代器位置

  //  beg    开始迭代器

  //  end    结束迭代器

  // _Pred  谓词





**示例：**

```c++
#include <algorithm>
#include <vector>

void myPrint(int val)
{
	cout << val << " ";
}

void test01() {
	vector<int> v;
	v.push_back(10);
	v.push_back(30);
	v.push_back(50);
	v.push_back(20);
	v.push_back(40);

	//sort默认从小到大排序
	sort(v.begin(), v.end());
	for_each(v.begin(), v.end(), myPrint);
	cout << endl;

	//从大到小排序
	sort(v.begin(), v.end(), greater<int>());
	for_each(v.begin(), v.end(), myPrint);
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**sort属于开发中最常用的算法之一，需熟练掌握













#### 4.3.2 random_shuffle

**功能描述：**

* 洗牌   指定范围内的元素随机调整次序



**函数原型：**

- `random_shuffle(iterator beg, iterator end);  `

  // 指定范围内的元素随机调整次序

  // beg 开始迭代器

  // end 结束迭代器

  

**示例：**

```c++
#include <algorithm>
#include <vector>
#include <ctime>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	srand((unsigned int)time(NULL));
	vector<int> v;
	for(int i = 0 ; i < 10;i++)
	{
		v.push_back(i);
	}
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;

	//打乱顺序
	random_shuffle(v.begin(), v.end());
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**random_shuffle洗牌算法比较实用，使用时记得加随机数种子













#### 4.3.3 merge

**功能描述：**

* 两个容器元素合并，并存储到另一容器中



**函数原型：**

- `merge(iterator beg1, iterator end1, iterator beg2, iterator end2, iterator dest);  `

  // 容器元素合并，并存储到另一容器中

  // 注意: 两个容器必须是**有序的**

  // beg1   容器1开始迭代器
  // end1   容器1结束迭代器
  // beg2   容器2开始迭代器
  // end2   容器2结束迭代器
  // dest    目标容器开始迭代器

  

**示例：**

```c++
#include <algorithm>
#include <vector>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v1;
	vector<int> v2;
	for (int i = 0; i < 10 ; i++) 
    {
		v1.push_back(i);
		v2.push_back(i + 1);
	}

	vector<int> vtarget;
	//目标容器需要提前开辟空间
	vtarget.resize(v1.size() + v2.size());
	//合并  需要两个有序序列
	merge(v1.begin(), v1.end(), v2.begin(), v2.end(), vtarget.begin());
	for_each(vtarget.begin(), vtarget.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**merge合并的两个容器必须的有序序列











#### 4.3.4 reverse

**功能描述：**

* 将容器内元素进行反转



**函数原型：**

- `reverse(iterator beg, iterator end);  `

  // 反转指定范围的元素

  // beg 开始迭代器

  // end 结束迭代器

  

**示例：**

```c++
#include <algorithm>
#include <vector>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v;
	v.push_back(10);
	v.push_back(30);
	v.push_back(50);
	v.push_back(20);
	v.push_back(40);

	cout << "反转前： " << endl;
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;

	cout << "反转后： " << endl;

	reverse(v.begin(), v.end());
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**reverse反转区间内元素，面试题可能涉及到









### 4.4 常用拷贝和替换算法

**学习目标：**

- 掌握常用的拷贝和替换算法

**算法简介：**

- `copy`                      // 容器内指定范围的元素拷贝到另一容器中
- `replace`                // 将容器内指定范围的旧元素修改为新元素
- `replace_if `          // 容器内指定范围满足条件的元素替换为新元素
- `swap`                     // 互换两个容器的元素




#### 4.4.1 copy

**功能描述：**

* 容器内指定范围的元素拷贝到另一容器中



**函数原型：**

- `copy(iterator beg, iterator end, iterator dest);  `

  // 按值查找元素，找到返回指定位置迭代器，找不到返回结束迭代器位置

  // beg  开始迭代器

  // end  结束迭代器

  // dest 目标起始迭代器



**示例：**

```c++
#include <algorithm>
#include <vector>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v1;
	for (int i = 0; i < 10; i++) {
		v1.push_back(i + 1);
	}
	vector<int> v2;
	v2.resize(v1.size());
	copy(v1.begin(), v1.end(), v2.begin());

	for_each(v2.begin(), v2.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**利用copy算法在拷贝时，目标容器记得提前开辟空间















#### 4.4.2 replace

**功能描述：**

* 将容器内指定范围的旧元素修改为新元素



**函数原型：**

- `replace(iterator beg, iterator end, oldvalue, newvalue);  `

  // 将区间内旧元素 替换成 新元素

  // beg 开始迭代器

  // end 结束迭代器

  // oldvalue 旧元素

  // newvalue 新元素



**示例：**

```c++
#include <algorithm>
#include <vector>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v;
	v.push_back(20);
	v.push_back(30);
	v.push_back(20);
	v.push_back(40);
	v.push_back(50);
	v.push_back(10);
	v.push_back(20);

	cout << "替换前：" << endl;
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;

	//将容器中的20 替换成 2000
	cout << "替换后：" << endl;
	replace(v.begin(), v.end(), 20,2000);
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**replace会替换区间内满足条件的元素













#### 4.4.3 replace_if

**功能描述:**  

* 将区间内满足条件的元素，替换成指定元素



**函数原型：**

- `replace_if(iterator beg, iterator end, _pred, newvalue);  `

  // 按条件替换元素，满足条件的替换成指定元素

  // beg 开始迭代器

  // end 结束迭代器

  // _pred 谓词

  // newvalue 替换的新元素



**示例：**

```c++
#include <algorithm>
#include <vector>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

class ReplaceGreater30
{
public:
	bool operator()(int val)
	{
		return val >= 30;
	}

};

void test01()
{
	vector<int> v;
	v.push_back(20);
	v.push_back(30);
	v.push_back(20);
	v.push_back(40);
	v.push_back(50);
	v.push_back(10);
	v.push_back(20);

	cout << "替换前：" << endl;
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;

	//将容器中大于等于的30 替换成 3000
	cout << "替换后：" << endl;
	replace_if(v.begin(), v.end(), ReplaceGreater30(), 3000);
	for_each(v.begin(), v.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**replace_if按条件查找，可以利用仿函数灵活筛选满足的条件







#### 4.4.4 swap

**功能描述：**

* 互换两个容器的元素



**函数原型：**

- `swap(container c1, container c2);  `

  // 互换两个容器的元素

  // c1容器1

  // c2容器2

  

**示例：**

```c++
#include <algorithm>
#include <vector>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v1;
	vector<int> v2;
	for (int i = 0; i < 10; i++) {
		v1.push_back(i);
		v2.push_back(i+100);
	}

	cout << "交换前： " << endl;
	for_each(v1.begin(), v1.end(), myPrint());
	cout << endl;
	for_each(v2.begin(), v2.end(), myPrint());
	cout << endl;

	cout << "交换后： " << endl;
	swap(v1, v2);
	for_each(v1.begin(), v1.end(), myPrint());
	cout << endl;
	for_each(v2.begin(), v2.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**swap交换容器时，注意交换的容器要同种类型













### 4.5 常用算术生成算法

**学习目标：**

- 掌握常用的算术生成算法



**注意：**

* 算术生成算法属于小型算法，使用时包含的头文件为 `#include <numeric>`



**算法简介：**

- `accumulate`      // 计算容器元素累计总和

- `fill`                 // 向容器中添加元素

  

#### 4.5.1 accumulate

**功能描述：**

*  计算区间内 容器元素累计总和



**函数原型：**

- `accumulate(iterator beg, iterator end, value);  `

  // 计算容器元素累计总和

  // beg 开始迭代器

  // end 结束迭代器

  // value 起始值



**示例：**

```c++
#include <numeric>
#include <vector>
void test01()
{
	vector<int> v;
	for (int i = 0; i <= 100; i++) {
		v.push_back(i);
	}

	int total = accumulate(v.begin(), v.end(), 0);

	cout << "total = " << total << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**accumulate使用时头文件注意是 numeric，这个算法很实用



#### 4.5.2 fill

**功能描述：**

* 向容器中填充指定的元素



**函数原型：**

- `fill(iterator beg, iterator end, value);  `

  // 向容器中填充元素

  // beg 开始迭代器

  // end 结束迭代器

  // value 填充的值



**示例：**

```c++
#include <numeric>
#include <vector>
#include <algorithm>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{

	vector<int> v;
	v.resize(10);
	//填充
	fill(v.begin(), v.end(), 100);

	for_each(v.begin(), v.end(), myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：**利用fill可以将容器区间内元素填充为 指定的值





### 4.6 常用集合算法

**学习目标：**

- 掌握常用的集合算法



**算法简介：**

- `set_intersection`          // 求两个容器的交集

- `set_union`                       // 求两个容器的并集

- `set_difference `              // 求两个容器的差集

  



#### 4.6.1 set_intersection

**功能描述：**

* 求两个容器的交集



**函数原型：**

- `set_intersection(iterator beg1, iterator end1, iterator beg2, iterator end2, iterator dest);  `

  // 求两个集合的交集

  // **注意:两个集合必须是有序序列**

  // beg1 容器1开始迭代器
  // end1 容器1结束迭代器
  // beg2 容器2开始迭代器
  // end2 容器2结束迭代器
  // dest 目标容器开始迭代器



**示例：**

```C++
#include <vector>
#include <algorithm>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v1;
	vector<int> v2;
	for (int i = 0; i < 10; i++)
    {
		v1.push_back(i);
		v2.push_back(i+5);
	}

	vector<int> vTarget;
	//取两个里面较小的值给目标容器开辟空间
	vTarget.resize(min(v1.size(), v2.size()));

	//返回目标容器的最后一个元素的迭代器地址
	vector<int>::iterator itEnd = 
        set_intersection(v1.begin(), v1.end(), v2.begin(), v2.end(), vTarget.begin());

	for_each(vTarget.begin(), itEnd, myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：** 

* 求交集的两个集合必须的有序序列
* 目标容器开辟空间需要从**两个容器中取小值**
* set_intersection返回值既是交集中最后一个元素的位置













#### 4.6.2 set_union

**功能描述：**

* 求两个集合的并集



**函数原型：**

- `set_union(iterator beg1, iterator end1, iterator beg2, iterator end2, iterator dest);  `

  // 求两个集合的并集

  // **注意:两个集合必须是有序序列**

  // beg1 容器1开始迭代器
  // end1 容器1结束迭代器
  // beg2 容器2开始迭代器
  // end2 容器2结束迭代器
  // dest 目标容器开始迭代器

  

**示例：**

```C++
#include <vector>
#include <algorithm>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v1;
	vector<int> v2;
	for (int i = 0; i < 10; i++) {
		v1.push_back(i);
		v2.push_back(i+5);
	}

	vector<int> vTarget;
	//取两个容器的和给目标容器开辟空间
	vTarget.resize(v1.size() + v2.size());

	//返回目标容器的最后一个元素的迭代器地址
	vector<int>::iterator itEnd = 
        set_union(v1.begin(), v1.end(), v2.begin(), v2.end(), vTarget.begin());

	for_each(vTarget.begin(), itEnd, myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：** 

- 求并集的两个集合必须的有序序列
- 目标容器开辟空间需要**两个容器相加**
- set_union返回值既是并集中最后一个元素的位置








#### 4.6.3  set_difference

**功能描述：**

* 求两个集合的差集



**函数原型：**

- `set_difference(iterator beg1, iterator end1, iterator beg2, iterator end2, iterator dest);  `

  // 求两个集合的差集

  // **注意:两个集合必须是有序序列**

  // beg1 容器1开始迭代器
  // end1 容器1结束迭代器
  // beg2 容器2开始迭代器
  // end2 容器2结束迭代器
  // dest 目标容器开始迭代器

  

**示例：**

```C++
#include <vector>
#include <algorithm>

class myPrint
{
public:
	void operator()(int val)
	{
		cout << val << " ";
	}
};

void test01()
{
	vector<int> v1;
	vector<int> v2;
	for (int i = 0; i < 10; i++) {
		v1.push_back(i);
		v2.push_back(i+5);
	}

	vector<int> vTarget;
	//取两个里面较大的值给目标容器开辟空间
	vTarget.resize( max(v1.size() , v2.size()));

	//返回目标容器的最后一个元素的迭代器地址
	cout << "v1与v2的差集为： " << endl;
	vector<int>::iterator itEnd = 
        set_difference(v1.begin(), v1.end(), v2.begin(), v2.end(), vTarget.begin());
	for_each(vTarget.begin(), itEnd, myPrint());
	cout << endl;


	cout << "v2与v1的差集为： " << endl;
	itEnd = set_difference(v2.begin(), v2.end(), v1.begin(), v1.end(), vTarget.begin());
	for_each(vTarget.begin(), itEnd, myPrint());
	cout << endl;
}

int main() {

	test01();

	system("pause");

	return 0;
}
```

**总结：** 

- 求差集的两个集合必须的有序序列
- 目标容器开辟空间需要从**两个容器取较大值**
- set_difference返回值既是差集中最后一个元素的位置



## 提高阶段项目：演讲比赛流程管理系统

### 1. 演讲比赛需求

#### 1.1 比赛规则

* 学校举行一场演讲比赛，共有**12个人**参加。**比赛共两轮**，第一轮为淘汰赛，第二轮为决赛。
* 每名选手都有对应的**编号**，如10001~10012
* 比赛方式：**分组比赛，每组6个人**；
* 第一轮分为两个小组，整体按照选手编号进行**抽签**后顺序演讲。
* 十个评委分别给每名选手打分，去除最高分和最低分，求的平均分为本轮选手的成绩
* 当小组演讲完后，淘汰组内排名最后的三个选手，**前三名晋级**，进入下一轮的比赛。
* 第二轮为决赛，**前三名胜出**
* 每轮比赛过后需要**显示晋级选手的信息**

#### 1.2 程序功能

* 开始演讲比赛：完成整届比赛的流程，每个比赛阶段需要给用户一个提示，用户按任意键后继续下一阶段
* 查看往届记录：查看之前比赛前三名结果，每次比赛都会记录到文件中，文件用.csv后缀名保存
* 清空比赛记录：将文件中数据清空
* 退出比赛程序：可以退出当前程序

 
