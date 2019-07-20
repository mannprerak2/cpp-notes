# cpp-notes
Some Quick Code notes for cpp (will work for c++ 11 and beyond)

## TABLE OF CONTENTS
1. [Useful Imports](#useful-imports)
2. [Iterating](#iterating)
3. [STL containers](#containers)
  1.[Vector](#vector)
### Useful Imports <a name="useful-imports"/>
```cpp
//basic
#include <iostream> // for cin, cout

// import everything
#include <bits/stdc++.h>

// STL DS
#include <vector>
#include <stack>
#include <queue>   // also has priority_queue
#include <deque>
#include <list>    //doubly ll
#include <forward_list>    //singly ll
#include <set>   //also has multiset
#include <map>   //also has multimap
#include <unordered_map>
#include <unordered_set>

using namespace std; // helpful 
```

### iterating (general) <a name="iterating"/>
```
// here 'ds' can be any container - array, vector, set, map, etc...
for(auto c: ds){ // ds can even be array here
  cout << c;
}

//simple iteration
for(auto it=ds.begin();it!=ds.end();it++)

//reverse iteration
for(auto it=ds.rbegin();it!=ds.rend();it++)
```

## CONTAINERS <a name="containers"/>
### vector <a name="vector"/>
```
vector<int> a;
a.push_back(1);
a.push_front(2);
a.front();
a.back();
a.size(); //unsigned int
a.empty();

```
