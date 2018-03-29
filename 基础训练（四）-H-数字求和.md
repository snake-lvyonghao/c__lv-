# H-数字求和
给定一个正整数a，以及另外的5个正整数，问题是：这5个整数中，小于a的整数的和是多少？ 
## Input
输入一行，只包括6个小于100的正整数，其中第一个正整数就是a。 
## Output
输出一行，给出一个正整数，是5个数中小于a的数的和。 
## Sample Input
10 1 2 3 4 11
## Sample Output
10
```
#include <stdio.h>
#include <stdlib.h>
#define N 5
int main(){
	int i,number[N + 1],total = 0;
	for( i = 0; i < N + 1; i++){
		scanf("%d",&number[i]);
	}
	for(i = 1;i <= N; i < i++ ){
		if(number[i] < number[0])
		total += number[i]; 
	}
	printf("%d",total);
} 
```
**ps：没什么好说的宏定义了一个N为了程序的重用性**
