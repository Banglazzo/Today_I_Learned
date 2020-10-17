# 2020-10-17 Stack
## Stack?
The "stack" temporarily stores that data.


Putting data into the stack is called "push."


and Taking data out of the stack is called "pop."


The stack processes the data in a Last-in-first-out fashion.



## Stack_Structure
![Stack](https://user-images.githubusercontent.com/66680536/96278388-63834300-1010-11eb-9ea6-ff725b43ef5c.png)

Stacks can be implemented using a structure.


The stack structure has three members.
##### "max," "ptr," and "stk".
"max" indicates the total capacity of the stack.


Indicates the number of data in the "ptr" stack.


"Stk" is a pointer that refers to an array to be used as a stack.



## Stack-related functions
#### Initialize
"Initialize" is a function that initializes the stack. 
``` C
int Initialize(IntStack *s, int max)
{
    s->ptr = 0;
    if((s->stk = calloc(max, sizeof(int))) == NULL) {
        s->max = 0;
        return -1;
    }
    s->max = max;
    return 0;
}
```
#### Push
"Push" is a function of adding data to the stack.
``` C
int Push(IntStack *s, int x)
{
    if(s->ptr >= s->max)
        return -1;
    s->stk[s->ptr++] = x;
    return 0;
}
```

#### Pop
"Pop" is a function of removing data from the stack.
``` C
int Pop(IntStack *s, int *x)
{
    if(s->ptr <= 0)
        return -1;
    *x = s->stk[s->ptr--];
    return 0;
}
```

#### Peek
"Peak" is a function similar to "pop" but returns without removing the data.
``` C
int Peek(IntStack *s, int *x)
{
    if(s->ptr <= 0)
        return -1;
    *x = s->stk[s->ptr-1];
    return 0;
}
```

#### Clear
"Clear" is a function that removes all data stored in the stack.
``` C
int Clear(IntStack *s)
{
    s->ptr = 0;
}
```

#### Capacity
"Capacity" is a function that returns a value of 'max'.
``` C
int Capacity(const IntStack *s)
{
    return s->max;
}
```
#### Size
"Size" is a function that returns the value of 'ptr'.
``` C
int Size(const IntStack *s)
{
    return s->ptr;
}
```
#### IsEmpty
"IsEmpty" is a function that checks if the stack is empty.
``` C
int IsEmpty(const IntStack *s)
{
    return s->ptr <= 0;
}
```
#### IsFull
"IsFull" is a feature that verifies that the stack is full.
``` C
int IsFull(const IntStack *s)
{
    return s->ptr >= s->max;
}
```
#### Search
"Search" is a function that searches for any value in the stack.
``` C
int Search(const IntStack *s, int x)
{
    int i;
    for(i = s->ptr - 1; i >= 0; i--)
        if(s->stk[i] == x)
            return i;
    return -1;
}
```
#### Print
"print" is a function that outputs all the data in the stack.
``` C
int Print(const IntStack *s)
{
    int i;
    for(i = 0; i < s->ptr; i++)
        printf("%d", s->stk[i]);
    printf("\n");
}
```
#### Terminate
"Terminate" is a function that is responsible for cleaning up behind.
``` C
int Terminate(IntStack *s)
{
    if(s->stk != NULL)
        free(s->stk);
    s->max = s->ptr = 0;
}
```