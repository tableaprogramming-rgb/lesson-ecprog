# PROG2 Day 6: Hands-On Function Exercise

## Overview

Day 6 is a **hands-on coding exercise** where students apply all function concepts from Days 1-5 in a real-world project.

---

## Project: Student Grade Management System

### What Students Will Build

A C program that manages student grades using multiple functions:
- Input quiz and exam scores
- Calculate weighted averages
- Determine final grade and letter
- Generate a professional report

### Key Learning Outcomes

By completing this exercise, students will:
1. Write and use **void functions** for input and output
2. Write and use **value-returning functions** for calculations
3. Pass data into functions using **parameters**
4. Understand **pass-by-value** semantics
5. Coordinate multiple functions in a complete program
6. Apply the **6-step debugging process** when needed

---

## Exercise Structure

### Files Included

- **Canvas Instructions** (`canvas/Hands-On-1-Functions/`)
  - Complete exercise instructions (Canvas LMS format)
  - Starter code
  - Expected outputs
  - Grading rubric

### Requirements

**5 Required Functions:**

1. `void inputScores()` - Read scores from user
2. `double calculateAverage()` - Compute average
3. `double calculateFinalGrade()` - Calculate weighted grade
4. `char getLetterGrade()` - Convert to letter
5. `void displayReport()` - Show results

**Input Data:**
- 5 quiz scores (0-100)
- 3 exam scores (0-100)

**Calculation:**
- Final Grade = (Quiz Avg × 0.4) + (Exam Avg × 0.6)

**Letter Grades:**
- A: 90-100
- B: 80-89
- C: 70-79
- D: 60-69
- F: Below 60

---

## How to Use

### For Students

1. Read the Canvas instructions: `canvas/Hands-On-1-Functions/DAY6_HANDS_ON_FUNCTION_EXERCISE.html`
2. Follow the step-by-step guide
3. Use the starter code provided
4. Test with the provided test cases
5. Submit your .c file and screenshot

### For Instructors

1. Share Canvas instruction file with students
2. Review their submitted code using grading rubric
3. Check that all 5 functions are implemented correctly
4. Verify calculations are accurate
5. Assess code quality and documentation

---

## Expected Time

- **Completion:** 90-120 minutes
- **Testing:** 15-20 minutes
- **Total:** ~2 hours

---

## Key Concepts Tested

| Concept | Usage |
|---------|-------|
| Function declarations | Prototypes at top of file |
| Function implementation | Code after main() |
| Function calls | Called from main() |
| Parameters | Data passed to functions |
| Return types | Void vs double vs char |
| Pass-by-value | Understanding parameter copies |
| Arrays | Storing quiz and exam scores |
| Loops | Reading multiple scores |
| Conditionals | Determining letter grades |
| Weighted calculations | Final grade formula |

---

## Common Challenges

### Challenge 1: Function Prototypes
**Issue:** Undefined reference errors
**Solution:** Declare all functions before main() with prototypes

### Challenge 2: Array Handling
**Issue:** Scores not stored correctly
**Solution:** Pass arrays and count to functions; use loop index

### Challenge 3: Calculations
**Issue:** Wrong averages or final grade
**Solution:** Use double for division; cast sum to double

### Challenge 4: Letter Grade Logic
**Issue:** All students get same letter grade
**Solution:** Check if-else ranges don't overlap

### Challenge 5: Understanding pass-by-value
**Issue:** Expecting function to modify original variable
**Solution:** Recognize parameters are copies; use return values

---

## Assessment

### Grading Rubric (100 points)

- **Compilation:** 5 points
- **Functions Implemented:** 30 points (6 each)
- **Correct Calculations:** 30 points
- **Correct Letter Grade:** 15 points
- **Code Quality & Documentation:** 15 points

### Test Cases

Students should test with:
1. **All high scores** → Grade A
2. **Mixed scores** → Grade B or C
3. **Low scores** → Grade D or F

---

## Next Steps

After Day 6, students will be ready for:
- Day 7: Arrays and Advanced Loops
- Day 8: Strings and File I/O
- Final Project: Comprehensive program using all concepts

---

## Resources

- **Instructions:** See `canvas/Hands-On-1-Functions/DAY6_HANDS_ON_FUNCTION_EXERCISE.html`
- **Day 5 Slides:** Review function concepts from `/Resources/day5/slides/`
- **Day 5 Exercises:** Reference solutions in `/Resources/day5/docs/DAY5_ANSWER_KEY.md`

---

**Last Updated:** June 18, 2026
**For:** PROG2 Enrichment Course, Summer Session
