## 代码记录
```c
#include<stdio.h>
#include<string.h>

int strMatch(char* s1, char* s2)
{
	int m = strlen(s1);
	int n = strlen(s2);
	int index;
	for (int i = 0;i <= m-n;i++)
	{
		int j = 0;
		while (j < n)
		{
			if (s1[i] == s2[j])
			{
				i++;
				j++;
				if (j == n)
				{
					return i - j;
				}
			}
			else
			{
				i = i - j;
				break;
			}
		}
	}
	return -1;
}

int main()
{
	char s1[] = "abcdefabcdzx";
	char s2[] = "abcz";
	int result = strMatch(s1, s2);
	printf("%d",result);
}

```
朴素字符串对齐
