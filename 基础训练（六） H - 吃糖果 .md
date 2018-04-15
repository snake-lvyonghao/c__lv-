# H - 吃糖果 
HOHO，终于从Speakless手上赢走了所有的糖果，是Gardon吃糖果时有个特殊的癖好，就是不喜欢将一样的糖果放在一起吃，喜欢先吃一种，下一次吃另一种，这样；可是Gardon不知道是否存在一种吃糖果的顺序使得他能把所有糖果都吃完？请你写个程序帮忙计算一下。 
## Input
第一行有一个整数T，接下来T组数据，每组数据占2行，第一行是一个整数N（0<N<=1000000)，第二行是N个数，表示N种糖果的数目Mi(0<Mi<=1000000)。 
## Output
对于每组数据，输出一行，包含一个"Yes"或者"No"。 
## Sample Input
2
3
4 1 1
5
5 4 3 2 1
## Sample Output
No
Yes


        
  
## Please use function scanf
Hint
Hint
```
#include <stdio.h>
#include <stdlib.h>
int main(){
	int a[10000],max = 0,sum = 0,i,t,nul;
	scanf("%d",&t);
	while(t--){
		sum = max = 0;
		scanf("%d",&nul);
		for(i = 0;i < nul;i++){
			scanf("%d",&a[i]);
				if(max < a[i]) max = a[i];
		}
		for(i = 0;i < nul;i++){
			if(a[i]!=max){
				sum += a[i];
			}
			if(sum >= max - 1) break;	
			}
		if(i == nul) printf("NO\n");
		else printf("YES\n"); 
}
}
```
