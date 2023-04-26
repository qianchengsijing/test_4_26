# test_4_26
#include <stdio.h>
//栈
//顺序栈的基本操作
#define MaxSize 10
typedef struct
{
	ElemType data[MaxSize];
	int top;
}SqStack;
//栈的初始化(初始化top为-1的情况）
void InitStack(SqStack &S)
{
	S.top = -1;
}
//判空
bool StackEmpty(SqStack S)
{
	if(S.top = -1)
		return true;
	else
		return false;
}
//进栈
bool Push(SqStack &S,ElemType x)
{
	if(S.top == MaxSize-1)
		return false;
	S.data[++S.top] = x;
	return true;
}
//出栈
bool Pop(SqStack &S,ElemType &x)
{
	if(S.top == -1)
		return false;
	x = S.data[S.top--];
	return true;
}
//访问栈顶元素
bool GetTop(SqStack S,ElemType &x)
{
	if(S.top == -1)
		return false;
	x = S.data[S.top];
	return true;
}
int main()
{
	SqStack S;
	InitStack(S);
	Push(&S,x);
	Pop(&S,&x);
	GetTop(S,&x);
	return 0;
}
//共享栈
#define MaxSize 10
typedef struct 
{
	ElemType data[MaxSize];
	int top0;
	int top1;
}ShStack;
//初始化
void InitStack(ShStack &S)
{
	S.top0 = -1;
	S.top1 = MaxSize;
}
//判空S.top1 = MaxSize && S.top0 = -1，判满S.top0 + 1 = S.top1
int main()
{
	ShStack S;
	InitStack(S);
	return 0;
}
//链栈(与单链表基本相同）
typedef struct Linknode
{
	ElemType data;
	struct Linknode* next;
}*LiStack;
//初始化（不带头结点）
bool InitSack(LiStack &Lhead)
{
	Lhead = NULL;
	return true;
}
void testStack()
{
	LiStack Lhead;
	InitStack(Lhead);
}
