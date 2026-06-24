# DAY 8: Multi-Dimensional Arrays (2D Arrays) - Documentation

**Course:** Computer Programming 2 (PROG2)  
**Lesson:** 4 - Multi-Dimensional Arrays (2 Week Unit)  
**Date:** June 24, 2026  
**Duration:** 50 minutes (Lecture + Lab)

---

## Overview

Day 8 introduces students to 2D arrays in C, covering declaration, initialization, element access, and basic operations. This is the first day of the 2-week Multi-Dimensional Arrays unit.

### Learning Outcomes
By the end of this session, students will:
1. Declare and initialize 2D arrays correctly
2. Access and modify individual elements
3. Traverse 2D arrays using nested loops
4. Pass 2D arrays to functions
5. Implement basic algorithms (sum, max, search)

---

## Files in This Directory

### For Students

| File | Purpose | Size | Time to Read |
|------|---------|------|--------------|
| **DAY8_EXERCISES.md** | 7 structured exercises with code traces, multiple choice, and programming tasks | 15 KB | 45-60 min |
| **README.md** | This file - overview and navigation | 8 KB | 5-10 min |

### For Instructors

| File | Purpose | Size | Time to Read |
|------|---------|------|--------------|
| **INSTRUCTOR_GUIDE.md** | Complete teaching plan with lesson breakdown, tips, common mistakes | 25 KB | 30-40 min |
| **DAY8_ANSWER_KEY.md** | Solutions to all exercises with explanations | 18 KB | 15-25 min |
| **README.md** | This file | 8 KB | 5 min |

---

## Quick Start

### For Students
1. **Review slides:** Open `../slides/index.html` in your browser
2. **Work through exercises:** Start with Exercise 8.1 in `DAY8_EXERCISES.md`
3. **Check answers:** Use `DAY8_ANSWER_KEY.md` to verify your work
4. **Submit on GitHub:** Push your completed code with clear commit messages

### For Instructors
1. **Prepare:** Read `INSTRUCTOR_GUIDE.md` 30 minutes before class
2. **Teach:** Follow the 50-minute session plan
3. **Grade:** Use rubric in `DAY8_ANSWER_KEY.md`
4. **Support:** Reference common mistakes section as needed

---

## Curriculum Structure

### This Unit (Lesson 4: Multi-Dimensional Arrays)
- **Day 8** (Today): Declaration, initialization, access, traversal
- **Day 9** (Tomorrow): Advanced operations, algorithms, problem-solving

### Prerequisites
- Single-dimensional arrays (Lesson 3)
- Nested loops (Lesson 1)
- Functions with parameters (Lesson 2)

### Leads To
- 2D arrays as function parameters
- Algorithms on matrices
- Introduction to dynamic allocation

---

## Exercise Breakdown

### Exercise 8.1: Declaration and Initialization (10 min)
**Skills:** Array declaration, indexing basics, understanding memory layout
- Code trace with MCQ answers
- Trace table to fill
- Task: Print matrix and calculate sum

**Key Concepts:**
- Syntax: `int matrix[rows][cols]`
- Initialization with nested braces
- Memory layout (row-major order)

### Exercise 8.2: Iterating Through 2D Arrays (10 min)
**Skills:** Nested loops, loop logic, accumulation
- Code trace showing loop iterations
- Trace table with execution steps
- Task: Format and find max in 4×4 matrix

**Key Concepts:**
- Nested loop pattern
- Loop variable scope
- Efficiency of loop order

### Exercise 8.3: Matrix Row and Column Operations (10 min)
**Skills:** Selective traversal, row/column distinction
- Code trace calculating row sum
- MCQ on operations
- Task: Calculate all row sums and all column sums

**Key Concepts:**
- Fixing one index, varying the other
- Row vs. column operations
- Edge cases (first/last row/column)

### Exercise 8.4: Passing 2D Arrays to Functions (10 min)
**Skills:** Function parameters, scope, array decay
- Code trace through function call
- MCQ on parameter syntax
- Task: Write function to sum matrix

**Key Concepts:**
- Parameter syntax requires column count
- Memory offset calculation
- Why column count matters

### Exercise 8.5: Finding Elements and Searching (10 min)
**Skills:** Search algorithms, conditional logic, early exit
- Code trace through search loop
- MCQ on search logic
- Task: Search and count occurrences

**Key Concepts:**
- Linear search in 2D
- Using flag for early exit
- Finding position (row, col)

### Exercise 8.6: Matrix Transpose (10 min)
**Skills:** Index manipulation, new data structure
- Code trace showing transpose
- MCQ on dimensions
- Task: Implement transpose for 3×3

**Key Concepts:**
- Swapping row/column indices
- Dimension changes (3×3→3×3, 2×3→3×2)
- Practical applications

### Exercise 8.7: Practical Application - Grade Matrix (20 min)
**Skills:** Integrating all previous concepts, real-world problem
- Scenario: Student grades in 4×3 matrix
- Task: Print, average, analyze grades
- Expected output: Formatted report

**Key Concepts:**
- Real-world data representation
- Complex multi-step algorithms
- Formatted output

---

## Interactive Slides

Located in `../slides/` folder:

| File | Exercise | Content |
|------|----------|---------|
| **index.html** | Overview | Introduction to 2D arrays, big picture |
| **exercise-8.1.html** | 8.1 | Declaration, initialization, access |
| **exercise-8.2.html** | 8.2 | Nested loops, traversal |
| **exercise-8.3.html** | 8.3 | Row and column operations |
| **exercise-8.4.html** | 8.4 | Functions with 2D array parameters |
| **exercise-8.5.html** | 8.5 | Searching and finding |
| **exercise-8.6.html** | 8.6 | Matrix transpose |
| **exercise-8.7.html** | 8.7 | Practical application |

**To view:** Open any HTML file in web browser (Chrome, Firefox, Safari, Edge)

---

## Key Concepts Map

```
2D Arrays
├── Declaration & Memory
│   ├── Syntax: int arr[ROWS][COLS]
│   ├── Memory layout (row-major)
│   └── Dimensions matter
├── Access & Traversal
│   ├── Index: arr[i][j]
│   ├── Nested loops (essential!)
│   └── Row vs column operations
├── Algorithms
│   ├── Sum all elements
│   ├── Find maximum/minimum
│   ├── Linear search
│   └── Matrix operations (transpose)
└── Functions & Parameters
    ├── Passing 2D arrays
    ├── Column count required
    └── Return values
```

---

## Common Student Questions & Answers

### Q1: "Why do we need 2D arrays?"
**A:** When you need to organize data in rows AND columns (like a spreadsheet). Example: Student grades with subjects.

### Q2: "Why can't I pass `int arr[3]` for a 2D array?"
**A:** Because 2D arrays need two indices. Also, the compiler needs to know the column count to calculate memory offsets.

### Q3: "What's the difference between `matrix[0][0]` and `matrix[0,0]`?"
**A:** C uses double brackets `[0][0]`. Single brackets `[0,0]` is a single index (the comma operator).

### Q4: "Can I have different lengths for different rows?"
**A:** No, in C all rows must be the same length. If you need this, use arrays of pointers or dynamic allocation.

### Q5: "How is a 2D array stored in memory?"
**A:** Row by row, sequentially. `matrix[0][0]`, `matrix[0][1]`, `matrix[0][2]`, `matrix[1][0]`, ... This is "row-major order."

### Q6: "Why does the order of loops matter?"
**A:** For readability and efficiency. Outer loop should vary slowly (rows), inner loop should vary quickly (columns), which matches memory layout.

---

## Assessment Rubric

### Exercise Code (40 points)
- **Compilation (10 pts):** Code compiles without errors
- **Syntax (10 pts):** Correct array declaration, indexing, loops
- **Variables (10 pts):** Proper variable declarations and initialization
- **Comments (10 pts):** Code is well-commented and readable

### Correctness (40 points)
- **Logic (20 pts):** Algorithm is correct and produces right results
- **Output (10 pts):** Output matches expected format
- **Edge cases (10 pts):** Handles boundary conditions (first/last element)

### Completeness (20 points)
- **All exercises attempted (10 pts):** At least 7 of 7 exercises attempted
- **Trace tables (5 pts):** All tables filled out correctly
- **MCQ answers (5 pts):** All multiple choice answered

---

## Tips for Students

### Before You Code
1. **Draw it out:** Sketch the array on paper with values
2. **Plan the loops:** Decide how many rows/columns you'll iterate
3. **Verify indices:** Check that your indices stay in bounds (0 to size-1)

### While Coding
1. **Use good names:** `rows`, `cols`, `i`, `j` (not `a`, `b`, `x`, `y`)
2. **Initialize before use:** Don't declare `int sum;` then add to it
3. **Print intermediate values:** Use `printf()` to debug

### After Coding
1. **Trace through:** Manually trace a small example
2. **Test edge cases:** First element `[0][0]`, last element
3. **Compare output:** Check if it matches expected output

---

## Tips for Instructors

### Before Class
- [ ] Review the instructor guide thoroughly
- [ ] Test all code examples in a compiler
- [ ] Create whiteboard diagrams on slides or paper
- [ ] Have your IDE ready for live coding
- [ ] Set up code sharing setup (if using)

### During Class
- [ ] Start with a real-world example (grades, game board, image pixels)
- [ ] Show memory layout visually
- [ ] Emphasize: **Nested loops are essential**
- [ ] Live code simple example together
- [ ] Pause frequently for student questions

### After Class
- [ ] Review student submissions on GitHub
- [ ] Provide feedback on first submissions
- [ ] Identify common mistakes to address next class
- [ ] Prepare extra help session if needed

---

## Assignment Options

### Option A: Structured Practice (Easy)
**For students needing extra support:**
- Complete Exercises 8.1-8.4
- Use answer key to self-grade
- Submit 2-3 key programs to GitHub
- **Due:** End of day

### Option B: Standard Assignment (Medium)
**For typical students:**
- Complete all 7 exercises
- Write working code for each
- Submit to GitHub with clear commit messages
- **Due:** Tomorrow's class

### Option C: Extended Project (Hard)
**For advanced students:**
- Complete Exercise 8.7 (grade matrix)
- Add features:
  - Read student names from user
  - Store in parallel array with grades
  - Add ability to find failing students
- **Due:** 2 days

---

## Classroom Setup Checklist

### Technology
- [ ] Projector/display working
- [ ] Slides loaded and tested
- [ ] C compiler available on student machines
- [ ] GitHub access available
- [ ] Internet connectivity

### Materials
- [ ] Printed copies of exercises (optional)
- [ ] Whiteboard or digital board
- [ ] Markers/stylus
- [ ] Code templates printed (optional)

### Setup
- [ ] Backup IDE/compiler loaded
- [ ] Example code tested and ready
- [ ] Time buffer for technical issues
- [ ] Chat/Q&A method established

---

## Related Resources

### Previous Lessons
- Lesson 1: Control Structures (loops, conditionals)
- Lesson 2: Functions (parameters, return values)
- Lesson 3: Single-Dimensional Arrays

### Next Lessons
- Lesson 4 Day 9: Advanced 2D array operations
- Lesson 5: Pointers (relates to array memory)
- Lesson 6: Strings (arrays of characters)

### External Learning Resources
- **GeeksforGeeks:** "2D Arrays in C" - Good visual explanations
- **TutorialsPoint:** "C 2D Arrays" - Step-by-step tutorial
- **YouTube:** "C Programming 2D Arrays" - Video walkthroughs
- **W3Schools:** C reference - Quick syntax lookup

---

## Quick Reference: 2D Array Syntax

### Declaration
```c
int matrix[3][4];          // 3 rows, 4 columns
double data[5][5];         // 5×5 array of doubles
char grid[10][10];         // 10×10 character grid
```

### Initialization
```c
int arr[2][3] = {{1,2,3}, {4,5,6}};    // Full init
int arr[2][3] = {0};                    // All zeros
int arr[][3] = {{1,2,3}, {4,5,6}};     // Row count optional
```

### Access
```c
matrix[0][0]    // First element (row 0, column 0)
matrix[i][j]    // Element at row i, column j
matrix[2][3]    // Row 2, column 3
```

### Nested Loops
```c
for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
        // Access matrix[i][j]
    }
}
```

### Function Parameter
```c
void func(int matrix[3][4]) { }          // Full dimensions
void func(int matrix[][4]) { }            // Column count required
int sumMatrix(int m[3][4]);               // As function declaration
```

---

## Navigation

- **📚 Back to Day 8 folder:** `../`
- **🎯 Interactive Slides:** Open `../slides/index.html`
- **🔧 Solutions:** See `DAY8_ANSWER_KEY.md`
- **👨‍🏫 Teaching Plan:** See `INSTRUCTOR_GUIDE.md`

---

## Contact & Support

**Questions about this material?**
- Check the FAQ section in `INSTRUCTOR_GUIDE.md`
- Review common mistakes section
- Refer to external resources listed above

**Want to contribute?**
- Found an error? Please report it
- Have better explanation? Submit it
- Want to add an exercise? Create an issue

---

**Last Updated:** June 23, 2026  
**Maintainer:** [Instructor Name]  
**License:** Educational - Free to use and modify for teaching
