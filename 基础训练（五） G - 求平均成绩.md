# G - 求平均成绩
假设一个班有n(n<=50)个学生，每人考m(m<=5)门课，求每个学生的平均成绩和每门课的平均成绩，并输出各科成绩均大于等于平均成绩的学生数量。 
## Input
输入数据有多个测试实例，每个测试实例的第一行包括两个整数n和m，分别表示学生数和课程数。然后是n行数据，每行包括m个整数（即：考试分数）。 
## Output
对于每个测试实例，输出3行数据，第一行包含n个数据，表示n个学生的平均成绩，结果保留两位小数；第二行包含m个数据，表示m门课的平均成绩，结果保留两位小数；第三行是一个整数，表示该班级中各科成绩均大于等于平均成绩的学生数量。 
每个测试实例后面跟一个空行。 
## Sample Input
2 2
5 10
10 20
## Sample Output
7.50 15.00
7.50 15.00
1
```
#include<stdio.h>  
#define max 50  
int main()  
{  
    int i,j,n,m;  
    int a[max][max];  
    double average1[max],average2[max];  
    while(~scanf("%d%d",&n,&m))  
    {  
        for(i=0;i<n;i++)  
        {  
            for(j=0;j<m;j++)  
                scanf("%d",&a[i][j]);  
        }  
        for(i=0;i<n;i++)  
        {  
            double sum1=0;  
            for(j=0;j<m;j++)  
            {  
                sum1+=a[i][j];  
            }  
            average1[i]=sum1/m;  
        }  
        for(j=0;j<m;j++)  
        {  
            double sum2=0;  
            for(i=0;i<n;i++)  
            {  
                sum2+=a[i][j];  
            }  
            average2[j]=sum2/n;  
        }  
        int y=0;
        for(i=0;i<n;i++)  
        {  
            int x=0;  
            for(j=0;j<m;j++)  
            {  
                if(a[i][j]>=average2[j])  
                    x++;  
            }  
            if(x==m)  
                y++;  
        }  
        for(i=0;i<n;i++)  
        {  
            if(i==0)  
                printf("%.2f",average1[i]);  
            else  
                printf(" %.2f",average1[i]);  
        }  
        printf("\n");  
        for(j=0;j<m;j++)  
        {  
            if(j==0)  
                printf("%.2f",average2[j]);  
            else  
                printf(" %.2f",average2[j]);  
        }  
        printf("\n");  
        printf("%d\n",y);  
        printf("\n"); 
    }  
    return 0;  
}
