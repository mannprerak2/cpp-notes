# cpp-notes
Some Quick Code notes for cpp (will work for c++ 11 and beyond)

## TABLE OF CONTENTS
1. [Useful Imports](#useful-imports)
2. [Iterating](#iterating)
3. [STL containers](#containers)
    1. [Vector](#vector)
    2. [set, multiset](#set)
    3. [map, multimap](#map)
    4. [unordered_set, unordered_map](#unordered)
### <a name="useful-imports"/>
### Useful Imports 
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
### <a name="iterating"/>
### iterating (general) 
```cpp
// here 'ds' can be any container - array, vector, set, map, etc...
for(auto c: ds){ // ds can even be array here
  cout << c;
}

//simple iteration
for(auto it=ds.begin();it!=ds.end();it++)
    cout << *it;
//reverse iteration
for(auto it=ds.rbegin();it!=ds.rend();it++)
    cout << *it
```
### <a name="containers"/>
## CONTAINERS 
### <a name="vector"/>
### vector 
```cpp
vector<int> a(10); // 10 elements with garbage value
vector<int> a(10,2); // 10 elements each with value 2
vector<int> a = {1,2,3,4};

a.push_back(1);
a.pop_back(); // void 
a.front();
a.back();
a.size(); //unsigned int
a.empty();
a.clear(); //remove everything

a.insert(a.begin()+3,5); //insert before 3rd position
a.erase(a.begin()+2); // remove at 2nd index ( 3rd element )
a.erase(a.begin(),a.begin()+2); // remove all, from param1 to param2(exclusive)

```
### <a name="set"/>
### set and multiset
```cpp
set<int, greater<int> > set; // elements sorted in descending order
set<int> set = {10,20,30,40,50}; // will be sorted in ascending order by default

set.size(); //unsigned
set.empty();
set.clear();
set.count(); //either 0 or 1
// O(logn) operations below -

set.insert(3);
set.find(20);	// returns iterator to element, or set.end() if not found
set.lower_bound(30);  // return iterator to element <= 30
set.upper_bound(30): // returns iterator to element > 30

// multiset operations ( multsets are sets whcih can hold duplicates too
set.count(10); // get count of number of 10's 
auto mypair = set.equal_range(10); //mypair has start and end iterator for key 10
```
### <a name="map"/>
### map and multimap
```cpp
map<int, int, greater<int> > map; //sorted in descending order of key
map<int, int> map;

map.size(); //unsigned
map.empty();
map.clear();
map.count(10); //either 0 or 1
// O(logn) operations below -

map.insert(make_pair(10,10));
map[20] = 20; //another way to insert
map.find(20); // returns iterator to element, or map.end() if not found
map.lower_bound(30);  // return iterator to element <= 30
map.upper_bound(30); // returns iterator to element > 30

// multimap operations ( multmaps are maps whcih can hold duplicates too
map.count(10); // get count of number of 10's
auto mypair = map.equal_range(10); //mypair has start and end iterator for key 10
```
### <a name="unordered"/>
### unordered_set and unordered_map
```cpp
unordered_set<int> set;
unordered_map<int,int> map;
// you can iterate both in O(n) but order is not guaranteed

//common operations
unordered.size(); //unisigned
unordered.clear();
unordered.erase(key); // removes key if found
unordered.find(key); // returns iterator to element, or unordered.end() if not found

//insertion
set.insert(key);

map.insert(make_pair(key,val));
map[key] = val;
```
