

### 1. What is an Array?
An array is a collection of elements, all of the same type, stored in contiguous memory locations. Each element in the array is identified by its index or subscript, which starts from zero.
- Imagine you have a row of boxes. Each box can hold a number or a piece of information.
- An array in programming is like that row of boxes. It's a way to store multiple pieces of information (like numbers) in one place.

### 2. How to Create an Array?

#### Deklaracija na niza od celosni broevi so golemina 5
```c
int numbers[5];  // Declaration of an integer array with size 5
```



- When you create an array, you're essentially saying, "I want a row of boxes, and each box will hold a number."
- and each box has a id number label on it starting from 0,1,2...   
- In C, you might say: `int numbers[5];`
    - This means you want to create an array called `numbers` that can hold 5 integers (whole numbers).

### 3. Putting Numbers in Boxes (Initializing):

- After creating the array, you can put numbers into each box.
- Example: `int numbers[5] = {1, 2, 3, 4, 5};`
    - Now, your `numbers` array has five boxes, and each box has a number from 1 to 5.

### 4. Finding Numbers in Boxes (Accessing):

- If you want to know what number is in a specific box, you can ask using the box's number (index).
- In programming, the first box is 0, the second is 1, and so on.
- Example: `int thirdNumber = numbers[2];`
    - This means you're getting the number from the third box (index 2) and putting it in a variable called `thirdNumber`.

### 5. Playing with all the Boxes (Looping):

- Sometimes, you want to do something with all the numbers in the boxes.
- You can use a loop, which is like saying, "Do this for each box in order."

Example:
```c
for (int i = 0; i < 5; i++) {
    printf("%d ", numbers[i]);
}
```

If you iterate over 0, 1, 2, 3, 4, 5, then number[i] corresponds to numbers[0], numbers[1], numbers[2], and so on. In this case, the first five elements of the array 'numbers' would be printed, namely 1, 2, 3, 4, 5.

```
ako 'i' odit 0,1,2,3,4,5 togas number[i] e prvo numbers[0], numbers[1], numbers[2]... Vustvari se pecatet prvite 5 elementi na nizata numbers vo ovoj slucaj 1,2,3,4,5
```
