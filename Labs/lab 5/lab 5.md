1. Enter the number of elements and array elements. To find the arithmetic mean of the largest and smallest element in the sequence.

```c
#include <stdio.h>

int largestAndSmallest(int arr[],int size){
	int largestNum = arr[0];
	int smallestNum = arr[0];
	for(int i= 0;i < size;i++){
		if (arr[i] > largestNum){
			largestNum = arr[i];
		}else if (arr[i] < smallestNum){
			smallestNum = arr[i];
		}
	}

	printf("largest num is %d, smallest num is %d",largestNum,smallestNum);
	return largestNum, smallestNum;

}

int main() {
	int size;
	scanf("%d",&size);

	int arr[size];

	for (int i = 0; i < size; ++i)
	{
		scanf("%d",&arr[i]);
	}

	largestAndSmallest(arr,size);
}
```

---

2. Enter the number of elements and array elements. To find which elements of the array are divisible by the number of its digits. 
	Example:
		• 210 is divisible by 3 (number of digits in 210)
		• 2140 is divisible by 4 (number of digits in 2140)
```c
#include <stdio.h>

int countDigits(int num) {
	int count;
	while (num != 0){
		num /= 10;
		count ++;
	}
	return count;
}

int main() {
    int size;

    //broj na elementi
    printf("Enter the number of elements: ");
    scanf("%d", &size);

    //vnesi sekoj elemnt na arr
    int arr[size];
    printf("Enter the array elements:\n");
    for (int i = 0; i < size; i++) {
        scanf("%d", &arr[i]);
    }

    for(int i =0; i < size; i++){
        int numDigits = countDigits(arr[i]);
        if (arr[i] % numDigits == 0) {
            printf("%d is divisible by %d\n", arr[i], numDigits);
        }
    }

    return 0;
}
```


---

3. Enter the number of elements and array elements. Print elements greater than half the maximum element and elements greater than half the minimum element.
	74568
	Max = 8 max/2 = 4       output: 7, 5, 6, 8
	Min = 4 min/2 = 2         output: 7, 4, 5, 6, 8


```c
#include <stdio.h>

int findMax(int arr[], int size) {
    int maxNum = arr[0];
    for (int i = 1; i < size; i++) {
        if (arr[i] > maxNum) {
            maxNum = arr[i];
        }
    }
    return maxNum;
}

int findMin(int arr[], int size) {
    int minNum = arr[0];
    for (int i = 1; i < size; i++) {
        if (arr[i] < minNum) {
            minNum = arr[i];
        }
    }
    return minNum;
}

int main() {
    int size;
    scanf("%d", &size);

    int arr[size];

    for (int i = 0; i < size; ++i) {
        scanf("%d", &arr[i]);
    }

    int largestNum = findMax(arr, size);
    int smallestNum = findMin(arr, size);

    printf("Max = %d, max/2 = %d   ", largestNum, largestNum / 2);
    

    printf("Output: ");
    for (int i = 0; i < size; ++i) {
        if (arr[i] > largestNum / 2) {
            printf("%d ", arr[i]);
        }
    }
printf("\nMin = %d, min/2 = %d   ", smallestNum, smallestNum / 2);
    printf("Output: ");
    for (int i = 0; i < size; ++i) {
        if (arr[i] > smallestNum / 2) {
            printf("%d ", arr[i]);
        }
    }

    return 0;
}
```

---

4. Read an array of n numbers, for each number print the sum of the digits in odd positions. The least significant digit is in position 1.
	Example:
	 2345 – the sum is 5+3 = 8
	1020 – the sum is 0+0 = 0
```c
#include <stdio.h>

int sumOfDigitsAtOddPositions(int num) {
    int sum = 0;
    int position = 1; // Start from the least significant digit (position 1)

    while (num > 0) {
        if (position % 2 != 0) { // Check if the position is odd
            sum += num % 10; // Add the least significant digit to the sum
        }
        num /= 10; // Move to the next digit
        position++; // Move to the next position
    }

    return sum;
}

int main() {
    int n;

    // Input the number of elements
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // Input array elements
    int arr[n];
    printf("Enter the array elements:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Calculate and print the sum of digits at odd positions for each number
    printf("Sum of digits at odd positions:\n");
    for (int i = 0; i < n; i++) {
        int sum = sumOfDigitsAtOddPositions(arr[i]);
        printf("For %d: %d\n", arr[i], sum);
    }

    return 0;
}
```

---
