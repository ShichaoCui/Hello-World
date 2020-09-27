# hellow-world
#include <stdio.h>
int sum(int score[10])
{
    int sum = 0;
    int i = 0;
    while(i <= 9)
    {
        sum += score[i];
        i++;
    }
    printf("总分为%d。\n",sum);
    return sum;
}
int max(int score[])
{
    int max = 0,i = 0;
    for(i;i <= 8;i++)
    {
        if(score[i]>score[i+1])
        {
            max = score[i];
            score[i] = score[i+1];
            score[i+1] = max;
        }
    }
    max = score[9];
    printf("最高分为%d。\n",max);
    return max;
}

int min(int score[])
{
    int min = 0,i = 0;
    for(i;i <= 8;i++)
    {
        if(score[i]<score[i+1])
        {
            min = score[i];
            score[i] = score[i+1];
            score[i+1] = min;
        }
    }
    min = score[9];
    printf("最低分为%d。\n",min);
    return min;
}
int aver(int score[10],int sum)
{
    int aver = sum/10;
    printf("平均分为%d。\n\n",aver);
}

int rank(int score[10])
{
    int max = 0;
    int i = 9,j;
    printf("考试成绩降序排序为：\n");
    for(i;i >= 0;i--)
    {
        j = 0;
        for(j;j < i;j++)
            if(score[j]>score[j+1])
            {
                max = score[j];
                score[j] = score[j+1];
                score[j+1] = max;
            }
        printf("第%d名为：%d分\n",10 - i,score[i]);
    }
}
int main()
{
    int score[10]={67,98,75,63,82,79,81,91,66,84};
    int Sum = sum(score);
    max(score);
    min(score);
    aver(score,Sum);
    rank(score);
    return 0;
}
