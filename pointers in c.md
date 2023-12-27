## Intro to pointers
Lets assume that starting address of this memory is 1000 and ending address is 1019. Okay. Now I want to store an integer inside this memory and my assumption is that integer will maximum to maximum take two bytes of memory. That is, it will take two blocks of memory. 

![](https://github.com/TomasDu/C-programing/blob/main/pointers%20in%20c-20231227154832916.webp)

For storing an integer, I'm taking one variable `i` which is of integer type. Therefore it is capable of storing an integer and I'm assuming that it will take these two blocks.

![](https://github.com/TomasDu/C-programing/blob/main/pointers%20in%20c-20231227155334539.webp)
---
Pointer is a variable which is capable of storing the initial address of the object which it wants to point to. In this example, I'm assuming that I have a pointer which will point to this particular object `i`. And for this purpose, it will simply point to the base address or the initial address of this object which is 1002.

Pointing to means it will simply store the base address or the initial address of the object. In this case it is variable `i`. Now, let me give you the definition of a pointer. Pointer is a special variable that is capable of storing some address. In our example, it is storing the base address of integer variable `i`.

![](https://github.com/TomasDu/C-programing/blob/main/pointers%20in%20c-20231227155640997.webp)

## syntax

### general syntax for declaring pointer variables:
```c
data_type *pointer_name;
```
- in pointers the data_type is not the same as in a normal int because pointers DON'T HAVE DATA they just point 👉️ 
- data_type in pointers referees to the type the pointer will be pointing at 

example:
```c
int *nekojInt;      //points to int value
char *nekjChar;     //points to chat value
float *nekojFloat;  //points to float value
```

```
BE CAREFULL
if your pointer will be pointing at a int variable type that pointer must have the same data_type

```

---

###  initializing pointers 
- if you declare a pointer a pointer wont do anything on its own it just points 
- you must initialize a pointer before you use it
- one way of doing this is to assign an address of an already existing variable make the pointer point to an address (pointer 👉️ variable address)

```c
int x = 5;    //declaring an variable of type int
int *ptr;     //pinter that will be pointing to an int value
*ptr = &x;    //points to the adress of x
```

![da](https://github.com/TomasDu/C-programing/blob/main/pointers%20in%20c-20231227161942055.webp)

- x has the value 5 and its address is 1000 the pointer is at address 2000 and its value is the value that is stored at the memory location 1000. Simply put the pointer  points to the value of x.

## use cases
For beginners working on simple programs, the use of pointers is not strictly necessary, but it can still be beneficial for learning and understanding certain concepts. Here are a few scenarios where using pointers is common and can provide insight even for beginners:
- pointers are usefully when we want to directly modify a value of some sort . 

1. **Function Parameter Passing:**
	- Using pointers as function parameters allows modifying variables in the calling function.
	- Example: Implementing a function to swap two numbers.

```c
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;
    swap(&x, &y);
    printf("After swapping: x = %d, y = %d\n", x, y);
    return 0;
}

```

---
2. **Array Manipulation:**
	- Pointers can simplify array manipulation and traversal.
	- Example: Reversing an array using pointers.

```c
#include <stdio.h>

void reverseArray(int *arr, int size) {
    int *start = arr;
    int *end = arr + size - 1;

    while (start < end) {
        int temp = *start;
        *start = *end;
        *end = temp;

        start++;
        end--;
    }
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int size = sizeof(arr) / sizeof(arr[0]);

    reverseArray(arr, size);

    printf("Reversed array: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}

```


---

### ADVANCED USE CASCES
1. **Dynamic Memory Allocation:**    
    - Pointers are often used with functions like `malloc`, `calloc`, and `free` to dynamically allocate and deallocate memory.
    - Example: Allocating memory for an array of integers at runtime.
    
2. **Passing Parameters by Reference:**    
    - Pointers allow passing parameters by reference, enabling functions to modify the original values.
    - Example: Implementing a swap function that exchanges the values of two variables.
    
3. **Arrays and Pointers:**    
    - Arrays and pointers are closely related in C, and pointers provide a way to iterate through array elements efficiently.
    - Example: Traversing an array using a pointer instead of array indexing.
    
4. **Strings and Pointers:**    
    - Strings in C are typically represented as arrays of characters, and pointers are often used for string manipulation.
    - Example: Using pointers to concatenate or manipulate strings.
    
5. **Function Pointers:**    
    - Pointers can be used to store addresses of functions, allowing for dynamic function calls.
    - Example: Implementing a callback mechanism where a function pointer is passed as an argument to another function.

6. **Data Structures:**    
    - Pointers are crucial for building complex data structures like linked lists, trees, and graphs.
    - Example: Creating a linked list where each node contains a pointer to the next node.

7. **Dynamic Data Structures:**    
    - Pointers are essential for implementing dynamic data structures like linked lists, where nodes can be dynamically allocated and linked together.
    - Example: Creating a dynamic linked list to store and manage data at runtime.

8. **File Handling:**    
    - Pointers are used in file handling operations for reading and writing data to files.
    - Example: Reading and writing data from/to a file using pointers.

9. **Performance Optimization:**    
    - Pointers can be used to optimize performance by directly manipulating memory locations.
    - Example: Implementing algorithms that require efficient memory access.

10. **Callback Functions:**    
    - Pointers to functions enable the use of callback mechanisms where a function is passed as an argument to another function.
    - Example: Implementing event handlers or sorting algorithms that accept a comparison function.


