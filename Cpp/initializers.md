---
tags:
  - Cpp
---
Syntax for initializing structs and unions
```cpp
struct point {
	float x,y,z;
};
point p = {1.0f,2.0f} // the z variable is emnpty-iniatialized, which is an overload depending on the type of the variable. In the case of floats its 0.0
``` 
