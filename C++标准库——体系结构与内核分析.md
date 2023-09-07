# C++标准库——体系结构与内核分析
体系结构：六大部件
内核分析：结构如何实现
**目标**：
* Level0:使用C++标准库
* level1:认识C++标准库（胸中自有丘壑）
* level2:**良好**使用C++标准库
* level3:扩充C++标准库（难）

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

