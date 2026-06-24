# DAY 8 AFTERNOON: Debugging 2D Arrays - Documentation

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026 (Afternoon Session)  
**Focus:** Finding and Fixing Bugs in 2D Array Code  
**Duration:** 50 minutes

---

## Overview

The afternoon session continues from the morning by focusing on **debugging skills**. Rather than learning to write 2D array code, students learn to **identify and fix bugs** in existing code.

### Learning Outcomes

By the end of this session, students will:
1. Recognize 8 common types of bugs in 2D array code
2. Understand why each bug occurs
3. Fix bugs systematically
4. Prevent similar bugs in their own code

---

## Files in This Directory

### For Students

| File | Purpose | Size | Time |
|------|---------|------|------|
| **DEBUGGING_EXERCISES.md** | 8 debugging exercises + 1 bonus | 20 KB | 45-60 min |
| **README.md** | This file - overview | 8 KB | 5 min |

### For Instructors

| File | Purpose | Size | Time |
|------|---------|------|------|
| **DEBUGGING_ANSWER_KEY.md** | Solutions with explanations | 22 KB | 30-40 min |
| **README.md** | This file | 8 KB | 5 min |

---

## Exercise Breakdown

### Exercise D1: Off-by-One Error in Loops
**Skills:** Loop bounds, array indexing, out-of-bounds access
**Bugs:** 3 bugs (loop conditions and initialization)
**Type:** Easy ⭐

**What Students Learn:**
- Why `<=` can be wrong instead of `<`
- How uninitialized max affects finding maximum
- Valid index range for an array

### Exercise D2: Wrong Function Parameter
**Skills:** Function parameters, array dimensions
**Bugs:** 1 bug (missing [4] in parameter)
**Type:** Easy ⭐

**What Students Learn:**
- Compiler needs column count for offset calculation
- Why both dimensions matter
- Function parameter syntax for 2D arrays

### Exercise D3: Uninitialized Variable
**Skills:** Variable initialization, accumulation pattern
**Bugs:** 1 bug (int sum not initialized)
**Type:** Medium ⭐⭐

**What Students Learn:**
- What "garbage value" means
- Why initialization is critical
- Non-deterministic behavior

### Exercise D4: Wrong Loop Nesting
**Skills:** Loop efficiency, logic optimization
**Bugs:** 1 bug (inefficient but not crash)
**Type:** Medium ⭐⭐

**What Students Learn:**
- Not all bugs cause crashes
- Logic errors are harder to spot
- Why understanding intent matters

### Exercise D5: Wrong Index Usage
**Skills:** Array indexing, index order convention
**Bugs:** 1 bug (swapped indices)
**Type:** Medium ⭐⭐

**What Students Learn:**
- Index order matters ([i][j] vs [j][i])
- Consistent conventions prevent bugs
- Out-of-bounds access

### Exercise D6: Type Conversion Issue
**Skills:** Type casting, division operators
**Bugs:** 1 bug (integer division)
**Type:** Medium ⭐⭐

**What Students Learn:**
- Integer vs floating-point division
- When to use casting
- Losing precision with integers

### Exercise D7: Logic Error in Algorithm
**Skills:** Algorithm correctness, conditional logic
**Bugs:** 1 bug (resetting flag in else clause)
**Type:** Hard ⭐⭐⭐

**What Students Learn:**
- Logic errors don't always crash
- Flags need careful handling
- Why understanding algorithm matters

### Exercise D8: Complex Nested Loop Bug
**Skills:** Multiple concepts combined
**Bugs:** 1 bug (off-by-one with diagonal access)
**Type:** Hard ⭐⭐⭐

**What Students Learn:**
- Bugs can hide in diagonal/special access patterns
- Out-of-bounds detection
- Combination of earlier concepts

### Bonus Challenge: Find All 5 Bugs
**Skills:** Comprehensive debugging
**Bugs:** 5 bugs (combination exercise)
**Type:** Challenge ⭐⭐⭐⭐

**What Students Learn:**
- Multiple bugs in one program
- Interdependencies between bugs
- Systematic debugging approach

---

## Bug Categories Covered

| Category | Exercise | Concept |
|----------|----------|---------|
| **Loop Bounds** | D1, D8 | Off-by-one errors |
| **Initialization** | D3, D2 | Variable setup |
| **Parameters** | D2 | Function declarations |
| **Indexing** | D5, D8 | Array access |
| **Type Issues** | D6 | Casting and division |
| **Logic** | D4, D7 | Algorithm correctness |
| **Combination** | Bonus | Multiple bugs together |

---

## How to Use These Materials

### For Individual Study

1. **Start with D1** (easiest)
2. Read the buggy code carefully
3. Answer the multiple choice questions
4. Identify all bugs
5. Write corrected code
6. Check against answer key
7. Move to next exercise

### For Group/Class Setting

1. **Instructor presents:** Overview of debugging
2. **Guided example:** Work through D1-D2 together
3. **Pair programming:** Students work in pairs on D3-D5
4. **Individual work:** Students tackle D6-D8
5. **Discussion:** Review solutions and lessons learned
6. **Challenge:** Attempt bonus exercise

### Time Allocation (50-minute session)

- **0-5 min:** Introduction and context
- **5-20 min:** Guided work on D1-D2 with class
- **20-40 min:** Students work on D3-D8 (instructor circulates)
- **40-50 min:** Discuss solutions, attempt bonus, wrap-up

---

## Debugging Strategies Taught

### Strategy 1: Read Code Carefully
- Understand what it's trying to do
- Look for obvious problems
- Don't assume it's correct

### Strategy 2: Ask Questions
- What's the intent of this code?
- What could go wrong?
- What are the edge cases?

### Strategy 3: Trace Execution
- Follow loop iterations manually
- Track variable values
- Identify where things go wrong

### Strategy 4: Check Fundamentals
- Array bounds
- Variable initialization
- Loop conditions
- Type conversions

### Strategy 5: Fix Minimally
- Don't rewrite entire program
- Find minimum change needed
- Keep original logic/structure

### Strategy 6: Verify Thoroughly
- Does it compile?
- Does it run without crash?
- Does output match expected?

---

## Common Patterns

### Pattern: Off-by-One
```c
// WRONG: for (int i = 0; i <= 3; i++)  // Goes 0,1,2,3
// RIGHT: for (int i = 0; i < 3; i++)   // Goes 0,1,2
```
**Prevention:** Remember: `i < SIZE` not `i <= SIZE`

### Pattern: Uninitialized Variable
```c
// WRONG: int sum; sum += value;
// RIGHT: int sum = 0; sum += value;
```
**Prevention:** Always initialize before use

### Pattern: Integer Division
```c
// WRONG: int avg = sum / 6;
// RIGHT: double avg = sum / 6.0;
```
**Prevention:** Use `double` for division when needed

### Pattern: Wrong Parameter
```c
// WRONG: void func(int matrix[3]) // 2D but missing column
// RIGHT: void func(int matrix[3][4]) // Both dimensions
```
**Prevention:** Always specify both array dimensions

### Pattern: Logic Error
```c
// WRONG: if (found) {found=1;} else {found=0;}
// RIGHT: if (found) {found=1;} // No else!
```
**Prevention:** Think carefully about what should happen

---

## Assessment Rubric

### Per-Exercise Grading

**Bug Identification (40%):**
- Identified all bugs correctly
- Understood why each is a bug
- Can explain the impact

**Corrected Code (40%):**
- Code compiles without errors
- Produces correct output
- Uses minimal changes

**Explanation (20%):**
- Explained each bug clearly
- Showed understanding of issue
- Discussed prevention

### Overall Grade

| Exercises Correct | Grade |
|-------------------|-------|
| 8/8 | A+ (95-100%) |
| 7/8 | A (90-94%) |
| 6/8 | B (80-89%) |
| 5/8 | C (70-79%) |
| 4/8 | D (60-69%) |
| <4/8 | F (<60%) |

**Bonus:** +5% if bonus challenge completed and correct

---

## Teaching Tips

### Before Class
- [ ] Work through all 8 exercises yourself
- [ ] Know exactly what each bug is
- [ ] Prepare compilation environment
- [ ] Have answers ready to share

### During Class
- [ ] Start with simple examples (D1-D2)
- [ ] Gradually increase difficulty
- [ ] Encourage group discussion
- [ ] Don't give away answers too quickly
- [ ] Let students struggle a bit (builds learning!)

### After Class
- [ ] Review common mistakes
- [ ] Discuss prevention strategies
- [ ] Emphasize importance of debugging
- [ ] Connect to future projects

### Discussion Topics

1. "Which bug was hardest to spot and why?"
2. "How would you have prevented this bug?"
3. "Have you written similar bugs in your own code?"
4. "What's your debugging strategy when stuck?"
5. "Why is debugging an important skill?"

---

## Complementary Materials

### Morning Session (Required Prerequisite)
- DAY8 morning exercises (declarations, initialization, access)
- Interactive presentations on 2D arrays
- Understanding basic concepts needed

### Related Topics
- Day 9: Advanced 2D array operations
- Strings: Same debugging issues apply
- Pointers: More complex debugging scenarios
- General testing and QA skills

---

## Key Takeaways

### What to Remember

✅ **Off-by-one errors** are the most common bug  
✅ **Always initialize** variables before using them  
✅ **Check array bounds** - valid indices 0 to N-1  
✅ **Function parameters** need full dimensions  
✅ **Watch types** - integer vs floating-point  
✅ **Understand intent** - know what code should do  
✅ **Trace manually** - follow code step-by-step  
✅ **Use error messages** - they're helpful!  

### What to Avoid

❌ Assuming code is correct without testing  
❌ Ignoring compiler/runtime error messages  
❌ Using `<=` in array loops  
❌ Leaving variables uninitialized  
❌ Integer division for non-integer results  
❌ Incomplete function parameters  
❌ Complex logic without clear intent  
❌ Not checking edge cases  

---

## Why This Matters in Real World

### Professional Programming Reality

- **50-70%** of coding time is debugging
- **Most expensive** part of projects
- **Critical skill** for employment
- **Separates** good from great developers

### What Employers Look For

✅ Can find and fix bugs quickly  
✅ Writes code others can debug easily  
✅ Prevents bugs rather than finding them later  
✅ Uses systematic approach to problem-solving  
✅ Learns from mistakes and prevents repeats  

---

## Resources for Further Learning

### In This Course
- Morning 2D array lessons (prerequisite)
- Day 9 advanced operations
- Future string and pointer lessons

### Online
- GeeksforGeeks debugging articles
- Stack Overflow (when stuck)
- Compiler/IDE documentation

### Books
- *The Pragmatic Programmer* - Great debugging chapter
- *Code Complete* - Has sections on debugging
- *Debugging* by David Agans

---

## Quick Links

- **Quick Start Guide:** ../QUICK_START.md
- **Main Exercises:** DEBUGGING_EXERCISES.md
- **Answer Key:** DEBUGGING_ANSWER_KEY.md
- **Morning Materials:** ../day8/docs/
- **Slides:** ../slides/ (in development)

---

## FAQ

### Q: Will the bonus challenge count for the grade?
A: It's optional but gives +5% bonus. Highly recommended to attempt!

### Q: What if I can't find all the bugs?
A: That's OK! You'll learn by checking the answer key. Keep practicing.

### Q: Can I work with a partner?
A: Yes! Pair programming can be helpful for debugging. Both should understand the solution.

### Q: Do I need to memorize all these bugs?
A: No, but you should recognize patterns when you see them. Experience builds recognition.

### Q: What if I disagree with the answer?
A: Test your solution! If it compiles, runs, and produces correct output, it's valid.

---

## Feedback Welcome

If you find:
- **Unclear exercises** - Let me know
- **Bugs in the solutions** - Let me know!
- **Better examples** - Suggest them
- **Missing concepts** - Request them

This material gets better with feedback!

---

**Last Updated:** June 23, 2026  
**Maintainer:** [Instructor Name]  
**Duration:** 50-minute afternoon session  
**Prerequisite:** Morning 2D arrays session (Day 8)
