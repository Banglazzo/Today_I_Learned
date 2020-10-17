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



## Stack-related functions (will be added slowly)
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