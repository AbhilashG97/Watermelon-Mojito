# Pointers

This section is all about pointers. ::

## Types of Pointers

1. Null Pointer
1. Wild Pointer
1. Dangling Pointer
1. Generic | Void Pointers
1. Far Pointer
1. Near Pointer
1. Huge Pointer
1. Function Pointer

### Null Pointer

A pointer that points to NULL. It is used to initialize a pointer to NULL. 

```c
int *pointer;

pointer = NULL;
```

### Wild Pointer

A pointer pointing to some random garbage address is called a Wild Pointer.

### Dangling Pointer

A pointer that is deallocated from an allocated memory is called a Dangling Pointer. 

```c
int *pointer;

pointer = (int *)malloc(sizeof(int));

free(pointer);
```

### Void Pointer

It is a pointer that can be used to store pointers of different data types. 

```c
int a = 10;
int *p;
p = &a;

float b = 20;
float *q;
q = &b;

Void * x;
x = &a;
printf("%d", (int *)x);

x = &b;
printf("%f", (float *)x);
```

:boom: Difference between ```malloc()``` and ```calloc()```

### Near and Far Pointers

### Function Pointers

It is a pointer that points to a function. 

```c
Void function_a() 
{
    printf("Hi");
}

Void function_b() 
{
    printf("Hello");
}

int main() 
{
    Void (*p[]) () = {function_a, fucntion_b};
}
```

:warning: Only functions of similar types should be stored in a function pointer array. Functions having different number of parameters, return types should not be stored in the same pointer array.

```c

Void f1() 
{
    printf("Hi");
}

Void f2() 
{
    printf("Hello");
}


Void dummy(*f1) 
{
    f1();
}

int main() 
{
    dummy(f1);
    dummy(f2);
}
```