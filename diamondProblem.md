# The diamond problem
The diamond problem occurs when two superclasses of a class have a common base class.

For e.g. 

![diamondEg](https://user-images.githubusercontent.com/10953202/159409099-8fcdc9f9-9eef-4bf8-95fc-bd079085ec0a.png)

``` c++

#include<iostream>
using namespace std;

// to keep code short struct is used instead of class
struct Person 
{ 
    Person(int x)
    {
        cout<< " Person::Person(int) called "<<endl;
    }
};

struct Father : Person
{
    Father(int x) : Person(x) 
    {
        cout<< " Father::Father(int) called "<<endl;
    }
};

struct Mother : Person
{
    Mother(int x) : Person(x) 
    {
        cout<< " Mother::Mother(int) called "<<endl;
    }
};

struct Child : Father, Mother 
{
    // constructor of base classes will be called in order of inheritance not in below order
    Child(int x) : Mother(x), Father(x) 
    {
        cout<< " Child::Child(int) called "<<endl;
    }
};

int main()
{
    Child c(30);
}
```

Following is output of this program:
```
 Person::Person(int) called 
 Father::Father(int) called 
 Person::Person(int) called 
 Mother::Mother(int) called 
 Child::Child(int) called 
```

You can see ambigutiy here. The constructor of person class is called twice. Once when Father object is created and next when the mother object is created.
The properties of the person class are inherited twice, giving rise to ambiguity.

Also the Person object's destructor will also be called twice when child object is destructed.

## Solution to diamond problem

Solution is to use the **virtual** keyword.

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
    
    Person(int x)
    {
        cout<< " Person::Person(int) called "<<endl;
    }
};

struct Father : virtual Person // note virtual keyword
{
    Father(int x) : Person(x) 
    {
        cout<< " Father::Father(int) called "<<endl;
    }
};

struct Mother : virtual Person // note virtual keyword
{
    Mother(int x) : Person(x) 
    {
        cout<< " Mother::Mother(int) called "<<endl;
    }
};

struct Child : Father, Mother 
{
    // constructor of base classes will be called in order of inheritance not in below order
    Child(int x) : Mother(x), Father(x) 
    {
        cout<< " Child::Child(int) called "<<endl;
    }
};

int main()
{
    Child c(30);
}
```
Output
```
 Person::Person() called 
 Father::Father(int) called 
 Mother::Mother(int) called 
 Child::Child(int) called 
```

We have used the **virtual** keyword when classes Father and Mother inherit the Preson class.

This is called "virtual inheritance" which gurantees that only a single instance of the inherited class(i.e. person class) is passed on.

In other words, the child class will have a single instance of Person class, shared by both the Father and Mother classes.
By having a single instance of the Person class, the ambiguity is resolved.

## Virtual inheriance calls default constructor

One thing to note about virtual inheriance is that even if the parameterized constructor of person class is explicitly called by Father and Mother class contructor through initialization lists, only the default constructor of the person class will be called.

This is because there's only a single instance of a virutal base class that is shared by multiple classes that inherit from it.

To prevent the default constructor running multiple times, the constructor for a virtual base class is not called by the class inheriting from it. Instead , teh constructor is called by the constructor of the concreate class.

In the above code Child class directly calls the base constrctor of Person.

## How to call parameterized constructor of virtual base class

You can do so by explicitly calling it in child class rather than the father or mother classes.

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
    
    Person(int x)
    {
        cout<< " Person::Person(int) called "<<endl;
    }
};

struct Father : virtual Person // note virtual keyword
{
    Father(int x) // optional-not callind person's constructor
    {
        cout<< " Father::Father(int) called "<<endl;
    }
};

struct Mother : virtual Person // note virtual keyword
{
    Mother(int x) // optional-not callind person's constructor
    {
        cout<< " Mother::Mother(int) called "<<endl;
    }
};

struct Child : Father, Mother 
{
    // explicitly calling Person's parameterized constructor
    Child(int x) : Mother(x), Father(x) , Person(x)
    {
        cout<< " Child::Child(int) called "<<endl;
    }
};

int main()
{
    Child c(30);
}

```
Output
```
 Person::Person(int) called 
 Father::Father(int) called 
 Mother::Mother(int) called 
 Child::Child(int) called 
```

Sources : 

[source](https://www.makeuseof.com/what-is-diamond-problem-in-cpp/)

[gfg](https://www.geeksforgeeks.org/multiple-inheritance-in-c/)
