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
