---
{"dg-publish":true,"permalink":"/07-c/c/","dgPassFrontmatter":true}
---


# c++语言对c语言的改进和拓展

## 编写一个C++风格的程序，输入半径radius，当radius为正数时，输出其面积area和周长circumference；否则，输出提示信息error input!（10分）

```
编写一个C++风格的程序，输入半径radius，当radius为正数时，输出其面积area和周长circumference；否则，输出提示信息**error input!**

具体要求如下：

①所有变量均定义为double类型;  

②输出面积和周长用语句：cout<<area<<" "<<circumference<<endl;

③输出提示信息用语句：cout<<"**error input!**"<<endl;

④圆周率用3.14159
```

```c++
#include <iostream>
using namespace std;
#define PI 3.14159
int main(){
    double radius;
    cin >> radius;
    if (radius>0)
    {
        double area;
        double circumference;
        area = PI * radius * radius;
        circumference = 2 * PI * radius;
        cout<<area<<" "<<circumference<<endl;
    }else {
        cout<<"error input!"<<endl;
    }
}

```

##   定义一个int型指针变量p,通过new运算符申请包含n个元素的动态一维数组， 输入数组的n个元素，然后求出所有正数的平均值、统计负数的个数。 输出这两个运算结果，最后用delete运算符释放动态内存空间。（10分）

```
定义一个int型指针变量p,通过new运算符申请包含n个元素的动态一维数组，

输入数组的n个元素，然后求出所有正数的平均值、统计负数的个数。

输出这两个运算结果，最后用delete运算符释放动态内存空间。

  

具体要求如下： 

①变量n定义为int型，通过语句cin>>n;输入该值(此处不考虑输入的n小于等于0的可能，直接输入正整数)

②输入p数组的元素是，用语句cin>>p[i]; 并且每输入一个元素都打回车，即每行只输入一个元素

③定义double型变量ave存放平均值，定义int型变量number存放负数个数，其余变量根据编程需要定义

④输出语句为：cout << "ave=" <<ave<<"  number="<<number<<endl;
```


```c++
#include <iostream>
using namespace std;
int main()
{
    int n;
    //cout << "输入n" << endl;
    cin >> n;
    int *p = new int[n];
    //cout << "输入每一项" << endl;
    for (int i = 0; i < n; i++)
    {
        /* code */
        cin >> p[i];
    }
    double ave=0;
    int number=0;
    int count = 0;
    int sum=0;
    for (int i = 0; i < n; i++)
    {
        /* code */
        if (p[i]>0)
        {
            count++;
            sum += p[i];
        }else if(p[i]<0){
            number++;
        }
        
    }
     if(count!=0){
        ave = sum / count;
    }
    cout << "ave=" <<ave<<"  number="<<number<<endl;
}
```

### 易错点分析
     if(count!=0){
        ave = sum / count;
    }
当你的输入数组的元素全部都是0的时候不能直接进行除法运算.