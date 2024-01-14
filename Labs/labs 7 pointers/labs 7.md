1. Write a C function that accepts an array of numbers as input parameters and the number of elements in the array. The function will remove all negative elements from the array. Use the function to remove elements. Do not use an extra array. Changes are made in the same array. Use pointers. Create a main() function.
```c
#include <stdio.h>

void removeNegatives(int arr[], int *size) {
    int newSize = 0;

    for (int i = 0; i < *size; i++) {
        if (arr[i] >= 0) {
            arr[newSize] = arr[i];
            newSize++;
        }
    }

    *size = newSize; 

}

int main() {
    int size;

    printf("Enter the number of elements: ");
    scanf("%d", &size);

    int arr[size];
    printf("Enter the array elements:\n");
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    removeNegatives(arr, &size);

    //print new arr
    printf("Array after removing negative elements:\n");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

---


