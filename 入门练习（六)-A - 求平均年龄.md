# A - 求平均年龄 
班上有学生若干名，给出每名学生的年龄（整数），求班上所有学生的平均年龄，保留到小数点后两位。
## Input
第一行有一个整数n（1<= n <= 100），表示学生的人数。其后n行每行有1个整数，表示每个学生的年龄，取值为15到25。 
## Output
输出一行，该行包含一个浮点数，为要求的平均年龄，保留到小数点后两位。 
## Sample Input
2
18
17
## Sample Output
17.50
```
#include <stdio.h>
#include <stdlib.h>
int main(){
	int number,numbers;
	float age,average,total;
	scanf("%d",&number);
	numbers = number;
	while(number--){
		scanf("%f",&age);
		total += age;
	}
	average = total/numbers;
	printf("%0.2f",average);
	return 0;
} 
```
