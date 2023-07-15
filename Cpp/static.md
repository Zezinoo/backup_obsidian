---
tags:
  - Cpp
  - Csharp
---
The static keyword tells the linker that the analysed symbol is to be used only in the current file, that is, it will only exist in the context of the current file's generated .obj
```cpp
#file 1.cpp
#include <iostream>
void foo(){
	std::cout << "Hi I'm foo 1." << std::endl
}
#file2.cpp
#include <iostream>
void foo(){
	std::cout << "Hi I'm foo 2." << std::endl
}
int main(){
	foo();
}
```
In the above example,if i try to build file1.cpp and file2.cpp into a target output the linker will fail with some sort of duplicate error something of the sort "one or more multiply defined symbols found". That is because it doesnt know which foo() to use. To circunvent that, i could use:
```cpp
#file 1.cpp
#include <iostream>
static void foo(){
	std::cout << "Hi I'm foo 1." << std::endl
}
#file2.cpp
#include <iostream>
static void foo(){
	std::cout << "Hi I'm foo 2." << std::endl
}
int main(){
	foo();#Outputs "Hi im foo 2."
}
```
The static keyword makes it so the linking is only **internal** .