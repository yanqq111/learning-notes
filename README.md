# learning-notes
my learning notes on C,   DataStructures ,python, AI

**# 我的学习笔记

## 2026年8月（入学前）
- 学完C语言程序设计
- 正在用C语言学习数据结构

## 代码记录
- [
- #include<stdio.h>

int main()
{
	int n;
	scanf("%d", &n);
	int money = 0;
	int day = 0;
	int floor = 1;
	while (((1 + floor) * floor / 2) < n)
	{
		floor++;
	}
	for (int i = 1;i <= floor;i++)
	{
		if (i == floor)
		{
			int num = n - day;
			for (int k = 1;k <= num;k++)
			{
				money += i;
			}
			break;
		}
		for (int j = 1;j <= i;j++)
		{
			money += i;
			day++;
		}
	}
	printf("%d",money);
}e25
] 用C语言实现

