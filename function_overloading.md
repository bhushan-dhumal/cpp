# const
C++ allows member methods to be overloaded on the basis of const type.

Overloading on the basis of const type can be useful when a function return reference or pointer.

We can make one fucntion const, that returns a const reference or const pointer, other non-const funciton, that returns non-const reference or pointer.

C++ allows funtion to be overloaded on the basis of const-ness of **parameters** only if the const paratmeter is a reference or a pointer.

# return type

Function overloading is possible in C++ but only if the fucntions must differ from each other by the types and the number of arguments in the argument list.

However, function can not be overloaded if they differ only in the return type.

Function overloading comes under compile-time polymorphism.

During compilation, the funtion signature is checked. So, functions can be overloaded, if the signatures are not the same.

The return type of a function has no effect on function overloading, therefore the same funtion signature with different return type will not be overloaded.

# floats
As per C++ standard, floating point literals(compile time constants) are treated as double unless explicitly specified by a suffix.(e.g 1.2f)

# inheritance
If a dervied class redines the base class memeber method then all the base class methods with the same name become hidden in the derived class.

If we want to overload a funtion of base class, it is possible to unhide it by using the 'using' keyword
