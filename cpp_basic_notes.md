# C++ Basics

Author: __*yufanana*__

This documentation was produced from the C++ for Complete Beginners course by John Purcell available for free on caveofprogramming.com and udemy.com. :)
</br>
____

## Table of Contents <a name="top"></a>

 1. [Basic Syntax](#1)<br>
    1.1 [Hello World](#1.1) <br>
    1.2 [Namespaces](#1.2) <br>
    1.3 [User Input](#1.3) <br>
    1.4 [Data Types](#1.4) <br>
    1.5 [If, else if, else](#1.5) <br>
    1.6 [While](#1.6) <br>
    1.7 [Do](#1.7) <br>
    1.8 [For](#1.8) <br>
    1.9 [Arrays](#1.9) <br>
    1.10 [Switch](#1.10) <br>
    1.11 [Conventions](#1.11) <br>
 2. [Subroutines](#1)<br>
    2.1 [Functions](#2.1) <br>
    2.2 [Prototypes](#2.2) <br>
 3. [Object Oriented Coding](#3)<br>
    3.1 [Classes](#3.1) <br>
    3.2 [Constructors & Destructors](#3.2) <br>
    3.3 [Overloading Constructors](#3.3) <br>
    3.4 [Getters & Setters](#3.4) <br>
    3.5 [Copy Constructors](#3.5) <br>
    3.6 [Polymorphism](#3.6) <br>
    3.7 [String Streams](#3.7) <br>
 4. [Object Oriented Coding](#4)<br>
    4.1 [Pointers](#4.1) <br>
    4.2 [Pointers & Arrays](#4.2) <br>
    4.3 [Character Arrays](#4.3) <br>
    4.4 [Reference Variables](#4.4) <br>
    4.5 [*const* Keyword](#4.5) <br>
    4.6 [*new* Operator](#4.6) <br>
 5. [Inheritance](#5)<br>
    5.1 [Parent & Sub-class](#5.1) <br>
    5.2 [Encapsulation](#5.2) <br>
    5.3 [Inherited Constructors](#5.3) <br>
    5.4 [*virtual* Keyword] (#5.4) <br>
 6. [Miscellaneous](#6)<br>
    6.1 [2's Complement](#6.1) <br>
    6.2 [*static* Keyword](#6.2) <br>
    6.3 [Bitwise Operator](#6.3) <br>
    6.4 [Pre & Post Fix](#6.4) <br>
    6.5 [Vectors](#6.5) <br>
 7. [Developing a Program](#6)<br>
    7.1 [Read from File](#7.1) <br>
    7.2 [Program Design](#7.2) <br>


## Section 1: Basic Syntax <a name="1"></a>
[Go to top](#top)

### 1.1 Hello World <a name="1.1"></a>
[Go to top](#top)

Use `#include <iostream>` to include the iostream *(input output stream)* file. This allows us to use console functions like `cout` & `cin`.

```c++
#include <iostream>

using namespace std;

int main(){
    cout << "Hello world" << endl;  // end line
    return 0;          // 0 means no error
}
```
`<<` can be read as *put to/insertion operator*.

`endl` flushes out any saved text outputs from cout with a line feed.

`flush` tells OS to output text without a line feed. Or, one can just omit this.

Possible to just do `cout << endl` to add line feed.

### 1.2 Namespaces <a name="1.2"></a>
[Go to top](#top)

`namespace` is a declarative region to define the scope of identifiers and prevent name collisions. For example,

`fyf::count()` for my user defined.

`std::count()` as the standard C++ function.

### 1.3 User Input <a name="1.3"></a>
[Go to top](#top)

`>>` can be read as *extract from/extraction operator*.

```c++
int age;
cout << "Enter your age: " << flush;
cin >> age;
cout << "Your age is " << age << endl;
```

### 1.4 Data Types <a name="1.4"></a>
[Go to top](#top)

Memory may differ from system to system. Should verify on the machine you are using.

Data | Size (bytes) | Range
:--- | :---: | :---
short int | 2 | -32,768 to 32,767
unsigned short int | 2 | 0 to 65,535
unsigned int | 4 | 0 to 4 billion+
int | 4 | -2 billion to 2 billion+
--- | --- | ---
long int | 4 | 
unsigned long int | 8 | 
long long int | 8 | 
--- | --- | ---
signed char | 1 | -128 to 127
unsigned char | 1 | 0 to 255
--- | --- | ---
float | 4 | 
double | 8 |
long double | 12 |

Helpful constants and function to read system settings.
```c++
LONG_MAX, INT_MAX, INT_MIN, sizeof(int)
```

Can prefix variable names with the first letter of the data type.
```c++
float fValue, double dValue, long lValue
bool bValue, char cValue
```

`char` uses [ASCII table](http://www.asciitable.com/)

Casting can be done to convert one data type to another using `()`.

`value1 = (double)7/2;`

### 1.5 If, else if, else <a name="1.5"></a>
[Go to top](#top)


```c++
if(condition == 1){
    // do something
}
else if(condition == 2){
    // do something
} 
else{
    // do something
}
```

__? : operator__ <br>
Exp1 ? Exp2 : Exp3; <br>
Evaluate Exp1. <br>
If true, Exp2 is evaluated and becomes the value of the expression. <br>
If false, Exp3 is evaluated and becomes the value of the expression. <br>

```c++
if(y < 10>){
    var = 30;
} else {
    var = 40;
}

var = (y < 10)? 30: 40;
```

AND `&&` 

OR `||` 

Inequalities `>, >=, <, <=, !=, ==` 

C++ uses __short-circuit boolean__ evaluation.

`bool1 && bool2` If bool1 is false, it will not evaluate bool2.

`bool1 || bool2` If bool1 is true, it will not evaluate bool2.

Use `&` and `|` to evaluate all expressiosn.

### 1.6 While <a name="1.6"></a>
[Go to top](#top)


```c++
while(i<=3){
        cout << "Hello there" << endl;
        i = i + 1; // i++
    }
```

### 1.7 Do <a name="1.7"></a>
[Go to top](#top)

`do` executes the code at least once, then it checks the condition as a `while` loop.

```c++
do{ 
    cout << "Enter password > " << flush;
    cin >> input;

    if(password != input){
        cout << "Access denied" << endl;
    }
} while(input != password);
```

### 1.8 For <a name="1.8"></a>
[Go to top](#top)

Remember to declare __data type__ of counter.

`for(<counter>; <condition>; <code done at end of loop>)`

```c++
for(int i = 0; i<5; i++){     
        cout << "Hello " << i << endl;
    }
```

`break` is used to escape the loop. </br>
`continue` is used to skip the rest of the loop.

Below is a handy trick for a dynamic loop exit condition.

```c++
int numberOfElements = sizeof(numberArray)/sizeof(int);
```

### 1.9 Arrays <a name="1.9"></a>
[Go to top](#top)


Errors will not be given if index is out of range. Array will contain random values or zero if not initialised.

```c++
int values[3];   // 3 items in array
values[0] = 4;
values[1] = 55;
values[2] = 25;
cout << values[0] << endl;

double numbers[4] = {2.5,23.4,123.4,22.3};
string fruits[] = {"apple","banana","pear"};
string animals[2][3]={
    {"fox","dog","cat"},
    {"cow","bird","lion"}
};
```

### 1.10 Switch <a name="1.10"></a>
[Go to top](#top)


Alternative implementation of `if` blocks. Switch case labels can only be used with `int` in default mode, cannot be variables. Add `break` after each case.

```c++
int value;
std::cin >> value;

switch(value){
case 4:     // take action if value is 4
    cout << "Value is 4" << endl;
    break;
case 5: 
    cout << "Value is 5" << endl;
    break;
case 6:
    cout << "Value is 6" << endl;
    break;
default:    // if no case labels matched
    cout << "Unrecognised value" << endl;
}
```
### 1.11 Conventions <a name="1.11"></a>
[Go to top](#top)

Following Java type convention, <br>
Variables are given lower case letters. <br>
Classes are given upper case letters.

## Section 2: Subroutines <a name="2"></a>
[Go to top](#top)

____
### 2.1 Functions <a name="2.1"></a>
[Go to top](#top)

Specify return type before the function name. </br>
`void` has no return type.

```c++
void displayName(){
    cout << "Your name is John" << endl;
}

int getAge(){
    int age;
    cout << "Enter your age: " << flush;
    cin >> age;
    return age;
}

int main(){
    // do something

    return 0; // for exit success
}
```

### 2.2 Prototypes <a name="2.2"></a>
[Go to top](#top)


Prototypes are used at the beginning of the file before the `main` function of in the header files. It serves to tell the program that such a function exists, and to look out for the implementation code later.

If the prototype is in the same `.cpp` as `main`, the following can be done.

```c++
void doSomething(); //prototype

int main(){
    doSomething();
    doSomething();
    return 0;
}

void doSomething(){
    cout << "Hello" << endl;
}
```
____
## Section 3: Object Oriented Coding <a name="3"></a>
[Go to top](#top)

### 3.1 Classes <a name="3.1"></a>
[Go to top](#top)

Default visibility of `class` is private. </br>
Default visibility of `struct` is public

Member functions <--aka--> Class methods </br>
Data members <--aka--> Class properties

`private` data members/member functions can only be accessed within the class.

*Good practice* </br>
Have a header file for all the prototypes of member functions and data members. Explanations of functions can go here. Have a `.cpp` file as the implementation code. `#include` the header file in the `.cpp` file. Define data members and member functions separately. Define private then public.

```c++
class Cat{
    private:
        // data members
    public:
        // data members
    private:
        // members functions
    public:
        // members functions
}
```

### 3.2 Constructors & Destructors <a name="3.2"></a>
[Go to top](#top)


Capitalise the first letter.
```c++
Cat::Cat(){
    // create cat
}

Cat::~Cat(){
    // destroy cat
}
```
### 3.3 Overloading Constructors <a name="3.3"></a>
[Go to top](#top)


It is like having different constructing modes, depending on the number of parameters or type of parameters passed.

```c++
Person::Person() {
	name = "undefined";
	age = 0;
}
Person::Person(string newName) {
	name = newName;
	age = 0;
};
Person::Person(string newName, int newAge) {
	name = newName;
	age = newAge;
};
```

### 3.4 Getters and Setters <a name="3.4"></a>
[Go to top](#top)

Used to read or write `private` data members.

```c++
void Person::setName(string newName) {
	name = newName;
}

string Person::getName() {
	return name;
}
```
### 3.5 Copy Constructors <a name="3.5"></a>
[Go to top](#top)


Copies field from `other` object to the present object.

```c++
// copy constructor definition
Animal(const Animal &other): name(other.name){cout << "Animal created by copying" << endl;}; 

Animal animal1;             // normal constructor
animal1.setName("Freddy");
Animal animal2 = animal1;      // copy constructor
```

### 3.6 Polymorphism <a name="3.6"></a>
[Go to top](#top)

An object can be part of multiple classes. It uses the idea of overloading operators and functions.

Say, `Animal` is a base class. `Cat` is a sub-class of `Animal`, and `HouseCat` is a sub-class of `Cat`. A base class pointer can refer to any derived class object.

```c++
Animal* pAnimal1 = new Cat;  
Animal* pAnimal2 = new HouseCat;
delete pAnimal1;
delete pAnimal2;
```

### 3.7 String Streams <a name="3.7"></a>
[Go to top](#top)


Special type of string. May be required for certain applications like reading csv files. `cin` is an example of utilisation of streams (I think).

```c++
#include <sstream>

int main() {
	string name = "Bob";
	int age = 32;

	stringstream ss;
	ss << "Name is: ";
	ss << name;
	ss << "; Age is: ";
	ss << age;

	cout << ss.str() << endl;

	return 0;
```
____
## Section 4: Pointers & Memory <a name="4"></a>
[Go to top](#top)


### 4.1 Pointers <a name="4.1"></a>
[Go to top](#top)


Use `*` to initialise pointer variables. </br>
Use `&` to dereference the pointer variable. </br> 
Prefix `p` is often given to pointer variables.

```c++
int nValue = 8;
int *pnValue = &nValue; 
// int pointer = memory address of nValue
nValue = 9;

cout << "Pointer to int address: " << pnValue << endl;
// prints something like 0x61fe14

cout << "Int value: " << nValue << endl;
// prints 9

cout << "Int value via pointer: " << *pnValue << endl; 
// dereference pointer to change value in memory address
// prints 9

```
### 4.2 Pointers & Arrays <a name="4.2"></a>
[Go to top](#top)


Array pointers do not contain information about memory size. <br>
Array pointers can be incremented to iterate through the array. <br>
Possible to compare pointers `pTexts != pEnd`.

```c++
string texts[] = {"one","two","three","four"};
int length = sizeof(texts)/sizeof(string);
for(int i=0;i<length;i++){
    cout << pTexts[i] << " " << flush;
}
cout << endl;

for(int i=0;i<length;i++, pTexts++){
    cout << *pTexts << " " << flush;
}
cout << endl;
```

`string *pElement = texts;` gives address of first element </br>
`string *pEnd = &texts[length];` gives address of last element

### 4.3 Character Arrays <a name="4.3"></a>
[Go to top](#top)


Strings as `char` arrays have to be null terminated.</br>
`char text1[6] = {'h','e','l','l','o',0};` </br>

Blank will be printed if the 5th index is printed here. </br>
`char text2[] = "hello";` </br>
Thus, should stop iterating right before the NULL terminating character to avoid dealing with blanks/NULL.

### 4.4 Reference Variables <a name="4.4"></a>
[Go to top](#top)


Reference variables is like the same as the original variable. <br>
Prefix a variable with a single `&` to use as a reference variable.

```c++
int value3 = 8;
int &value4 = value3;     
```
In the example above, `&value4` is a reference variable of `value3`. <br>
`&value4` cannot hold a new value. <br>
Any edits made to `value4` will apply to `value3` too. They are the same thing.


### 4.5 *const* Keyword <a name="4.5"></a>
[Go to top](#top)


`const` disallows any change in object properties when used in member funtions (helps reduce bugs), or any change in value when used for variables.

`const` variables requires inline declaration and definition. *e.g.* </br>
`const double PI = 3.141592;`

*Convention*: use uppercase for `const` variables e.g. `PI, SCREEN_WIDTH, NPARTICLES`.

### 4.6 *new* Operator <a name="4.6"></a>
[Go to top](#top)


Returns a pointer to an object created in the heap. </br>
`delete` has to be called whenever `new` is used to free up memory resources or avoid memory leak. </br>
Use `[]` to `delete` multiple objects. </br>
`->` can be used like a dot operator on these object pointers.

```c++
Animal *pCat1 = new Animal();
pCat1->setName("Freddy");
pCat1->speak();
delete pCat1;

Animal *pAnimal = new Animal[5];
delete [] pAnimal;

char *pMem = new char[1000];
delete [] pMem;
```
____

## Section 5: Inheritance <a name="5"></a>
[Go to top](#top)


### 5.1 Parent & Sub-class <a name="5.1"></a>
[Go to top](#top)


Here, `Cat` is a sub-class of `Animal`.
```c++
class Cat: public Animal {
    // class definitions
};
```

### 5.2 Encapsulation <a name="5.2"></a>
[Go to top](#top)

Encapsulation is the concept of binding the data and the functions that manipulate the data together, keeping them safe from outside interference and misuse. This led to the concept of __data hiding__.

This allows for __data abstration__ where only the interfaces are exposed, and hiding the implementation details from the user.

*YuFan: I think this is specific to private members*.

### 5.3 Inherited Constructors <a name="5.3"></a>
[Go to top](#top)

If a sub-class object is created, the parent class constructor will be called first, followed by the sub-class constructor.

Constructors can only be inherited from direct super class.
```c++
class Machine {
private:
    int id;
public:
    Machine(): id(0) {cout << "Machine no arg constructor called" << endl;}
    Machine(int m_id): id(m_id) {cout << "Machine ID arg constructor called" << endl;}
    void info() {cout << "ID: " << id << endl;}
};

class Vehicle: public Machine {
public:
    Vehicle() {cout << "Vehicle no arg constructor called" << endl;}
    // not allowed to refer to id in Vehicle class
    Vehicle(int v_id): Machine(v_id) {cout << "Vehicle ID arg constructor called" << endl;}
    // constructors are not auto inherited from super class
};
```

### 5.4 *virtual* Keyword <a name="5.4"></a>
[Go to top](#top)

Virtual functions in derived classes are used to override/re-defined member functions in the base class.

So, derived class objects will call the virtual function instead of the original base class member function.

More information from [GeeksforGeeks](https://www.geeksforgeeks.org/virtual-function-cpp/).

## Section 6: Miscellaneous <a name="6"></a>
[Go to top](#top)

### 6.1 2's Complement <a name="6.1"></a>
[Go to top](#top)

It is a method to deal with arithmetic operation in computers at the bit-level. `min = -max - 1`

There is also a 1's complement method.

### 6.2 *static* Keyword <a name="6.2"></a>
[Go to top](#top)

`static` variables are associated with the class, not the object. <br>
They are shared between all objects of the class. <br>
They exist even when no objects are instantiated. <br>
Objects are able to change static variables. 

`static` functions can only access `static` variables.

### 6.3 Bitwise Operator <a name="6.3"></a>
[Go to top](#top)

Bitwise operators work at bit-level by comparing the 1's and 0's.

E.g. `&` AND operator
| Item | Bits|
| :--- | :--- |
|color |  101011000100110100110100|
|mask | 111111110000000000000000|
|result | 101011000000000000000000|

[GeeksforGeeks](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/) has a good summary haha.

### 6.4 Pre & Post Fix <a name="6.4"></a>
[Go to top](#top)

`value++`: use the variable, then implement operator
`++value`: implement operator, then use the variable

This will output 1.
```c++
int value = 1;
std::cout << "Postfix: " << value++ << std::endl;
```

This will output 2.
```c++
int value = 1;
std::cout << "Prefix: " << ++value << std::endl;
```

### 6.5 Vectors <a name="6.5"></a>
[Go to top](#top)

Vectors are more versatile than arrays. `#include <vector>` is required. Possible to have a vector of vectors. </br>
`vector<vector<double>> data;`

`push_back()` adds the element to the back of the array.

## Section 7: Developing a Program <a name="7"></a>
[Go to top](#top)

### 7.1 Read from File <a name="7.1"></a>
[Go to top](#top)

`getline(myFile, line)` returns true when there is still a new line to be read.

`getline(ss,value,',')` works with the `ss` stream, stores each read in `value` using '`,`' as the delimiter.

The sample code below reads a .csv file with a header. Each line contains `float`/`double` values.
```c++
#include <iostream>
#include <vector>
#include <fstream>
#include <sstream>

using namespace std;

void func(vector<vector<double>> &data, string fileName){

    ifstream myFile;
    string line;
    vector<double> targetData;
    myFile.open(fileName);

    getline(myFile,line);       // skip first line
    while (getline(myFile,line)) {
        stringstream ss(line);
        string value;
        targetData.clear();
        
        while(getline(ss,value,',')){
            double temp = stod(value);
            targetData.push_back(temp);
        }
        data.push_back(targetData);
    }

    myFile.close();
}

int main(){
    
    vector<vector<double>> data;
    string fileName = "data.csv";
    func(data, fileName);

    for(int i=0; i<data.size();i++){
        for(int j=0; j<data[i].size();j++){
            cout << data[i][j] << ", ";
        }
        cout << endl;
    }

    return 0;
}
```

### 7.2 Program Design <a name="7.2"></a>
[Go to top](#top)

__Header files__ </br>
Can be designed in mind for it to be reusable in other contexts. <br>
So, try to design code unique to your context in a separate file. <br>
And possibly transferrable files should not reference those unique files.
