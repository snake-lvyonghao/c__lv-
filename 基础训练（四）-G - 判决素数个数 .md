# G - 判决素数个数 
输入两个整数X和Y，输出两者之间的素数个数（包括X和Y）。
## Input
两个整数X和Y（1 <= X,Y <= 10 5）。 
## Output
输出一个整数，表示X，Y之间的素数个数（包括X和Y）。 
## Sample Input
1 100
## Sample Output
25
```
#include <stdio.h>
#include <stdlib.h>
void swap(int *a,int *b)/*交换两个数据的地址*/
{
	int t;
	t = *a;
	*a = *b;
	*b = t;
}
int main(){
	int x,y,i,j,total = 0;
	scanf("%d %d",&x,&y);									/*获取检查边界*/ 
	if(x > y)												/*比较边界*/
		swap(&x,&y);
	for(i = x;i <= y;i ++){									/*边界范围内全部检查*/ 
		int flag = 1;
		for(j=2;j<i;j++) {									/*判断是否为素数*/ 
        	if(i%j==0)
        	flag=0; 
    	}
    	if (flag !=0 )
    		total += 1;
	}
	if(x==1||y==1)												/*边界如果有1则最终结果减去1*/ 
	total -= 1; 
	printf("%d",total);							
	return 0;
}
```


