Inheritance is when a subclass of a predefined class is created. The subclass also said to _extend_ the parent class
```cpp
class Dog {
public:
	float Weight;
	char* Name;
	void Bark(){
	std::cout << "Bark!" << std::endl;	
	}
}
class Shiba : public Dog {
	char* Fur;
}
int main(){
	Shiba doge;
	doge.Bark();
}
```
The main takeaway here is that the doge instance of type Shiba but also of type Dog, where Shiba acts a superset of the class Dog.
Constructors cannot be inherited, except with the use of the using keyword. `using DOG::DOG` , since C++11. You could do it explicitly inhereting the parent directory with 
```cpp
class Shiba{
Shiba(): Dog() {
//some code
	}
}
```


