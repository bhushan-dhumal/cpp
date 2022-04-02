# split string by specific charchter

[stackowerflow](https://stackoverflow.com/questions/10058606/splitting-a-string-by-a-character)

Using vectors, strings and stringstream. A tad cumbersome but it does the trick.
``` c++
#include <string>
#include <vector>
#include <sstream>

std::stringstream test("this_is_a_test_string");
std::string segment;
std::vector<std::string> seglist;

while(std::getline(test, segment, '_'))
{
   seglist.push_back(segment);
}
```
Which results in a vector with the same contents as

``` c++
std::vector<std::string> seglist{ "this", "is", "a", "test", "string" };
```

# convert string to char*

[stackoverflow](https://stackoverflow.com/questions/7352099/stdstring-to-char)

It won't automatically convert (thank god). You'll have to use the method c_str() to get the C string version.
``` c++ 
std::string str = "string";
const char *cstr = str.c_str();
```

Note that it returns a const char *; you aren't allowed to change the C-style string returned by c_str(). If you want to process it you'll have to copy it first:
``` c++
std::string str = "string";
char *cstr = new char[str.length() + 1];
strcpy(cstr, str.c_str());
// do stuff
delete [] cstr;
```
Or in modern C++:
``` c++
std::vector<char> cstr(str.c_str(), str.c_str() + str.size() + 1);
```
  
# convert string to int without leading zeros

[atoi](https://www.simplilearn.com/tutorials/cpp-tutorial/atoi-in-cpp)

## C++ atoi() Function

The atoi() function in C++ is defined in the cstdlib header. 

It accepts a string parameter that contains integer values and converts the passed string to an integer value. 

If the string is null or has any non-integer value, atoi in C++ silently fails the execution without throwing any error or exception.

### Syntax of atoi in C++
#### The syntax of the C++ atoi() function is:
``` c++
int atoi (const char * str);
```

#### Parameters of atoi in C++:
The C++ atoi() function accepts only a single parameter, which is:

str: The string that needs to be converted to an integer value


#### Return Value of atoi in C++

The atoi() function returns the converted integer value if the execution is successful. 

If the passed string is not convertible to an integer, it will return a zero.


### Reverse stiring 
``` c++
string s("Hello world");
string rev = string(s.rbegin(),s.rend());
```
