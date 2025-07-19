
### Min Heap
. 
In C++, the default `priority_queue` is a **max heap**, meaning the top element is the largest. If you're using `priority_queue<vector<int>> pq;`, it will compare vectors using `operator<`, which compares lexicographically — so it becomes a **max heap** of vectors.

You can also convert a max to a min heap by storing the negative values of the data , store 3 as -3 , etc as a work around . 
To convert it into a **min heap**, you need to provide a custom comparator that inverts the comparison.

Here's how you can define a min-heap `priority_queue` of `vector<int>`:

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <functional>

using namespace std;

// Custom comparator for min heap
struct Compare {
    bool operator()(const vector<int>& a, const vector<int>& b) {
        return a > b; // greater-than makes it a min-heap
    }
};

int main() {
    priority_queue<vector<int>, vector<vector<int>>, Compare> pq;

    pq.push({3, 4});
    pq.push({1, 2});
    pq.push({2, 5});

    while (!pq.empty()) {
        vector<int> top = pq.top();
        pq.pop();
        cout << "[" << top[0] << ", " << top[1] << "]\n";
    }

    return 0;
}
```

### Explanation:
- `priority_queue<Type, Container, Comparator>`
- `Compare` uses `operator()>` instead of `<`, effectively making the `priority_queue` a **min heap**.
- For `vector<int>`, this will compare lexicographically.