## 代码记录
```c
#include<stdio.h>
#include<stdlib.h>

MAXSIZE = 100;

typedef int Elemtype;

typedef struct
{
	Elemtype* data;
	int lenth;
}Seqlist;

Seqlist* initlist()
{
	Seqlist* L = (Seqlist*)malloc(sizeof(Seqlist));
	L->data = (Elemtype*)malloc(sizeof(Elemtype) * MAXSIZE);
	L->lenth = 0;
	return L;
}

void appendElem(Seqlist* L, Elemtype a)
{
	if (L->lenth > MAXSIZE)
	{
		printf("添加失败");
		return;
	}
	L->data[L->lenth] = a;
	L->lenth++;
}

void insertElem(Seqlist* L, int position, int e)
{
	if (position > L->lenth && position < 1)
	{
		printf("插入失败");
		return;
	}
	for (int i = L->lenth - 1;i >= position - 1;i--)
	{
		L->data[i + 1] = L->data[i];
	}
	L->data[position - 1] = e;
	L->lenth++;
}

void deleteElem(Seqlist* L, int position)
{
	if (position > L->lenth && position < 1)
	{
		printf("删除失败");
		return;
	}
	for (int i = position - 1;i < L->lenth;i++)
	{
		L->data[i] = L->data[i + 1];
	}
	L->lenth--;
}

int findElem(Seqlist* L, int e)
{
	for (int i = 0;i < L->lenth;i++)
	{
		if (L->data[i] == e)
		{
			return i + 1;
		}
	}
	printf("没有找到");
	return;
}
```
用C语言实现Sequancekist和它的基本功能
