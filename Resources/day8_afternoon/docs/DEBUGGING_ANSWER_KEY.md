# DAY 8 AFTERNOON: Debugging 2D Arrays - Answer Key

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026 (Afternoon Session)  
**For Instructors Only**

---

## Debugging Exercise 1: Off-by-One Error in Loops

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D1.1 | **B** | Accessing matrix[3][j] or matrix[i][3] is out of bounds; valid indices are 0-2 |
| D1.2 | **C** | Both `i < 3` and `i <= 2` are correct; also both work for columns |
| D1.3 | **B** | If matrix contains negative numbers or all positive < max, initialization fails |

### Bugs Identified

**Bug 1:** `for (int i = 0; i <= 3; i++)` should be `for (int i = 0; i < 3; i++)`
- Using `<=` instead of `<` causes out-of-bounds access

**Bug 2:** `for (int j = 0; j <= 3; j++)` should be `for (int j = 0; j < 3; j++)`
- Same issue with columns

**Bug 3:** `int max = 0;` should be `int max = matrix[0][0];`
- If all values are negative, initializing to 0 won't find the actual maximum

### Corrected Code

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {10, 20, 30},
        {40, 50, 60},
        {70, 80, 90}
    };
    
    int max = matrix[0][0];  // Initialize to first element
    for (int i = 0; i < 3; i++) {  // Changed <= to <
        for (int j = 0; j < 3; j++) {  // Changed <= to <
            if (matrix[i][j] > max) {
                max = matrix[i][j];
            }
        }
    }
    
    printf("Maximum value: %d\n", max);
    return 0;
}
```

**Output:** `Maximum value: 90` ✅

### Why These Bugs Matter
- **Off-by-one errors** are among the most common in programming
- They often compile without errors but crash at runtime
- Array indexing is 0-based; for a 3×3 array, valid indices are 0, 1, 2
- **Initialization** must consider all possible values, not just positive numbers

---

## Debugging Exercise 2: Wrong Function Parameter

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D2.1 | **B** | Missing [4] specification for columns |
| D2.2 | **B** | Compiler uses column count to calculate memory offsets between rows |
| D2.3 | **C** | Both `int matrix[3][4]` and `int matrix[][4]` work; row count can be omitted |

### The Bug

**Parameter declaration:** `int sumMatrix(int matrix[3])` 
- Missing the column count `[4]`
- This causes a **compilation error**
- Or if it compiles, the offset calculation is wrong

**The Fix:** Change to `int sumMatrix(int matrix[3][4])` or `int sumMatrix(int matrix[][4])`

### Why This Matters

When accessing `matrix[i][j]`, the compiler calculates:
```
memory_address = base_address + (i * COLS + j) * sizeof(int)
```

Without knowing the column count (4), the compiler cannot calculate the correct offset.

### Corrected Code

```c
#include <stdio.h>

int sumMatrix(int matrix[3][4]) {  // Fixed: added [4]
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

**Output:** `Sum: 78` ✅

**Calculation:** 1+2+3+4+5+6+7+8+9+10+11+12 = 78

---

## Debugging Exercise 3: Uninitialized Variable

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D3.1 | **B** | Uninitialized variables contain garbage/random values from memory |
| D3.2 | **B** | Initialize to 0; Option C (initialize to first value) is for max/min |
| D3.3 | **A** | Output is unpredictable; depends on what garbage value was in memory |

### The Bug

**Uninitialized variable:** `int sum;` then immediately `sum += grades[row][j];`

This adds to whatever random value is in memory, producing garbage results.

**The Fix:** `int sum = 0;` before using it in any operation

### Why This Matters

- Uninitialized variables cause **non-deterministic behavior** (random results)
- Different runs of the program produce different outputs
- This is a **runtime** bug, not a compilation error
- Always initialize variables before using them!

### Corrected Code

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
    int sum = 0;  // Fixed: Initialize to 0
    
    for (int j = 0; j < 3; j++) {
        sum += grades[row][j];
    }
    
    double average = sum / 3.0;
    printf("Average for row %d: %.2f\n", row, average);
    return 0;
}
```

**Output:** `Average for row 2: 81.67` ✅

**Calculation:** (78 + 85 + 82) / 3.0 = 245 / 3.0 = 81.67

---

## Debugging Exercise 4: Wrong Loop Nesting

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D4.1 | **C** | The condition `if (j == col)` works but is inefficient; checking every column |
| D4.2 | **C** | Inefficient: sums all elements, but the if-statement filters for column 2 only |
| D4.3 | **A** | Better to loop rows only and directly access column index |

### The Bug (Not a crash, but inefficient)

**Current code:** Nested loops (columns outer, rows inner) with an if-statement
- This checks every element (12 iterations for 3×4)
- Only adds elements where j==col (4 iterations do work)
- Wasteful and confusing logic

**The Fix:** Loop only rows, directly access the column
- Much clearer intent
- Only 3 iterations needed

### Why This Matters

This shows **logic errors** that don't crash but are:
- Inefficient (unnecessary iterations)
- Confusing (unclear intent)
- Hard to maintain
- Common mistakes when learning

### Corrected Code

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
    
    // Better approach: loop only rows, access specific column
    for (int i = 0; i < 3; i++) {
        sum += data[i][col];
    }
    
    printf("Sum of column %d: %d\n", col, sum);
    return 0;
}
```

**Output:** `Sum of column 2: 21` ✅

**Calculation:** 3 + 7 + 11 = 21

---

## Debugging Exercise 5: Wrong Index Usage

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D5.1 | **A** | The assignment uses transposed indices; both assignment and print would work if indices matched |
| D5.2 | **B** | Transposed output (though in this case, undefined which is filled first) |
| D5.3 | **A** | The bug is in assignment; print loop uses standard [i][j] convention |

### The Bugs

**Bug 1:** `matrix[j][i] = num;` should be `matrix[i][j] = num;`
- Assignment uses swapped indices (transposed)
- Print uses standard indices [i][j]
- Mismatch causes wrong output

**Why it's wrong:** 
- Outer loop: i goes 0→1, j goes 0→2
- First iteration: matrix[0][0] = 1, matrix[1][0] = 2, matrix[2][0] = 3
- But matrix is only 2×3 (not 3×2!)
- Accessing matrix[2][0] is out of bounds for a 2×3 array

### Corrected Code

```c
#include <stdio.h>

int main() {
    int matrix[2][3];
    int num = 1;
    
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            matrix[i][j] = num;  // Fixed: use [i][j]
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

**Output:**
```
1 2 3 
4 5 6 
```
✅

### Why This Matters

- Index order matters! Always use consistent conventions
- [i] = row (first dimension)
- [j] = column (second dimension)
- Common bug when thinking in terms of transpose

---

## Debugging Exercise 6: Type Conversion Issue

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D6.1 | **D** | All are correct - type should be double, integer division loses decimal |
| D6.2 | **A** | Prints 35 (integer division loses .0) instead of 35.0 |
| D6.3 | **D** | All three methods work: 6.0, (double)sum, or (double) cast |

### The Bug

**Integer Division:** `int average = sum / 6;`

When both operands are integers, C performs integer division:
- 210 / 6 = 35 (exact)
- But if sum was 211, result would be 35 (truncated from 35.166...)

**The Fix:** Make one operand floating-point
- `double average = sum / 6.0;` (6.0 is double)
- `double average = (double)sum / 6;` (cast sum to double)
- `double average = sum / (double)6;` (cast 6 to double)

### Corrected Code

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
    
    // Fixed: Use double and division by 6.0
    double average = sum / 6.0;
    printf("Average: %.1f\n", average);
    return 0;
}
```

**Output:** `Average: 35.0` ✅

**Calculation:** 210 / 6.0 = 35.0

### Why This Matters

- **Type matters** in C - operations depend on operand types
- Integer division is **truncation**, not rounding
- Common source of subtle bugs where results are "close but wrong"
- Always be careful with division by counts

---

## Debugging Exercise 7: Logic Error in Algorithm

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D7.1 | **B** | The else clause resets found even after finding the value |
| D7.2 | **B** | Prints "not found" because found is reset after the target is found |
| D7.3 | **D** | All solutions work: remove else, add break, or restructure |

### The Bug

**Logic Error:**
```c
if (matrix[i][j] == target) {
    found = 1;  // Found it!
}
else {
    found = 0;  // But we reset it here!
}
```

This resets `found` to 0 for every element that doesn't match.

**Trace with target=5:**
- Check 1: not 5, found=0
- Check 2: not 5, found=0
- Check 3: not 5, found=0
- Check 4: not 5, found=0
- Check 5: **IS 5, found=1** ✓
- Check 6: not 5, found=0 ❌ (Reset! Bug!)
- ... continues, ends with found=0

### Corrected Code (Three Solutions)

**Solution A: Remove the else**
```c
int found = 0;
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        if (matrix[i][j] == target) {
            found = 1;  // Set to 1 and never reset
        }
    }
}
```

**Solution B: Early exit with break**
```c
int found = 0;
for (int i = 0; i < 3 && !found; i++) {
    for (int j = 0; j < 3 && !found; j++) {
        if (matrix[i][j] == target) {
            found = 1;
            break;  // Exit immediately!
        }
    }
}
```

**Solution C: Use different flag logic**
```c
int notFound = 1;  // Track "not found" instead
for (int i = 0; i < 3 && notFound; i++) {
    for (int j = 0; j < 3 && notFound; j++) {
        if (matrix[i][j] == target) {
            notFound = 0;
        }
    }
}
if (!notFound) {
    printf("Value %d was found\n", target);
}
```

**Output:** `Value 5 was found` ✅

---

## Debugging Exercise 8: Complex Nested Loop Bug

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| D8.1 | **D** | All are correct - 3×3 array has valid indices 0-2 only |
| D8.2 | **C** | Crash or undefined behavior accessing matrix[3][3] |

### The Bug

**Off-by-one in loop:** `for (int i = 0; i < 4; i++)`

For a 3×3 array, valid indices are [0][0] through [2][2].

When i=3, accessing matrix[3][3] is **out of bounds**.

**The Fix:** `for (int i = 0; i < 3; i++)`

### Corrected Code

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    // Print main diagonal
    for (int i = 0; i < 3; i++) {  // Fixed: < 3 instead of < 4
        printf("%d ", matrix[i][i]);
    }
    printf("\n");
    
    return 0;
}
```

**Output:** `1 5 9 ` ✅

---

## Bonus Challenge: Find All 5 Bugs

### Bugs Identified

**Bug 1:** Function parameter `int matrix[3]` should be `int matrix[3][4]`
- Missing column dimension

**Bug 2:** `int sum;` should be `int sum = 0;`
- Uninitialized variable

**Bug 3:** `i <= 3` should be `i < 3`
- Off-by-one error (array is 3×4, valid row indices 0-2)

**Bug 4:** `return sum / 12;` loses decimal in division
- Should be `return sum / 12.0;` or cast to double
- Actually, this should return a double or cast result

**Bug 5:** Depends on Bug 2
- If sum is uninitialized, this line doesn't work correctly

### Corrected Code

```c
#include <stdio.h>

double processMatrix(int matrix[3][4]) {  // Bug 1: Added [4]
    int sum = 0;  // Bug 2: Initialize to 0
    for (int i = 0; i < 3; i++) {  // Bug 3: Changed <= to <
        for (int j = 0; j < 4; j++) {
            sum += matrix[i][j];
        }
    }
    return sum / 12.0;  // Bug 4: Changed to 12.0 for floating-point division
}

int main() {
    int arr[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    double result = processMatrix(arr);
    printf("Average: %.0f\n", result);
    
    return 0;
}
```

**Output:** `Average: 6` ✅

**Calculation:** (1+2+...+12) / 12 = 78 / 12 = 6.5, but with int print would be 6

---

## Common Bug Patterns & Prevention

### Pattern 1: Off-by-One Errors
**Cause:** Using `<=` instead of `<`, or vice versa
**Prevention:** Remember arrays are 0-indexed; for size N, valid indices are 0 to N-1
**Check:** `for (int i = 0; i < ROWS; i++)` not `i <= ROWS`

### Pattern 2: Uninitialized Variables
**Cause:** Declaring variable but not setting initial value
**Prevention:** Always initialize: `int sum = 0;`
**Check:** Look for `int x;` followed immediately by `x +=` or similar

### Pattern 3: Type Mismatches
**Cause:** Integer division when floating-point needed
**Prevention:** Use `.0` or cast: `sum / 6.0` or `(double)sum / 6`
**Check:** Watch for arithmetic with percentages, averages, ratios

### Pattern 4: Wrong Dimensions
**Cause:** Function parameter missing column count
**Prevention:** Always specify both: `matrix[ROWS][COLS]`
**Check:** Function parameters must have complete dimensions

### Pattern 5: Logic Errors
**Cause:** Unnecessary else clauses or incorrect conditions
**Prevention:** Think carefully about what should happen in each case
**Check:** Trace through algorithm with pen and paper

### Pattern 6: Index Swapping
**Cause:** Using [j][i] instead of [i][j] accidentally
**Prevention:** Use consistent convention: i=row, j=column
**Check:** Review array accesses; match declaration order

### Pattern 7: Out of Bounds
**Cause:** Accessing array[size] or beyond
**Prevention:** Always check loop bounds match array dimensions
**Check:** Verify `i < ROWS` and `j < COLS`

---

## Assessment Rubric

### For Each Debugging Exercise
- **Bug Identification (50%):** Correctly identified all bugs
- **Bug Explanation (25%):** Explained why it's a bug and its impact
- **Correct Solution (25%):** Fixed code compiles and produces correct output

### Overall Assessment
- **7-8 exercises correct:** Excellent (90-100%)
- **6 exercises correct:** Good (80-89%)
- **5 exercises correct:** Satisfactory (70-79%)
- **4 exercises correct:** Needs Improvement (60-69%)
- **<4 exercises:** Requires More Practice (<60%)

### Bonus Challenge Bonus
- If completed and correct: +10% to overall grade

---

## Teaching Notes

### Key Concepts to Emphasize

1. **Debugging is a skill** - It takes practice and persistence
2. **Read error messages** - They often tell you exactly what's wrong
3. **Use print statements** - `printf()` is your debugging friend
4. **Test incrementally** - Build and test as you go
5. **Know the rules** - Understanding C's rules prevents bugs

### Common Student Mistakes

- Confusing `<=` with `<` (off-by-one)
- Forgetting to initialize accumulators
- Not reading compiler/runtime errors carefully
- Assuming buggy code will work "close enough"
- Not testing edge cases (first element, last element, boundary)

### Discussion Questions

1. "What's the most common type of bug you encountered?"
2. "How would you prevent off-by-one errors?"
3. "Why do uninitialized variables exist in C?"
4. "How can you make your code less error-prone?"

---

**Last Updated:** June 23, 2026  
**Maintainer:** Instructor Name
