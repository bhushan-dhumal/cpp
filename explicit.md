# Use of explicit keyword

Explicit keyword is used to mark constructors to not implcitly convert types in c++.

It is optional for constructors that take exactly one argument and works on constructors(with single argument) since those are the only constructors that can be used in type casting.


In c++, if a class has a constructor which can be called with a single argument then this constructor becomes conversion constructor because such a constructor allows concersion of the single argument to the class being constructed.


We can avoid such implicit conversion as these may lead to unexpcted results.

We can make the constructor explicit with the help of **explicit keyword**

Link : [gfg](https://www.geeksforgeeks.org/use-of-explicit-keyword-in-cpp/#:~:text=Explicit%20Keyword%20in%20C%2B%2B%20is%20used%20to%20mark%20constructors,be%20used%20in%20type%20casting.)

## Example(own) :
``` c++
#include<iostream>
using namespace std;

// to keep code short struct is used instead of class
struct Person 
{ 
    Person() // default constructor is added
    {
        cout<< "Person::Person() called " <<endl;
    }
    
    /* explict */ Person(int x)
    {
        cout<< " Person::Person(int) called "<<endl;
    }
    
};


int main()
{
    Person p = 10;
}
```
Output : ```  Person::Person(int) called  ```

Error when explicit is mentioned before parametirized constructor :
```
error: conversion from ‘int’ to non-scalar type ‘Person’ requested
```
P.S. Not sure about the reason but when you make constructor explicit it should be the only constructor present in class.
If you have any other constructor it gives below error.
```
error: ‘explict’ does not name a type
```


