# Day 7 Answer Key: Single-Dimensional Arrays

**For Instructor Use Only**

---

# Exercise Set 1: Array Declaration & Initialization

## Answer 7.1.1: Simple Array Declaration

**Code:**
```c
#include <stdio.h>

void main() {
    int numbers[5];
    
    numbers[0] = 10;
    printf("First element: %d\n", numbers[0]);
}
```

**Answers:**

1. **What does `int numbers[5]` do?**
   - Declares an array named `numbers` that can hold 5 integer values
   - Creates memory space for 5 integers
   - Indices are 0, 1, 2, 3, 4
   - Initial values are undefined (garbage values)

2. **What is the value of `numbers[0]` before assignment?**
   - Undefined/garbage value (technically uninitialized)
   - Students may write "unknown" or "garbage value"

3. **What is printed?**
   ```
   First element: 10
   ```

4. **Array diagram after assignments:**
   ```
   Index:  0    1    2    3    4
   Value: [10]  [?]  [?]  [?]  [?]    (? = uninitialized)
   ```

**Teaching Notes:**
- Emphasize 0-based indexing
- Note that other elements are uninitialized
- Students often forget array indices start at 0

---

## Answer 7.1.2: Array with Initialization

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

**Answers:**

1. **Values stored at each index:**
   - `values[0]` = 5
   - `values[1]` = 10
   - `values[2]` = 15
   - `values[3]` = 20

2. **What does `= {5, 10, 15, 20}` do?**
   - Initializes each element with the specified values in order
   - This is called "array initialization"
   - Must match the size (4 elements for 4 values)

3. **Output:**
   ```
   Index 0: 5
   Index 2: 15
   Index 3: 20
   ```

4. **What about `values[4]`?**
   - This is out of bounds
   - Would access undefined memory
   - Program may crash or access garbage value
   - This is undefined behavior

**Teaching Notes:**
- Highlight that initialization gives known values
- Explain array bounds checking (or lack thereof in C)
- This is a security and correctness issue

---

## Answer 7.1.3: Multiple Arrays

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

**Answers:**

1. **How many arrays? Names?**
   - 2 arrays: `arr1` and `arr2`

2. **Size of each array?**
   - Both have size 3 (indices 0, 1, 2)

3. **Output:**
   ```
   1
   20
   3
   30
   ```

4. **Memory diagram:**
   ```
   arr1:   Index: 0   1   2
          Value: [1] [2] [3]
   
   arr2:   Index: 0   1   2
          Value: [10] [20] [30]
   ```

**Teaching Notes:**
- Show that arrays are independent
- Multiple arrays can coexist
- Each array maintains its own data

---

---

# Exercise Set 2: Array Indexing

## Answer 7.2.1: Index-Based Access

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

**Answers:**

1. **Values of variables:**
   - `first` = 85 (from `scores[0]`)
   - `middle` = 78 (from `scores[2]`)
   - `last` = 88 (from `scores[4]`)

2. **Output:**
   ```
   85 78 88
   ```

3. **Why is `scores[4]` the "last" element?**
   - Array size is 5
   - Valid indices: 0, 1, 2, 3, 4
   - 4 is the highest valid index
   - In arrays of size N, last index is N-1

4. **Index of third element?**
   - Third element → index 2 (because we count from 0)
   - Index = position - 1

**Teaching Notes:**
- Reinforce 0-based indexing
- Show the pattern: for size N, indices are 0 to N-1
- This is a common source of off-by-one errors

---

## Answer 7.2.2: Index Variable

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

**Answers:**

1. **Value of `arr[index]` when `index = 2`:**
   - `arr[2]` = 30

2. **First printf output:**
   ```
   arr[2] = 30
   ```

3. **After `index = 4`, what is `arr[index]`?**
   - `arr[4]` = 50

4. **Complete output:**
   ```
   arr[2] = 30
   arr[4] = 50
   ```

**Teaching Notes:**
- Show that index is just a variable
- Can use expressions or variables as indices
- `arr[index]` evaluates to `arr[value_of_index]`

---

## Answer 7.2.3: Accessing and Modifying

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

**Answers:**

1. **`data[1]` before modification:**
   - 200

2. **`data[1]` after assignment:**
   - 250

3. **Did modification affect other elements?**
   - No, only `data[1]` changed
   - `data[0]` and `data[2]` remain the same

4. **Complete output:**
   ```
   Before: 200
   After: 250
   Others: 100, 300
   ```

**Teaching Notes:**
- Modifying one element doesn't affect others
- This shows array element independence
- Important for understanding array operations

---

---

# Exercise Set 3: Looping Through Arrays

## Answer 7.3.1: Simple Loop

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

**Answers:**

1. **Number of loop executions:**
   - 3 times (for i = 0, 1, 2)

2. **Value of `i` on each iteration:**
   - Iteration 1: i = 0, then i++
   - Iteration 2: i = 1, then i++
   - Iteration 3: i = 2, then i++
   - After iteration 3: i = 3, condition becomes false

3. **Value of `arr[i]` on each iteration:**
   - i = 0: arr[0] = 5
   - i = 1: arr[1] = 10
   - i = 2: arr[2] = 15

4. **Complete output:**
   ```
   5
   10
   15
   ```

5. **Why `i < 3` and not `i <= 3`?**
   - Array has 3 elements (indices 0, 1, 2)
   - `i < 3` includes 0, 1, 2 (correct)
   - `i <= 3` would include 0, 1, 2, 3 (out of bounds!)
   - Using `i <= 3` would try to access `arr[3]` which doesn't exist

**Teaching Notes:**
- Show the loop iteration table
- Emphasize loop bounds
- This is the foundation for array processing

---

## Answer 7.3.2: Loop with Condition

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

**Answers:**

1. **Number of loop iterations:**
   - 5 times (i = 0, 1, 2, 3, 4)

2. **Which elements are printed?**
   - i = 0: nums[0] = 2, not > 5, not printed
   - i = 1: nums[1] = 4, not > 5, not printed
   - i = 2: nums[2] = 6, yes > 5, **printed**
   - i = 3: nums[3] = 8, yes > 5, **printed**
   - i = 4: nums[4] = 10, yes > 5, **printed**

3. **Complete output:**
   ```
   6 is greater than 5
   8 is greater than 5
   10 is greater than 5
   ```

4. **If condition was `nums[i] > 6`:**
   ```
   8 is greater than 6
   10 is greater than 6
   ```
   (Only 8 and 10 are > 6)

**Teaching Notes:**
- Show how conditionals filter array elements
- This is the foundation for searching
- Many algorithms combine loops and conditions

---

## Answer 7.3.3: Building an Array in Loop

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

**Answers:**

1. **Formula:**
   - `result[i] = i * 10`

2. **Values stored in result after loop:**
   - i = 0: result[0] = 0 * 10 = 0
   - i = 1: result[1] = 1 * 10 = 10
   - i = 2: result[2] = 2 * 10 = 20
   - i = 3: result[3] = 3 * 10 = 30
   
   Array: `{0, 10, 20, 30}`

3. **Complete output:**
   ```
   result[0] = 0
   result[1] = 10
   result[2] = 20
   result[3] = 30
   ```

4. **Memory diagram:**
   ```
   Index:  0    1    2    3
   Value: [0] [10] [20] [30]
   ```

**Teaching Notes:**
- Show how to populate arrays programmatically
- This is more realistic than initialization
- Foundation for input processing

---

---

# Exercise Set 4: Array Manipulation

## Answer 7.4.1: Modifying Elements

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

**Answers:**

1. **`values[0]` after `values[0] = values[0] * 10`:**
   - Started as 1
   - 1 * 10 = 10
   - `values[0]` = 10

2. **`values[1]` after `values[1] = values[1] + 5`:**
   - Started as 2
   - 2 + 5 = 7
   - `values[1]` = 7

3. **`values[2]` after `values[2] = values[0] + values[1]`:**
   - Uses updated values: values[0] = 10, values[1] = 7
   - 10 + 7 = 17
   - `values[2]` = 17

4. **Complete output:**
   ```
   10 7 17
   ```

5. **Does order matter?**
   - YES! Critical!
   - If we changed values[0] last, the answer would be different
   - Show what would happen if we did them in different order:
     ```
     If values[2] was first:
     values[2] = 1 + 2 = 3 (before modifications)
     Then values[0] = 10, values[1] = 7
     Output: 10 7 3 (different!)
     ```

**Teaching Notes:**
- Show the trace table step by step
- Emphasize that order of operations matters
- This is a common source of confusion

---

## Answer 7.4.2: Shifting Values

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

**Answers:**

1. **What does the first loop do?**
   - Adds 100 to each element

2. **Values after first loop:**
   - arr[0] = 1 + 100 = 101
   - arr[1] = 2 + 100 = 102
   - arr[2] = 3 + 100 = 103
   - arr[3] = 4 + 100 = 104
   - Array: `{101, 102, 103, 104}`

3. **What does the second loop do?**
   - Prints each element (with space after)

4. **Output:**
   ```
   101 102 103 104 
   ```
   (Note: space after 104, then newline)

**Teaching Notes:**
- Show how to transform all elements
- Useful for normalization, scaling, etc.
- Second loop is just printing

---

## Answer 7.4.3: Conditional Modification

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

**Answers:**

1. **Which elements are less than 10?**
   - nums[1] = 5 (yes, < 10)
   - nums[3] = 8 (yes, < 10)

2. **Which will be changed to 0?**
   - nums[1] and nums[3]

3. **Final state of array:**
   - nums[0] = 10 (unchanged, not < 10)
   - nums[1] = 0 (changed from 5)
   - nums[2] = 15 (unchanged, not < 10)
   - nums[3] = 0 (changed from 8)
   - Array: `{10, 0, 15, 0}`

4. **Output:**
   ```
   10 0 15 0 
   ```

**Teaching Notes:**
- Conditional modification is powerful
- Real-world example: data cleaning/filtering
- Shows selective transformation

---

---

# Exercise Set 5: Searching & Analysis

## Answer 7.5.1: Finding an Element

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

**Answers:**

1. **Target value:**
   - 30

2. **Which element matches target?**
   - arr[2] = 30

3. **Index where target is found:**
   - Index 2

4. **Output:**
   ```
   Found 30 at index 2
   ```

5. **If searching for 25:**
   - 25 is not in the array
   - Loop runs but condition is never true
   - **No output** (nothing is printed)

**Teaching Notes:**
- Basic linear search
- Emphasis on the index where found
- What happens if not found?

---

## Answer 7.5.2: Sum and Average

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

**Answers:**

1. **Initial value of `sum`:**
   - 0

2. **Value of sum after each iteration:**
   - i = 0: sum = 0 + 10 = 10
   - i = 1: sum = 10 + 20 = 30
   - i = 2: sum = 30 + 30 = 60
   - i = 3: sum = 60 + 40 = 100

3. **Final value of sum:**
   - 100

4. **Average:**
   - 100 / 4 = 25

5. **Output:**
   ```
   Sum: 100
   Average: 25
   ```

**Teaching Notes:**
- Accumulation pattern
- Using division for average
- Note: integer division (no decimals)
- What if we had {10, 20, 30, 41}? Average = 101/4 = 25 (rounded down)

---

## Answer 7.5.3: Finding Min and Max

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

**Answers:**

1. **Why start at i = 1?**
   - We already initialized min and max to data[0]
   - No need to compare data[0] with itself
   - Efficiency: saves one comparison

2. **Initial values:**
   - min = data[0] = 15
   - max = data[0] = 15

3. **On each iteration:**
   - i = 1: data[1] = 8
     - 8 < 15? YES → min = 8
     - 8 > 15? NO
   - i = 2: data[2] = 23
     - 23 < 8? NO
     - 23 > 15? YES → max = 23
   - i = 3: data[3] = 5
     - 5 < 8? YES → min = 5
     - 5 > 23? NO
   - i = 4: data[4] = 19
     - 19 < 5? NO
     - 19 > 23? NO

4. **Final min:**
   - 5

5. **Final max:**
   - 23

6. **Output:**
   ```
   Min: 5
   Max: 23
   ```

**Teaching Notes:**
- This is the standard min/max algorithm
- Initialize to first element
- Compare all remaining elements
- Foundation for sorting algorithms

---

---

# Common Student Mistakes

## Mistake 1: Off-by-One Indexing
**What students do:**
```c
int arr[3] = {1, 2, 3};
int value = arr[3];  // Wrong! Should be arr[2]
```
**Why:** Confusion about array sizes vs. indices
**Fix:** Remind: Array size N has indices 0 to N-1

## Mistake 2: Forgetting Loop Bounds
**What students do:**
```c
for(int i = 0; i <= 5; i++)  // Array is size 5!
    printf("%d\n", arr[i]);   // Will access arr[5] (out of bounds!)
```
**Why:** Forgetting that last valid index is size-1
**Fix:** Use `i < size` not `i <= size`

## Mistake 3: Uninitialized Variables
**What students do:**
```c
int arr[5];  // No initialization
printf("%d", arr[0]);  // Garbage value!
```
**Why:** Don't understand what happens to new arrays
**Fix:** Always initialize or set values before using

## Mistake 4: Assuming Order of Operations
**What students do:**
```c
a[0] = 5;
a[0] = a[0] * 2;
// Students predict 5 instead of 10
```
**Why:** Don't trace step-by-step
**Fix:** Show the trace table clearly

## Mistake 5: Not Understanding Array Independence
**What students do:**
```c
int a[3] = {1, 2, 3};
int b[3] = {4, 5, 6};
a[0] = 100;
// Students think b[0] changed too!
```
**Why:** Don't understand arrays are separate
**Fix:** Show memory diagram

---

## Grading Rubric

### Full Credit (100%)
- ✅ Correct output
- ✅ Clear trace of all steps
- ✅ Variable states shown correctly
- ✅ Explanation of key operations

### Partial Credit (70-80%)
- ✅ Correct output
- ✅ Trace mostly correct, minor errors
- ⚠️ Some missing variable states
- ⚠️ Explanation unclear but shows thinking

### Partial Credit (40-70%)
- ⚠️ Output may have minor errors
- ⚠️ Trace present but incomplete
- ⚠️ Some variable states missing
- ❌ Explanation unclear or missing

### No Credit (0-40%)
- ❌ Output incorrect
- ❌ No trace shown or completely wrong
- ❌ No explanation

**Remember:** The process matters more than the answer. A student with wrong output but clear thinking deserves more credit than correct output with no work shown.

---

**For more teaching guidance, see INSTRUCTOR_GUIDE.md**
