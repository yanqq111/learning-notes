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
#include<stdlib.h>

typedef int Elemtype;

typedef struct node
{
	Elemtype data;
	struct node* next;
}Node;

Node* inithead()
{
	Node* head = (Node*)malloc(sizeof(Node));
	head->data = 0;
	head->next = NULL;
	return head;
}

void inserthead(Node* L,Elemtype e)
{
	Node* p = (Node*)malloc(sizeof(Node));
	p->next = L->next;
	p->data = e;
	L->next = p;
}

void listnode(Node* L)
{
	printf("%d\n", L->data);
	Node* p = L->next;
	while (p!= NULL)
	{
		printf("%d\n",p->data);
		p = p->next;
	}
	printf("\n");
}

Node* gettail(Node* L)
{
	Node* p = L;
	while (p->next != NULL)
	{
		p = p->next;
	}
	return p;
}

Node* inserttail(Node*L,Elemtype e)
{
	Node* p = (Node*)malloc(sizeof(Node));
	L->next = p;
	p->data = e;
	p->next = NULL;
	return p;
}

void insertnode(Node* L, int position, Elemtype e)
{
	Node* p = L;
	int i = 0;
	while (i < position - 1)
	{
		p = p->next;
		i++;
		if (p == NULL)
		{
			printf("插入失败");
			return;
		}
	}
	Node* q = (Node*)malloc(sizeof(Node));
	Node* temp = p->next;
	p->next = q;
	q->data = e;
	q->next = temp;
	return;
}

void deletenode(Node* L, int position)
{
	Node* p = L;
	int i = 0;
	while (i < position - 1)
	{
		p = p->next;
		i++;
		if (p == NULL)
		{
			printf("超出范围");
			return;
		}
	}
	if (p->next == NULL)
	{
		printf("删除位置为空");
		return;
	}
	Node* q = p->next;
	p->next = q->next;
	free(q);
	return;
}

int listlenth(Node* L)
{
	Node* p = L;
	int len = 0;
	while (p != NULL)
	{
		p = p->next;
		len++;
	}
	return len;
}

void freelist(Node*L)
{
	Node* p = L->next;

	while (p->next != NULL)
	{
		Node* q = p->next;
		free(p);
		p = q;
	}
	L->next = NULL;
}
```
用C语言实现linklist和它的基本功能

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


## 代码记录
```c

```
用C语言实现linklist和它的基本功能

