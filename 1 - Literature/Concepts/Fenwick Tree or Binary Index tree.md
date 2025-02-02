Source : https://youtu.be/CWDQJGaN1gY?si=wW_wOIyhwnbckZMX
### Intro 

Fenwick tree is a data structure that is used to get prefix sums but also have  the updates happen faster than `O(n)` . Prefix array take `O(n)` to build `O(n)` update and `O(1)` to return the prefix sums . The problem here is obvious , we want to update the prefix sum at a much faster pace than `O(n)` and the Fenwick tree offers a solution. Fenwick tree take `O(nLogn)` to build and `O(Log n )` to return the prefix sum and `O(log n)` to update the prefix array .


### Structure 
![[Pasted image 20250124183405.png]]
- In the above tree is the structure of Fenwick tree .  How do we get the prefix sum from this tree . 
- **How the fuck did this tree even form ??** - The logic behind constructing this tree is the simple part . We just take any number and flip the right most bit and we get the parent . That’s it . ![[Pasted image 20250124222747.png]] 
- Let’s say each node in this tree represents a smaller prefix sum , for instance node 4 having (0,3) , and by correctly traversing these nodes we can have a prefix sum returned to us . 
- **How do we assign which node has which sub-prefixes** - The logic behind this any number can be represented as a sum of powers of two (binary representation) . To put this into perspective . This is how it would look . ![[Pasted image 20250124185712.png]]
- This is how it would work 1 could be represented at the sum of 0 and 2^0 . What this basically means is that we will start with the index of all the right value (which is 0) and we would store the next 2^0 elements  which is one . Therefore the node 1 can store the prefix sum of indexes 0 to 0 (basically one elements ) . Another example would be node 3 , so the sum of all right side of powers of two would give us the indice to start which is 2 and then we would take next 2^0 elements in the sub-prefix sum which is just 1 elements hence (2,2).
- After we populate the whole it for all the indices on the nodes it would look like this .![[Pasted image 20250124190504.png]]
- If you look closely , you will notice that if we traverse up through the node we can achieve a prefix sum .
- In code , the tree is stored as array  where each node is an index to the corresponding index  and then we can traverse this array to get the prefix sum . 


### Searching 

- To search and get a prefix sum let us say that we want prefix sum from the index 8 . 
	- We add 1 to the index and then we get 9 . 
	- We get the 2s complement of the number . 
	- We perform BITWISE AND with the original number . 
	- And then with subtract this from the original number . 
- After performing this we get the parent of the current node . 
- After getting the parent node we add it to the sum and then we perform the above steps again until we arrive at zero . ![[Pasted image 20250124235431.png]]


### Updating 
- Updating nodes happens in a much similar manner to searching except there is one small change .
	- Get 2s complement of the number . 
	- Perform BITWISE AND of the number and the 2s Complement .
	- Add the result of the BITWISE operation to the original number . 
- After getting the next node , we perform this operation repeatedly until we get a number that is more than the size of the Fenwick tree . 
- ![[Pasted image 20250125003524.png]]





### Code 

```
#include <bits/stdc++.h>

using namespace std;

template <class T>
class FenTree {
    // this tree is one based index
    int n;
    vector<T> tree;
public:
    FenTree(int n) {
        tree.assign(n + 1, 0);
        this->n = n;
    }
    void set(int i, T v) {
        while (i <= n) {
            tree[i] += v;
            i += i & -i;
        }
    }
    T get(int i) {
        T sm = 0;
        while (i >= 1) {
            sm += tree[i];
            i -= i & -i;
        }
        return sm;
    }
};

int main() {
    FenTree<int> ft(10);

    ft.set(1, 1);
    ft.set(2, 2);
    ft.set(3, 3);

    cout << ft.get(10) << endl;


    return 0;
}
```