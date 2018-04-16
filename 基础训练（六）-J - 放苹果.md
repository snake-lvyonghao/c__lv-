# J - 放苹果 
把M个同样的苹果放在N个同样的盘子里，允许有的盘子空着不放，问共有多少种不同的分法？（用K表示）5，1，1和1，5，1 是同一种分法。 
## Input
第一行是测试数据的数目t（0 <= t <= 20）。以下每行均包含二个整数M和N，以空格分开。1<=M，N<=10。 
## Output
对输入的每组数据M和N，用一行输出相应的K。 
## Sample Input
1
7 3
## Sample Output
8
```
#include <stdio.h>
#include <stdlib.h>
int a[11][11],m,n,t;
void intn(){
	int i,j;
	for(i = 1;i <= 10;i++){
		a[0][i] = 1;
		a[i][1] = 1;
	}
	for(i = 1;i < 11 ;i++){
		for(j = 2;j < 11;j++){
			if(i >= j){
				a[i][j] = a[i-j][j] + a[i][j-1];
			}
			else{
				a[i][j] = a[i][j - 1];
		}
		}
	}
}
int main(){
	intn();
	scanf("%d",&t);
	while(t--){
		scanf("%d %d",&m,&n);
		printf("%d\n",a[m][n]);
	}
  return 0;
}
```
