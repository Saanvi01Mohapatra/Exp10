# EXP-10
## Aim
To study and implement Pointer Operations (Call by value and Call by reference)
## Theory
*Call by Reference:* In Call by Reference, instead of passing a copy of the variable, the address (or reference) of the variable is passed to the function. The function can then modify the actual value of the argument used to call the function. Call by Value is safer when you want to ensure that the original data isn’t modified.

*Call by Reference:* In Call by Reference, instead of passing a copy of the variable, the address (or reference) of the variable is passed to the function. The function can then modify the actual value of the argument used to call the function. Call by Reference is more efficient for large data structures and when you need to modify the original data.

| Aspect                  | Call by Value                                  | Call by Reference                            |
|-------------------------|------------------------------------------------|----------------------------------------------|
| *Definition*          | Passes a copy of the actual parameter's value. | Passes a reference (or address) to the actual parameter. |
| *Parameter Type*      | The function receives a duplicate of the value. | The function receives a reference to the original variable. |
| *Effect on Original*  | Changes made to the parameter within the function do not affect the original value. | Changes made to the parameter within the function directly affect the original variable. |
| *Memory Usage*        | Typically uses more memory since a copy of the value is created. | Generally uses less memory as only a reference is passed, not the actual value. |
| *Performance*         | May be slower if the value is large or complex, due to copying overhead. | Usually faster as only the reference is passed, reducing the need for copying large data structures. |


### CODE1:
```
/*Saanvi mohapatra
23070123110
ENTC B2
EXCP 10 _1*/
#include<iostream> 
using namespace std; 
void swap(int x, int y) 
{
    int swap;
    swap=x;
    x=y;
    y=swap;
}

int main() 
{
    int a=20, b=50;
    swap(a,b);
    cout<<"Value of a is: "<<a<<"\n";
    cout<<"Value of b is: "<<b<<"\n";
    return 0;
}
```
### OUTPUT:
```
[Running] cd "c:\Users\Saanvi\Desktop\CDS\" && g++ EXP10_1.cpp -o EXP10_1 && "c:\Users\Saanvi\Desktop\CDS\"EXP10_1
Value of a is: 20
Value of b is: 50
```
### Code 2:
```
/*Saanvi
23070123110
ENTC B2
EXCP 10 _1*/
#include<iostream> 
using namespace std; 
void swap(int *x, int *y) 
{
    int *swap;
    swap=x;
    x=y;
    y=swap;
}

int main() 
{
    int a=32,b=34;
    swap(a,b);
    cout<<"Value of a is: "<<a<<"\n";
    cout<<"Value of b is: "<<b<<"\n";
    return 0;
}
```
### output:
```
[Running] cd "c:\Users\Saanvi\Desktop\CDS\" && g++ tempCodeRunnerFile.cpp -o tempCodeRunnerFile && "c:\Users\Saanvi\Desktop\CDS\"tempCodeRunnerFile
Value of a is: 34
Value of b is: 32
```
### Code 3:

```
/*Saanvi
23070123112
ENTC B2
EXCP 10 _3*/#include<iostream> 
using namespace std; 
void swap(int *x, int *y) 
{
    int swap;
    swap=*x;
    *x=*y;
    *y=swap;
}

int main() 
{
    int a=12,b=24;
    swap(&a,&b);
    cout<<"Value of a is: "<<a<<"\n";
    cout<<"Value of b is: "<<b<<"\n";
    return 0;
}
```
### Output:
```
[Running] cd "c:\Users\Saanvi\Desktop\CDS\" && g++ tempCodeRunnerFile.cpp -o tempCodeRunnerFile && "c:\Users\Saanvi\Desktop\CDS\"tempCodeRunnerFile
Value of a is: 24
Value of b is: 12

[Done] exited with code=0 in 0.379 seconds
```
## Conclusion:

Call by Value 1 is effective when you need to maintain the integrity of the original data and when working with small or primitive data types where copying overhead is minimal. It provides safety against unintended modifications but can become inefficient with large data.

Call by Reference is ideal for scenarios where modifying the original data is desired or necessary, and it offers performance benefits due to reduced copying. It is particularly beneficial for large data structures but requires careful handling to avoid accidental side effects.

The choice between Call by Value 1 and Call by Reference should be made based on the requirements of data modification, memory efficiency, and performance considerations.
