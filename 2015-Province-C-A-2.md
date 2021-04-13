# 星系炸弹

### 题目

阿尔法炸弹 2015 年 1 月 1 日放置，定时 15 天，则它在 2015 年 1 月 16 日爆炸。

贝塔炸弹，2014 年 11 月 9 日放置，定时 1000 天，请你计算它爆炸的准确日期。

请填写该日期，格式为  `yyyy-mm-dd` 即 4 位年份 2 位月份 2 位日期。比如：`2015-02-19`。

请严格按照格式书写。不能出现其他文字或符号。

### 思路

题目要求定时 1000 天，则以年月日的顺序，依次后移，等后移满 1000 天为止。


### 代码（C）

```c
#include<stdio.h>
int main(){
	int days=1000;
	int CommonMonths[13]={0,31,28,31,30,31,30,31,31,30,31,30,31};
	int LeapMonths[13] = {0,31,29,31,30,31,30,31,31,30,31,30,31};
	int year=2014,month=11,day=9;
	while(days>=365){
		year++;
		if(((year%4==0)&&(year%100!= 0))||year%400==0)
			days-=366;
		else 
			days-=365;
	}
	while(days>=28){
		days-=CommonMonths[month%13];
		month++;
		if(month>12){
			year++;
			month%=13;
		}
	}
	day+=days;
	if(day>=CommonMonths[month]){
		day-=CommonMonths[month];
		month++;
	}
	printf("%d-%02d-%02d",year,month,day);
	return 0; 
} 
```

### 答案提交

```
2017-08-05
```

