# DAY 8 AFTERNOON: Debugging 2D Arrays - Exercise Worksheets

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026 (Afternoon Session)  
**Topic:** Identifying and Fixing Bugs in 2D Array Code  
**Instructor:** [Name]

---

## Overview

This afternoon session focuses on **debugging** - finding and fixing errors in 2D array code. Each exercise contains intentional bugs that you must identify, understand, and correct.

### Learning Objectives
By the end of this session, you will:
- Identify common 2D array bugs
- Understand why bugs occur
- Fix bugs and verify solutions
- Prevent similar bugs in future code

---

## Debugging Exercise 1: Off-by-One Error in Loops

### The Problem
The following code attempts to find the maximum value in a 3×3 array, but it has a bug. Identify and fix it.

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {10, 20, 30},
        {40, 50, 60},
        {70, 80, 90}
    };
    
    int max = 0;  // ❌ Bug here!
    for (int i = 0; i <= 3; i++) {  // ❌ Bug here!
        for (int j = 0; j <= 3; j++) {  // ❌ Bug here!
            if (matrix[i][j] > max) {
                max = matrix[i][j];
            }
        }
    }
    
    printf("Maximum value: %d\n", max);
    return 0;
}
```

### Questions

**D1.1:** What happens when i=3 or j=3?
- [ ] The loop exits normally
- [ ] The program accesses invalid memory (out of bounds)
- [ ] The loop increments to i=4
- [ ] The maximum is correctly found

**D1.2:** What should the loop conditions be?
- [ ] `i < 3` and `j < 3`
- [ ] `i <= 2` and `j <= 2`
- [ ] Both are correct
- [ ] Neither is correct

**D1.3:** What's wrong with initializing `max = 0`?
- [ ] If all values in the matrix are positive, it works fine
- [ ] If the matrix has negative values or all positive values < current max, it fails
- [ ] There's nothing wrong
- [ ] It's wasteful but not incorrect

### Your Task: Fix the Code

**Identify all bugs:**
1. Bug 1: _______________
2. Bug 2: _______________
3. Bug 3: _______________

**Write the corrected code:**
```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {10, 20, 30},
        {40, 50, 60},
        {70, 80, 90}
    };
    
    // TODO: Fix the bugs
    
    printf("Maximum value: %d\n", max);
    return 0;
}
```

**Expected Output:**
```
Maximum value: 90
```

---

## Debugging Exercise 2: Wrong Function Parameter

### The Problem
This function is supposed to sum all elements in a 3×4 matrix, but it has a parameter bug.

```c
#include <stdio.h>

int sumMatrix(int matrix[3]) {  // ❌ Bug here!
    int sum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 4; j++) {
            sum += matrix[i][j];
        }
    }
    return sum;
}

int main() {
    int arr[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    int total = sumMatrix(arr);
    printf("Sum: %d\n", total);
    return 0;
}
```

### Questions

**D2.1:** What's the compilation error?
- [ ] Function parameter type mismatch
- [ ] Missing dimension specification (missing [4])
- [ ] Array name mismatch
- [ ] No error - code works fine

**D2.2:** Why is the column count important in the parameter?
- [ ] It helps with variable names
- [ ] The compiler needs it to calculate memory offsets
- [ ] It prevents confusion
- [ ] It doesn't matter

**D2.3:** What should the parameter be?
- [ ] `int matrix[3][4]`
- [ ] `int matrix[][4]`
- [ ] Either A or B
- [ ] `int *matrix`

### Your Task: Fix the Code

**What's the bug?**
The function parameter should be: `________________`

**Write the corrected function:**
```c
int sumMatrix(________) {  // Fix this!
    int sum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 4; j++) {
            sum += matrix[i][j];
        }
    }
    return sum;
}
```

**Expected Output:**
```
Sum: 78
```

---

## Debugging Exercise 3: Uninitialized Variable

### The Problem
This code calculates the average of a row, but forgets to initialize a variable.

```c
#include <stdio.h>

int main() {
    int grades[4][3] = {
        {85, 90, 78},
        {92, 88, 95},
        {78, 85, 82},
        {88, 92, 89}
    };
    
    int row = 2;
    int sum;  // ❌ Bug: Not initialized!
    
    for (int j = 0; j < 3; j++) {
        sum += grades[row][j];  // ❌ Adding to garbage value!
    }
    
    double average = sum / 3.0;
    printf("Average for row %d: %.2f\n", row, average);
    return 0;
}
```

### Questions

**D3.1:** What happens with uninitialized `sum`?
- [ ] It automatically starts at 0
- [ ] It has a garbage/random value
- [ ] The program crashes immediately
- [ ] It works fine by chance

**D3.2:** What's the fix?
- [ ] `int sum;` → No fix needed
- [ ] `int sum = 0;` → Initialize to 0
- [ ] `int sum = grades[row][0];` → Initialize to first value
- [ ] Either B or C works

**D3.3:** What will be the (incorrect) output?
- [ ] Unpredictable (depends on garbage value in memory)
- [ ] Always the same wrong value
- [ ] Average = 81.67 (correct answer)
- [ ] 0 (because sum was uninitialized)

### Your Task: Fix the Code

**What's the bug?**
Line: `int sum;` should be: `________________`

**Write the corrected code:**
```c
#include <stdio.h>

int main() {
    int grades[4][3] = {
        {85, 90, 78},
        {92, 88, 95},
        {78, 85, 82},
        {88, 92, 89}
    };
    
    int row = 2;
    int sum = ____;  // Fix this!
    
    for (int j = 0; j < 3; j++) {
        sum += grades[row][j];
    }
    
    double average = sum / 3.0;
    printf("Average for row %d: %.2f\n", row, average);
    return 0;
}
```

**Expected Output:**
```
Average for row 2: 81.67
```

---

## Debugging Exercise 4: Wrong Loop Nesting

### The Problem
This code tries to find the sum of a specific column, but the loops are in the wrong order.

```c
#include <stdio.h>

int main() {
    int data[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    int col = 2;
    int sum = 0;
    
    for (int j = 0; j < 4; j++) {      // ❌ Wrong outer loop!
        for (int i = 0; i < 3; i++) {  // ❌ Wrong inner loop!
            if (j == col) {
                sum += data[i][j];
            }
        }
    }
    
    printf("Sum of column %d: %d\n", col, sum);
    return 0;
}
```

### Questions

**D4.1:** What's wrong with the loop order?
- [ ] Nothing - the loops work correctly
- [ ] The outer and inner loops should be swapped for efficiency
- [ ] The condition `if (j == col)` works but is inefficient
- [ ] All of the above - it's inefficient and confusing

**D4.2:** What does the buggy code actually do?
- [ ] Correctly sums column 2
- [ ] Only adds one element to sum
- [ ] Sums all elements (inefficiently)
- [ ] Crashes due to out of bounds access

**D4.3:** What's the better approach?
- [ ] `for (int i = 0; i < 3; i++)` then access `data[i][col]`
- [ ] Use the exact code as written
- [ ] Transpose the matrix first
- [ ] Use recursion instead

### Your Task: Fix the Code

**Describe the bug:**
The loop logic is inefficient because _______________________

**Write the corrected, more efficient code:**
```c
#include <stdio.h>

int main() {
    int data[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    int col = 2;
    int sum = 0;
    
    // TODO: Fix the loops to be efficient
    
    printf("Sum of column %d: %d\n", col, sum);
    return 0;
}
```

**Expected Output:**
```
Sum of column 2: 21
```

---

## Debugging Exercise 5: Wrong Index Usage

### The Problem
This code tries to fill a matrix with sequential numbers, but uses indices wrong.

```c
#include <stdio.h>

int main() {
    int matrix[2][3];
    int num = 1;
    
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            matrix[j][i] = num;  // ❌ Indices are swapped!
            num++;
        }
    }
    
    // Print the matrix
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

### Questions

**D5.1:** What gets filled incorrectly?
- [ ] Nothing - the code works fine
- [ ] The assignment uses transposed indices
- [ ] The print loop accesses the wrong locations
- [ ] Both B and C are involved

**D5.2:** What will be printed?
- [ ] 1 2 3 / 4 5 6 (Correct sequential fill)
- [ ] 1 4 / 2 5 / 3 6 (Transposed)
- [ ] Out of bounds error
- [ ] Garbage values or undefined behavior

**D5.3:** Which is the bug?
- [ ] Assignment: `matrix[j][i]` should be `matrix[i][j]`
- [ ] Print loop needs to be fixed
- [ ] Both the assignment and print need fixing
- [ ] The initialization is wrong

### Your Task: Fix the Code

**Identify the bug:**
In the first nested loop, the assignment `matrix[j][i] = num;` should be: `________________`

**Write the corrected code:**
```c
#include <stdio.h>

int main() {
    int matrix[2][3];
    int num = 1;
    
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            matrix[____][____] = num;  // Fix this!
            num++;
        }
    }
    
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

**Expected Output:**
```
1 2 3 
4 5 6 
```

---

## Debugging Exercise 6: Type Conversion Issue

### The Problem
This code calculates an average but gets wrong results due to integer division.

```c
#include <stdio.h>

int main() {
    int matrix[2][3] = {
        {10, 20, 30},
        {40, 50, 60}
    };
    
    int sum = 0;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            sum += matrix[i][j];
        }
    }
    
    int average = sum / 6;  // ❌ Integer division!
    printf("Average: %d\n", average);
    return 0;
}
```

### Questions

**D6.1:** What's wrong with `int average = sum / 6;`?
- [ ] The type should be `double`, not `int`
- [ ] Integer division loses the decimal part
- [ ] 210 / 6 = 35, but we lose the .0
- [ ] All of the above

**D6.2:** What will be printed?
- [ ] Average: 35
- [ ] Average: 35.0 (correct)
- [ ] Average: 35.5 (wrong)
- [ ] Compilation error

**D6.3:** How to fix it?
- [ ] `double average = sum / 6.0;`
- [ ] `double average = (double)sum / 6;`
- [ ] Cast one operand to double
- [ ] All of the above work

### Your Task: Fix the Code

**The bug:**
Using `int` for average with integer division loses precision

**Write the corrected code:**
```c
#include <stdio.h>

int main() {
    int matrix[2][3] = {
        {10, 20, 30},
        {40, 50, 60}
    };
    
    int sum = 0;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            sum += matrix[i][j];
        }
    }
    
    double average = _________;  // Fix this!
    printf("Average: %.1f\n", average);
    return 0;
}
```

**Expected Output:**
```
Average: 35.0
```

---

## Debugging Exercise 7: Logic Error in Algorithm

### The Problem
This code tries to check if a value exists in the matrix, but the logic is wrong.

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    int target = 5;
    int found = 0;
    
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (matrix[i][j] == target) {
                found = 1;  // ❌ Found it!
            }
            else {
                found = 0;  // ❌ Bug: Resetting found!
            }
        }
    }
    
    if (found) {
        printf("Value %d was found\n", target);
    } else {
        printf("Value %d was not found\n", target);
    }
    
    return 0;
}
```

### Questions

**D7.1:** What's the problem with this logic?
- [ ] Nothing - the code works correctly
- [ ] The `else` clause resets `found` to 0 even after finding the value
- [ ] The loop doesn't continue after finding the value
- [ ] The printf statements are wrong

**D7.2:** What will be printed if target=5?
- [ ] "Value 5 was found" (Correct)
- [ ] "Value 5 was not found" (Incorrect, because found is reset)
- [ ] Compilation error
- [ ] Nothing (infinite loop)

**D7.3:** How to fix this?
- [ ] Remove the `else` clause entirely
- [ ] Add `break;` when found = 1
- [ ] Change `else { found = 0; }` to just remove it
- [ ] Any of the above would work

### Your Task: Fix the Code

**Describe the bug:**
The `else` clause resets `found` even after the value is found

**Write the corrected code (two possible solutions):**

**Solution A: Remove the else clause**
```c
if (matrix[i][j] == target) {
    found = 1;
}
// TODO: Remove the else clause!
```

**Solution B: Use early exit**
```c
if (matrix[i][j] == target) {
    found = 1;
    break;  // Exit inner loop
}
// TODO: No else clause needed!
```

**Expected Output:**
```
Value 5 was found
```

---

## Debugging Exercise 8: Complex Nested Loop Bug

### The Problem
This code tries to print the matrix diagonally, but has multiple bugs.

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    // Print main diagonal
    for (int i = 0; i < 4; i++) {  // ❌ Off-by-one!
        printf("%d ", matrix[i][i]);
    }
    printf("\n");
    
    return 0;
}
```

### Questions

**D8.1:** What's wrong with `i < 4`?
- [ ] Array is 3×3, so valid indices are 0-2
- [ ] Accessing matrix[3][3] is out of bounds
- [ ] Should be `i < 3`
- [ ] All of the above

**D8.2:** What will happen?
- [ ] Print: 1 5 9 (Correct)
- [ ] Access matrix[3][3] (out of bounds)
- [ ] Crash or undefined behavior
- [ ] Print garbage value for 4th element

### Your Task: Fix the Code

**The bug:**
Loop condition should be: `________________`

**Write the corrected code:**
```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    // Print main diagonal
    for (int i = 0; ____; i++) {  // Fix this!
        printf("%d ", matrix[i][i]);
    }
    printf("\n");
    
    return 0;
}
```

**Expected Output:**
```
1 5 9 
```

---

## Bonus: Find All Bugs (Challenge Exercise)

### The Problem
This code has **5 intentional bugs**. Find and fix them all!

```c
#include <stdio.h>

int processMatrix(int matrix[3]) {  // Bug 1
    int sum;  // Bug 2
    for (int i = 0; i <= 3; i++) {  // Bug 3
        for (int j = 0; j < 4; j++) {
            if (i < 3) {
                sum += matrix[i][j];  // Bug 5: Depends on Bug 2
            }
        }
    }
    return sum / 12;  // Bug 4
}

int main() {
    int arr[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    int result = processMatrix(arr);
    printf("Average: %d\n", result);
    
    return 0;
}
```

### Your Task: Find All 5 Bugs

**Bug 1:** _______________________________________________

**Bug 2:** _______________________________________________

**Bug 3:** _______________________________________________

**Bug 4:** _______________________________________________

**Bug 5:** _______________________________________________

### Write the Corrected Code

```c
#include <stdio.h>

// TODO: Fix all 5 bugs

int main() {
    int arr[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    int result = processMatrix(arr);
    printf("Average: %d\n", result);
    
    return 0;
}
```

**Expected Output:**
```
Average: 6
```
(Sum = 78, Average = 78/12 = 6)

---

## Summary of Common 2D Array Bugs

| Bug Type | Example | How to Fix |
|----------|---------|-----------|
| **Off-by-one in loops** | `i < 4` for 3×3 array | Use `i < ROWS` |
| **Wrong array dimensions** | `int arr[3]` for 3×4 | Must specify both: `[3][4]` |
| **Uninitialized variables** | `int sum;` then `sum +=` | Initialize: `int sum = 0;` |
| **Wrong index order** | `matrix[j][i]` when should be `[i][j]` | Use consistent convention |
| **Integer division** | `int avg = sum / 6;` | Use `double` or cast: `sum / 6.0` |
| **Logic errors** | Resetting found flag | Remove unnecessary else clauses |
| **Wrong function params** | `int matrix[3]` | Include both: `matrix[3][4]` |
| **Out of bounds access** | Accessing `matrix[3][3]` in 3×3 array | Check loop bounds |

---

## Debugging Tips

1. **Read error messages carefully** - they often point to the exact line
2. **Trace execution manually** - follow the code step-by-step on paper
3. **Print intermediate values** - use `printf()` to see what's happening
4. **Test with small arrays** - use 2×2 or 3×3 before larger ones
5. **Check loop bounds** - verify indices stay within 0 to size-1
6. **Verify function parameters** - ensure both dimensions are specified
7. **Initialize all variables** - especially sums, counts, and flags
8. **Compare with expected output** - check if your output matches

---

## Submission Checklist

- [ ] All 8 debugging exercises completed
- [ ] Bugs identified correctly
- [ ] Code fixed and compiles
- [ ] Output matches expected results
- [ ] Code is well-commented
- [ ] Bonus challenge attempted (optional)
- [ ] Files submitted to GitHub

---

**Last Updated:** June 23, 2026  
**Maintainer:** Instructor Name
