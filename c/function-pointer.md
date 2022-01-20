# Function Pointer

Today I learned how to declare and initialize a function pointer in c. The following syntax will define a pointer a function `f`.

```c
output-type (*pf)(input-types) = &f;
```

The function `f` can then be called via the pointer to `f` by executing the following statement

```c
(*pf)(<input params>);
```