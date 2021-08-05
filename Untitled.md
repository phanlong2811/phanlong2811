#### 1. Applicability of Different Data Structures 
- Average-case complexity

| Data Structures | Insert | Find Max | Find Min | Delete  | Search  |  Space  |
| --- | --- | --- | --- |--- |--- |--- |
| Binary Search Tree (BST) | $$O(\log{n})$$ | $$O(\log{n})$$ | $$O(\log{n})$$ | $$O(\log{n})$$ | $O(\log{n})$ | $$O(n)$$ |
| Red Black Tree (RBT) | $$O(\log{n})$$ | $$O(\log{n})$$ | $$O(\log{n})$$ | $$O(\log{n})$$ | $$O(\log{n})$$ | $$O(n)$$ |
| Linked List | $$O(1)$$ | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ |
| Queue | $$O(1)$$ | $$O(n)$$ | $$O(n)$$ | $$O(\log{n})$$ | $$O(n)$$ | $$O(n)$$ |
| Heap | $$O(\log{n})$$ | $$O(1)$$ | $$O(1)$$ | $$O(\log{n})$$ | $$O(n)$$ | $$O(n)$$ |
| Unsorted Array | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ | $$O(n)$$ |
- Almost every space of data structures has a complexity of O(n). so we will not compare the storage space but only care about the complexity of the operations.
- i. I will select BST, RBT, Heap to perform Insert, Find Max operations for the reasons :  
    - each operation ( including insert or find max) will need average at most $O(\log{n})$ per query
    - the others, one of them or both, will lose $O(n)$.
- ii. Similarly, when you have more operations, you need to consider the running time complexity and space requirements. When I need perform : Insert, Find Max, Find Min, Delete, Search, Space, I will select BST, RBT because :
    - each operation will need at most $O(\log{n})$ per query.
    - the others, one of them, will lose $O(n)$.

#### 2. Applicability of Different Data Structures 
- a. I will choose Red Black Tree (RBT) because:
    -  Inserts, deletes and searches can be easily performed with an average complexity of  $O(\log{n})$ for each operation
    -  This complexity is good enough for 10000 customers when combined with hash table

- b. We have :
    $$\begin{aligned}
    f = n / k
    \end{aligned}
    $$ 
    - In there :
        - $f$ is load factor
        - $n$ is size of hashmap
        - $k$ is number of buckets
    - According to the problem we have : $f = 50$, $\max{k} =$ number of customers $= 10000$, so I will choose $n = f * \max{k} = 500000$

- c. 
```cpp=
#include "bits/stdc++.h"

class Customer {
    int customerID;
    std::string name, accountNumber;
    double accountBalance;
};

class Hash {
    int BUCKET;
    std::list<int> *table;
public:
    Hash(int sizeBucket);  // Constructor

    // inserts a key into hash table
    void insertItem(int key) {};

    // deletes a key from hash table
    void deleteItem(int key);

    // hash function to map name to key
    int hashFunction(std::string name) {
        // do something
    }
};

Hash::Hash(int val) {
    // Constructor number of bucket
}

void Hash::insertItem(int key) {
    // inserts a key into hash table
}

void Hash::deleteItem(int key) {
    // deletes a key from hash table
}

int main() {
    // implement your code
    return 0;
}
```