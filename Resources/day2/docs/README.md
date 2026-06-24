# PROG2 Day 2: Documentation Files

This folder contains all teaching and learning materials for Day 2 exercises.

---

## Files Overview

### For Students

**DAY2_EXERCISES.md** (Main Student Worksheet)
- 5 exercises on compound conditions (AND/OR operators)
- 5 exercises on while loops
- 5 exercises mixing conditions + loops
- 2 error-finding exercises
- 5 output prediction exercises
- Progressive difficulty (Level 1 → Level 3 Challenge)
- **Use this:** To practice code tracing and prediction

### For Instructors

**DAY2_ANSWER_KEY.md** (Complete Answer Guide)
- Expected outputs for all exercises
- Detailed explanations and traces
- Common student mistakes
- Teaching notes and discussion points
- Grading tips and rubric
- **Use this:** To grade work and prepare discussion

**INSTRUCTOR_GUIDE.md** (Implementation Strategy)
- How to deliver the exercises in class
- Three different implementation approaches
- Key concepts to emphasize (AND vs OR, while mechanics)
- Exercise-by-exercise facilitation tips
- Prevention of common errors
- Discussion points for class
- Timeline options and extensions
- **Use this:** To plan your teaching strategy

**README.md** (This File)
- Overview of Day 2 materials
- File descriptions
- Quick start guide for instructors
- How to use these materials

---

## Quick Start for Instructors

### Before Class:
1. Read INSTRUCTOR_GUIDE.md (10 min overview)
2. Work through DAY2_EXERCISES.md yourself (20 min)
3. Read DAY2_ANSWER_KEY.md (10 min for key answers)
4. Choose your implementation approach (Hybrid recommended)

### During Class:
1. Model Exercise 2.1 (Compound Conditions) on whiteboard
2. Have students work through Exercises 2.2-2.5 individually
3. Circulate and check for understanding
4. Collect work at end of class

### After Class:
1. Grade using DAY2_ANSWER_KEY.md rubric
2. Note common mistakes
3. Plan discussion points for next class

---

## Content Overview

### Exercise Set 1: Compound Conditions (AND/OR)
- **Exercise 2.1**: Simple AND (age >= 18 AND hasLicense)
- **Exercise 2.2**: AND with false result
- **Exercise 2.3**: Simple OR (weekend detection)
- **Exercise 2.4**: Complex AND with if-else-if
- **Exercise 2.5**: Multiple OR conditions (grade checking)

**Learning Focus:**
- Evaluate BOTH parts of AND
- Understand AND requires both TRUE
- Understand OR requires only ONE TRUE
- Apply to real-world conditions

---

### Exercise Set 2: Simple While Loops
- **Exercise 3.1**: Basic counter loop (count 1 to 3)
- **Exercise 3.2**: Accumulation loop (sum 1+2+3+4)
- **Exercise 3.3**: Decrement loop (5, 3, 1)

**Learning Focus:**
- Check condition BEFORE each iteration
- Track variable updates in loop
- Count loop iterations correctly
- Identify when loop exits

---

### Exercise Set 3: Mixed Conditions + Loops
- **Exercise 4.1**: If-else inside while loop (even/odd checker)
- **Exercise 4.2**: AND condition inside loop (range counter)

**Learning Focus:**
- Combine loops with conditions
- Apply AND/OR evaluation each iteration
- Track multiple variables
- Understand execution order

---

### Exercise Set 4: Error Finding
- **Exercise 5.1**: Wrong loop condition (< vs <=)
- **Exercise 5.2**: Compound condition logic

**Learning Focus:**
- Spot off-by-one errors
- Understand when logic is correct vs incorrect
- Explain WHY an error is problematic

---

### Exercise Set 5: Output Prediction
- **Exercises 6.1-6.5**: Predict outputs of mixed code

**Learning Focus:**
- Apply all learned concepts
- Predict before running
- Verify understanding independently

---

## Grading Guidance

### What to Grade (in order of importance):

1. **Condition Evaluation** (25%)
   - Both parts of AND/OR checked
   - Correct evaluation (TRUE/FALSE)
   - Clear work shown

2. **Loop Tracing** (25%)
   - Condition checked each iteration
   - Variable values tracked
   - Iteration count correct

3. **Completeness** (20%)
   - All exercises attempted
   - All blanks filled
   - Work shown

4. **Explanations** (20%)
   - Clear reasoning
   - References specific code
   - Shows understanding

5. **Correctness** (10%)
   - Final answers match expected outputs
   - Logic is sound

### Sample Rubric:
- **90-100%:** All complete, clear work, correct answers
- **75-89%:** Most complete, work shown, clear explanations
- **60-74%:** Some incomplete, work shown for most, explanations present
- **<60%:** Many incomplete, minimal work, missing explanations

---

## Common Student Mistakes to Watch For

### Mistake 1: AND/OR Confusion
- **Sign:** Student writes "FALSE AND TRUE = TRUE"
- **Response:** Review truth tables, use real-world examples
- **Prevention:** Have them check BOTH parts before combining

### Mistake 2: Off-by-One Loop Errors
- **Sign:** Output is "1 2 3" but should be "1 2 3 4"
- **Response:** Check the loop condition at each step
- **Prevention:** Have them write condition check for EVERY iteration

### Mistake 3: Skipping Steps
- **Sign:** Just answers, no traces shown
- **Response:** Require "show your work" for credit
- **Prevention:** Make traces mandatory for partial credit

### Mistake 4: Wrong Variable Updates
- **Sign:** Variable doesn't change properly in loop
- **Response:** Show the update statement separately
- **Prevention:** Have them circle/highlight update statements

---

## How to Use These Materials

### In Class:
```
0. Introduce Day 2 (5 min)
1. Model Exercise 2.1 together on board (10 min)
2. Students work on Exercises 2.2-2.5 (15 min) [Circulate]
3. Model Exercise 3.1 together on board (10 min)
4. Students work on Exercises 3.2-3.3 (15 min) [Circulate]
5. Discuss common mistakes (5 min)
```

### As Homework:
```
- Assign Exercise Sets 2 + 3 for homework
- Due next class
- Go over answers together
- Allow questions and discussion
```

### For Self-Study:
```
1. Read DAY2_EXERCISES.md
2. Work through each exercise carefully
3. Show all your work (traces, condition checks)
4. Compare your answers with DAY2_ANSWER_KEY.md
5. If wrong, figure out where your thinking broke down
```

---

## Connection to Day 1

**Day 1** covered:
- Simple if-else statements
- Basic for loops
- Nested loops

**Day 2** builds by adding:
- Compound conditions (AND/OR)
- While loops (instead of just for loops)
- Deeper tracing skills

**Future days** will use these as foundation for:
- Functions with conditions
- Arrays with complex loops
- Pointers and condition checking

---

## Tips for Success

### For Students:
1. ✅ **Show your work** - Every condition check, every iteration
2. ✅ **Trace carefully** - Don't skip steps
3. ✅ **Predict first** - THEN verify with code
4. ✅ **Ask questions** - About concepts, not answers
5. ✅ **Compare outputs** - Find where you went wrong

### For Instructors:
1. ✅ **Model behavior first** - Show how to trace
2. ✅ **Circulate while they work** - Catch mistakes early
3. ✅ **Ask Socratic questions** - Don't just give answers
4. ✅ **Discuss mistakes** - Make them learning opportunities
5. ✅ **Build class culture** - Where tracing and care are valued

---

## Questions?

- **Student stuck on Exercise 2.3?** → Review Exercise 2.1 first
- **Student getting loop counts wrong?** → Have them count on fingers
- **Student confused about AND/OR?** → Use real-world examples
- **Student wants to use AI?** → Remind them: "We're building understanding"

---

## File Organization

```
day2/
├── docs/
│   ├── DAY2_EXERCISES.md      ← Student worksheet
│   ├── DAY2_ANSWER_KEY.md     ← Instructor answers + rubric
│   ├── INSTRUCTOR_GUIDE.md    ← Teaching strategy
│   └── README.md              ← This file
│
└── slides/
    ├── index.html             ← Main presentation menu (coming)
    ├── exercise-2.1.html      ← Interactive presentation (coming)
    └── ...                     ← Other exercise presentations
```

---

## Updates & Maintenance

**Last Updated:** [Date when materials created]
**Maintained By:** [Your name/role]
**Version:** 1.0 (Initial Release)

### Future Improvements:
- [ ] Create interactive Reveal.js presentations
- [ ] Add video walkthroughs
- [ ] Create differentiated versions (easier/harder)
- [ ] Add more examples

---

Good luck with Day 2! Students who master these concepts will find the rest of PROG2 much more manageable. 🚀
