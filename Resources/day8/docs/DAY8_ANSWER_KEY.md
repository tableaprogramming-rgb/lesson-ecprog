# DAY 8: Multi-Dimensional Arrays (2D Arrays) - Answer Key

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026  
**For Instructors Only**

---

## Exercise 8.1: 2D Array Declaration and Initialization - ANSWERS

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| Q1.1 | **B** | `matrix[3][4]` declares a 2D array with 3 rows and 4 columns |
| Q1.2 | **C** | `matrix[1][2]` refers to row 1 (second row), column 2 (third column), which is 7 |
| Q1.3 | **C** | `matrix[2][3]` refers to row 2 (third row), column 3 (fourth column), which is 12 |

### Trace Table Solution

| Step | Line | Statement | matrix[1][2] | matrix[2][3] | Output |
|------|------|-----------|--------------|--------------|--------|
| 1 | 3 | `int matrix[3][4] = {...}` | 7 | 12 | (No output yet) |
| 2 | 9 | `printf("Value at matrix[1][2]..."` | 7 | 12 | "Value at matrix[1][2]: 7" |
| 3 | 10 | `printf("Value at matrix[2][3]..."` | 7 | 12 | "Value at matrix[2][3]: 12" |

### Programming Task Solution

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    // Print all elements using nested loops
    printf("Matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    // Calculate sum of all elements
    int sum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            sum += matrix[i][j];
        }
    }
    
    printf("Sum of all elements: %d\n", sum);
    
    return 0;
}
```

**Expected Output:**
```
Matrix:
1 2 3
4 5 6
7 8 9
Sum of all elements: 45
```

---

## Exercise 8.2: Iterating Through 2D Arrays - ANSWERS

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| Q2.1 | **D** | Inner loop runs 3 times (j = 0, 1, 2) and outer loop runs 2 times = 6 total iterations |
| Q2.2 | **D** | Sum = 1+2+3+4+5+6 = 21 |
| Q2.3 | **B** | `sum += arr[i][j]` is equivalent to `sum = sum + arr[i][j]`, which adds the element to sum |

### Trace Table Solution

| Step | i | j | arr[i][j] | sum | Action |
|------|---|---|-----------|-----|--------|
| 1 | 0 | 0 | 1 | 1 | sum = 0 + 1 = 1 |
| 2 | 0 | 1 | 2 | 3 | sum = 1 + 2 = 3 |
| 3 | 0 | 2 | 3 | 6 | sum = 3 + 3 = 6 |
| 4 | 1 | 0 | 4 | 10 | sum = 6 + 4 = 10 |
| 5 | 1 | 1 | 5 | 15 | sum = 10 + 5 = 15 |
| 6 | 1 | 2 | 6 | 21 | sum = 15 + 6 = 21 |

### Programming Task Solution

```c
#include <stdio.h>

int main() {
    int matrix[4][4] = {
        {12, 8, 15, 3},
        {7, 19, 2, 14},
        {6, 11, 9, 5},
        {18, 4, 13, 20}
    };
    
    // Print matrix with formatting
    printf("Matrix:\n");
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 4; j++) {
            printf("%3d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    // Find and print maximum element
    int max = matrix[0][0];
    int maxRow = 0, maxCol = 0;
    
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 4; j++) {
            if (matrix[i][j] > max) {
                max = matrix[i][j];
                maxRow = i;
                maxCol = j;
            }
        }
    }
    
    printf("Maximum element: %d at position [%d][%d]\n", max, maxRow, maxCol);
    
    return 0;
}
```

**Expected Output:**
```
Matrix:
 12   8  15   3
  7  19   2  14
  6  11   9   5
 18   4  13  20
Maximum element: 20 at position [3][3]
```

---

## Exercise 8.3: Matrix Row and Column Operations - ANSWERS

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| Q3.1 | **C** | The loop iterates through `matrix[1][0]`, `matrix[1][1]`, `matrix[1][2]` which is row 1 |
| Q3.2 | **B** | matrix[1][0]=4, matrix[1][1]=5, matrix[1][2]=6 (all elements in row 1) |
| Q3.3 | **B** | Sum of row 1: 4+5+6 = 15 |

### Programming Task Solution

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    // Calculate and print row sums
    printf("Row sums: ");
    for (int i = 0; i < 3; i++) {
        int rowSum = 0;
        for (int j = 0; j < 3; j++) {
            rowSum += matrix[i][j];
        }
        if (i > 0) printf(", ");
        printf("%d", rowSum);
    }
    printf("\n");
    
    // Calculate and print column sums
    printf("Column sums: ");
    for (int j = 0; j < 3; j++) {
        int colSum = 0;
        for (int i = 0; i < 3; i++) {
            colSum += matrix[i][j];
        }
        if (j > 0) printf(", ");
        printf("%d", colSum);
    }
    printf("\n");
    
    return 0;
}
```

**Expected Output:**
```
Row sums: 6, 15, 24
Column sums: 12, 15, 18
```

---

## Exercise 8.4: Passing 2D Arrays to Functions - ANSWERS

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| Q4.1 | **B** | Prints "1 2" on first line, then "3 4" on second line |
| Q4.2 | **B** | Must specify the number of columns in the parameter; rows are implicit |
| Q4.3 | **C** | 4 times total (2 outer iterations × 2 inner iterations) |

### Programming Task Solution

```c
#include <stdio.h>

int sumMatrix(int matrix[3][3]) {
    int sum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            sum += matrix[i][j];
        }
    }
    return sum;
}

int main() {
    int arr[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    int total = sumMatrix(arr);
    printf("Total sum: %d\n", total);
    
    return 0;
}
```

**Expected Output:**
```
Total sum: 45
```

**Key Point:** When passing 2D arrays to functions:
- Parameter format: `type arrayName[rows][cols]`
- Only the first dimension (rows) can be omitted
- The number of columns MUST be specified
- Alternative: `int sumMatrix(int matrix[][3])` (row count can be omitted)

---

## Exercise 8.5: Finding Elements and Searching - ANSWERS

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| Q5.1 | **B** | `&& !found` stops the search as soon as the element is found |
| Q5.2 | **A** | 7 is at matrix[1][2] (row 1, column 2) |
| Q5.3 | **C** | Initialized to -1 to indicate "not found" |

### Programming Task Solution

```c
#include <stdio.h>

int main() {
    int matrix[4][4] = {
        {1, 2, 3, 2},
        {4, 5, 2, 6},
        {7, 8, 9, 2},
        {2, 10, 11, 12}
    };
    
    int target = 2;
    int count = 0;
    int found = 0;
    int firstRow = -1, firstCol = -1;
    
    // Count occurrences and find first position
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 4; j++) {
            if (matrix[i][j] == target) {
                count++;
                if (!found) {
                    found = 1;
                    firstRow = i;
                    firstCol = j;
                }
            }
        }
    }
    
    // Print results
    if (found) {
        printf("First occurrence of %d at position [%d][%d]\n", target, firstRow, firstCol);
    } else {
        printf("Not found\n");
    }
    
    printf("Total occurrences of %d: %d\n", target, count);
    
    return 0;
}
```

**Expected Output:**
```
First occurrence of 2 at position [0][1]
Total occurrences of 2: 4
```

---

## Exercise 8.6: Matrix Transpose - ANSWERS

### Multiple Choice Answers

| Question | Answer | Explanation |
|----------|--------|-------------|
| Q6.1 | **B** | Original is 2×3, transpose is 3×2 (swap dimensions) |
| Q6.2 | **A** | transpose[0][0] = matrix[0][0] = 1 |
| Q6.3 | **B** | transpose[2][1] = matrix[1][2] = 6 |

### Programming Task Solution

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    int transpose[3][3];
    
    // Calculate transpose
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            transpose[j][i] = matrix[i][j];
        }
    }
    
    // Print original
    printf("Original Matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    // Print transpose
    printf("\nTranspose Matrix:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", transpose[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

**Expected Output:**
```
Original Matrix:
1 2 3
4 5 6
7 8 9

Transpose Matrix:
1 4 7
2 5 8
3 6 9
```

---

## Exercise 8.7: Practical Application - Grade Matrix - ANSWER

### Complete Solution

```c
#include <stdio.h>

int main() {
    // Student grades: 4 students, 3 subjects
    int grades[4][3] = {
        {85, 90, 78},    // Student 0: Math, English, Science
        {92, 88, 95},    // Student 1
        {78, 85, 82},    // Student 2
        {88, 92, 89}     // Student 3
    };
    
    char subjects[3][10] = {"Math", "English", "Science"};
    
    // Print Grade Matrix
    printf("GRADE MATRIX\n");
    printf("           Math  English  Science\n");
    for (int i = 0; i < 4; i++) {
        printf("Student %d: ", i);
        for (int j = 0; j < 3; j++) {
            printf("%3d ", grades[i][j]);
        }
        printf("\n");
    }
    
    // Student Averages
    printf("\nSTUDENT AVERAGES\n");
    double maxStudentAvg = 0;
    int maxStudentIndex = 0;
    
    for (int i = 0; i < 4; i++) {
        int sum = 0;
        for (int j = 0; j < 3; j++) {
            sum += grades[i][j];
        }
        double avg = sum / 3.0;
        printf("Student %d: %.2f\n", i, avg);
        
        if (avg > maxStudentAvg) {
            maxStudentAvg = avg;
            maxStudentIndex = i;
        }
    }
    
    // Subject Averages
    printf("\nSUBJECT AVERAGES\n");
    double minSubjectAvg = 100;
    int minSubjectIndex = 0;
    
    for (int j = 0; j < 3; j++) {
        int sum = 0;
        for (int i = 0; i < 4; i++) {
            sum += grades[i][j];
        }
        double avg = sum / 4.0;
        printf("%s: %.2f\n", subjects[j], avg);
        
        if (avg < minSubjectAvg) {
            minSubjectAvg = avg;
            minSubjectIndex = j;
        }
    }
    
    // Highest and lowest
    printf("\nSUMMARY\n");
    printf("Highest average: Student %d (%.2f)\n", maxStudentIndex, maxStudentAvg);
    printf("Lowest subject average: %s (%.2f)\n", subjects[minSubjectIndex], minSubjectAvg);
    
    return 0;
}
```

**Expected Output:**
```
GRADE MATRIX
           Math  English  Science
Student 0:  85   90   78
Student 1:  92   88   95
Student 2:  78   85   82
Student 3:  88   92   89

STUDENT AVERAGES
Student 0: 84.33
Student 1: 91.67
Student 2: 81.67
Student 3: 89.67

SUBJECT AVERAGES
Math: 85.75
English: 88.75
Science: 86.00

SUMMARY
Highest average: Student 1 (91.67)
Lowest subject average: Science (86.00)
```

---

## Grading Rubric

### Code Quality (40 points)
- Proper variable declarations: 5 pts
- Correct loop structure: 10 pts
- Proper indexing: 10 pts
- Code formatting and comments: 15 pts

### Functionality (40 points)
- Program compiles without errors: 10 pts
- Correct output: 20 pts
- All exercises attempted: 10 pts

### Correctness (20 points)
- Logic is sound: 10 pts
- Edge cases handled: 5 pts
- Results match expected output: 5 pts

### Common Mistakes to Watch For

1. **Off-by-one errors:** Loop conditions using `i < n` instead of `i <= n`
2. **Incorrect array dimensions:** Swapping rows and columns
3. **Forgetting brackets in 2D access:** Using `array[i, j]` instead of `array[i][j]`
4. **Incorrect function parameters:** Not specifying column count in 2D array parameters
5. **Uninitialized variables:** Not initializing sum/max variables before loops
6. **Type issues:** Using `int` for division instead of `float` or `double`

---

## Teaching Notes

### Key Concepts to Emphasize

1. **Memory Layout:** 2D arrays are stored in row-major order (rows are contiguous)
2. **Index Bounds:** Arrays are 0-indexed; valid indices are 0 to (size-1)
3. **Nested Loops:** Always use nested loops for 2D array traversal
4. **Function Parameters:** Compiler needs to know column count to calculate offsets
5. **Practical Applications:** Use real-world examples (grades, maps, game boards)

### Common Student Confusion

- **Why do we need column count?** Explain memory layout and offset calculation
- **How are 2D arrays stored?** Use visual diagrams showing row-major order
- **Why matrix[1][2] and not matrix[1,2]?** Show syntax differences between languages

### Recommended Teaching Order

1. Start with declaration and initialization
2. Show how to access single elements
3. Introduce nested loops for traversal
4. Show functions with 2D parameters
5. Progress to algorithms (search, sum, transpose)
6. End with practical application

---

**Last Updated:** June 23, 2026  
**Maintainer:** Instructor Name
