# PROG2 Day 5: Functions Lesson Materials
## Void Functions, Value-Returning Functions, and Parameter Passing

---

## What's in Day 5?

**Day 5 focuses on MASTERING FUNCTIONS** - a critical programming skill. These exercises build on Days 1-4 and cover practical function concepts that students need for all future programming.

---

## Files in This Folder

### 1. DAY5_EXERCISES.md
**Student Worksheet** - Exercises for students to solve

**Contains:**
- 6 exercise sets with 30+ total problems
- Focus areas:
  - Void functions (calling, execution, multiple calls)
  - Value-returning functions (return values, type matching)
  - Parameters and arguments (terminology, pass-by-value)
  - Combined concepts (multiple parameters and returns)
  - Common mistakes (missing returns, type mismatches)
  - Function design practice (write functions from scratch)

**How Students Should Use It:**
1. Read the function code and expected output
2. Trace through the code step-by-step
3. Identify what the function does
4. Answer questions about execution
5. Fix buggy code
6. Write functions to solve problems

**Time to Complete:** ~120 minutes to 2 hours for all exercises

---

### 2. DAY5_ANSWER_KEY.md
**Instructor Guide** - Complete solutions with detailed explanations

**Contains:**
- Answers to all 30+ exercises
- Step-by-step execution traces
- Explanation of function behavior
- Correct fixed code
- Verification traces showing variable states
- Key lessons for each exercise set

**How to Use:**
- Review before class to prepare
- Use to grade student work
- Share selective sections with students (after they attempt)
- Reference for explaining function concepts

---

## Exercise Organization

### Exercise Set 1: Understanding Void Functions (3 exercises)
**Difficulty:** Easy-Medium
**Focus:** Function calls, execution order, no return values

- 1.1: Calling void functions correctly (missing parentheses bug)
- 1.2: Multiple void function calls (tracing execution)
- 1.3: Void functions with parameters (understanding greet(name))

### Exercise Set 2: Understanding Value-Returning Functions (3 exercises)
**Difficulty:** Medium
**Focus:** Return values, type matching, computation

- 2.1: Simple return values (understanding how return replaces call)
- 2.2: Type mismatch in return (integer division)
- 2.3: Conditional returns (different return values based on logic)

### Exercise Set 3: Parameters and Arguments (3 exercises)
**Difficulty:** Medium
**Focus:** Terminology, pass-by-value, parameter matching

- 3.1: Parameters vs arguments (correct terminology)
- 3.2: Pass-by-value semantics (why changes in function don't affect original)
- 3.3: Multiple parameters (parameter order matters)

### Exercise Set 4: Combining Concepts (2 exercises)
**Difficulty:** Medium-Hard
**Focus:** Functions with both parameters and returns

- 4.1: Parameters AND return values (multi-step tracing)
- 4.2: Multiple parameters with computation (realistic function usage)

### Exercise Set 5: Common Mistakes (3 exercises)
**Difficulty:** Hard
**Focus:** Finding and fixing real bugs in functions

- 5.1: Missing return statement (function returns garbage)
- 5.2: Void function returning value (incorrect syntax)
- 5.3: Type mismatch errors (return type doesn't match what's returned)

### Exercise Set 6: Function Design Practice (3 exercises)
**Difficulty:** Hard
**Focus:** Writing functions from scratch

- 6.1: Write a void function (given requirements)
- 6.2: Write a value-returning function (given requirements)
- 6.3: Write a function with parameters (given requirements)

---

## Suggested Classroom Usage

### Option A: Self-Paced Practice
1. Students work through exercises in order
2. They submit answers (on paper or Canvas assignment)
3. You review using the answer key
4. Provide feedback on their explanations and traces

### Option B: Guided Instruction
1. Work Exercise 1.1 together as a class (how to call functions)
2. Have students predict output before showing trace
3. Work Exercise 2.1 together (understanding return values)
4. Have students work in pairs on Exercise 3.1
5. Progress through remaining exercises
6. Allow 5-10 minutes per exercise for discussion
7. Use Exercise Set 6 for creative practice

### Option C: Exam Preparation
1. These exercises directly build on Days 1-4
2. Assign as homework to reinforce concepts
3. Use as review material before next exam
4. Focus on understanding HOW functions work, not just syntax

---

## Key Skills Developed

After completing Day 5, students should be able to:

1. **Understand void functions** - Functions that perform tasks without returning values
2. **Master value-returning functions** - Functions that compute and return results
3. **Learn parameter passing** - How to pass data INTO functions using pass-by-value
4. **Trace function execution** - Follow variables through function calls step-by-step
5. **Match function signatures** - Return types, parameters, and arguments must align
6. **Identify function bugs** - Missing returns, type mismatches, wrong arguments
7. **Write correct functions** - Apply proper syntax and design practices
8. **Explain function behavior** - Clearly describe what functions do and why
9. **Design functions** - Write functions from scratch to solve problems

---

## Debugging Functions Checklist

Teach students this systematic approach:

- [ ] **READ:** Understand what the function SHOULD do
- [ ] **PREDICT:** What will it ACTUALLY do?
- [ ] **TRACE:** Follow variables through execution step-by-step
- [ ] **FIND:** Which line is the bug?
- [ ] **UNDERSTAND:** Why does that line cause the problem?
- [ ] **FIX:** Write the correct version
- [ ] **VERIFY:** Trace the fixed code to confirm it works
- [ ] **EXPLAIN:** Write your explanation clearly

---

## Common Student Mistakes

### Mistake 1: Not Using () for Function Calls
Students reference the function without calling it.

**Fix:** Require use of () in all function calls. greet() calls it; greet just references it.

### Mistake 2: Not Tracing Through Functions
Students identify output without understanding HOW the function produces it.

**Fix:** Require step-by-step traces with parameter values and return values documented.

### Mistake 3: Confusing Parameters and Arguments
Students mix up the terms or don't understand they're different.

**Fix:** Consistently use correct terminology and explain: parameters = definition, arguments = call.

### Mistake 4: Not Understanding Pass-by-Value
Students expect changes to parameters inside functions to affect the original variable.

**Fix:** Show concrete examples that changes inside functions don't affect calling function's variables.

### Mistake 5: Missing Return Statements
Students write value-returning functions but forget the return statement.

**Fix:** Emphasize: if function is int (or other type), it MUST have return statement at end.

### Mistake 6: Wrong Return Types
Students return wrong type (e.g., string from int function).

**Fix:** Check return type matches what function is declared to return.

---

## Difficulty Progression

**Easy (Building confidence):**
- Exercise 1.1: Basic void function calling
- Exercise 2.1: Simple return values

**Medium (Developing skills):**
- Exercise 1.2: Multiple function calls with execution order
- Exercise 2.2: Understanding type effects (integer division)
- Exercise 3.1: Parameters vs arguments terminology
- Exercise 4.1: Combining parameters and returns

**Hard (Mastery level):**
- Exercise 1.3: Void functions with parameters
- Exercise 3.2: Pass-by-value semantics
- Exercise 3.3: Multiple parameters with correct order
- Exercise 4.2: Complex multi-parameter functions
- Exercise 5.1-5.3: Finding and fixing real bugs
- Exercise 6.1-6.3: Writing functions from scratch

---

## Grading Rubric

For each exercise, evaluate:

| Criterion | Points | Notes |
|-----------|--------|-------|
| **Understands concept** | 2 | Does student correctly explain the function behavior? |
| **Provides trace** | 2 | Step-by-step with parameter and return values? |
| **Explains why** | 2 | Is explanation clear and correct? |
| **Writes fix** | 2 | Is the fix syntactically correct (if applicable)? |
| **Verifies answer** | 1 | Does trace confirm correct behavior? |
| **TOTAL** | 9 | Per exercise (adjust as needed) |

**Example for Exercise 1.1:**
```
Concept: Function not called (missing parentheses) ✓ (2 pts)
Trace: greet without () is reference, not call ✓ (2 pts)
Explanation: () executes the function; without it, nothing happens ✓ (2 pts)
Fix: greet() with parentheses ✓ (2 pts)
Verify: Trace shows output when () added ✓ (1 pt)
TOTAL: 9/9
```

---

## Tips for Instructors

1. **Emphasize the 6-step debugging process**
   - READ → PREDICT → TRACE → FIND → FIX → VERIFY
   - Use this for ALL function problems

2. **Use tracing tables religiously**
   - Every exercise should have a trace table
   - Students must show parameter values, return values
   - This reveals bugs faster than reading code alone

3. **Connect to real programming**
   - "Every C program uses functions"
   - "These bugs appear in professional code too"
   - "Good function design makes code maintainable"

4. **Pair programming opportunities**
   - Have strong students help others trace
   - Peer review of function designs
   - Peer coding of Exercise Set 6

5. **Build up confidence**
   - Start with void functions (easier to understand)
   - Progress to value-returning (adds complexity)
   - Then add parameters (full picture)
   - Finally combine everything

6. **Real-world context**
   - Show functions from actual open-source projects
   - Emphasize that understanding functions is KEY skill
   - Everyone struggles with pass-by-value initially

7. **Debugging is a SKILL**
   - Requires practice
   - Reward good tracing more than correct answers
   - Process > Product

---

## Answers To Common Questions

**Q: How long should this take?**
A: 2 hours for all exercises. Can be split across sessions.

**Q: Can I give hints?**
A: Yes! Guide them with "Have you traced the parameters?" rather than "it should return X"

**Q: What if students are stuck?**
A: Have them trace MORE carefully, not read the answer. Usually tracing reveals understanding gaps.

**Q: Should I teach debugging tools?**
A: After mastering manual tracing, then introduce debuggers. Manual first!

**Q: How do I know if they really understand?**
A: Ask them to write functions YOU specify. If they can, they understand.

**Q: When do they need to know pass-by-value?**
A: Right now! This concept appears repeatedly in C. Later they'll learn pass-by-reference (pointers).

---

## Next Steps After Day 5

1. **Arrays and Loops** - Iterate through data structures
2. **Pointers and Pass-by-Reference** - Advanced parameter passing
3. **Strings and Character Arrays** - Practical data handling
4. **File I/O** - Reading and writing files using functions
5. **Final Project** - Apply all concepts in a real program

---

## Files Provided

```
day5/
├── docs/
│   ├── DAY5_EXERCISES.md      ← Student worksheet (6 sets, 30+ exercises)
│   ├── DAY5_ANSWER_KEY.md     ← Instructor guide (detailed solutions)
│   └── README.md              ← This file
└── slides/
    ├── index.html             ← Interactive Reveal.js presentation (23 slides)
    └── README.md              ← Slides documentation
```

---

## Questions or Issues?

If you need:
- **More exercises:** Create similar ones following the template format
- **Difficulty adjustment:** Modify exercises to easier/harder versions
- **Function-specific walkthroughs:** Refer to answer key or ask for specific examples

---

**Good luck with Day 5! Remember: Functions are the building blocks of all programming.** 💪

---

*Last Updated: June 16, 2026*
*Designed for: PROG2 Enrichment Course for Computer Programming (Summer)*
