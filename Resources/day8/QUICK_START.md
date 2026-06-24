# DAY 8: 2D Arrays - Quick Start Guide

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026  
**Topic:** Multi-Dimensional Arrays (2D Arrays)  

---

## 📚 What You'll Learn Today

By the end of Day 8, you'll understand:
- How to declare and initialize 2D arrays
- How to access individual elements using row and column indices
- How to traverse 2D arrays with nested loops
- How to pass 2D arrays to functions
- How to implement basic algorithms (sum, max, search)

---

## 🚀 Quick Navigation

### For Students

**Step 1: Watch the Overview**
```
Open: slides/index.html
Duration: 15-20 minutes
```
This introduces 2D arrays and shows real-world examples.

**Step 2: Work Through Exercises**
```
1. Start with: slides/exercise-8.1.html
2. Then: docs/DAY8_EXERCISES.md (Exercise 8.1)
3. Repeat for exercises 8.2 through 8.7
```

**Step 3: Check Your Work**
```
Reference: docs/DAY8_ANSWER_KEY.md
Compare your answers with solutions
```

---

### For Instructors

**Step 1: Prepare (30 minutes)**
```
Read: docs/INSTRUCTOR_GUIDE.md
Review: All exercise presentations (slides/exercise-8.*.html)
Setup: IDE for live coding
```

**Step 2: Teach (50 minutes)**
```
1. Show index.html (10 min)
2. Follow teaching plan in INSTRUCTOR_GUIDE.md
3. Use individual exercise presentations during teaching
4. Live code examples alongside students
5. Address questions
```

**Step 3: Assess**
```
Students complete: docs/DAY8_EXERCISES.md
Grade using rubric: In docs/DAY8_ANSWER_KEY.md
Review common mistakes section
```

---

## 📁 Folder Structure

```
day8/
├── docs/
│   ├── README.md                  ← Overview of all docs
│   ├── DAY8_EXERCISES.md          ← Student worksheets (7 exercises)
│   ├── DAY8_ANSWER_KEY.md         ← Solutions & grading rubric
│   └── INSTRUCTOR_GUIDE.md        ← Complete teaching plan
├── slides/
│   ├── index.html                 ← Overview presentation
│   ├── exercise-8.1.html          ← Interactive slides for Ex 8.1
│   ├── exercise-8.2.html          ← Interactive slides for Ex 8.2
│   ├── exercise-8.3.html          ← Interactive slides for Ex 8.3
│   ├── exercise-8.4.html          ← Interactive slides for Ex 8.4
│   ├── exercise-8.5.html          ← Interactive slides for Ex 8.5
│   ├── exercise-8.6.html          ← Interactive slides for Ex 8.6
│   ├── exercise-8.7.html          ← Interactive slides for Ex 8.7
│   ├── README.md                  ← Slides documentation
│   ├── slides.md                  ← Optional markdown reference
│   └── .gitignore
└── QUICK_START.md                 ← This file
```

---

## 🎯 Today's Objectives

### Knowledge Goals
- [ ] Understand 2D array declaration syntax
- [ ] Explain row-major memory layout
- [ ] Describe why both dimensions are needed
- [ ] Understand how nested loops traverse 2D arrays

### Skill Goals
- [ ] Write code to declare and initialize 2D arrays
- [ ] Access any element using [row][col] syntax
- [ ] Write nested loops to process all elements
- [ ] Pass 2D arrays to functions
- [ ] Implement sum, max, and search algorithms

### Application Goals
- [ ] Complete all 7 exercises
- [ ] Debug 2D array code
- [ ] Solve real-world problems (grade matrix, game board, etc.)

---

## 💻 Key Code Patterns

### Declaration
```c
int matrix[3][4];  // 3 rows, 4 columns
```

### Initialization
```c
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

### Access Element
```c
int value = matrix[row][col];
matrix[0][0] = 99;
```

### Traverse with Nested Loops
```c
for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
        // Do something with matrix[i][j]
    }
}
```

### Pass to Function
```c
void processMatrix(int matrix[3][4]) {
    // Column count is REQUIRED
}
```

---

## ⏱️ Timing Guide

| Activity | Duration | Location |
|----------|----------|----------|
| Overview Slides | 15-20 min | slides/index.html |
| Exercise 8.1 | 10 min | slides/exercise-8.1.html |
| Exercise 8.2 | 10 min | slides/exercise-8.2.html |
| Exercise 8.3 | 10 min | slides/exercise-8.3.html |
| Exercise 8.4 | 10 min | slides/exercise-8.4.html |
| Exercise 8.5 | 10 min | slides/exercise-8.5.html |
| Exercise 8.6 | 10 min | slides/exercise-8.6.html |
| Exercise 8.7 | 15 min | slides/exercise-8.7.html |
| **TOTAL** | **90 min** | - |

**In-class time: 50 minutes** → Do overview + 2-3 exercises  
**Homework: 40 minutes** → Complete remaining exercises

---

## 📖 Exercise Summary

| # | Title | Focus | Difficulty |
|---|-------|-------|-----------|
| 8.1 | Declaration & Initialization | Understanding array structure | ⭐ Easy |
| 8.2 | Nested Loops & Traversal | Loop execution order | ⭐ Easy |
| 8.3 | Row & Column Operations | Selective access | ⭐⭐ Medium |
| 8.4 | Functions & Parameters | Passing arrays | ⭐⭐ Medium |
| 8.5 | Searching | Finding elements | ⭐⭐ Medium |
| 8.6 | Matrix Transpose | Index manipulation | ⭐⭐⭐ Hard |
| 8.7 | Practical Application | Integrating concepts | ⭐⭐⭐ Hard |

---

## ✅ Before Class Checklist

### Students
- [ ] Read: docs/README.md
- [ ] View: slides/index.html in browser
- [ ] Complete: Exercise 8.1
- [ ] Have: Text editor and C compiler ready
- [ ] Setup: GitHub account for code submission

### Instructors
- [ ] Test: All HTML slides in your browser
- [ ] Setup: IDE/compiler for live coding
- [ ] Print: docs/DAY8_EXERCISES.md (optional)
- [ ] Review: docs/INSTRUCTOR_GUIDE.md
- [ ] Prepare: Whiteboard for diagrams

---

## 🎓 Learning Outcomes (CILO)

After completing Day 8, students will be able to:

**CILO 1:** Simulate the behavior and detect the output of program codes involving 2D arrays
- Trace execution of nested loops
- Determine values accessed by array indices
- Predict output of 2D array programs

**CILO 3:** Apply techniques of structured decomposition to 2D array problems
- Use functions with 2D array parameters
- Break complex problems into array operations
- Implement algorithms using helper functions

**CILO 5:** Design and implement programs using 2D arrays
- Write declaration and initialization code
- Implement traversal and search algorithms
- Debug array indexing errors

---

## 🐛 Common Mistakes to Avoid

1. **Wrong Syntax:** `matrix[0,0]` ❌ → `matrix[0][0]` ✅
2. **Wrong Access:** Treating 2D as 1D ❌ → Always use [row][col] ✅
3. **Off-by-One:** Loop `i <= ROWS` ❌ → Use `i < ROWS` ✅
4. **Uninitialized:** `int max;` then using it ❌ → Initialize first ✅
5. **Forgot Column:** `void func(int a[3])` ❌ → `void func(int a[3][4])` ✅

---

## 📞 Getting Help

### Questions During Class
- Raise your hand → Ask the instructor
- Check INSTRUCTOR_GUIDE.md → Common mistakes section
- Look at code examples → Try to understand patterns

### Outside of Class
- Review: docs/DAY8_EXERCISES.md → Re-read the problem
- Check: docs/DAY8_ANSWER_KEY.md → See solution approach
- Test: Compile and run your code → See actual error messages
- Practice: Complete bonus exercises → Build confidence

---

## 🔄 Next Steps

### After Day 8
- Complete homework exercises (8.1-8.7)
- Push code to GitHub with good commit messages
- Review INSTRUCTOR_GUIDE.md for common mistakes
- Ask questions on anything unclear

### Before Day 9
- Be ready for advanced 2D array operations
- Know how to declare and traverse 2D arrays
- Understand nested loop patterns
- Be able to pass arrays to functions

---

## 🎯 Success Criteria

### For Exercises
- [ ] Code compiles without errors
- [ ] Correct output produced
- [ ] Proper array declarations
- [ ] Correct nested loops
- [ ] Good code formatting
- [ ] Appropriate comments

### For Learning
- [ ] Can explain what `matrix[2][1]` accesses
- [ ] Can write nested loops for any 2D array
- [ ] Can pass 2D array to function
- [ ] Can implement sum/max/search algorithms
- [ ] Can debug array indexing errors

---

## 📚 Additional Resources

### If You Want More Examples
- GeeksforGeeks: "2D Arrays in C"
- TutorialsPoint: "C 2D Arrays"
- YouTube: "C Programming 2D Arrays Explained"

### If You Want to Go Deeper
- Pointer arithmetic (how 2D arrays work in memory)
- Dynamic 2D arrays (malloc for variable sizes)
- 3D arrays (extending to 3 dimensions)

---

## 📝 Homework Submission

**What to Submit:**
- Exercise codes (8.1-8.7 or at least 8.1-8.5)
- Each as separate .c file
- Commits to GitHub with clear messages

**Commit Message Format:**
```
day8: exercise 8.1 - 2d array declaration
day8: exercise 8.2 - nested loops and sum
day8: exercise 8.3 - row and column operations
```

**Due:** Next class session

---

## 💡 Pro Tips

1. **Draw It Out:** Sketch the matrix on paper before coding
2. **Test Small:** Test with 2×2 before larger arrays
3. **Print Values:** Add printf() to debug what's happening
4. **Compare Output:** Check your output against expected
5. **Ask Questions:** Don't sit confused - ask the instructor!

---

## 🎬 Getting Started Right Now

### Students
1. Open `slides/index.html` in your browser (fullscreen with F)
2. Click through the overview
3. Open `docs/DAY8_EXERCISES.md`
4. Start Exercise 8.1
5. Code, test, compare with answer key

### Instructors
1. Read `docs/INSTRUCTOR_GUIDE.md` (15 min)
2. Test `slides/index.html` in your projector setup
3. Prepare `slides/exercise-8.1.html` for first example
4. Have your IDE open for live coding
5. Start class with the overview slides

---

**Ready? Open `slides/index.html` in your browser to begin!**

---

**Last Updated:** June 23, 2026  
**Maintainer:** [Instructor Name]  
**Questions?** See docs/INSTRUCTOR_GUIDE.md or docs/README.md
