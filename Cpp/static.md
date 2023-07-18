---
tags:
  - Cpp
  - Csharp
---
## Translation Units
The static keyword tells the linker that the analysed symbol is to be used only in the current file, that is, it will only exist in the context of the current file's generated .obj
```cpp
#file 1.cpp
#include <iostream>
int variable;
void foo(){
	std::cout << "Hi I'm foo 1." << std::endl
}
#file2.cpp
#include <iostream>
int variable;
void foo(){
	std::cout << "Hi I'm foo 2." << std::endl
}
int main(){
	foo();
}
```
In the above example,if i try to build file1.cpp and file2.cpp into a target output the linker will fail with some sort of duplicate error something of the sort "one or more multiply defined symbols found. That is because it doesnt know which foo() to use.  It will also complain about the duplication of variable, much for the same cause. To circunvent that, i could use:
```cpp
#file 1.cpp
#include <iostream>
int variable;
static void foo(){
	std::cout << "Hi I'm foo 1." << std::endl
}
#file2.cpp
#include <iostream>
extern int variable; //The extern keyword tell the linker to look for a declaration of variable that is external to the scope of the current translation unit.
static void foo(){
	std::cout << "Hi I'm foo 2." << std::endl
}
int main(){
	foo();#Outputs "Hi im foo 2."
}
```
The static keyword makes it so the linking is only **internal** .
## Classes and Structs

^ab429a

When used inside classes or structs, the keyword acquires another meaning.
### Static variables
A static variable is a variable that is shared across all instances of a class/struct , meaning that if there is a method that change it, it changes it across all entitites.
```cpp
class Entity {
	public:
		static int x,y;
		void Print(){
			std::cout << x << y << std::endl
		}	
	
}
int Entity:: x;
int Entity:: y;
// The above lines of code have to be used because we must initialize the static variables as the only exist in the class scope. Its almost like x and y are variables that live in the Entity namespace.
int main(){
	Entity e1; 
	e1.x = 10;
	ei.y = 5;
	Entity e2;
	e2.x = 11;
	e2.y = 6;
	e1.Print();
	e2.Print();
	//Both prints return 11,6
	Entity::x = 0;
	Entity::y =1;
	e1.Print();e2.Print();
	//That's the correct way to assign static variables. Both prints now return 0 and 1 
}
```
### Static methods
A static method has the same philosphy as a static variable, meaning that it cannot acess variables that are not static;that are outside of the class scope.
```cpp
class Entity{
public:
	static int x,y;
	int p,q;
	static Print(int switch){
		if(switch==1)
		std::cout << x << y << std::endl;
		if(switch==2)
		std::cout << p << q << std::endl;
	}
}
int main(){
	Entity e1;e1.x = 0 ; e1.y = 1;e1.p=2;e1.q=3;
	e1.Print(1);//suceeds
	e1.Print(2);//Fails, because the variables are not static. To use on static variables, one would have to pass an entity instance to a static method and then acess those instance values.
}
``` 
