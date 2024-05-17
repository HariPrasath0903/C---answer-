
### Pointer to an Array

A pointer to an array points to the entire array as a single unit. Here is a detailed example program to illustrate this concept:

```c
#include <stdio.h>

int main() {
    // Declare and initialize an array of 5 integers
    int arr[5] = {1, 2, 3, 4, 5};

    // Declare a pointer to an array of 5 integers
    int (*ptr)[5] = &arr;

    // Access elements of the array using the pointer
    printf("Elements of the array using pointer to an array:\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", (*ptr)[i]);
    }
    printf("\n");

    return 0;
}
```

**Explanation:**
1. `int arr[5] = {1, 2, 3, 4, 5};` declares and initializes an array of 5 integers.
2. `int (*ptr)[5] = &arr;` declares a pointer to an array of 5 integers and initializes it with the address of `arr`.
3. `(*ptr)[i]` is used to access elements of the array through the pointer. Here, `(*ptr)` dereferences the pointer to get the array, and `[i]` accesses the i-th element of that array.

### Array of Pointers

An array of pointers is an array where each element is a pointer to an individual element or another array. Here is a detailed example program to illustrate this concept:

```c
#include <stdio.h>

int main() {
    // Declare and initialize three integer variables
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
1. `int a = 10, b = 20, c = 30;` declares and initializes three integer variables.
2. `int *ptrArr[3];` declares an array of 3 pointers to integers.
3. `ptrArr[0] = &a;`, `ptrArr[1] = &b;`, and `ptrArr[2] = &c;` initialize each element of the array of pointers with the address of the respective integer variable.
4. `*ptrArr[i]` is used to access the value pointed to by each pointer in the array. Here, `ptrArr[i]` gets the i-th pointer, and `*` dereferences it to get the value it points to.

### Summary

- **Pointer to an Array**: A single pointer that points to the entire array. Access elements using `(*ptr)[i]`.
- **Array of Pointers**: An array where each element is a pointer to a different variable or array. Access elements using `*ptrArr[i]`.
