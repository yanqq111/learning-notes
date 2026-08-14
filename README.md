# learning-notes
my learning notes on C,   DataStructures ,python, AI

**# 我的学习笔记
## 2026年8月（入学前）
- 学完C语言程序设计
- 正在用C语言学习数据结构

## 代码记录
```c
#include <stdio.h>

int main()
{
    int n;
    scanf("%d", &n);
    int money = 0;
    int day = 0;
    int floor = 1;
    while (((1 + floor) * floor / 2) < n) {
        floor++;
    }
    for (int i = 1; i <= floor; i++) {
        if (i == floor) {
            int num = n - day;
            for (int k = 1; k <= num; k++) {
                money += i;
            }
            break;
        }
        for (int j = 1; j <= i; j++) {
            money += i;
            day++;
        }
    }
    printf("%d\n", money);
    return 0;
}
```
用C语言实现<img width="660" height="394" alt="屏幕截图 2026-08-13 101954" src="https://github.com/user-attachments/assets/ddb90395-5734-4a3f-bb51-bee25ed66521" />

## 代码记录
```c
#include<stdio.h>

int main()
{
	int L;
	scanf("%d",&L);
	int count = 0;
	if (L % 3 == 0)
	{
		for (int a = 1;a < L / 3;a++)
		{
			for (int b = a;L - a - b >= b;b++)
			{
				int c = L - a - b;
				if (b - a < c && a + b > c)
				{
					count++;
				}
				else
				{
					continue;
				}
			}
		}
	}
	else
	{
		for (int a = 1;a <= L / 3;a++)
		{
			for (int b = a;L - a - b >= b;b++)
			{
				int c = L - a - b;
				if (b - a < c && a + b > c)
				{
					count++;
				}
				else
				{
					continue;
				}
			}
		}
	}
	printf("%d",count);
}
```
用C语言实现<img width="650" height="571" alt="屏幕截图 2026-08-14 122354" src="https://github.com/user-attachments/assets/47ebfd7f-ae87-4658-8e8f-95af5a61762f" />

