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
