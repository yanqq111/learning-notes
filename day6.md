## 代码记录
```c
#include<stdio.h>
#include<stdlib.h>

typedef int elem;

typedef struct node
{
	elem data;
	struct node *next;
}Node;

Node* initializelist()
{
	Node* L = (Node*)malloc(sizeof(Node));
	L->data = 0;
	L->next = NULL;
	return L;
}

int gettail(Node*L)
{
	int count = 0;
	Node* p = L;
	while (p != NULL)
	{
		p = p->next;
		count++;
	}
	return count;
}

int insetnode(Node* L, int tail,elem e)
{
	Node* p = L;
	Node* q = (Node*)malloc(sizeof(Node));
	for (int i = 0;i < tail - 1;i++)
	{
		p = p->next;
	}
	q->data = e;
	p->next = q;
	q->next = NULL;
	return tail+1;
}

Node* deletenode(Node* L, int i)
{
	Node* p = L;
	for (int j = 0;j < i - 1;j++)
	{
		p = p->next;
	}
	Node* q = p->next;
	p->next = q->next;
	free(q);
	return p->next;
}

void listnode(Node* L)
{
	Node* p = L;
	while (p != NULL)
	{
		printf("%d\n", p->data);
		p = p->next;
	}
	return;
}

int main()
{
	Node* head = initializelist();
	Node* temp = head;
	int tail = gettail(head);
	tail = insetnode(head, tail,21);
	tail = insetnode(head, tail,-15);
	tail = insetnode(head, tail,-7);
	tail = insetnode(head, tail,15);
	int arr[22] = { 0 };
	for (int i = 0;i < tail;i++)
	{
		arr[abs(temp->data)]++;
		if (arr[abs(temp->data)] >1 )
		{
			temp = deletenode(head, i);
			tail = tail - 1;
			continue;
		}
		temp = temp->next;
	}
	listnode(head);
}
```

用C语言实现<img width="2560" height="1600" alt="屏幕截图 2026-08-22 210239" src="https://github.com/user-attachments/assets/40bce6a2-f892-4fad-99ee-3dabdf215cf8" />
