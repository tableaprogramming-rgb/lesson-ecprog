# PROG2 Day 3: Documentation Files

This folder contains all teaching and learning materials for Day 3 debugging exercises.

---

## Overview

**Day 3 Focus:** Debugging - Finding and fixing bugs in existing code

**Key Difference from Day 1-2:**
- Students are given **buggy code** instead of correct code
- Task is to **identify the bug**, explain why it's wrong, and **fix it**
- Develops critical thinking and debugging skills

---

## Files in This Folder

### For Students

**DAY3_EXERCISES.md** (Main Student Worksheet)
- Exercise context and expected behavior
- Buggy code for students to analyze
- Worksheet sections to identify and fix bugs
- Progressive difficulty levels
- **Use this:** To practice debugging and critical thinking

### For Instructors

**DAY3_ANSWER_KEY.md** (Complete Answer Guide)
- Detailed explanation of each bug
- Why the bug causes incorrect output
- Trace showing the problem
- Correct code and explanation
- Common student errors and misconceptions
- Teaching discussion points
- Grading rubrics and examples
- **Use this:** To grade work, prepare discussion, understand student thinking

**README.md** (This File)
- Overview of Day 3 materials
- How to use the resources
- Debugging pedagogy notes

---

## What Makes Day 3 Different

### Day 1-2: Code Reading
- **Given:** Correct code
- **Task:** Predict output (trace execution)
- **Skill:** Understanding code flow

### Day 3: Debugging
- **Given:** Buggy code
- **Task:** Find bug, explain why, fix it
- **Skill:** Critical thinking, problem-solving, testing

---

## All Day 3 Exercises (Complete Set)

### Exercise 1.1: Off-by-One Error (Sum 1 to 5)
- **Bug Type:** Loop boundary condition error
- **Complexity:** Easy (good introduction to debugging)
- **Context:** Program should sum 1+2+3+4+5=15, but sums 1+2+3+4=10
- **Bug:** Loop condition `i < 5` should be `i <= 5`
- **Learning:** Understanding `<` vs `<=` in loop conditions

### Exercise 1.2: Assignment vs Comparison (Check if x = 5)
- **Bug Type:** Wrong operator (= vs ==)
- **Complexity:** Easy
- **Context:** Program should check if x equals 5; x starts at 3
- **Bug:** Using `=` (assignment) instead of `==` (comparison) in if condition
- **Fix:** Change `if (x = 5)` to `if (x == 5)`
- **Learning:** Assignment operators change variables; comparison operators check equality

### Exercise 2.1: AND vs OR Operator (Range check)
- **Bug Type:** Wrong logical operator (&& vs ||)
- **Complexity:** Easy-Medium
- **Context:** Check if x is in range 0 < x < 10; x = 15
- **Bug:** Using `||` (OR) instead of `&&` (AND) for range checking
- **Fix:** Change `if (x > 0 || x < 10)` to `if (x > 0 && x < 10)`
- **Learning:** When to use AND vs OR; AND needed for "between" ranges

### Exercise 2.2: Missing Loop Increment (Print 1 to 5)
- **Bug Type:** Missing increment in for loop
- **Complexity:** Medium
- **Context:** Program should print 1 2 3 4 5, but prints 1 forever
- **Bug:** For loop missing `i++` in third part
- **Fix:** Change `for (int i = 1; i <= 5; )` to `for (int i = 1; i <= 5; i++)`
- **Learning:** All three parts of for loop are critical; missing increment causes infinite loop

### Exercise 3.1: Logic Error (Backwards Condition)
- **Bug Type:** Backwards condition logic
- **Complexity:** Medium
- **Context:** Determine if number is positive; x = 10
- **Bug:** Condition `if (x < 0)` prints "positive" (backwards logic)
- **Fix:** Change `if (x < 0)` to `if (x > 0)`
- **Learning:** Logic can be syntactically correct but semantically wrong

---

## How to Use These Materials

### In Class

**Option 1: Guided Debugging (Recommended)**
```
0. Show buggy code on projector (from presentation)
5. Ask: "What's wrong with this code?"
10. Guide students to find the bug
15. Ask: "Why does this cause wrong output?"
20. Have them trace the loop
25. Ask: "How would you fix it?"
30. Show the corrected code
35. Verify the fix works
```

**Option 2: Independent Practice**
```
- Hand out printed DAY3_EXERCISES.md
- Students work individually or in pairs
- They identify the bug and write the fix
- Check answers using DAY3_ANSWER_KEY.md
- Discuss common mistakes as a class
```

### As Homework
```
1. Assign DAY3_EXERCISES.md
2. Students complete debugging worksheets
3. Due next class
4. Go over answers together
5. Discuss debugging strategies
```

### For Self-Study
```
1. Read DAY3_EXERCISES.md (buggy code)
2. Work through the bug independently
3. Write your fix
4. Check DAY3_ANSWER_KEY.md
5. If wrong, figure out why (don't just memorize)
```

---

## Key Teaching Points

### What Students Should Learn

1. **Bugs Are Normal**
   - Professional programmers write bugs constantly
   - Debugging is a core programming skill
   - This is where the real learning happens

2. **Context Matters**
   - Always read what the program should do
   - Without context, you can't find the bug
   - "What should this sum?" is different from "What values go in the loop?"

3. **Tracing Finds Bugs**
   - Systematic tracing reveals where code breaks
   - Better than random guessing
   - Shows exactly what's going wrong

4. **Testing Your Fix**
   - Don't just suggest a fix
   - Verify it actually works
   - Trace the corrected code

### Common Misconceptions to Address

**Misconception 1:** "This code looks right, so it must be right"
- **Reality:** Code can look right but be logically wrong
- **Fix:** Trace it step-by-step to verify

**Misconception 2:** "Off-by-one just means I miscounted"
- **Reality:** Off-by-one is a logic error in boundary conditions
- **Fix:** Understand `<` vs `<=`, first vs last iteration

**Misconception 3:** "I just need to find the fix, not understand why"
- **Reality:** Understanding prevents future bugs
- **Fix:** Require explanation alongside the fix

---

## Grading Guidance

### What to Grade

| Aspect | Weight | What to Look For |
|--------|--------|-----------------|
| **Bug Identified** | 25% | Correct line number, accurate description |
| **Explanation** | 35% | Why bug causes wrong output, trace evidence |
| **Fix Provided** | 25% | Correct code change, verified to work |
| **Clarity** | 15% | Reasoning is clear, work is organized |

### Sample Rubric

- **90-100%:** Bug identified correctly, clear explanation with trace, correct fix provided, verified
- **75-89%:** Bug identified, explanation present, fix is correct but minimal verification
- **60-74%:** Bug found but explanation is unclear, fix might work but not fully verified
- **<60%:** Bug not identified OR fix doesn't work OR no reasoning shown

---

## Answer Key Guidance

**For Instructors:**
- Use DAY3_ANSWER_KEY.md to understand common student errors
- The "Teaching Notes" section has discussion ideas
- The "Grading Examples" show real student work and how to score it

**Important:** Don't just hand out the answer key. Use it to:
1. Understand what students should learn
2. Anticipate their mistakes
3. Guide them to understanding
4. Grade fairly

---

## Debugging Methodology

Teach students this systematic approach:

**Step 1: Understand the Context**
- What should this program do?
- What output is expected?

**Step 2: Run the Program Mentally**
- Trace through the code
- Track variable values
- Note where it breaks

**Step 3: Find the Bug**
- Where does the trace differ from expectation?
- What line causes the wrong behavior?

**Step 4: Understand Why**
- Why does that line cause a bug?
- What was the programmer's error?

**Step 5: Fix It**
- What should the line be instead?
- Write the corrected code

**Step 6: Verify**
- Trace the fixed code
- Confirm it produces correct output

---

## Why Debugging Matters

- **Professional Reality:** 50% of developer time is debugging, not coding
- **Learning Tool:** Debugging teaches more than writing code from scratch
- **Error Detection:** Students learn by seeing what NOT to do
- **Problem-Solving:** Develops systematic thinking skills
- **Confidence:** "I can fix broken code" is powerful skill

---

## Next Steps (Future Day 3 Exercises)

As you create more Day 3 exercises:

1. **Vary the bug types:**
   - Off-by-one errors (loop boundaries)
   - Wrong operators (<vs<=, &&vs||, =vs==)
   - Missing increments/decrements
   - Wrong variable names
   - Logic errors in conditions
   - Array indexing problems

2. **Progress in difficulty:**
   - Start: Simple, obvious bugs
   - Middle: More subtle bugs
   - Advanced: Bugs that require deep understanding

3. **Use diverse contexts:**
   - Sums and counting
   - Patterns and loops
   - Conditionals and branches
   - Nested structures
   - Real-world scenarios

4. **Encourage exploration:**
   - "What if we wanted to sum 0-5 instead?"
   - "Would this fix work if the loop started at 0?"
   - "What other bugs could this code have?"

---

## Resources for Instructors

### Debugging Best Practices:
1. **Rubber Duck Debugging** - Explain the code to someone (or something)
2. **Systematic Tracing** - Step-by-step variable tracking
3. **Hypothesis Testing** - "I think the bug is here because..."
4. **Minimal Testing** - Use simple test cases that show the bug clearly

### Teaching Tips:
- Normalize bugs ("Bugs are learning opportunities")
- Show professional code with bugs ("Happens to experts too")
- Celebrate bug discovery ("Great eye for finding issues!")
- Connect to real programming ("This is what you'll do professionally")

---

## Questions?

- **"How do I help students find bugs without just giving them the answer?"** → Use Socratic questions: "Where does the trace break? Why would that happen? What should it be instead?"
- **"Students get frustrated with buggy code"** → Normal! Frustration leads to learning. Celebrate when they find the bug.
- **"Can I use these as a quiz?"** → Yes! Debugging exercises make excellent assessments.

---

**Created for PROG2 Day 3: Debugging - Finding and Fixing Bugs**

Last Updated: [Date]
Maintainer: [Instructor Name]

Good luck with debugging! 🐛→🔧
