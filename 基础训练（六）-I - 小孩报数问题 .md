# I - 小孩报数问题 
有N个小孩围成一圈，给他们从1开始依次编号，现指定从第W个开始报数，报到第S个时，该小孩出列，然后从下一个小孩开始报数，仍是报到S个出列，如此重复下去，直到所有的小孩都出列（总人数不足S个时将循环报数），求小孩出列的顺序。 
## Input
第一行输入小孩的人数N（N<=64） 
接下来每行输入一个小孩的名字(人名不超过15个字符) 
最后一行输入W,S (W < N)，用逗号","间隔 
## Output
按人名输出小孩按顺序出列的顺序，每行输出一个人名 
## Sample Input
5
Xiaoming
Xiaohua
Xiaowang
Zhangsan
Lisi
2,3
## Sample Output
Zhangsan
Xiaohua
Xiaoming
Xiaowang
Lisi
```
#include<stdio.h>

int main()
{
    int n,s,m,w;
    int b[101];
	char d[101][101];
	s=0;
	scanf("%d",&n);
	for(int i=0;i<n;i++)
	{
	    	b[i]=i;
		 scanf("%s",&d[i]);
	}
	 
	scanf("%d,%d",&w,&m);
	w=(w+n-1)%n;
	do
	{
		w=(w+m-1)%n;
		printf("%s\n",d[b[w]]);
	  for(int j=w;j<n-1;j++)
	        b[j]=b[j+1];
	        
	}while(--n);
	return 0;
}
```
