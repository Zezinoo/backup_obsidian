---
tags:
  - Cpp
---
Enums are a form of structures in C++ that allow you to bundle up some integers in a group and refer only to them.In the end, enums are just ints. An example 
```cpp
enum orbitals {
	S=2 , P=6 , D=10 , F=14//By the default, the enum will start counting from 0 in the first variable assigned, but values can be explicitly assigned like above; 
}
orbitals hidrogen = S;
orbitals quark = 27; //This assignment fails, because 27 is not defined in the enum
//Using enums inside classes or structs
class Atom {
	enum Orbitals{
	S=2 , P =6 , D=10 , F=14
	};
	enum Shells{
	K=1 , L , M , N, O , P ,Q };
	Orbitals m_orbital; Shell m_shells;
public :
	void setOrbital(Orbitals orbital){m_orbital = orbital};
	void setShell(Shells shell){m_shell = shell};
}
int main(){
	Atom hidrogen;
	hidrogen.setOrbital(Atom::S);
	hidrogen.setShell(Atom::K);
	//Need to use Atom:: to refer to the enums inside Atom
}
```
