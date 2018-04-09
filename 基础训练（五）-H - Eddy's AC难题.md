# H - Eddy's AC难题 
Eddy是个ACMer,他不仅喜欢做ACM题,而且对于Ranklist中每个人的ac数量也有一定的研究,他在无聊时经常在纸上把Ranklist上每个人的ac题目的数量摘录下来，然后从中选择一部分人(或者全部)按照ac的数量分成两组进行比较，他想使第一组中的最小ac数大于第二组中的最大ac数，但是这样的情况会有很多，聪明的你知道这样的情况有多少种吗? 

特别说明：为了问题的简化，我们这里假设摘录下的人数为n人，而且每个人ac的数量不会相等，最后结果在64位整数范围内. 
## Input
输入包含多组数据，每组包含一个整数n,表示从Ranklist上摘录的总人数。 
## Output
对于每个实例，输出符合要求的总的方案数，每个输出占一行。 
## Sample Input
2
4
## Sample Output
1
17
```
#include<stdio.h>
long long C(long long m,long long n){
     long long s=1,i;
     for(i=1;i<=m;i++)
         s=s*(n-i+1)/i;;
     return s;
 }
int main(){
    long long n,i,res;
    while(scanf("%I64d",&n)!=EOF){
        res=0;
        for(i=2;i<=n;i++)
            res+=(i-1)*C(i,n);
        printf("%I64d\n",res);
    }
    return 0;
}
```
