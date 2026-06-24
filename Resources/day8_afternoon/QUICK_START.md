# DAY 8 AFTERNOON: Debugging 2D Arrays - Quick Start Guide

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026 (Afternoon Session)  
**Duration:** 50 minutes  
**Topic:** Identifying and Fixing Bugs in 2D Array Code

---

## What You'll Learn

This **debugging-focused** afternoon session complements the morning's exercises by teaching you to:
- **Identify** common bugs in 2D array code
- **Understand** why bugs occur
- **Fix** bugs systematically
- **Prevent** similar mistakes in future code

---

## Session Overview

### Format
- **Morning (9:00-10:00):** Learn 2D array concepts and basics
- **Afternoon (2:00-3:00):** Find and fix bugs in provided code

### What's Different
- **Morning:** "How do I write this?"
- **Afternoon:** "What's wrong with this?"

This teaches you real debugging skills used by professional programmers!

---

## 8 Debugging Exercises + 1 Bonus Challenge

### Exercise Difficulty Levels

| # | Title | Difficulty | Bug Type |
|---|-------|-----------|----------|
| D1 | Off-by-One Error | ⭐ Easy | Loop bounds |
| D2 | Wrong Function Parameter | ⭐ Easy | Array dimensions |
| D3 | Uninitialized Variable | ⭐⭐ Medium | Variable init |
| D4 | Wrong Loop Nesting | ⭐⭐ Medium | Logic/efficiency |
| D5 | Wrong Index Usage | ⭐⭐ Medium | Index order |
| D6 | Type Conversion Issue | ⭐⭐ Medium | Integer vs double |
| D7 | Logic Error in Algorithm | ⭐⭐⭐ Hard | Algorithm logic |
| D8 | Complex Nested Loop Bug | ⭐⭐⭐ Hard | Multiple bugs |
| Bonus | Find All 5 Bugs | ⭐⭐⭐⭐ Challenge | Combination |

---

## How to Approach Each Exercise

### Step 1: Read the Buggy Code
- Don't run it yet
- Look for obvious problems
- Ask: "What is this code trying to do?"

### Step 2: Identify Bugs
- Use the questions to guide your analysis
- Try to find ALL bugs, not just one
- Check: array dimensions, loop bounds, variables

### Step 3: Understand Why It's Wrong
- Predict what happens when code runs
- Will it crash? Produce wrong output? Be inefficient?
- Trace through with a small example

### Step 4: Fix It
- Change the minimum needed to fix bugs
- Don't rewrite the whole thing
- Keep the original logic/structure

### Step 5: Verify
- Compile the fixed code
- Run with the expected input
- Compare output with expected result

---

## Bug Categories You'll Learn

### 1. **Off-by-One Errors** (Exercises D1, D8)
```c
// WRONG:
for (int i = 0; i <= 3; i++)  // Goes 0,1,2,3 - too many!

// CORRECT:
for (int i = 0; i < 3; i++)   // Goes 0,1,2 - just right
```

### 2. **Uninitialized Variables** (Exercise D3)
```c
// WRONG:
int sum;        // What's the initial value? Unknown!
sum += 5;       // Adding to garbage

// CORRECT:
int sum = 0;    // Start at 0
sum += 5;       // Now it's 5
```

### 3. **Wrong Array Dimensions** (Exercise D2)
```c
// WRONG:
void func(int matrix[3]) {  // Missing column count!

// CORRECT:
void func(int matrix[3][4]) {  // Both dimensions specified
```

### 4. **Type Issues** (Exercise D6)
```c
// WRONG:
int average = sum / 6;    // Integer division - loses decimals!

// CORRECT:
double average = sum / 6.0;  // Floating-point division
```

### 5. **Index Confusion** (Exercise D5)
```c
// WRONG:
matrix[j][i] = value;  // Transposed!

// CORRECT:
matrix[i][j] = value;  // Correct order
```

### 6. **Logic Errors** (Exercise D7)
```c
// WRONG:
if (found) { found = 1; }  // Found it
else { found = 0; }        // Reset it! Bug!

// CORRECT:
if (found) { found = 1; }  // Found it (don't reset)
// No else clause
```

---

## Debugging Tools You Can Use

### 1. **Compile and Read Error Messages**
```bash
gcc program.c -o program
# Look for: "warning:", "error:", "undeclared identifier"
```

### 2. **Add Print Statements**
```c
printf("Debug: i=%d, j=%d, value=%d\n", i, j, matrix[i][j]);
```

### 3. **Trace Manually**
- Write out loop iterations on paper
- Track variable values
- Identify where things go wrong

### 4. **Test Small Cases**
- Use 2×2 or 3×3 arrays
- Easier to trace by hand
- Fewer iterations to verify

### 5. **Check Array Bounds**
```c
// Question: Is this valid?
matrix[3][4]  // For a 3×3 array? NO - out of bounds!
matrix[2][2]  // For a 3×3 array? YES - last element
```

---

## Session Timeline

### Minute 0-5: Introduction
- Overview of debugging
- Why this is important
- How the exercises work

### Minute 5-40: Guided Practice
- Work through exercises D1-D8 together
- Start with instructor leading
- Gradually transition to student work
- Discuss solutions after each exercise

### Minute 40-50: Challenge & Wrap-up
- Students attempt bonus challenge
- Group discussion of common bugs found
- Preview what happens next

---

## Your Debugging Checklist

Before you say "This is fixed!":

- [ ] Code compiles without errors
- [ ] Code runs without crashing
- [ ] Output matches expected result
- [ ] Understood ALL bugs (not just one)
- [ ] Know WHY it was a bug
- [ ] Know HOW to prevent it next time

---

## Common Debugging Mistakes

### ❌ "The code looks right to me"
→ **Try:** Compile it and read error messages carefully!

### ❌ "I'll just rewrite the whole thing"
→ **Try:** Find minimum changes needed; understand the bug

### ❌ "It works on my computer"
→ **Try:** Test with different inputs; find the edge case

### ❌ "I don't understand why it's wrong"
→ **Try:** Trace through with pen/paper; print debug values

### ❌ "Good enough; it mostly works"
→ **Try:** Fix bugs properly; 99% correct is still wrong

---

## Real-World Context

**Why Learn Debugging?**

Professional developers spend **50-70% of time debugging**, not writing new code!

**Skills You're Learning:**
- Problem-solving
- Attention to detail
- Systematic thinking
- Patience and persistence

These are the MOST valuable skills in programming!

---

## Key Terminology

| Term | Meaning |
|------|---------|
| **Bug** | An error in code that causes wrong behavior |
| **Crash** | Program terminates unexpectedly |
| **Out of bounds** | Accessing array index outside valid range |
| **Off-by-one** | Loop goes one iteration too many/few |
| **Garbage value** | Random uninitialized value in memory |
| **Logic error** | Code runs but produces wrong result |
| **Runtime error** | Error that occurs when program runs |
| **Compilation error** | Error caught by compiler (won't run) |

---

## Success Tips

### 1. **Read ALL the questions**
Each exercise has questions to guide your bug hunt

### 2. **Don't skip uninitialized variables**
This is the #1 source of mysterious bugs

### 3. **Check loop bounds FIRST**
Off-by-one errors are very common

### 4. **Ask "What should this do?"**
Understanding intent makes bugs obvious

### 5. **Use your compiler/runtime errors**
They're telling you exactly what's wrong!

### 6. **Work incrementally**
Fix one bug at a time, test after each fix

### 7. **Celebrate when you find a bug!**
Each bug found is a skill gained

---

## File Structure

```
day8_afternoon/
├── docs/
│   ├── DEBUGGING_EXERCISES.md    ← 8+1 exercises with bugs
│   ├── DEBUGGING_ANSWER_KEY.md   ← Solutions & explanations
│   └── README.md                  ← Documentation
├── slides/
│   ├── index.html                ← Presentation (coming soon)
│   └── README.md
└── QUICK_START.md               ← This file
```

---

## Getting Started RIGHT NOW

### For Students

1. **Open:** `docs/DEBUGGING_EXERCISES.md`
2. **Start with:** Exercise D1 (easiest)
3. **For each exercise:**
   - Read the buggy code
   - Answer the questions
   - Write fixed code
   - Verify it compiles and runs
4. **Check answers:** `docs/DEBUGGING_ANSWER_KEY.md`
5. **Next exercise:** Move to D2

### For Instructors

1. **Read:** `docs/DEBUGGING_ANSWER_KEY.md` (understand all solutions)
2. **Prepare:** Pick 3-4 exercises to do together live
3. **Setup:** Have IDE ready to compile and run
4. **Lead:** Walk through first exercise with class
5. **Support:** Have students attempt next exercises
6. **Discuss:** Go over solutions and lessons learned

---

## Submission Checklist

- [ ] All 8 debugging exercises completed
- [ ] Bugs correctly identified in each
- [ ] Fixed code compiles without errors
- [ ] Output matches expected results
- [ ] Code is readable with comments
- [ ] Bonus challenge attempted (optional)
- [ ] All files pushed to GitHub

---

## After the Afternoon Session

### What You've Learned
✅ Common bugs and how to identify them
✅ How to systematically debug code
✅ Prevention techniques for future projects

### What's Next
→ Day 9: Advanced 2D array operations
→ Use debugging skills on more complex problems
→ Apply to other programming projects

---

## Helpful Reminders

> "Every good programmer has written buggy code. The best programmers are good at FINDING and FIXING bugs, not avoiding them."

> "If your code doesn't compile, fix the compiler errors first."

> "If your code compiles but doesn't work, add print statements to see what's happening."

> "When all else fails, trace through your code by hand on paper."

---

## Debugging Mindset

| Beginner | Expert |
|----------|--------|
| Hopes code will work | Expects bugs; finds them quickly |
| Frustrated by errors | Sees errors as learning opportunities |
| Searches randomly for problems | Systematically narrows down the issue |
| Rewrites everything | Fixes minimum needed |
| Gives up when stuck | Tries different approaches |

**Your goal:** Think like an expert!

---

## Questions During Session

### "Where's the bug?"
→ Check: Array bounds, loop conditions, variable initialization, type mismatches

### "Why is this a bug?"
→ Think: What does the code do? What should it do? What's the difference?

### "How do I fix it?"
→ Make: Minimum change needed to make it work

### "How do I prevent this?"
→ Remember: This pattern; avoid it next time

---

## One More Thing...

### The Most Important Debugging Skill

**Read your compiler/runtime error messages.**

They're not angry at you. They're telling you exactly what's wrong!

```
Error: array subscript out of bounds
       ^ Your array access is invalid

Error: use of uninitialized variable 'sum'
       ^ You used sum before setting its value

Error: too many arguments to function 'sumMatrix'
       ^ You passed wrong number of parameters
```

**Listen to your error messages!** They're your friend.

---

**Ready to Find Some Bugs?** 🐛  
Open `docs/DEBUGGING_EXERCISES.md` and start with Exercise D1!

---

**Last Updated:** June 23, 2026  
**Duration:** 50-minute afternoon session  
**Difficulty:** Medium (builds on morning content)
