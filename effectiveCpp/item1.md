# Item 1
## View C++ as a federation of languages.
1. c
2. object-oriented c++
3. Template c++
4. STL

Rules of effective c++ vary depending on the part of c++ you are using.
E.g. pass-by-value is generally more efficient than pass-by-reference for build-in (i.e. C-like) types, but when you move from C part of C++ to object-oriented c++, the existence of user-defined constructors and destructors means that pass-by-reference-to-const is usually better.
This is especially the case when working in Templates C++, because there, you don't even know the type of object you're dealing with . When you cross into STL, however you know that iterators and fuctions objects are modeled on pointers in C, so for iterators and function objects in the STL, the old c pass-by-value rule applies again
