

### Pointer to an Array

A pointer to an array points to the entire array, allowing access to its elements. This is useful when you want to pass an entire array to a function without decaying it to a pointer to its first element.

Here's a detailed example:

```c
#include <stdio.h>

// Function that takes a pointer to an array of 5 integers
void printArray(int (*ptr)[5]) {
    printf("Elements of the array using pointer to an array:\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", (*ptr)[i]);
    }
    printf("\n");
}

int main() {
    // Declare and initialize an array of 5 integers
    int arr[5] = {1, 2, 3, 4, 5};

    // Declare a pointer to an array of 5 integers
    int (*ptr)[5] = &arr;

    // Pass the pointer to the array to a function
    printArray(ptr);

    return 0;
}
```

**Explanation:**
- `int arr[5]` declares and initializes an array of 5 integers.
- `int (*ptr)[5]` declares a pointer to an array of 5 integers and initializes it to the address of `arr`.
- `printArray` function takes a pointer to an array of 5 integers as a parameter.
- Inside `printArray`, we access elements of the array using `(*ptr)[i]`.

### Array of Pointers

An array of pointers is an array where each element is a pointer. This is useful when you want to manage a collection of pointers, each pointing to different variables or arrays.

Here's a detailed example:

```c
#include <stdio.h>

int main() {
    // Declare three integer variables
    int a = 10, b = 20, c = 30;

    // Declare an array of 3 pointers to integers
    int *ptrArr[3];

    // Initialize the array of pointers
    ptrArr[0] = &a;
    ptrArr[1] = &b;
    ptrArr[2] = &c;

    // Access values using the array of pointers
    printf("Values accessed using array of pointers:\n");
    for (int i = 0; i < 3; i++) {
        printf("%d ", *ptrArr[i]);
    }
    printf("\n");

    return 0;
}
```

**Explanation:**
- `int a = 10, b = 20, c = 30` declares three integer variables.
- `int *ptrArr[3]` declares an array of 3 pointers to integers.
- Each element of `ptrArr` is assigned the address of an integer variable (`a`, `b`, and `c`).
- We access the values pointed to by the pointers using `*ptrArr[i]`.

### Summary

- **Pointer to an Array**: 
  - Definition: Points to the entire array.
  - Syntax: `int (*ptr)[size] = &array;`
  - Example usage: Useful for passing arrays to functions.
  - Access: `(*ptr)[index]`
- **Array of Pointers**:
  - Definition: An array where each element is a pointer.
  - Syntax: `int *ptrArr[size];`
  - Example usage: Useful for managing multiple pointers, such as to multiple variables or dynamically allocated arrays.
  - Access: `*ptrArr[index]`
