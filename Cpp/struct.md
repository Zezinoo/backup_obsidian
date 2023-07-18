---
tags:
  - Cpp
---
Structs are a concept thats inherited from the C programming language. Like the number says, they are a way of structuring data, but one could also define methods that pertain to the struct.
```cpp 
struct 2Vec{
	float x;
	float y;
	void Add(2Vec& otherVec){
		x += otherVec.x;
		y += otherVec.y	
} 
```
An important difference to classes is that struct members are public by default.
Generally is nice to assign structs to types of data that have less [[complexity]] , while using classes for higher complexity structures.
You can initialize a struct with [[initializers]].