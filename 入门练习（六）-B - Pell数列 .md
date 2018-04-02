# B - Pell数列 
Pell数列a 1, a 2, a 3, ...的定义是这样的，a 1 = 1, a 2 = 2, ... , a n = 2 * a n − 1 + a n - 2 (n > 2)。 
给出一个正整数k，要求Pell数列的第k项模上32767是多少。 
## Input
第1行是测试数据的组数n，后面跟着n行输入。每组测试数据占1行，包括一个正整数k (1 ≤ k < 1000000)。 
## Output
n行，每行输出对应一个输入。输出应是一个非负整数。 
## Sample Input
2
1
8
## Sample Output
1
408
``` 
#include <stdio.h>  
#define MOD 32767  
#define N 1000000  
int pell[N+1];  
  
void setpell(int n)  
{  
    int i;  
  
    pell[1] = 1;  
    pell[2] = 2;  
  
    for(i=3; i<=n; i++)  
        pell[i] = (2 * pell[i - 1] + pell[i - 2]) % MOD;  
}  
  
int main(void)  
{  
    int n, i;  
  
    setpell(N);  
  
    scanf("%d", &n);  
    while(n--) {  
        scanf("%d", &i);  
  
        printf("%d\n", pell[i]);  
    }  
    return 0;  
}  
```
