### C + OOP = C++
__Object-oriented programming (OOP) is a computer programming model that organizes software design around data, or objects, rather than functions and logic.__
## Feature of OOP
- Class
- Object
- Abstraction
- Polymorphism
- Inheritance
- Encapsulation

## What is a class ?
A class is a template from which individual object can be created.   
<br />
Class Declaration
---
```c++
class Student{
    public:
        int id;
        double gpa;
}
```

## What is an Object?
Any class type variable is called an object.    
<br />  
Object Declaration
---
```c++
classname objectName
//single object
Student Rahim
//Multiple object
Student Rahim, Karim, Salam, Borkot
```

## Example of Object, Class and function 
```c++
#include<iostream>
using namespace std;
class Student{
    public:
        int id;
        double gpa;
        void display(){
            cout<<id<<" "<<gpa<<endl;
        }
        void setValue(int x, double y){
            x = id;
            y = gpa;
        }
}
int main()
{
    Student Jasim, Rahim;
    Jasim.id = 101;
    Jasim.gpa = 5.00;
    // cout<<Jasim.id<<" "<<Jasim.gpa<<endl;
    Jasim.display(); // do same task like above line

    // Rahim.id = 102;
    // Rahim.gpa = 5.00;
    Rahim.setValue(102, 5.00);
    // cout<<Rahim.id<<" "<<Rahim.gpa<<endl;
    Rahim.display();
}
```

## Constructor in C++   
_constructor name will be same name of class name_
```c++
#include<iostream>
using namespace std;
class Student{
    public:
        int id;
        double gpa;
        void display(){
            cout<<id<<" "<<gpa<<endl;
        }
        //parametrized constructor
        Student(int x, double y){
            id = x;
            gpa = y;
        }
        //default constrcutor;
        Student(){
            cout<<" Default Constructor "<<endl;
        }
}
int main()
{
    //called default constructor
    Student obj;
    //called parametrized constructor
    Student Jasim(101, 5.00);
    Jasim.display(); 

    Student Rahim(102, 4.76);
    Rahim.display();
}
```

## What is Constructor
Constructor is a special type of function that is used to initialize the object.

## Properties of Constructor
- constructor is a special type of function
- constructor has the same name as that of the class it belongs 
- constructor has no return type not even void
- it is called automatically

## Types of Constructor
1. Default constructor
2. Parametrized constructor

## Destuctor
Destructor is a special type of function that is used to destroyed an object.
## Example of constructor and destructor
```c++
#include<iostream>
using namespace std;
class Student{
    public:
        int id;
        double gpa;
        void display(){
            cout<<id<<" "<<gpa<<endl;
        }
        //parametrized constructor
        Student(int x, double y){
            id = x;
            gpa = y;
        }
        //descructor;
        ~Student(){
            cout<<" Class will be finished" <<endl;
        }
        
}
int main()
{
    //called default constructor
    Student obj;
    //called parametrized constructor
    Student Jasim(101, 5.00);
    Jasim.display(); 

    Student Rahim(102, 4.76);
    Rahim.display();
}
```

## Selection Operator(->)
we can access or call variable or function inside class using pointer instead of (.)
```c++
int main(){
    Student ob;
    Student *p = &ob;
    p->display()
}
```

## Constant Variable
can not be modified after using variable using const keyword

```const int x = 20;```

## Constructor Initializer
```c++
#include<iostream>
using namespace std;

class Student{
    public:
        const int admissionFee;
        const int examFee;
        int id;

        Student(int x, int y, int z):admissionFee(x), examFee(y){
            cout<<admissionFee<<endl;
            cout<<examFee<<endl;
            id = z;
            cout<<"Id = "<<endl;
        }
        
        
}
int main()
{
  Student ob(52003, 3440, 2);
  return 0;  
}
```

## Encapsulation
Encapsulation is a process of 
- combining variables and functions in a single unit (class)
- Protecting data by declaring them as private


Private data will be hidden from other classes and they can only be accessed through public function of their current class. That is known as data hiding.

```c++
#include<iostream>
using namespace std;

class Student{
    private:
        string name;
    public:
        void setName(string x){
            name = x;
        }
        void getName(){
            return name;
        }
        
        
}
int main()
{
  Student ob;
  ob.setName('jasim');
  cout<<ob.getName()<<endl;
  return 0;  
}
```
_When we should use `this keyword`_   
local variable and class variable name same

## What is Inheritance ?
The process of obtaining the data members and functions from one class to another class is known as inheritance.

## What are the importance of inheritance?
- code reusability.
- Application development time is less.
- Application take less memory.
- Application execution time is less.

```c++
#include<iostream>
using namespace std;
class Person{
    public:
        string name;
        int age;
        void display1(){
            cout<<name<<" "<<age<<endl;
        }
}
class Student:public Person{
    public:
        int id;
        void display2(){
            // cout<<name<<" "<<age<<" "<< id<<endl;
            display1();
        }   
}
int main()
{
  Student std;
  std.id = 101;
  std.name = "rahim";
  std.age = 26;
  std.display2();

  return 0;  
}
```

## Types of Inheritance:
1. Single Inheritance
2. Multilevel Inheritance
3. Hierarchical Inheritance
4. Multiple Inheritance
5. Hybrid Inheritance

### 1. Single Inheritance
``` A-> B```
In this sort of inheritance, one subclass inherit from one superclass.
```c++
class A{
    ..............
    .......
}

class B:public A{
    ......
}
```
### 2. Multilevel Inheritance
In this sort of inheritance, the superclass for one is the subclass for Another.
```c++
In this sort of inheritance, the superclass for one is the subclass for Another.
```
```A->B->C->D```
```c++
class A{
    ..............
    .......
}

class B:public A{
    ......
}
class C:public B{
    .....
}
```

### 3. Hierarchical Inhertance
In this sort of inheritance, multiple subclass derived from single superclass.

``` 
A-> B
A-> C
A-> D
```
```c++
class A{
    ..............
    .......
}

class B:public A{
    ......
}
class C:public A{
    .....
}
```
### 4. Multiple Inheritance
In multiple inheritance, a class can inherit more than one class.
```
A->B
c->B
```
### 5. Hybrid Inheritance
Hybrid Inheritance is a combination of more than one type of inheritance.


### Function overriding
function name will be same and parameter list will be same but work in different purposes.

### Function overloading vs function overriding   
|Function Overloading | Function Overriding |
|----------- | --------------|
| Parameter must be different | Parameter must be same |   
|It occurs within the same class | It occurs between two classes - a sub class and a super class |   
|Inheritance is not involved | Inertiance is involved |  
|Return type may or may not be same | Return type must be same |   
| one method does not hide another | child method hides parent another |


## Polymorphism
poly + morphism
= many + forms

### Types of Polymorphism
1. Compile type polymorphism / static binding - Function overloading
2. Run type polymorphism / dynamic binding - Function overriding

## Abstraction
### What is Abstraction ?
Abstraction is the process of hiding the implementation details and showing only the functionality to the user.

### Properies of Abstract class
---
- object can be created.
    - Example:MobileUser(m);(invalid)
- we can create pointer and reference of base abstract class points
    - Example:MobileUser *m;
- It can have constructor





