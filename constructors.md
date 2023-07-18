 A method that initializes an instance of the class with something you defined.
 ```cpp
 class Entity{
	float x,y;
	Entity(float X , float Y){
		x = X;
		y = Y;
		std::cout << "Entity created" << std::endl
	}
 }
int main(){
	Entity e1(1.0f , 2.0f);
}
```
If no constructor is specified, C++ provides the class with an empty constructor `Entity(){}` as default. Constructors can be [[overloading | overloaded ]] like any other method.