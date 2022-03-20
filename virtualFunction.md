A virtual function is used to replace the implementation provided by the base class.

The replacement is always called whenever the object in question is actually of the derived class, even if the object is accessed by a base pointer rather than a derived pointer.

1. A virtual funtion is a memeber fuction which is present in the base class and redefined by the derived class.
2. When we use the same fucntion name in both base and dervied class, the funtion in base class is declared with a keyword virtual.
3. When the fuction is made virtual,  then c++ determines at run-time which function is to be called based on the type of the object pointed by the base class pointer.
Thus, by making the base class pointer to point to different objects, we can execute different versions of the virtual fucntions.

Key Points :
1. Virtual fucntion can not be static.
2. A class can have a virtual destructor but it can not have a virtual constructor.

Links

[virtual-table-vptr](https://www.go4expert.com/articles/virtual-table-vptr-t16544/)

[gfg](https://practice.geeksforgeeks.org/problems/what-are-vtable-and-vptr)
