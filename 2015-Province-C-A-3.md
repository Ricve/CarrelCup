# 奇妙的数字

### 题目

小明发现了一个奇妙的数字，它的平方 和 立方正好把0~9的10个数字每个用且只用了一次，你能猜出这个数是多少吗？

请填写该数字，不要填写任何多余的内容。

### 思路

首先经过简单验算， ![](http://latex.codecogs.com/svg.latex?100^{2}=10000) ,![](http://latex.codecogs.com/svg.latex?100^{3}=1000000),可见100的平方与立方共5+7位，位数大于10，故得出该数应在100以内。

验证每个数用且用了一次，可记录其每位数是否刚好出现0~9的每个数，若存在数未出现过，则必有其它数出现超过一次。

### 代码(C)

```c
#include<stdio.h>
#include<stdbool.h>
bool DigitsRecord(int i){
	int numbers[10]={0};
	int square=i*i;
	int cube=i*i*i;
	while(square){
		numbers[square%10]=1;
		square/=10;
	}
	while(cube){
		numbers[cube%10]=1;
		cube/=10;
	}
	for(int j=0;j<10;j++){
		if(!numbers[j])
			return false;
	}
	return true;
}
int main(){
	int i;
	for(i=1;i<=100;i++){
		if(DigitsRecord(i)){
//			printf("i=%d,i^2=%d,i^3=%d\n",i,i*i,i*i*i);
			printf("%d",i);
			break;
		}
	}
	return 0; 
} 
```

### 答案提交

```
69
```

