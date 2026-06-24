# Day 7 Exercises: Single-Dimensional Arrays

## Instructions for Students

**Goal:** Learn to read, trace, and understand single-dimensional array code.

**How to Work:**
1. Read the code carefully
2. Trace through step-by-step
3. Show your work (write the trace)
4. Predict the output
5. Check your answer (after predicting)

**No shortcuts!**
- No running code before predicting output
- No using AI to check answers
- No guessing - trace step by step
- Show your reasoning in writing

---

---

# Exercise Set 1: Array Declaration & Initialization

## Exercise 7.1.1: Simple Array Declaration

**Code:**
```c
#include <stdio.h>

void main() {
    int numbers[5];
    
    numbers[0] = 10;
    printf("First element: %d\n", numbers[0]);
}
```

**Questions:**
1. What does `int numbers[5]` do? Explain in your own words.
2. What is the value of `numbers[0]` before the assignment?
3. What is printed to the console?
4. Draw a diagram of the array after all assignments.

---

## Exercise 7.1.2: Array with Initialization

**Code:**
```c
#include <stdio.h>

void main() {
    int values[4] = {5, 10, 15, 20};
    
    printf("Index 0: %d\n", values[0]);
    printf("Index 2: %d\n", values[2]);
    printf("Index 3: %d\n", values[3]);
}
```

**Questions:**
1. What values are stored at each index?
2. What does the `= {5, 10, 15, 20}` part do?
3. What is the output of this program?
4. What would happen if you tried to access `values[4]`?

---

## Exercise 7.1.3: Multiple Arrays

**Code:**
```c
#include <stdio.h>

void main() {
    int arr1[3] = {1, 2, 3};
    int arr2[3] = {10, 20, 30};
    
    printf("%d\n", arr1[0]);
    printf("%d\n", arr2[1]);
    printf("%d\n", arr1[2]);
    printf("%d\n", arr2[2]);
}
```

**Questions:**
1. How many arrays are declared? Name them.
2. What is the size of each array?
3. What is the output?
4. Draw a diagram showing both arrays in memory.

---

---

# Exercise Set 2: Array Indexing

## Exercise 7.2.1: Index-Based Access

**Code:**
```c
#include <stdio.h>

void main() {
    int scores[5] = {85, 90, 78, 92, 88};
    
    int first = scores[0];
    int middle = scores[2];
    int last = scores[4];
    
    printf("%d %d %d\n", first, middle, last);
}
```

**Questions:**
1. What are the values of `first`, `middle`, and `last`?
2. What is the output?
3. Why is `scores[4]` the "last" element in a 5-element array?
4. What would be the index of the third element?

---

## Exercise 7.2.2: Index Variable

**Code:**
```c
#include <stdio.h>

void main() {
    int arr[5] = {10, 20, 30, 40, 50};
    
    int index = 2;
    int value = arr[index];
    
    printf("arr[%d] = %d\n", index, value);
    
    index = 4;
    printf("arr[%d] = %d\n", index, arr[index]);
}
```

**Questions:**
1. What is the value of `arr[index]` when `index = 2`?
2. What is printed on the first printf line?
3. After `index = 4`, what is `arr[index]`?
4. What is the complete output?

---

## Exercise 7.2.3: Accessing and Modifying

**Code:**
```c
#include <stdio.h>

void main() {
    int data[3] = {100, 200, 300};
    
    printf("Before: %d\n", data[1]);
    
    data[1] = 250;
    
    printf("After: %d\n", data[1]);
    printf("Others: %d, %d\n", data[0], data[2]);
}
```

**Questions:**
1. What is `data[1]` before modification?
2. What is `data[1]` after the assignment `data[1] = 250`?
3. Did modifying `data[1]` affect the other elements?
4. What is the complete output?

---

---

# Exercise Set 3: Looping Through Arrays

## Exercise 7.3.1: Simple Loop

**Code:**
```c
#include <stdio.h>

void main() {
    int arr[3] = {5, 10, 15};
    
    for(int i = 0; i < 3; i++) {
        printf("%d\n", arr[i]);
    }
}
```

**Questions:**
1. How many times does the loop execute?
2. What is the value of `i` on each iteration?
3. What is `arr[i]` on each iteration?
4. What is the complete output?
5. Why do we use `i < 3` and not `i <= 3`?

---

## Exercise 7.3.2: Loop with Condition

**Code:**
```c
#include <stdio.h>

void main() {
    int nums[5] = {2, 4, 6, 8, 10};
    
    for(int i = 0; i < 5; i++) {
        if(nums[i] > 5) {
            printf("%d is greater than 5\n", nums[i]);
        }
    }
}
```

**Questions:**
1. How many times does the loop run?
2. Which array elements are printed? Why?
3. What is the complete output?
4. What would the output be if the condition was `nums[i] > 6`?

---

## Exercise 7.3.3: Building an Array in Loop

**Code:**
```c
#include <stdio.h>

void main() {
    int result[4];
    
    for(int i = 0; i < 4; i++) {
        result[i] = i * 10;
        printf("result[%d] = %d\n", i, result[i]);
    }
}
```

**Questions:**
1. What formula is used to calculate each value? (`result[i] = ?`)
2. What values are stored in `result` after the loop?
3. What is the complete output?
4. Draw a diagram of the `result` array after the loop completes.

---

---

# Exercise Set 4: Array Manipulation

## Exercise 7.4.1: Modifying Elements

**Code:**
```c
#include <stdio.h>

void main() {
    int values[3] = {1, 2, 3};
    
    values[0] = values[0] * 10;
    values[1] = values[1] + 5;
    values[2] = values[0] + values[1];
    
    printf("%d %d %d\n", values[0], values[1], values[2]);
}
```

**Questions:**
1. What is `values[0]` after `values[0] = values[0] * 10`?
2. What is `values[1]` after `values[1] = values[1] + 5`?
3. What is `values[2]` after `values[2] = values[0] + values[1]`?
4. What is the complete output?
5. Does the order of operations matter here?

---

## Exercise 7.4.2: Shifting Values

**Code:**
```c
#include <stdio.h>

void main() {
    int arr[4] = {1, 2, 3, 4};
    
    for(int i = 0; i < 4; i++) {
        arr[i] = arr[i] + 100;
    }
    
    for(int i = 0; i < 4; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}
```

**Questions:**
1. What does the first loop do to each element?
2. What values are in the array after the first loop?
3. What does the second loop do?
4. What is the output?

---

## Exercise 7.4.3: Conditional Modification

**Code:**
```c
#include <stdio.h>

void main() {
    int nums[4] = {10, 5, 15, 8};
    
    for(int i = 0; i < 4; i++) {
        if(nums[i] < 10) {
            nums[i] = 0;
        }
    }
    
    for(int i = 0; i < 4; i++) {
        printf("%d ", nums[i]);
    }
    printf("\n");
}
```

**Questions:**
1. Which elements are less than 10?
2. Which elements will be changed to 0?
3. What is the final state of the array?
4. What is the output?

---

---

# Exercise Set 5: Searching & Analysis

## Exercise 7.5.1: Finding an Element

**Code:**
```c
#include <stdio.h>

void main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int target = 30;
    
    for(int i = 0; i < 5; i++) {
        if(arr[i] == target) {
            printf("Found %d at index %d\n", target, i);
        }
    }
}
```

**Questions:**
1. What is the `target` value?
2. Which element matches the target?
3. At what index is the target found?
4. What is the output?
5. What would happen if you searched for 25?

---

## Exercise 7.5.2: Sum and Average

**Code:**
```c
#include <stdio.h>

void main() {
    int values[4] = {10, 20, 30, 40};
    int sum = 0;
    
    for(int i = 0; i < 4; i++) {
        sum = sum + values[i];
    }
    
    int average = sum / 4;
    
    printf("Sum: %d\n", sum);
    printf("Average: %d\n", average);
}
```

**Questions:**
1. What is the initial value of `sum`?
2. What is the value of `sum` after each iteration of the loop?
3. What is the final value of `sum`?
4. What is the `average`?
5. What is the output?

---

## Exercise 7.5.3: Finding Min and Max

**Code:**
```c
#include <stdio.h>

void main() {
    int data[5] = {15, 8, 23, 5, 19};
    int min = data[0];
    int max = data[0];
    
    for(int i = 1; i < 5; i++) {
        if(data[i] < min) {
            min = data[i];
        }
        if(data[i] > max) {
            max = data[i];
        }
    }
    
    printf("Min: %d\n", min);
    printf("Max: %d\n", max);
}
```

**Questions:**
1. Why does the loop start at `i = 1` instead of `i = 0`?
2. What are the initial values of `min` and `max`?
3. On each iteration, which values satisfy `data[i] < min`? Which satisfy `data[i] > max`?
4. What is the final value of `min`?
5. What is the final value of `max`?
6. What is the output?

---

---

## Challenge Problems (Optional)

### Challenge 7.1: Reverse Array
```c
int arr[5] = {1, 2, 3, 4, 5};
// Without creating a new array, swap elements so arr becomes {5, 4, 3, 2, 1}
// Hint: Use a temporary variable for swapping
```

### Challenge 7.2: Count Occurrences
```c
int nums[7] = {1, 2, 2, 3, 2, 4, 5};
// Count how many times the value 2 appears
```

### Challenge 7.3: Check Sorted
```c
int values[5] = {10, 20, 30, 40, 50};
// Check if array is sorted in ascending order
```

---

## Answer Format Reminder

For each exercise, always show:
1. **Your Trace:** Step-by-step execution
2. **Variable Table:** State of variables at each step
3. **Expected Output:** What prints to console
4. **Reasoning:** Why you think this is correct

**Example Format:**
```
Exercise 7.1.1:

Step 1: Declare int numbers[5]
  → Creates array with 5 slots, all uninitialized

Step 2: numbers[0] = 10
  → numbers[0] is now 10

Step 3: printf("First element: %d\n", numbers[0])
  → Prints: "First element: 10"

Output:
First element: 10
```

Good luck! 🚀
