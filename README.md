# cpp-notes
Some Quick Code notes for cpp (will work for c++ 11 and beyond)

## TABLE OF CONTENTS
1. [Useful Imports](#useful-imports)
2. [Iterating](#iterating)
3. [STL containers](#containers)
    1. [vector and deque](#vector)
    2. [set, multiset](#set)
    3. [map, multimap](#map)
    4. [unordered_set, unordered_map](#unordered)
    5. [priority_queue](#priority_queue)
    6. [stack and queue](#stackqueue)
    7. [list](#list)
4. [Important STL algo's](#stl-algos)
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
### Iterating 
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
    
//moving iterator
advance(it,3); //move iterator forward by 3, useful function in list traversal

//get iterator
auto it = prev(ds.end(),3); //3rd from end
auto it = next(ds.begin(),2); //2nd from begin
```
### <a name="containers"/>
## CONTAINERS 
### <a name="vector"/>
### vector and deque
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

//deque operations (all those in vector plus these) 
deque<int> d;
d.push_front(10);
d.pop_front();
// deqeue is double ended queue, faster insert and delete than vector
// but contingous memory is not guaranteed.so traversal is slightly slower
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
### <a name="priority_queue"/>
### priority_queue
```cpp
priority_queue<int> a; //max heap
priority_queue<int, vector<int>, greater<int> > q; // min heap, vector/deque can be used
q.push(1);
q.top(); // max or min depending on constructor
q.pop();

q.size(); //unsigned

while(!q.empty())
{
    cout << q.top() << " ";
    q.pop();
}
```
### <a name="stackqueue"/>
### stack and queue
```cpp
stack<int> s; // 2nd argument in <> can be vector, dequeue, list
s.push(10);
s.top();
s.pop();
s.size();
s.empty();

queue<int,list<int> > d; // default is deque for 2nd param
q.push(10);
q.front(); // instead of top
q.back(); //last insertion
q.pop(); //deletes front
```
### <a name="list"/>
### list
```cpp
list<int> l = {1, 2, 3, 4, 5, 6};
l.push_back(7);
l.push_front(0);
l.front();
l.back();
l.pop_back();
l.pop_front();
l.size();
l.empty();
l.clear();

auto it = l.begin();
it++;
l.insert(it, 10); //insert 10 at iterator position
l.insert(it, 10, 5); //insert 5, 10 times at iterator position
l.remove(10); //remove by key
l.erase(it); //remove by iterator position
l.erase(it_start,it_end); //erase inclusinve start till exclusive end

//algorithms
l.reverse();
l.sort(greater<int>()); // default is ascending, u can use custom comparator function as well
l.unique();

list<int> new_l = {1, 2, 3, 4, 5, 6};

l.splice(l.begin(), new_l, new_it1, new_it2); transfer from new_l to l
l.merge(new_l); // both list must be ordered(ascending), input list will by cleared
```
### <a name="stl-algos"/>
### Important STL Algorithms
```cpp
vector<int> v = {1, 2, 3, 4, 5, 6, 7, 8, 9};

//simple  useful algo's
random_shuffle(v.begin(), v.end()); // can also provide a random number generator
sort(v.begin(), v.end()); //uses quicksort internally

// sorting with lambda comparator (works in c++11 and beyond)
sort(v.begin(),v.end(),[](int a, int b){
    	return a>b; // sorts in reverse
});
bool b = binary_search(v.begin(), v.end(), 6);
reverse(v.begin(), v.end()); // iterator must be bidirectional (wont work for forward_list)
auto it_max = max_element(v.begin(),v.end());
auto it_min = min_element(v.begin(),v.end());

auto it_lower = lower_bound(v.begin(),v.end(),3); // first element <=3
auto it_upper= upper_bound(v.begin(),v.end(),3); //first element >3 

int count_occ = count(v.begin(),v.end(),4);
auto found = find(v.begin(),v.end(),8);

//advance
v.erase(unique(v.begin(),v.end()),v.end()); // remove adjacent duplicates only (only works for sorted array)

//permutations
next_permutation(v.begin(), v.end()); // goes to next perm for sorted 

prev_permutation(v.begin(),v.end()); //goes to previous perm for sorted vector

int a = distance(v.begin(),v.end()); // get distance between iterators
```

