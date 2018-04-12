# F - 反素数 
反素数就是满足对于任意i(0<i<x),都有g(i)<g(x),(g(x)是x的因子个数),则x为一个反素数。现在给你一个整数区间[a,b],请你求出该区间的x使g(x)最大。 
## Input
第一行输入n,接下来n行测试数据 
输入包括a,b, 1<=a<=b<=5000,表示闭区间[a,b]. 
## Output
输出为一个整数,为该区间因子最多的数.如果满足条件有多个,则输出其中最小的数. 
## Sample Input
3
2 3
1 10
47 359
## Sample Output
2
6
240  
## Hint
2的因子为：1 2
10的因子为:1 2 5 10
```
#include <iostream>
#include <cstring>
using namespace std;
int main(){
	int n,a,b,max,i,j,sum,max_sum;
	cin >> n;
	while(n--){
		cin>>a>>b;
		max = a;
		max_sum = 0;
		for(i = a;i <= b; i++){
			sum = 0;
			for(j = 1;j <= i/2;j++){
				if(i % j == 0){
					sum++;
				}
				if( i != 1) sum++;
				if(sum > max_sum){
					max_sum = sum;
					max = i;
				}
			}
		}
		cout <<max<<endl;
	}
	 return 0;
} 
```
        
 
