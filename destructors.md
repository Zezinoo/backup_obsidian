Destructors are methods that are called whenever a class instance gets out of scope. 
 ```cpp
 class Entity{
	float x,y;
	Entity(float X , float Y){
		x = X;
		y = Y;
		std::cout << "Entity created" << std::endl
	}
	~Entity(){
		std::cout << "Entity destroyed" << std::endl
	}
 }
void func(){
	Entity e1(1.0f , 2.0f);
}
int main(){
	func();//Outputs "Entity Destroyed" when the function ends e1 gets out of scope
}
```
Usually used for freeing allocated memory or cleaning up something that was initilized by a [[constructors | constructor]] when the class was instatatied. Can be called expicitly with `e1.~Entity()` but there's rarely any need for that.