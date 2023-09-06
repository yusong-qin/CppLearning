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
### STL六大部件
容器
分配器
算法
迭代器
适配器
仿函数
六大部件之间的关系：



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
cout<<count_if(vi.begin(),vi.end(),not1(bind2nd(less<int>(),40)));
    return 0;   
}
```

**“前闭后开”区间** [)