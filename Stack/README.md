# 2020-10-17 Stack
## Stack?
The "stack" temporarily stores that data.


Putting data into the stack is called "push."


and Taking data out of the stack is called "pop."


The stack processes the data in a Last-in-first-out fashion.



## Stack_Structure
![white](https://user-images.githubusercontent.com/66680536/96274741-d76f1c80-100b-11eb-87ae-d649e1efb676.png)

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