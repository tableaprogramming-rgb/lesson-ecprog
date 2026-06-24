# PROG2 Day 4: Advanced Debugging Exercises
## Materials Overview

---

## What's in Day 4?

**Day 4 focuses on PRACTICAL debugging skills** for students who struggled with bug tracing on the exam. These exercises build on Days 1-3 and cover real-world bug scenarios.

---

## Files in This Folder

### 1. DAY4_EXERCISES.md
**Student Worksheet** - Exercises for students to solve

**Contains:**
- 6 exercise sets with varying difficulty
- 11 total bug tracing problems
- Focus areas:
  - Logic operator bugs (||, &&, >, <, >=, <=)
  - Counter and accumulator errors
  - Loop control bugs
  - Boundary condition mistakes
  - Complex multi-condition logic
  - Variable initialization issues

**How Students Should Use It:**
1. Read the buggy code
2. Understand what it SHOULD do
3. Find which line is buggy
4. Explain WHY it's wrong
5. Write the correct version
6. Trace through the fix to verify

**Time to Complete:** ~90 minutes to 2 hours for all exercises

---

### 2. DAY4_ANSWER_KEY.md
**Instructor Guide** - Complete solutions with detailed explanations

**Contains:**
- Answers to all 11 exercises
- Step-by-step traces for each bug
- Explanation of WHY each bug occurs
- Correct fixed code
- Verification traces
- Key lessons for each category

**How to Use:**
- Review before class to prepare
- Use to grade student work
- Share selective sections with students (after they attempt)
- Reference for explaining bugs

---

## Exercise Organization

### Exercise Set 1: Logic Operator Bugs (2 exercises)
**Difficulty:** Medium
**Focus:** || vs &&, boundary conditions

- 1.1: Range checking with wrong operator
- 1.2: Even/odd filtering confusion

### Exercise Set 2: Counter & Accumulator Bugs (2 exercises)
**Difficulty:** Medium
**Focus:** Proper variable usage, initialization

- 2.1: Double counting (obvious mistake)
- 2.2: Wrong variable accumulation (subtle mistake)

### Exercise Set 3: Loop Control Bugs (2 exercises)
**Difficulty:** Medium-Hard
**Focus:** Loop structure, iteration bounds

- 3.1: Wrong increment value in loop
- 3.2: Nested loop off-by-one error

### Exercise Set 4: Boundary Condition Bugs (2 exercises)
**Difficulty:** Hard
**Focus:** < vs <=, > vs >=, sentinel values

- 4.1: Reversed operator (< vs >)
- 4.2: Sentinel value handling order

### Exercise Set 5: Complex Logic Bugs (1 exercise)
**Difficulty:** Hard
**Focus:** Multi-condition truthiness

- 5.1: AND vs OR in complex expressions (comparison exercise)

### Exercise Set 6: Variable Scope & State Bugs (1 exercise)
**Difficulty:** Medium
**Focus:** Initialization, resets, variable management

- 6.1: Forgotten variable reset between loops

---

## Suggested Classroom Usage

### Option A: Self-Paced Practice
1. Students work through exercises in order
2. They submit answers (on paper or Canvas assignment)
3. You review using the answer key
4. Provide feedback on their explanations and traces

### Option B: Guided Instruction
1. Work Exercise 1.1 together as a class
2. Emphasize the debugging process (read → predict → trace → find → fix → verify)
3. Have students work in pairs on Exercise 1.2
4. Progress to more difficult exercises
5. Allow 5-10 minutes per exercise for discussion

### Option C: Exam Preparation
1. These exercises directly address gaps from Day 3 exam
2. Assign as homework before the next exam
3. Use as review material
4. Focus on explaining HOW to find bugs, not just what the bugs are

---

## Key Skills Developed

After completing Day 4, students should be able to:

1. **Identify logic operator mistakes** (||, &&, comparison operators)
2. **Spot counter/accumulator errors** (double counting, wrong variables)
3. **Find loop boundary bugs** (off-by-one, wrong increment)
4. **Understand boundary conditions** (< vs <=, > vs >=)
5. **Trace complex conditional logic** (AND vs OR, nested conditions)
6. **Fix variable initialization issues** (forgotten resets, undefined values)
7. **Explain bugs clearly** (which line, why it's wrong, how to fix)
8. **Verify fixes work** (trace the corrected code to confirm)

---

## Debugging Process Checklist

Teach students this systematic approach:

- [ ] **READ:** Understand what the code SHOULD do
- [ ] **PREDICT:** What will it ACTUALLY do?
- [ ] **TRACE:** Follow variables through execution step-by-step
- [ ] **FIND:** Which line is the bug?
- [ ] **UNDERSTAND:** Why does that line cause the problem?
- [ ] **FIX:** Write the correct version
- [ ] **VERIFY:** Trace the fixed code to confirm it works
- [ ] **EXPLAIN:** Write your explanation clearly

---

## Common Student Mistakes

### Mistake 1: Not Tracing
Students identify the bug without tracing through the code first.

**Fix:** Require step-by-step traces with actual values. Make it mandatory for answers.

### Mistake 2: Only Finding Output
Students see wrong output but don't trace to find the buggy LINE.

**Fix:** Emphasize "which line has the error?" as the first question.

### Mistake 3: Vague Explanations
Students say "it's wrong" without explaining WHY.

**Fix:** Require explanations like:
- "Line 8 uses OR but should use AND because..."
- "The loop increments by 2 so it skips..."
- "count is never reset so it accumulates from..."

### Mistake 4: Not Verifying
Students fix code but don't trace through the fixed version.

**Fix:** Require a verification trace showing the fix produces correct output.

---

## Difficulty Progression

**Easy (Building confidence):**
- Exercise 1.1: Clear logic error
- Exercise 2.1: Obvious double counting

**Medium (Developing skills):**
- Exercise 1.2: Requires understanding modulo
- Exercise 2.2: Subtle variable mix-up
- Exercise 3.1: Loop behavior understanding

**Hard (Mastery level):**
- Exercise 3.2: Nested loop complexity
- Exercise 4.1: Operator reversal (common mistake)
- Exercise 4.2: Sentinel value logic
- Exercise 5.1: AND vs OR truth tables
- Exercise 6.1: Variable state management

---

## Grading Rubric

For each exercise, evaluate:

| Criterion | Points | Notes |
|-----------|--------|-------|
| **Identifies bug** | 2 | Which line? Is it correct? |
| **Explains why** | 2 | Is explanation clear and correct? |
| **Provides trace** | 2 | Step-by-step with values? |
| **Writes fix** | 2 | Is the fix syntactically correct? |
| **Verifies fix** | 1 | Does trace show fix works? |
| **TOTAL** | 9 | Per exercise (adjust as needed) |

**Example for Exercise 1.1:**
```
Buggy line: 8 ✓ (2 pts)
Explanation: Uses OR instead of AND, so everything gets counted except... ✓ (2 pts)
Trace: i=3: (3 > 5 || 3 < 15) = F || T = T ✓ (2 pts)
Fix: if (i >= 5 && i <= 15) ✓ (2 pts)
Verify: i=5: (5 >= 5 && 5 <= 15) = T && T = T ✓ (1 pt)
TOTAL: 9/9
```

---

## Tips for Instructors

1. **Emphasize process over answer**
   - Correct answer without good explanation = partial credit
   - Good process with minor errors = most credit

2. **Use bugs as teaching moments**
   - "This bug appears in real code"
   - "Here's why professional developers use code review"
   - "This is why we test edge cases"

3. **Connect to previous exams**
   - "This is exactly the type of bug that appeared on the exam"
   - Help students see patterns in bugs

4. **Pair programming opportunities**
   - Have strong students help struggling ones trace
   - Peer review of bug analysis

5. **Real-world context**
   - Show examples from actual open-source bugs
   - Emphasize that everyone writes these bugs
   - Debugging is a KEY SKILL in programming

---

## Answers To Common Questions

**Q: How long should this take?**
A: 1.5 to 2 hours for all exercises. Can be split across two sessions.

**Q: Can I give hints?**
A: Yes! Guide them with "Have you traced i=5?" rather than "it should be &&"

**Q: What if students are stuck?**
A: Have them trace MORE carefully, not read the answer. Usually tracing reveals the bug.

**Q: Should I teach debugging tools?**
A: After mastering manual tracing, then introduce debuggers. Manual first!

**Q: How do I know if they really understand?**
A: Ask them to find bugs in code YOU write. If they can, they understand.

---

## Next Steps After Day 4

1. **Quiz or Exam** with similar bug-tracing questions
2. **Code Review Exercise** where students critique each other's code
3. **Intentional Bugs** - students write buggy code, peers find bugs
4. **Real Programs** - have students debug their own assignment code

---

## Files Provided

```
day4/
├── docs/
│   ├── DAY4_EXERCISES.md      ← Student worksheet (6 sets, 11 exercises)
│   ├── DAY4_ANSWER_KEY.md     ← Instructor guide (detailed solutions)
│   └── README.md              ← This file
└── slides/                    ← (Will be added for interactive lessons)
```

---

## Questions or Issues?

If you need:
- **More exercises:** See Day 3 format for how to create similar ones
- **Difficulty adjustment:** Comment to adjust exercises easier/harder
- **Specific bug types:** Reach out for additional practice problems

---

**Good luck with Day 4! Remember: Debugging is a SKILL that improves with PRACTICE.** 💪

---

*Last Updated: June 16, 2026*
*Designed for: PROG2 Enrichment Course for Computer Programming (Summer)*
