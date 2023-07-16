Basic type in c++ are
bool -> 1 byte
char -> 1 byte
short -> 2bytes
int -> 4bytes
long -> 4bytes
long long -> 8bytes

### Decimals
double -> 2 bytes
float -> 4 bytes , declare it with f

All types of variables are numbers, meaning you can do something like ``` char = 65 ```  . But some operators behave differently whith different keywords in your variable declaration. Check [[overloading]] .

You can always check the size of your variable with the sizeof() operator. This is will be useful wihth dynamic memory allocation later.

You can also add the unsigned keyword to the variable definition to gain 1 extra bit.
One interesting detail lies in the bool size. Why 1 byte? Because of [[memory | memory adressing ]]  .
#Cpp 
