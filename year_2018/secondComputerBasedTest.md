# Foreword
## 函数
函数的声明
函数的调用
`````
//定义你写的函数在调用的函数之前

void myFunction(int a,int b){
//some code
}

void myAnotherFunction(){
  //define a and b
  //...
  myFunction(a,b)
}
`````


可以任意调用库函数

## 提交
截止时间 10.15 晚八点 尽量早的提交，早点提交可以加分
题目没有分值估计和要求，没有写的题目也写上题号，创建github仓库，答案文件放在里面，github链接发给团队邮箱

# 第一题：
给定两个数组，这两个数组的长度相同 ，将这两个数组对应位置的元素相减，然后放入一个新的数组，并输出,不需要返回这个数组
例如
 {1,2,3,4,5} - {4,5,6,7,8} = {-3,-3,-3,-3,-3}

> 注意： 这两个数组的长度和具体的数字是不知道的，但是一定是一样长
最好使用一个函数处理
函数原型： ``void process(int[]a, int b[]) ``

在``main()`` 中调用的时候可以自己放入一个测试样例 如：


```
int main(){
    int []a = {1,2,3};
    int []b = {4,5,6};
    process(a,b);
   return 0;
}
```

# 第二题：
我们知道高斯求和是求 1- 100 的和，现在需要写1 -100 中的奇数和 并输出结果
函数原型 int sum(int start,int end) 或者 int sum()
前一种使用参数传入开始和结束的数字 后面一种在函数体中指定 从 1 (start) 开始 且 100 ( end )

# 第三题：
在不使用多余的数组空间的情况下，完成数组的reverse()
不使用多余空间：不允许开辟新的数组空间存放中间结果
```
例如{3,4,6,2,5,6} -> {6,5,2,6,4,3}
```
> 注意： 输入的数组是不知道的，最好使用函数处理
> 推荐使用的函数原型 void reverse(int a[])

# 第四题
要求：不用临时变量，交换a,b的值，输出交换后的结果。  
不只有一种方法，会几个写几个


# 第五题

快速排序算法里有一个经典的划分过程：我们通常采用某种方法取一个元素作为主元，通过交换，把比主元小的元素放到它的左边，比主元大的元素放到它的右边。 给定划分后的 N 个互不相同的正整数的排列，请问有多少个元素可能是划分前选取的主元？

例如给定  N = 5, 排列是1、3、2、4、5。则：

1 的左边没有元素，右边的元素都比它大，所以它可能是主元;  
尽管 3 的左边元素都比它小，但其右边的 2 比它小，所以它不能是主元；  
尽管 2 的右边元素都比它大，但其左边的 3 比它大，所以它不能是主元；  
类似原因，4 和 5 都可能是主元。

- 要求:
写一个函数（可以调用其它函数）参数为一个数组，和其长度，把这个数组中可能为主元的结果用printf输出
比如上面的，数组{1、3、2、4、5},则输出1,4,5

```
  void findPrincipalElement(int array[],int length){
    .....
    .....
  }
```

# 第六题

分析代码作用

```
#include <stdio.h>

int fun(int n){
  int i=2;	
  for(i=2;i<=sqrt(n);i++){
    if(n%i==0)			
    return 0;	
  }
  return 1;	
}

int main(){
  int i;
  for(i=100;i<=200;i++){
  if(fun(i))		
  printf("%d ",i);	
  }	
  return 0;
}

```

# 第七题

写出输出结果，并分析程序。
```
#include "stdio.h"
#include <math.h>

void sortA(int *a, int n){
  for(int i=0;i<n-1;i++){
    for(int j=0;j<n-i-1;j++){
        if (a[j]>a[j+1])
	{
	  int t=a[j];
	  a[j]=a[j+1];
	  a[j+1]=t;
	}
    }
  }
}

int check(int a[],int n){
  int i;
  int b[n];
  if (n==1)
  {
    printf("yes\n");
    return 0;
  }else{
    for(i=0;i<n-1;i++)
    b[i]=fabs(a[i]-a[i+1]);
    sortA(b,n);
    for(i=0;i<n-2;i++)
    {
       if (b[i+1]-b[i]==1)
         continue;
       else break;
     }
     if (i==n-2) printf("yes\n");
     else printf("no\n");
   }
   return 0;
}

int main(){
  int array[]={4,8,10,7,6,11};
  check(array,6);
  return 0;
}
```
# 第八题

输出一个正方形，要求实现一个函数``void printSquare(int a)``输出一个正方形。 参数a的值一定是一个奇数。
输出举例：
```
a = 1
**
**


a = 3
***
* *
***

a = 5

*****
*   *
*   *
*   *
*****

...
a = 2*n -1 
.....


```


长和宽相等 （输出同一样数目的*） 中间是空心的（使用空格表示）
