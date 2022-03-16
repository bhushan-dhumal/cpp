# move constructor
takes r-value as argument. it used to transfer ownership of resource from one object to another object.
``` c++
class A
{
   private:
      int *ptr;
   public:
      A(A&& a)
      {
        ptr = a.ptr;
        a.ptr = nullptr;
      }
}:
```
