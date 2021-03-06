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
Pointer to vector
```
    vector<int> *v = new vector<int>(10);
    v->at(2); //Retrieve using pointer to member
    v->operator[](2); //Retrieve using pointer to operator member
    v->size(); //Retrieve size
    vector<int> &vr = *v; //Create a reference
    vr[2]; //Normal access through reference
    delete &vr; //Delete the reference. You could do the same with
                //a pointer (but not both!)
```

while initializing vector size and capacity remains same.

but while inserting/pushing element into vector if capacity is full then it doubles the capacity.

### Methods
push_back()

pop_back()

front()

back()

## Stack

### Methods
push()

pop()

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

## Priority Queue
```
// max heap
priority_queue<int> pq;
pq.push(10);
pq.top();
pq.pop();

// min heap
priority_queue<int,vector<int>,greater<int>> minpq;
minpq.push(20);

// priority queue on pair with own comparator(ordered by second element (Min))

typedef pair<int,int> pi;

struct myComp
{
  constexpr bool operator()(pair<int,int> const& a, pair<int,int> const& b) const noexcept
  { 
      return a.second > b.second; // looks like for min , greater should be used and for max less should be used. reversed of what we do to sort vector.
  }
};

priority_queue<pi,vector<pi>,myComp> pq;
// Insertion of the elements
p1.push(make_pair(4, 5));
p1.push(make_pair(5, 4));
p1.push(make_pair(1, 6));
p1.push(make_pair(7, 3));
p1.push(make_pair(9, 4));

/* output
7 3
5 4
9 4
4 5
1 6
*/

```


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
how to pass lambda expression as an argument?
