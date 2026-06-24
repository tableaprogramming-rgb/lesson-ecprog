# Template for Creating Exercise Presentations (8.3 - 8.7)

This document provides a template and instructions for creating the remaining exercise presentations.

## Pattern Summary

All exercise presentations follow this structure:

### Slide 1: Code Overview
- Shows the complete code
- Sets context for what will be traced
- Duration: Quick view (not traced yet)

### Slides 2+: Step-by-Step Execution
- Each slide shows one execution step
- Code is shown on the left (50% width)
- Variables/output shown on the right (50% width)
- Highlighted line shows current position
- Table shows variable states

### Last Slide: Key Concepts
- Summary of what was learned
- 4 key takeaways highlighted
- Color-coded with learning objectives

---

## Exercise-Specific Content

### Exercise 8.3: Row and Column Operations

**Code to trace:**
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

**Key Steps:**
1. Declare and initialize matrix
2-4. Loop iterations (j=0,1,2) calculating rowSum
5. Print result

**Concepts:**
- Fixed row index (1), varying column index (j)
- Selective traversal (not entire matrix)
- Single loop instead of nested (different from 8.2)

---

### Exercise 8.4: Functions with 2D Arrays

**Code to trace:**
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

**Key Steps:**
1. Declare array in main()
2. Call sumMatrix() function
3. Inside function: nested loops and accumulation
4. Return sum to main()
5. Print result

**Concepts:**
- Function parameter: `int matrix[3][3]` (column count required!)
- Array passed by reference (not copied)
- Return value from function
- Scope of variables (arr in main, matrix in function)

---

### Exercise 8.5: Searching

**Code to trace:**
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

**Key Steps:**
1. Initialize variables (target, found flag, position)
2-5. Loop iterations until element found
6-9. Check condition and update position
10. Exit loops (early termination with `&& !found`)
11-12. Print results

**Concepts:**
- Linear search algorithm
- Using flag for early exit (`&& !found`)
- Comparing with target value
- Storing position (row, col) when found
- Conditional output based on found status

---

### Exercise 8.6: Matrix Transpose

**Code to trace:**
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

**Key Steps:**
1. Declare two arrays (different dimensions!)
2-6. Nested loop with swapped indices: `transpose[j][i] = matrix[i][j]`
7-15. Print original matrix
16-24. Print transposed matrix

**Concepts:**
- Index swapping: matrix[i][j] becomes transpose[j][i]
- Dimension change: 2×3 becomes 3×2
- Two separate matrices with different sizes
- Understanding how indices work
- Real-world application in linear algebra

---

### Exercise 8.7: Practical Application (Grade Matrix)

**Code to trace:**
```c
#include <stdio.h>

int main() {
    int grades[4][3] = {
        {85, 90, 78},
        {92, 88, 95},
        {78, 85, 82},
        {88, 92, 89}
    };
    
    // Calculate student averages
    printf("Student Averages:\n");
    for (int i = 0; i < 4; i++) {
        int sum = 0;
        for (int j = 0; j < 3; j++) {
            sum += grades[i][j];
        }
        double avg = sum / 3.0;
        printf("Student %d: %.2f\n", i, avg);
    }
    
    // Calculate subject averages
    printf("Subject Averages:\n");
    for (int j = 0; j < 3; j++) {
        int sum = 0;
        for (int i = 0; i < 4; i++) {
            sum += grades[i][j];
        }
        double avg = sum / 4.0;
        printf("Subject %d: %.2f\n", j, avg);
    }
    
    return 0;
}
```

**Key Steps:**
1. Declare and initialize grade matrix (4 students, 3 subjects)
2-10. Calculate and print student averages
11-21. Calculate and print subject averages

**Concepts:**
- Real-world data representation
- Different traversal patterns (rows vs columns)
- Type conversion (int to double for division)
- Multiple operations on same data
- Practical problem-solving with arrays
- Formatted output (printf with formats)

---

## HTML Template Structure

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PROG2 Day 8 - Exercise 8.X: [Title]</title>
    
    <!-- Copy the CSS from exercise-8.1.html or exercise-8.2.html -->
    <link rel="stylesheet" href="...">
    <style>
        /* Paste all styles from existing exercises */
    </style>
</head>
<body>
    <div class="reveal">
        <div class="slides">
            
            <!-- Slide 1: Code Overview -->
            <section>
                <div class="slide-container">
                    <div class="slide-header">
                        <h2>Exercise 8.X: [Title]</h2>
                        <p>[Brief description]</p>
                    </div>
                    <div class="slide-content" style="justify-content: center; align-items: center;">
                        <div style="width: 100%; text-align: center;">
                            <pre><code>
[Full code here - copy from exercise description]
                            </code></pre>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- Slides 2+: Step-by-step execution -->
            <!-- Copy pattern from exercise-8.1.html or exercise-8.2.html -->
            
            <!-- Last Slide: Key Concepts -->
            <section>
                <div class="slide-container">
                    <div class="slide-header">
                        <h2>Key Concepts from Exercise 8.X</h2>
                        <p>[Description]</p>
                    </div>
                    <div class="slide-content" style="flex-direction: column; padding: 20px 40px;">
                        <div style="margin: 10px 0;">
                            <h3 style="color: #FFD93D; font-size: 1em;">1. [Concept 1]</h3>
                            <p style="margin: 5px 0; font-size: 0.85em;">[Explanation]</p>
                        </div>
                        <!-- Repeat for 4 concepts -->
                    </div>
                </div>
            </section>
            
        </div>
    </div>
    
    <!-- Scripts (copy from existing exercises) -->
    <script src="..."></script>
</body>
</html>
```

---

## Quick Creation Steps

1. **Copy an existing exercise HTML** (e.g., exercise-8.2.html)
2. **Change title** in `<title>` tag and first `<h2>`
3. **Replace code** in the first `<section>` with new code
4. **Modify step-by-step slides**:
   - Adjust number of slides needed
   - Update which lines are highlighted
   - Change variable values in tables
5. **Update last slide** with 4 key concepts
6. **Save as** exercise-8.X.html
7. **Test in browser** - verify all slides work

---

## Step Visualization Tips

### For Row Operations (Ex 8.3)
Show matrix with one row highlighted in different colors as it's summed

### For Search (Ex 8.5)
Highlight cells one by one, show found indicator changing

### For Transpose (Ex 8.6)
Show two matrices side-by-side with arrows showing index swapping

### For Practical (Ex 8.7)
Show matrix visualization changing as calculations happen

---

## Content Specifications

### Exercise 8.3
- **Slides:** 5 (overview + 3 steps + concepts)
- **New concept:** Fixed index with loop
- **Difficulty:** Medium

### Exercise 8.4  
- **Slides:** 5 (overview + 2 steps + function call + concepts)
- **New concept:** Function parameters, column count required
- **Difficulty:** Medium

### Exercise 8.5
- **Slides:** 6-7 (overview + 4-5 steps + concepts)
- **New concept:** Search with early exit
- **Difficulty:** Medium

### Exercise 8.6
- **Slides:** 5 (overview + 2 steps showing transpose + 2 output + concepts)
- **New concept:** Index swapping, dimension changes
- **Difficulty:** Hard

### Exercise 8.7
- **Slides:** 6-7 (overview + row avg + col avg + output + concepts)
- **New concept:** Multiple operations, practical application
- **Difficulty:** Hard

---

## Common HTML Elements

### Highlight a line of code
```html
<span class="highlight-line">int x = 5;</span>
```

### Add a comment
```html
<span class="comment">// This is a comment</span>
```

### Create a variables table
```html
<table>
    <tr><th>Variable</th><th>Value</th></tr>
    <tr><td>x</td><td>5</td></tr>
</table>
```

### Show output
```html
<div class="output-section">
    <h3>Output</h3>
    Value is 5
</div>
```

---

## Testing Before Upload

1. Open HTML in browser
2. Click through all slides with arrow keys
3. Check that:
   - All text is readable
   - Code formatting looks correct
   - No broken links
   - Matrix visualizations render
   - Tables display properly
4. Press 'F' for fullscreen - test readability
5. Check on multiple browsers if possible

---

## Guidelines for Consistency

- Use same color scheme (#64B5F6 for headers, #FFD93D for highlights)
- Keep font sizes consistent (0.5em for code, 0.85em for text)
- Use same transition (fade) between slides
- Match naming: exercise-8.X.html format
- Keep titles in format: "Exercise 8.X: [Title]"
- Each exercise ends with 4 key concepts

---

## Files to Create

1. `exercise-8.3.html` - Row and column operations
2. `exercise-8.4.html` - Functions with 2D arrays
3. `exercise-8.5.html` - Searching
4. `exercise-8.6.html` - Matrix transpose
5. `exercise-8.7.html` - Practical application

---

## Estimated Time to Create

- Each exercise: 20-30 minutes
- Total for all 5: 2-2.5 hours
- With testing and refinement: 3 hours

---

**Note:** Exercises 8.1 and 8.2 are complete examples. Use them as templates for 8.3-8.7.

For questions about HTML structure, refer to the existing exercise files.
