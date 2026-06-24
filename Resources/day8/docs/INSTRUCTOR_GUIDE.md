# DAY 8: Multi-Dimensional Arrays (2D Arrays) - Instructor Guide

**Course:** Computer Programming 2 (PROG2)  
**Lesson:** 4 - Multi-Dimensional Arrays (2 Week Unit, Day 8 is first day)  
**Date:** June 24, 2026  
**For Instructors Only**

---

## Lesson Overview

### Learning Objectives

By the end of Day 8, students will be able to:
1. Declare and initialize 2D arrays properly
2. Access individual elements using row and column indices
3. Use nested loops to traverse a 2D array
4. Pass 2D arrays to functions
5. Implement basic 2D array algorithms (search, sum, find max)
6. Understand array storage in memory

### CILO Coverage

This lesson directly supports:
- **CILO 1:** Simulate behavior and detect output of program codes
- **CILO 3:** Apply structured decomposition (functions with array parameters)
- **CILO 5:** Design and test programs using fundamental constructs

---

## Session Plan

### Session Duration: 50 minutes

| Time | Activity | Content | Materials |
|------|----------|---------|-----------|
| 0-5 min | Review | Single-dimensional arrays recap | Slide: Quick review |
| 5-10 min | Introduction | Why 2D arrays? Real-world examples | Slides: Grade matrix, game board, image pixels |
| 10-20 min | Declaration | Declaration syntax, memory layout | Interactive slides, whiteboard |
| 20-25 min | Initialization | Different initialization methods | Code examples |
| 25-35 min | Access & Traversal | Accessing elements, nested loops | Exercise 8.1 interactive slides |
| 35-45 min | Live Coding | Build a simple sum program together | Code along with students |
| 45-50 min | Q&A | Address questions, preview tomorrow | Take questions |

---

## Pre-Lesson Preparation

### Before Class
- [ ] Review all 7 interactive presentations (HTML files)
- [ ] Test all code examples in exercise slides
- [ ] Prepare visual diagrams for memory layout
- [ ] Set up code editor/IDE for live coding
- [ ] Download or have ready: Dev C++, VS Code, or online compiler

### Materials Needed
- [ ] Projector/Display for slides
- [ ] Whiteboard for diagrams
- [ ] Student laptops with C compiler
- [ ] GitHub for code submission
- [ ] Optional: Printed exercise worksheets

### Handouts to Prepare
- [ ] DAY8_EXERCISES.md (printed or shared)
- [ ] Visual memory layout diagram (rows × columns)
- [ ] Index mapping reference card

---

## Lesson Content Details

### Section 1: Review of Single-Dimensional Arrays (5 minutes)

**Goal:** Refresh memory of array basics before introducing 2D concept.

**Key Points to Recap:**
- Declaration: `int arr[10];`
- Indexing starts at 0
- Accessing: `arr[i]`
- Uses: storing multiple values of same type

**Quick Quiz Question:**
"What will this print?"
```c
int nums[5] = {10, 20, 30, 40, 50};
printf("%d", nums[3]);  // Answer: 40
```

---

### Section 2: Introduction to 2D Arrays (5 minutes)

**Goal:** Motivate why 2D arrays are needed.

**Real-World Examples:**
1. **Grade Book:** Students (rows) × Subjects (columns)
2. **Game Board:** Chess or Tic-Tac-Toe (8×8 or 3×3)
3. **Image/Pixel Map:** Image width × Image height
4. **Spreadsheet:** Rows × Columns of data
5. **Map/Grid:** Terrain elevation (coordinates)

**Show Visual Examples:**
```
Grade Matrix Example:
         Math  English  Science
Student1  85     90       78
Student2  92     88       95
Student3  78     85       82
```

**Discussion Question:**
"Why can't we use a single array for this data? Why do we need 2D?"
- Answer: Need two independent indices to access data

---

### Section 3: Declaration and Initialization (10 minutes)

#### Syntax Explanation

**Declaration:**
```c
int matrix[ROWS][COLS];
int matrix[3][4];  // 3 rows, 4 columns (12 total elements)
```

**Key Point:** Always specify BOTH dimensions. Unlike functions, the first dimension cannot be omitted at declaration.

#### Memory Layout Visualization

**Create this diagram on whiteboard:**

```
int matrix[3][4]:

Row 0: [0][0] [0][1] [0][2] [0][3]
Row 1: [1][0] [1][1] [1][2] [1][3]
Row 2: [2][0] [2][1] [2][2] [2][3]

In Memory (Row-Major Order):
[0][0] → [0][1] → [0][2] → [0][3] → [1][0] → [1][1] → [1][2] → [1][3] → [2][0] → ...
```

**Explain:** 
- C stores arrays in **row-major order** (rows stored sequentially)
- This matters for memory efficiency and function parameters

#### Initialization Methods

**Method 1: Complete initialization**
```c
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

**Method 2: Partial initialization (rest are 0)**
```c
int matrix[3][3] = {
    {1, 2},
    {4, 5},
    {7}
};
// Results: [1,2,0], [4,5,0], [7,0,0]
```

**Method 3: All zeros**
```c
int matrix[3][3] = {0};  // All elements set to 0
```

**Method 4: Nested loop initialization**
```c
int matrix[3][3];
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        matrix[i][j] = i + j;
    }
}
```

---

### Section 4: Accessing Elements (5 minutes)

**Syntax:**
```c
matrix[row][col]  // Both indices required
```

**Example:**
```c
int matrix[3][4] = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};

printf("%d\n", matrix[0][0]);  // Prints: 1
printf("%d\n", matrix[1][2]);  // Prints: 7
printf("%d\n", matrix[2][3]);  // Prints: 12
```

**Common Mistakes:**
- Using `matrix[0,0]` instead of `matrix[0][0]` ❌
- Forgetting second bracket ❌
- Using `matrix[row, col]` like in math ❌

---

### Section 5: Nested Loops for Traversal (10 minutes)

**The Pattern:**
```c
for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
        // Access matrix[i][j]
    }
}
```

**Important Naming:**
- Outer loop: Use `i` for row index
- Inner loop: Use `j` for column index
- Variables for dimensions: `ROWS`, `COLS`, or `rows`, `cols`

#### Example 1: Print all elements

```c
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        printf("%d ", matrix[i][j]);
    }
    printf("\n");  // Newline after each row
}
```

#### Example 2: Calculate sum

```c
int sum = 0;
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        sum += matrix[i][j];
    }
}
printf("Sum: %d\n", sum);
```

#### Example 3: Find maximum

```c
int max = matrix[0][0];
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        if (matrix[i][j] > max) {
            max = matrix[i][j];
        }
    }
}
printf("Maximum: %d\n", max);
```

**Key Teaching Point:** Emphasize the **nesting order matters**:
- Outer loop = rows (changes less frequently)
- Inner loop = columns (changes more frequently)
- This follows row-major memory order

---

### Section 6: Passing 2D Arrays to Functions (5 minutes)

**The Rule:**
```c
void processMatrix(int matrix[3][4]) {  // Column count REQUIRED
    // Can access matrix[i][j]
}

// Alternative (row count can be omitted):
void processMatrix(int matrix[][4]) {
    // Still need [4] to specify columns
}

// Both work, but second is more flexible
```

**Why Column Count is Required:**
- Compiler needs to know column count to calculate memory offset
- For 1D array: `arr[5]` in function = `int *arr` internally
- For 2D array: `matrix[3][4]` in function needs the `[4]` to calculate offset
- Example: To find `matrix[1][2]`, compiler calculates: `base_address + (1 * 4 + 2) * sizeof(int)`

**Live Coding Example:**

```c
#include <stdio.h>

void printMatrix(int m[3][4]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 4; j++) {
            printf("%d ", m[i][j]);
        }
        printf("\n");
    }
}

int sumMatrix(int m[3][4]) {
    int sum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 4; j++) {
            sum += m[i][j];
        }
    }
    return sum;
}

int main() {
    int matrix[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    printMatrix(matrix);
    printf("Sum: %d\n", sumMatrix(matrix));
    
    return 0;
}
```

---

## Exercise Implementation Guide

### Exercise 8.1: Declaration and Initialization (10 minutes)

**What Students Do:**
- Answer multiple choice questions
- Fill in trace tables
- Write code to print matrix and calculate sum

**Live Coding During Class:**
```c
// Live code this together, step by step
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

// Print matrix
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        printf("%d ", matrix[i][j]);
    }
    printf("\n");
}
```

**Common Issues to Address:**
- Students forgetting to initialize with proper braces
- Confusing rows and columns
- Indexing errors (trying to access matrix[3][3] when only 0-2 valid)

---

### Exercise 8.2: Nested Loop Traversal (10 minutes)

**Focus:** Understanding loop execution flow

**Guided Activity:**
1. Show the trace table
2. Have students manually trace through loops
3. Run the code and verify output matches

**Discussion Question:**
"If we swap the loops (outer for j, inner for i), what changes?"
- Output order changes (prints by column instead of row)
- Total iterations stay the same
- Memory access becomes less efficient

---

### Exercise 8.3: Row and Column Operations (10 minutes)

**Key Teaching Point:** 
Understand the difference between:
- Row operations: Fix `i`, vary `j`
- Column operations: Fix `j`, vary `i`

**Whiteboard Activity:**
Draw a 3×3 matrix and color different rows/columns:
```
    Col0  Col1  Col2
Row0  1     2     3    ← Sum this row
Row1  4     5     6
Row2  7     8     9
```

---

### Exercise 8.4: Functions (10 minutes)

**Demonstration:** Show how dimensions matter in parameters

**Interactive Question:**
"What happens if I don't specify [3][3] in the parameter?"
- Compiler error - cannot calculate memory offsets
- Compiler needs column count

**Have students test:** What if they change parameter to `int matrix[3][5]`?
- Program still compiles but gives wrong results
- Memory offset calculation would be wrong

---

### Exercise 8.5: Searching (10 minutes)

**Introduce the `found` flag pattern:**

```c
int found = 0;
for (int i = 0; i < 3 && !found; i++) {
    for (int j = 0; j < 4 && !found; j++) {
        if (matrix[i][j] == target) {
            found = 1;
            // Store position if needed
        }
    }
}
```

**Why this matters:** Early exit for efficiency (important in large arrays)

---

### Exercise 8.6: Transpose (10 minutes)

**Visual Explanation:**
```
Original:        Transpose:
1 2 3           1 4 7
4 5 6    -->    2 5 8
7 8 9           3 6 9
```

**Key Insight:**
```c
transpose[j][i] = matrix[i][j];  // Swap indices!
```

**Extension Question:**
"What if it's not a square matrix (3×3)?"
- Original: 3×3 → Transpose: 3×3 (same)
- Original: 2×3 → Transpose: 3×2 (swapped!)
- Original: 4×5 → Transpose: 5×4 (swapped!)

---

### Exercise 8.7: Practical Application (20 minutes)

**Scenario Context:** Grade management system

**Build Together:**
1. First: Print the grade matrix formatted nicely
2. Then: Calculate student averages
3. Then: Calculate subject averages
4. Finally: Find highs/lows

**Teaching Strategy:**
- Live code the first part together
- Let students code the averaging part
- Have them compare results

**Real-World Connection:**
"Imagine you're building a system for your school. This is how you'd store and process grade data!"

---

## Live Coding Strategy

### Exercise for Live Coding Session (15 minutes)

**"Build a Matrix Sum Calculator Together"**

```c
#include <stdio.h>

int main() {
    int data[3][3];
    
    // Let students input values or use hardcoded
    // Then calculate different sums together:
    
    // 1. Sum all elements
    int totalSum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            totalSum += data[i][j];
        }
    }
    printf("Total Sum: %d\n", totalSum);
    
    // 2. Sum middle row
    int rowSum = data[1][0] + data[1][1] + data[1][2];
    printf("Middle Row Sum: %d\n", rowSum);
    
    // 3. Find maximum
    // ... let students help code this
    
    return 0;
}
```

**Pause Points for Student Input:**
- "What should we do next?"
- "How do we find the maximum?"
- "Can we do this more efficiently?"

---

## Assessment Strategies

### Quick Formative Checks (During Class)

1. **Multiple Choice Questions:** Show on slides, have students respond
2. **Think-Pair-Share:** Ask question, discuss with neighbor, share answers
3. **Show of Hands:** "Who thinks the answer is A?" (Gauge understanding)
4. **Whiteboard Practice:** Have students trace 2 steps on paper, compare

### Summative Assessment (After Class)

**Homework Assignment Options:**

**Option A (Structured):**
- Complete exercises 8.1-8.5 during next lab session
- Submit code on GitHub with clear commit messages
- Show output for verification

**Option B (Project-Based):**
- Create a 3×3 "game board" (e.g., Tic-Tac-Toe, simple grid game)
- Implement functions to check rows/columns/diagonals
- Due in 2-3 days

**Option C (Assessment):**
- Quiz: 5 multiple choice + 2 code trace questions
- Code writing: Write function to find max in matrix

---

## Common Mistakes & How to Address

### Mistake #1: Bracket Confusion
**What students write:**
```c
int matrix[3][4];
printf("%d", matrix[0,2]);  // Wrong: comma instead of brackets
```

**How to fix:**
- Emphasize: "C uses [brackets] for arrays, always"
- Show syntax error message
- Have them practice correct syntax multiple times

### Mistake #2: Off-by-One Errors
**What students write:**
```c
for (int i = 0; i <= 3; i++) {  // Should be < 3, not <= 3
    for (int j = 0; j <= 4; j++) {
        printf("%d ", matrix[i][j]);  // Will crash! Out of bounds
    }
}
```

**How to fix:**
- Teach the pattern: `for (int i = 0; i < ROWS; i++)`
- Emphasize: "Arrays are 0-indexed, so valid indices are 0 to SIZE-1"
- Show example of access violation

### Mistake #3: Forgetting Column Count in Functions
**What students write:**
```c
void process(int matrix[3]) {  // Missing column count!
    // ...
}
```

**How to fix:**
- Explain offset calculation
- Show error message: "In passing array, the second dimension must be specified"
- Practice with multiple examples

### Mistake #4: Uninitialized Variables
**What students write:**
```c
int max;  // No initialization!
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        if (matrix[i][j] > max) {  // Comparing with garbage value
            max = matrix[i][j];
        }
    }
}
```

**How to fix:**
- Always initialize: `int max = matrix[0][0];`
- Or: `int max = INT_MIN;` (from limits.h)
- Have them trace what happens with uninitialized variable

### Mistake #5: Type Conversion Issues
**What students write:**
```c
int avg = sum / count;  // Integer division! Result is wrong
printf("Average: %.2f\n", avg);  // Prints integer, not decimal
```

**How to fix:**
- Show difference: `9 / 2 = 4` (int) vs `9 / 2.0 = 4.5` (double)
- Teach cast: `(double) sum / count`
- Have them print both and compare

---

## Visual Aids & Diagrams

### Create These on Whiteboard

**Diagram 1: Array Memory Layout**
```
int matrix[3][4]:

        Col0  Col1  Col2  Col3
       ┌─────┬─────┬─────┬─────┐
Row0   │ 1   │ 2   │ 3   │ 4   │
       ├─────┼─────┼─────┼─────┤
Row1   │ 5   │ 6   │ 7   │ 8   │
       ├─────┼─────┼─────┼─────┤
Row2   │ 9   │ 10  │ 11  │ 12  │
       └─────┴─────┴─────┴─────┘

Memory Address:
0x100: [1] [2] [3] [4] [5] [6] [7] [8] [9] [10] [11] [12]
         ↑                       ↑
      matrix[0][0]          matrix[1][0]
```

**Diagram 2: Loop Execution**
```
Nested Loops: for (int i = 0; i < 2; i++) for (int j = 0; j < 3; j++)

Iteration Order:
Step 1: i=0, j=0 → matrix[0][0]
Step 2: i=0, j=1 → matrix[0][1]
Step 3: i=0, j=2 → matrix[0][2]
Step 4: i=1, j=0 → matrix[1][0]
Step 5: i=1, j=1 → matrix[1][1]
Step 6: i=1, j=2 → matrix[1][2]
```

---

## Timing Notes

- **If running behind:** Skip bonus exercises (8.B1-B4), focus on 8.1-8.7
- **If ahead:** Add bonus exercises or introduce dynamic allocation preview
- **Pacing:** Spend most time on accessing elements and nested loops (Sections 4-5)

---

## Resources for Student Help

### External Resources (Good for Supplemental Videos)
- GeeksforGeeks: 2D Arrays in C
- TutorialsPoint: C 2D Arrays
- YouTube: "C 2D Arrays Explained"

### Documentation to Reference
- Show students what an error message means
- Point to compiler documentation
- Explain how to read error messages

---

## Next Day (Day 9) Preview

### What's Coming
- More complex matrix operations
- Passing multidimensional arrays to multiple functions
- Searching and sorting algorithms in 2D arrays
- Introduction to 3D arrays (brief)

### Prerequisite Check for Day 9
- Students should be comfortable with nested loops
- Should understand function parameters with 2D arrays
- Should be able to write code to access any element

**Assign for tomorrow:**
"Read the next section on advanced matrix operations and bring 3 questions"

---

## Teacher Reflection Notes

After teaching this lesson, consider:

1. **Which concepts gave students most trouble?**
   - Nested loops?
   - Function parameters?
   - Off-by-one errors?

2. **What worked well?**
   - Which examples were most effective?
   - Which live-coding segments were helpful?

3. **What to adjust next time?**
   - Spend more time on problem areas?
   - Add more examples of a specific concept?
   - Change the order of topics?

4. **Student questions to address:**
   - Keep a list of good questions that came up
   - Use them for next year's lesson

---

## Appendix: Quick Reference for Instructors

### Code Templates for 2D Arrays

**Print Matrix:**
```c
for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
        printf("%d ", matrix[i][j]);
    }
    printf("\n");
}
```

**Sum All Elements:**
```c
int sum = 0;
for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
        sum += matrix[i][j];
    }
}
```

**Find Maximum:**
```c
int max = matrix[0][0];
for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
        if (matrix[i][j] > max) max = matrix[i][j];
    }
}
```

**Pass to Function:**
```c
void function(int matrix[ROWS][COLS]) {
    // COLS is required, ROWS is optional
}
```

---

**Last Updated:** June 23, 2026  
**Maintainer:** [Instructor Name]
