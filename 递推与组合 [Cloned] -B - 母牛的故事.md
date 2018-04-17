# B - 母牛的故事 
有一头母牛，它每年年初生一头小母牛。每头小母牛从第四个年头开始，每年年初也生一头小母牛。请编程实现在第n年的时候，共有多少头母牛？ 
## Input
输入数据由多个测试实例组成，每个测试实例占一行，包括一个整数n(0<n<55)，n的含义如题目中描述。 
n=0表示输入数据的结束，不做处理。
## Output
对于每个测试实例，输出在第n年的时候母牛的数量。 
每个输出占一行。
## Sample Input
2
4
5
0
## Sample Output
2
4
6
```
#include <stdio.h>
#include <stdlib.h>
int main(){
	int  n,a,b,c,d,i;
	scanf("%d",&n);
	while(n){
	if(n == 0) break;
	if(n < 4) printf("%d\n",n);
	else{
		n = n-4;
		a = b = c = d = 1;
		for(i = 0;i < n;i++){
			d = c + d;
			c = b;
			b = a;
			a = d;
		}
		printf("%d\n",a+b+c+d);
	}	
	}
	return 0;
}
```
