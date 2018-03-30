# I - 字符替换 
把一个字符串中特定的字符全部用给定的字符替换，得到一个新的字符串。
## Input
只有一行，由一个字符串和两个字符组成，中间用单个空格隔开。字符串是待替换的字符串，字符串长度 小于等于30个字符，且不含空格等空白符； 
接下来一个字符为需要被替换的特定字符； 
接下来一个字符为用于替换的给定字符。 
## Output
一行，即替换后的字符串。 
## Sample Input
hello-how-are-you o O
## Sample Output
hellO-hOw-are-yOu
```
#include <stdio.h>
#include <stdlib.h>
#define N 30  
char s[N + 1];  
int main(void)  
{  
    char c1, c2;  
    int i;  
  	scanf("%s %c %c", s, &c1, &c2);  
    i = 0;  
    while(s[i]) {  
        putchar(s[i] == c1 ? c2 : s[i]);  
        i++;  
    }  
    putchar('\n');  
  
    return 0; 
}
```
