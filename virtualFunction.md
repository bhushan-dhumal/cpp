# Explanantion from YT
A virtual function is used to replace the implementation provided by the base class.

The replacement is always called whenever the object in question is actually of the derived class, even if the object is accessed by a base pointer rather than a derived pointer.

1. A virtual funtion is a memeber fuction which is present in the base class and redefined by the derived class.
2. When we use the same fucntion name in both base and dervied class, the funtion in base class is declared with a keyword virtual.
3. When the fuction is made virtual,  then c++ determines at run-time which function is to be called based on the type of the object pointed by the base class pointer.
Thus, by making the base class pointer to point to different objects, we can execute different versions of the virtual fucntions.

Key Points :
1. Virtual fucntion can not be static.
2. A class can have a virtual destructor but it can not have a virtual constructor.

# Explanantion from GFG

To implement virtual functions, C++ uses a special form of late binding known as the virtual table or vTable.

The **virtual table** is a lookup table of funtions used to resolve function calls in a dynamic/late bindng manner.


Every class that uses virtual funtion(or is dervied from a class that uses virtual funtion) is given its own virtual table.


This table is simply a static array that the compiler creates at compile time.

A virtual table contains one entry for each virtual fucntion that can be called by object of the class.


Each entry in this vTable is simply a Fucntion Pointer that points to the most-derived funcion accessibile by that class i.e. the most Base class.


The compiler also adds a hidden pointer to the base class, which we call \*__vPtr.


\*__vPtr is set (automatically) when a class instance is created so that it points to the virtual table for that class.

\*__vPtr is inherited by derived classes.


Links

[virtual-table-vptr](https://www.go4expert.com/articles/virtual-table-vptr-t16544/)

[gfg](https://practice.geeksforgeeks.org/problems/what-are-vtable-and-vptr)
