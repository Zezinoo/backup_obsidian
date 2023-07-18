---
tags:
  - Cpp
---
pointers are variables that store some memory adress, usually the adress of some variable
```cpp
int a = 8;
void* ptr = nullptr; // #nullptr is equal to 0 = NULL = #define 0
int* ptr1 = &a;
*ptr1 = 10; // here its important that is ptr1 is declared as something other than void, otherwise the compiler wont know how many bytes of data to set aside in order to allocate the value you want; *ptr is called dereferencing a pointer
std::cout << *ptr1 << std::endl; //prints 10;
std::cin.get();
```
[[memory]] adresses are always integer numbers, so pointers always store integer numbers, meaning that ```type* ptr ``` is just telling the compiler that the variable stored in the memory adress stored in ptr is of type ```type```.
You could also declare a pointer like so 
```cpp
char* ptr = new char[8] // This means im setting aside eights bytes of data and ptr is a memory adress to the start of that 8 bytes.
memset(ptr,0,8) // the syntax is (adress,value,how many bytes), so this allocates 8 bytes of data to 0 starting from the byte adressed by ptr
delete[] ptr; //frees the data allocated to ptr; similar to malloc and free dynamic in C
``` 
Its important to note that declaring a variable like `int a ;` allocates it to [[stack]]  while `new`  allocates it to [[heap]] .
One could also freely create a pointer to a pointer.
```cpp
int a = 8;
int* ptr = &a;
int** ptr2 = &ptr;
``` 
Also look into [[references]] , as a syntax sugar for pointer operations.
