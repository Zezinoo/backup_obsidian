---
tags:
  - Cpp
---
Classes are ways of organizing data and the building block of the [[OOP]] paradigm.They are very similar to a [[struct]].
In C++, one can declare a class like so:
```cpp
class Car{
public:
	int m_rating;
private:
	string m_brand // m_ is a convention for members of the class
	string m_model;
	int m_year;
public:
	void setModel(str model){// functions inside classes are called methods
		m_model = model
	}
	void GetInfo(){
		std::cout << m_model +" " << m_rating << std::endl
	}
}
int main(){
Car car;
car.setModel("Ford");
car.m_rating = 10;
car.GetInfo(); 
}
```
A class type is called an **object** and something like `Entity e1` is called an **instance** of that object. One could define [[constructors]] and [[destructors]] for some class.
In  C++, member of classes are private by default, meaning they can only be acessed by other members of the class. You could change this behavior with the public keyword.
Note that the private member m_model has to be changed used a [[setter]] , which is a function that can acess private member inside the class. One would also have to use [[getter]] to acess the value of a member outside the class. 
Classes can have [[static#^ab429a | static]]  methods and variables 