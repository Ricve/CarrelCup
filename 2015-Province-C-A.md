# 方程的整数解

### 题目

求出方程 

![](http://latex.codecogs.com/svg.latex?a^{2}+b^{2}+c^{2}=1000)

除 `a,b,c=6,8,30​` 外的解。

填写该解中最小的数字。

### 求解

#### 思路

通过循环遍历求出是方程的解且是 $6,8,10$ 以外的最小值。

#### 代码

##### C

```c
#include <stdio.h>
int main(int argc, char *argv[])
{
  int i,j,k;
  int min=1000;
  for(i=1;i<=1000;i++){
    for(j=1;j<=1000;j++){
      for(k=1;k<=1000;k++){
        if((i*i+j*j+k*k==1000)){
          if(i<min&&i!=6&&i!=8&&i!=30)
            min=i;
          if(j<min&&j!=6&&j!=8&&j!=30)
            min=j;
          if(k<min&&k!=6&&k!=8&&k!=30)
            min=k;
        }
      }
    }
  }
  printf("%d",min);
  return 0;
}
```

#### 答案提交

```
10
```

