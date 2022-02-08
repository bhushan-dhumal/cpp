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
