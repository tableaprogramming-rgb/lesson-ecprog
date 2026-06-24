# PROG2 Day 7: Single-Dimensional Arrays - Documentation

## What's In This Folder

This folder contains a complete set of exercises designed to teach students **single-dimensional array concepts** through careful code reading and tracing.

---

## Files Overview

### 1. **DAY7_EXERCISES.md** (Student-Facing)
The main exercise document for students.

**Contains:**
- Exercise 7.1: Array Declaration & Initialization (3 problems)
- Exercise 7.2: Array Indexing (3 problems)
- Exercise 7.3: Looping Through Arrays (3 problems)
- Exercise 7.4: Array Manipulation (3 problems)
- Exercise 7.5: Searching & Analysis (3 problems)

**Topics Covered:**
- Array declaration syntax
- Array initialization with values
- Index-based element access
- For loops with array iteration
- Modifying array values
- Finding elements (searching)
- Calculating totals (summing/averaging)
- Finding min/max values

**How to Use:**
- Print and distribute to students
- Or share digitally
- Have them work through in class or as homework
- Requires hand-written traces/explanations

---

### 2. **DAY7_ANSWER_KEY.md** (Instructor-Only)
Complete answers and explanations for all exercises.

**Contains:**
- Detailed solution for each exercise
- Expected output with variable traces
- Common student mistakes
- Teaching notes for each section
- Discussion points

**How to Use:**
- Reference while grading
- Use discussion points in class
- Check student understanding against expected reasoning
- Prepare for common misconceptions

---

### 3. **INSTRUCTOR_GUIDE.md** (Instructor-Only)
Complete implementation guide with pedagogy and strategy.

**Contains:**
- Opening speech to set class culture
- Three implementation options (in-class, homework, hybrid)
- Exercise-by-exercise facilitation tips
- Grading rubric and framework
- How to prevent cheating
- Strategies for struggling students
- Timeline options

**How to Use:**
- Read before class
- Use facilitation tips while circulating
- Reference grading rubric when evaluating
- Share implementation strategy with yourself

---

## Quick Start for Instructors

### Preparation (30 minutes before class)
1. Read INSTRUCTOR_GUIDE.md (especially "Opening Speech")
2. Review DAY7_ANSWER_KEY.md to know what to expect
3. Print DAY7_EXERCISES.md (or share digitally)
4. Prepare whiteboard/screen for modeling Exercise 7.1

### During Class (50 minutes)
1. **Opening (5 min):** Read the opening speech from INSTRUCTOR_GUIDE.md
2. **Modeling (10 min):** Work through Exercise 7.1 together on whiteboard
3. **Guided Practice (20 min):** Students do Exercises 7.2-7.3 while you circulate
4. **Independent Work (10 min):** Students do Exercises 7.4-7.5
5. **Wrap-up (5 min):** Collect, discuss one common mistake

### After Class
- Review student work using DAY7_ANSWER_KEY.md
- Note patterns of misunderstanding
- Identify 1-2 errors to address next class
- Decide whether to assign remaining exercises as homework

---

## What Students Need

**Materials:**
- Printed copy of DAY7_EXERCISES.md (or digital access)
- Pen and paper (for traces and explanations)
- Dev C or similar C compiler (only after predictions are made)

**Mindset:**
- Willingness to slow down and think carefully
- Understanding that this isn't about speed, it's about understanding
- Acceptance that not knowing is okay - that's why they're here to learn

---

## Learning Outcomes

By completing Day 7 exercises, students will:

✅ **Understand:**
- How to declare arrays
- How array indexing works (0-based)
- How to loop through arrays
- How to modify array values
- How to search and analyze array data

✅ **Be Able to:**
- Trace code involving array declarations
- Predict program output for array programs
- Track variable state as arrays are modified
- Work with arrays in loops
- Show their reasoning clearly

✅ **Believe:**
- That understanding arrays is foundational
- That tracing is a valuable skill
- That asking themselves (not AI) is how they learn

---

## Exercise Difficulty Progression

### Exercise Set 1 (Declaration & Initialization) - Level Progression
- 7.1.1: Simple array declaration (Level 1) ✓ Warm-up
- 7.1.2: Array initialization with values (Level 1) ↑ Same difficulty
- 7.1.3: Multiple arrays (Level 2) ↑ More complex

### Exercise Set 2 (Indexing) - Variety
- 7.2.1: Single element access
- 7.2.2: Multiple element access
- 7.2.3: Index variable usage

### Exercise Set 3 (Looping) - Increasing Complexity
- 7.3.1: Simple for loop through array
- 7.3.2: Loop with conditions
- 7.3.3: Nested loops with arrays

### Exercise Set 4 (Manipulation) - Building Skills
- 7.4.1: Modify single element
- 7.4.2: Modify multiple elements
- 7.4.3: Building array with assignments

### Exercise Set 5 (Searching/Analysis) - Problem Solving
- 7.5.1: Finding an element
- 7.5.2: Calculating sum/average
- 7.5.3: Finding min/max

---

## Timing Guidance

### If using as 50-minute in-class activity:
- Introduction & setup: 5 min
- Model Exercise 7.1: 10 min
- Guided practice (7.2-7.3): 15 min
- Independent work (7.4-7.5): 15 min
- Wrap-up: 5 min

### If using as homework:
- Exercise Set 1: 20-30 minutes
- Exercise Set 2: 20-30 minutes
- Exercise Set 3: 20-30 minutes
- Exercise Set 4: 20-30 minutes
- Exercise Set 5: 25-35 minutes
- **Total:** 105-155 minutes (for thorough work)

### If using as multiple sessions:
- Session 1: Exercise Set 1-2 (in-class)
- Session 2: Exercise Set 3-4 (in-class or homework)
- Session 3: Exercise Set 5 (homework)
- Session 4: Challenge problems (quiz or advanced)

---

## Customization Ideas

### Make It More Challenging:
- Vary array sizes
- Add more complex search conditions
- Use 2D arrays (preview of next lesson)
- Create custom exercises using same format

### Make It More Accessible:
- Provide partially completed traces
- Give code segments in smaller chunks
- Pair students for collaborative tracing
- Have students explain aloud before writing

### Make It More Relevant:
- Use context students care about (grades, sports scores, etc.)
- Modify examples to match student interests
- Have students write code for each other

---

## Notes for Success

1. **The traces matter more than the answers**
   - A student with wrong answer but clear thinking ≠ failure
   - A student with right answer but no work = potential plagiarism

2. **Normalize mistakes**
   - Getting traces "wrong" is learning, not failure
   - Use mistakes as teaching moments
   - Celebrate effort and clarity

3. **This sets the tone**
   - How you teach Day 7 defines how arrays are understood
   - If you insist on understanding, students will provide it
   - If you accept shortcuts, shortcuts spread

4. **Consistency matters**
   - Keep the "no internet, no AI" boundary firm
   - Every exercise should require explanation
   - Recognize and reward clear thinking

---

## Visual Reference: Array Concepts

### Array Declaration
```c
int numbers[5];      // Declare array of 5 integers
int arr[3] = {1,2,3}; // Declare and initialize
```

### Array Indexing (0-based)
```
Index:  0    1    2    3    4
Value: [10] [20] [30] [40] [50]

Access: numbers[0] = 10
        numbers[2] = 30
        numbers[4] = 50
```

### Array in Loop
```c
for(int i = 0; i < 5; i++) {
    printf("%d\n", numbers[i]);  // Access each element
}
// Output: 10 20 30 40 50 (each on new line)
```

---

## Questions or Feedback?

If you adapt these exercises or find issues:
- Test them yourself first
- Note what works and what doesn't
- Consider how your students respond
- Iterate for next semester

This is a starting point - make it your own! 🚀

---

**Created for PROG2: Computer Programming 2**
**Lesson: Single-Dimensional Arrays (Lesson 3)**
**Goal: Develop deep array understanding through careful code reading**
