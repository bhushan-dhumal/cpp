## Vector : 
 ``` c++
 // Create a vector of size n with all values as 10.
 vector<int> vect(n, 10);
```

Sort vector by second coordinate. e.g ``` points = [[10,16],[2,8],[1,6],[7,12]] ```
``` c++
    static int cmp(const vector<int>& v1, const vector<int>& v2)
    {
        return (v1[1] < v2[1]);
    }
    
    sort(points.begin(), points.end(), cmp);
```

while initializing vector size and capacity remains same.

but while inserting/pushing element into vector if capacity is full then it doubles the capacity.

## List

doubly link list 

## Forward List
Singly link list

## Array

static array

## static arry vs dynamic array
array created on stack is called static array.

size of the array should be given at compile time and it is constatnt.

memory allocation and deallocation handled automatically.

e.g. ``` int foo[10];```


array created on heap is called dynamic array.

size of the array can be given on run time hence it can be variable.

you need to make sure memory is free at the end.

e.g. 
``` 
int n = 10;
int* foo = new int[n];
delete[] foo;
```
## Pair
used to store two hetrogenous objects

make_pair() method can be used to create pair object.

## Tuple
used to store hetrogenous objects.

tie() is used to unpack elments from tuple.
ignore keyword can be used in tie for value you do not want to unpack.


## Unordered map:
Initialization
```
        unordered_map<char,int> umap = 
        {
            {'I', 1},
            {'V', 5},
            {'X', 10},
            {'L', 50},
            {'C', 100},
            {'D', 500},
            {'M', 1000}
        };
```

iterating map to get all key or values
below code not tested on ide but used in company code
```
for(auto e : umap)
{
  e.first;
  e.second;

}
```

## Ordered map:
```
 map<int,int> mp;
 
 mp.insert(pari<int,int>(1,6));
 mp.insert(pari<int,int>(2,16));
 mp.insert(pari<int,int>(2,61));
 mp.insert(pari<int,int>(3,28));
 
 map<int,int>::iterator itr;
 for(itr = mp.begin();itr != mp.end();itr++)
 {
   cout<<itr->first<<"\t";
   cout<<itr->second<<endl;
 }
```

to change default sorting way , you can pass greater<int> or less<int> while declaring map
 
 ```
 map<int,int,greater<int>> mp;
 
 ```

Links :
[GFG](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/),
[Initialize unordered map](https://iq.opengenus.org/different-ways-to-initialize-unordered-map-in-cpp/)

## Deque
``` c++
    deque <int> gquiz;
    gquiz.push_back(10);
    gquiz.push_front(20);
    gquiz.push_back(30);
    gquiz.push_front(15);
 ```
[GFG](https://www.geeksforgeeks.org/deque-cpp-stl/)

# lambda expression
``` c++
[]() -> return_type
```
& take all values by reference
 
= take all values by copy

``` c++
#include<funtional>

auto test = [](int x, int y){ return x+y;};
function<int(int,int)> test1 = [](int x, inty){return x-y;};

test(10,20); // 30
test1(20,10); // 10


```
