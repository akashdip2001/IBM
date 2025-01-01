![Screenshot (911)](https://github.com/user-attachments/assets/10b196fd-0cf5-4b5a-ab37-3326b979056f)

## Sample Test

![Screenshot (910)](https://github.com/user-attachments/assets/472dcc6b-acac-4df4-9d9d-4c5a9b831f2a)

Here’s the implementation of the `fizzBuzz` function in C:

```c
#include <stdio.h>
#include <assert.h>

/*
 * Complete the 'fizzBuzz' function below.
 *
 * The function accepts INTEGER n as parameter.
 */
void fizzBuzz(int n) {
    for (int i = 1; i <= n; i++) {
        if (i % 3 == 0 && i % 5 == 0) {
            printf("FizzBuzz\n");
        } else if (i % 3 == 0) {
            printf("Fizz\n");
        } else if (i % 5 == 0) {
            printf("Buzz\n");
        } else {
            printf("%d\n", i);
        }
    }
}

int main() {
    int n;
    scanf("%d", &n); // Take input for the value of n
    fizzBuzz(n);     // Call the fizzBuzz function
    return 0;
}
```

### Explanation:
1. **Function Definition**:
   - The `fizzBuzz` function accepts an integer `n` as input.
   - A `for` loop iterates from `1` to `n`.
   - The conditions check divisibility:
     - If divisible by both `3` and `5`, print "FizzBuzz".
     - If divisible only by `3`, print "Fizz".
     - If divisible only by `5`, print "Buzz".
     - Otherwise, print the current number.

2. **Main Function**:
   - Reads the input value `n` using `scanf`.
   - Calls the `fizzBuzz` function with the input value.

3. **Output**:
   - The program outputs the required "FizzBuzz" values for all integers from 1 to `n`.

---

## Question 1

![Screenshot (912)](https://github.com/user-attachments/assets/72c99220-6eb7-4e2f-a7ed-1d4f7707ce1f)

implementation of the `minStart` function in C:

```c
#include <stdio.h>
#include <assert.h>
#include <limits.h>

/*
 * Complete the 'minStart' function below.
 *
 * The function is expected to return a LONG INTEGER.
 * The function accepts INTEGER ARRAY arr as parameter.
 */
long minStart(int arr_count, int arr[]) {
    long running_sum = 0;
    long min_running_sum = 0;

    for (int i = 0; i < arr_count; i++) {
        running_sum += arr[i];
        if (running_sum < min_running_sum) {
            min_running_sum = running_sum;
        }
    }

    // The minimum starting value x such that running sum is always at least 1
    return 1 - min_running_sum;
}

int main() {
    int arr[] = {-4, 3, 2, 1};
    int arr_count = sizeof(arr) / sizeof(arr[0]);
    
    long result = minStart(arr_count, arr);
    printf("Minimum starting value: %ld\n", result);

    return 0;
}
```

### Explanation:
1. **Variables**:
   - `running_sum`: Tracks the cumulative sum as elements are added.
   - `min_running_sum`: Tracks the smallest value of the running sum.

2. **Logic**:
   - Iterate through the array, updating `running_sum` after adding each element.
   - Update `min_running_sum` if the current `running_sum` is smaller than `min_running_sum`.
   - After the loop, the minimum starting value `x` is calculated as `1 - min_running_sum`.

3. **Output**:
   - The program prints the minimum starting value `x` such that the running sum is at least 1 after every iteration.

4. **Constraints**:
   - Handles up to `10^5` elements efficiently.

---

## Question 2

![Screenshot (913)](https://github.com/user-attachments/assets/b1afca1d-4a10-4f74-8c95-c3aecbffb1bd)

implementation of the `maxDifference` function in C:

```c
#include <stdio.h>
#include <limits.h>

/*
 * Complete the 'maxDifference' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts INTEGER_ARRAY px as parameter.
 */
int maxDifference(int px_count, int px[]) {
    int min_price = INT_MAX; // Minimum price seen so far
    int max_diff = -1;       // Maximum positive difference

    for (int i = 0; i < px_count; i++) {
        if (px[i] < min_price) {
            min_price = px[i]; // Update the minimum price
        } else {
            int diff = px[i] - min_price; // Calculate the difference
            if (diff > max_diff) {
                max_diff = diff; // Update the maximum difference
            }
        }
    }

    return max_diff;
}

int main() {
    int px[] = {7, 1, 2, 5};
    int px_count = sizeof(px) / sizeof(px[0]);

    int result = maxDifference(px_count, px);
    printf("Maximum Difference: %d\n", result);

    return 0;
}
```

### Explanation:
1. **Variables**:
   - `min_price`: Tracks the smallest price encountered so far.
   - `max_diff`: Tracks the maximum positive spread.

2. **Logic**:
   - Traverse the array `px`.
   - If the current price is smaller than `min_price`, update `min_price`.
   - Otherwise, calculate the difference between the current price and `min_price`.
   - If the difference is greater than `max_diff`, update `max_diff`.

3. **Output**:
   - The function returns the maximum positive spread.
   - If no positive difference exists, `max_diff` remains `-1`.

4. **Constraints**:
   - Efficiently handles up to `10^5` elements using `O(n)` time complexity.


![Screenshot 2025-01-02 022543](https://github.com/user-attachments/assets/f98e7cc1-ffb3-4d01-8996-46fe919a8efe)
![Screenshot (914)](https://github.com/user-attachments/assets/cfcc41c0-2fe7-4a94-842f-a489f52a68b7)
