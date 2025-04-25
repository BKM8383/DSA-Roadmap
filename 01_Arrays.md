### Arrays

- **Declaration:**
    - `int arr[5];` — Declares an array of size 5.
    - `int arr[n];` — Declares an array with size `n`.
    - `int arr[] = {1, 2, 3, 4, 5};` — Initializes an array with specific values.
    - `int arr[5] = {0};` — Initializes all elements to 0.
    - `int arr[5] = {1};` — Initializes the first element to 1 and the rest to 0.
    - `int arr[] = {1, 2, 3, 4, 5};` — Initializes with 5 elements.
    - `int n = sizeof(arr) / sizeof(arr[0]);` — Calculates the number of elements in the array.

---

### Traversal

- **Methods:**
    - `for(int i = 0; i < arr.size(); i++)` — Loop through the array using index.
    - `for(int x : arr)` — Range-based for loop (value).
    - `for(int &x : arr)` — Range-based for loop (reference).
    - `for(auto x : arr)` — Auto keyword to infer type.
    - `for(auto &x : arr)` — Auto with reference.

---

### Array vs Pointers

- **Example:**
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6};  // Array of 6 elements
    int *ptr = arr;  // Pointer pointing to the first element of the array

    // Size of array vs pointer
    cout << sizeof(arr) << " " << sizeof(ptr) << endl;  // sizeof(arr) is the total size of the array, sizeof(ptr) is the size of the pointer itself

    // Accessing elements using array and pointer (both give the same result)
    cout << *(arr + 2) << " " << arr[2] << " " << *(ptr + 2) << " " << ptr[2] << " " << 2[arr] << " " << 2[ptr] << endl;  // Access elements using array and pointer syntax (interchangeable)

    // What you can't do with arr that you can do with ptr
    ptr = ptr + 2;  // You can reassign a pointer to point to any location in memory.
    cout << *ptr << endl;  // After ptr is moved, it points to the third element (value: 3)

    // What you can't do with arr:
    // arr = arr + 2;  // Error: You cannot change the address of the array itself. `arr` is a constant pointer.
    
    return 0;
}
