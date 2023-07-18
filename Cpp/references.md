---
tags:
  - Cpp
---
References are syntax sugar for pointers. Meaning that it's not an actual variable in our code, just some way to _reference_ variables easier when we are writing.
An example:
```cpp
#include <iostream>
#define LOG(x) std::cout << x << std::endl

void Increment(int value){
	value++;
}

int main{
	int a = 2;
	Increment(a);
	LOG(a);
}
``` 
The output of this program is simply 2. That happens because the increment functions takes the value of a, creates a variable in the local scope with the value two and increments that local variable. To solve that, we could change the return typy of increment and do something like `a = Increment(a)` . Or, a more elegant way of doing it is passing the memory adress of a and changing that in the function, like so:
```cpp
#include <iostream>
#define LOG(x) std::cout << x << std::endl

void Increment(int* value){// Im passing value by *reference*
	(*value)++;//The parenthesis is here because of order of operations.Otherwise, the adress value would be added to first, then dereferenced. We want it to be dereferenced first.
}

int main{
	int a = 2;
	Increment(&a);
	LOG(a);
}
``` 
We can make this code cleaner using references, which again, are just syntax sugar.
```cpp
#include <iostream>
#define LOG(x) std::cout << x << std::endl

void Increment(int& value){// Im passing a by reference
	value++;
}

int main{
// int& ref = a; This is how you declare a reference, it should always be declared based on a existing variable.
	int a = 2;
	Increment(a);
	LOG(a);
}
// I could also do it like 
// int& ref = a;
// Increment(ref); it also returns 6
// But its not necessary
``` 
That also does it. Note that references are [[consts]] meaning that
```cpp
int a =2;
int* ptr = &a;
int& ref = a;
int b = 4;
ref = b; //this sets a = b = 4; the memory adress a ref references cannot be changed;
ptr = &b; // this now gives ptr the adress of b
LOG(a); // 2
LOG(*ptr); // 4
 ```
 