# DAY 8: Multi-Dimensional Arrays (2D Arrays) - Exercise Worksheets

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026  
**Topic:** 2D Array Declaration, Initialization, Access, and Manipulation  
**Instructor:** [Name]

---

## Exercise 8.1: 2D Array Declaration and Initialization

### Objective
Understand how to declare and initialize 2D arrays in C, and access individual elements.

### Code Trace - Read through the code and trace execution step by step

```c
#include <stdio.h>

int main() {
    int matrix[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    printf("Value at matrix[1][2]: %d\n", matrix[1][2]);
    printf("Value at matrix[2][3]: %d\n", matrix[2][3]);
    
    return 0;
}
```

### Questions

**Q1.1:** What does `matrix[3][4]` represent?
- [ ] A 3D array with 4 elements
- [ ] A 2D array with 3 rows and 4 columns
- [ ] A 2D array with 4 rows and 3 columns
- [ ] A single array with 7 elements

**Q1.2:** What will be printed for `matrix[1][2]`?
- [ ] 2
- [ ] 6
- [ ] 7
- [ ] 11

**Q1.3:** What will be printed for `matrix[2][3]`?
- [ ] 10
- [ ] 11
- [ ] 12
- [ ] 3

### Trace Table

Fill in the trace table by executing the code step by step:

| Step | Line | Statement | matrix[1][2] | matrix[2][3] | Output |
|------|------|-----------|--------------|--------------|--------|
| 1 | 3 | `int matrix[3][4] = {...}` | ? | ? | |
| 2 | 9 | `printf("Value at matrix[1][2]..."` | 7 | 12 | "Value at matrix[1][2]: 7" |
| 3 | 10 | `printf("Value at matrix[2][3]..."` | 7 | 12 | "Value at matrix[2][3]: 12" |

### Programming Task

**Task 8.1:** Write a C program that:
1. Declares a 3×3 integer array
2. Initializes it with values 1-9
3. Prints all elements using nested loops
4. Calculates and prints the sum of all elements

```c
#include <stdio.h>

int main() {
    // TODO: Declare and initialize 3x3 array
    
    // TODO: Print all elements using nested loops
    
    // TODO: Calculate sum of all elements
    
    return 0;
}
```

---

## Exercise 8.2: Iterating Through 2D Arrays

### Objective
Learn how to use nested loops to traverse a 2D array and perform operations on elements.

### Code Trace

```c
#include <stdio.h>

int main() {
    int arr[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };
    
    int sum = 0;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            sum += arr[i][j];
        }
    }
    
    printf("Sum: %d\n", sum);
    
    return 0;
}
```

### Questions

**Q2.1:** How many times will the inner loop execute?
- [ ] 2
- [ ] 3
- [ ] 5
- [ ] 6

**Q2.2:** What value will `sum` have after the loops complete?
- [ ] 6
- [ ] 10
- [ ] 15
- [ ] 21

**Q2.3:** What does `sum += arr[i][j]` do?
- [ ] Assigns arr[i][j] to sum
- [ ] Adds arr[i][j] to sum
- [ ] Subtracts arr[i][j] from sum
- [ ] Multiplies sum by arr[i][j]

### Trace Table

| Step | i | j | arr[i][j] | sum | Action |
|------|---|---|-----------|-----|--------|
| 1 | 0 | 0 | 1 | 1 | sum = 0 + 1 |
| 2 | 0 | 1 | 2 | 3 | sum = 1 + 2 |
| 3 | 0 | 2 | 3 | 6 | sum = 3 + 3 |
| 4 | 1 | 0 | 4 | 10 | sum = 6 + 4 |
| 5 | 1 | 1 | 5 | 15 | sum = 10 + 5 |
| 6 | 1 | 2 | 6 | 21 | sum = 15 + 6 |

### Programming Task

**Task 8.2:** Write a C program that:
1. Creates a 4×4 array
2. Initializes it with values (user input or hardcoded)
3. Prints each row on a new line with formatted spacing
4. Finds and prints the maximum element

```c
#include <stdio.h>

int main() {
    int matrix[4][4] = {
        {12, 8, 15, 3},
        {7, 19, 2, 14},
        {6, 11, 9, 5},
        {18, 4, 13, 20}
    };
    
    // TODO: Print matrix with formatting
    // TODO: Find and print maximum element
    
    return 0;
}
```

---

## Exercise 8.3: Matrix Row and Column Operations

### Objective
Perform operations on specific rows and columns of a 2D array.

### Code Trace

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    int rowSum = 0;
    for (int j = 0; j < 3; j++) {
        rowSum += matrix[1][j];
    }
    
    printf("Sum of row 1: %d\n", rowSum);
    
    return 0;
}
```

### Questions

**Q3.1:** What does this code calculate?
- [ ] Sum of all elements
- [ ] Sum of column 1
- [ ] Sum of row 1
- [ ] Sum of the main diagonal

**Q3.2:** Which elements are being summed?
- [ ] matrix[0][1], matrix[1][1], matrix[2][1]
- [ ] matrix[1][0], matrix[1][1], matrix[1][2]
- [ ] matrix[0][0], matrix[1][1], matrix[2][2]
- [ ] All elements in the matrix

**Q3.3:** What will be printed?
- [ ] Sum of row 1: 12
- [ ] Sum of row 1: 15
- [ ] Sum of row 1: 24
- [ ] Sum of row 1: 45

### Programming Task

**Task 8.3:** Write a C program that:
1. Creates a 3×3 matrix with arbitrary values
2. Calculates the sum of each row
3. Calculates the sum of each column
4. Prints both results

Example output:
```
Row sums: 6, 15, 24
Column sums: 12, 15, 18
```

```c
#include <stdio.h>

int main() {
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    
    // TODO: Calculate and print row sums
    // TODO: Calculate and print column sums
    
    return 0;
}
```

---

## Exercise 8.4: Passing 2D Arrays to Functions

### Objective
Learn how to pass 2D arrays as function parameters and manipulate them.

### Code Trace

```c
#include <stdio.h>

void printMatrix(int matrix[2][2]) {
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
}

int main() {
    int arr[2][2] = {
        {1, 2},
        {3, 4}
    };
    
    printMatrix(arr);
    
    return 0;
}
```

### Questions

**Q4.1:** What will be printed?
- [ ] 1 2 3 4
- [ ] 1 2\n3 4
- [ ] (1, 2) (3, 4)
- [ ] 1\n2\n3\n4

**Q4.2:** When passing a 2D array to a function, what must be included in the parameter?
- [ ] The number of rows only
- [ ] The number of columns only
- [ ] Both rows and columns
- [ ] Neither

**Q4.3:** How many times does the inner loop execute?
- [ ] 2
- [ ] 3
- [ ] 4
- [ ] 8

### Programming Task

**Task 8.4:** Write a C program with a function that:
1. Takes a 3×3 matrix as parameter
2. Calculates and returns the sum of all elements
3. Call the function from main() with a test matrix

```c
#include <stdio.h>

int sumMatrix(int matrix[3][3]) {
    // TODO: Calculate and return sum
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

---

## Exercise 8.5: Finding Elements and Searching

### Objective
Practice searching algorithms on 2D arrays.

### Code Trace

```c
#include <stdio.h>

int main() {
    int matrix[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };
    
    int target = 7;
    int found = 0;
    int row = -1, col = -1;
    
    for (int i = 0; i < 3 && !found; i++) {
        for (int j = 0; j < 4 && !found; j++) {
            if (matrix[i][j] == target) {
                found = 1;
                row = i;
                col = j;
            }
        }
    }
    
    if (found) {
        printf("Found %d at position [%d][%d]\n", target, row, col);
    } else {
        printf("Not found\n");
    }
    
    return 0;
}
```

### Questions

**Q5.1:** Why is `&& !found` used in the loop conditions?
- [ ] To count elements
- [ ] To stop searching once the element is found
- [ ] To avoid index errors
- [ ] To print the result

**Q5.2:** What will be printed?
- [ ] Found 7 at position [1][2]
- [ ] Found 7 at position [2][3]
- [ ] Not found
- [ ] Found 7 at position [0][2]

**Q5.3:** What are the initial values of row and col?
- [ ] 0 and 0
- [ ] 1 and 1
- [ ] -1 and -1
- [ ] 3 and 4

### Programming Task

**Task 8.5:** Write a C program that:
1. Creates a 4×4 matrix
2. Searches for a specific value (user input or hardcoded)
3. If found, print position; if not, print "Not found"
4. Count how many times the value appears in the matrix

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
    
    // TODO: Count occurrences of target
    // TODO: Print first position found
    // TODO: Print count of occurrences
    
    return 0;
}
```

---

## Exercise 8.6: Matrix Transpose

### Objective
Understand matrix operations like transposition.

### Code Trace

```c
#include <stdio.h>

int main() {
    int matrix[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };
    
    int transpose[3][2];
    
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            transpose[j][i] = matrix[i][j];
        }
    }
    
    printf("Original:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    printf("Transpose:\n");
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", transpose[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

### Questions

**Q6.1:** What are the dimensions of the transpose?
- [ ] 2×3
- [ ] 3×2
- [ ] 2×2
- [ ] 3×3

**Q6.2:** What value will be at transpose[0][0]?
- [ ] 1
- [ ] 2
- [ ] 4
- [ ] 0

**Q6.3:** What will be printed for transpose[2][1]?
- [ ] 3
- [ ] 6
- [ ] 5
- [ ] 2

### Programming Task

**Task 8.6:** Write a C program that:
1. Creates a 3×3 matrix
2. Calculates its transpose
3. Prints both the original and transposed matrices side by side

---

## Exercise 8.7: Practical Application - Grade Matrix

### Objective
Apply 2D array concepts to a real-world scenario.

### Scenario
Create a program that manages student grades in a 4×3 matrix where:
- Rows represent 4 students
- Columns represent 3 subjects (Math, English, Science)

### Code Skeleton

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
    
    // TODO: Calculate average for each student
    // TODO: Calculate average for each subject
    // TODO: Find student with highest average
    // TODO: Find subject with highest average
    // TODO: Print formatted report
    
    return 0;
}
```

### Requirements

Write a program that:
1. **Print Grade Matrix:** Display all grades in formatted table
2. **Student Averages:** Calculate and print average grade for each student
3. **Subject Averages:** Calculate average grade for each subject
4. **Find Maximum:** Identify which student has the highest average
5. **Identify Weak Subject:** Identify which subject has the lowest average

### Expected Output Example

```
GRADE MATRIX
           Math  English  Science
Student 0:  85      90       78
Student 1:  92      88       95
Student 2:  78      85       82
Student 3:  88      92       89

STUDENT AVERAGES
Student 0: 84.33
Student 1: 91.67
Student 2: 81.67
Student 3: 89.67

SUBJECT AVERAGES
Math: 85.75
English: 88.75
Science: 86.00

Highest average: Student 1 (91.67)
Lowest subject average: Science (86.00)
```

---

## Bonus Exercises

### Exercise 8.B1: Diagonal Sums
Calculate the sum of elements on the main diagonal of a square matrix.

### Exercise 8.B2: Anti-Diagonal Sum
Calculate the sum of elements on the anti-diagonal (opposite diagonal).

### Exercise 8.B3: Spiral Matrix
Print matrix elements in spiral order (outer edges working inward).

### Exercise 8.B4: Matrix Multiplication
Multiply two 2×2 matrices and print the result.

---

## Submission Checklist

- [ ] All exercises (8.1 - 8.7) completed
- [ ] Code compiles without errors
- [ ] All trace tables filled out correctly
- [ ] Multiple choice questions answered
- [ ] Code produces correct output
- [ ] Code is properly commented
- [ ] Files submitted on GitHub with clear commit messages

---

## Tips for Success

1. **Visualize the array:** Draw it out on paper before coding
2. **Use meaningful names:** Use `rows` and `cols` for loop bounds
3. **Remember indexing:** Arrays are 0-indexed (starts at 0)
4. **Check bounds:** Ensure loop conditions match array dimensions
5. **Test with small arrays:** Use 2×2 or 3×3 for debugging
6. **Print intermediate values:** Use printf() to verify correctness

---

**Last Updated:** June 23, 2026  
**Maintainer:** Instructor Name
