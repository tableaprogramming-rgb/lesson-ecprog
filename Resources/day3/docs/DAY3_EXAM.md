# PROG2 Day 3: Debugging Exam

**Intermediate Difficulty Level**

---

## Exam Instructions

**Time Limit:** 60 minutes

**Rules:**
1. You may use pen and paper for tracing
2. You may NOT use a compiler or IDE
3. You may NOT ask for help from others
4. Show ALL your work - line numbers, traces, and explanations

**Scoring:**
- Each question: 25 points
- Total: 100 points

---

## Question 1: Multiple Condition Bug (25 points)

**Context:** This program should count how many numbers between 1 and 20 are positive AND greater than 10.
- Example: 11, 12, 13, ... 20 should be counted (10 numbers)
- The program should output: `Count: 10`

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;

    for (int i = 1; i <= 20; i++) {
        if (i > 0 || i > 10) {
            count++;
        }
    }

    printf("Count: %d\n", count);

    return 0;
}
```

**What it ACTUALLY outputs:** `Count: 20`

**Your Task:**
1. **Find the bug:** What line(s) have the error?
2. **Explain why:** Why does this cause the wrong output?
3. **Trace it:** Show what happens with 3 test values (i = 5, i = 15, i = 1)
4. **Write the fix:** What should the code be?
5. **Verify:** Show the corrected code produces `Count: 10`

**Show your work:**
```
Buggy line(s): _______

What's wrong:
__________________________________________________________________
__________________________________________________________________

Trace with test values:
  i = 5:  Condition (5 > 0 || 5 > 10) evaluates to: ________
  i = 15: Condition (15 > 0 || 15 > 10) evaluates to: ________
  i = 1:  Condition (1 > 0 || 1 > 10) evaluates to: ________

Why this is wrong:
__________________________________________________________________
__________________________________________________________________

The fix (rewrite the if condition):
if (________________) {

Explanation of your fix:
__________________________________________________________________
```

---

## Question 2: Loop Boundary with Increment (25 points)

**Context:** This program should calculate the factorial of 5 (5! = 5 × 4 × 3 × 2 × 1 = 120)

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int result = 1;

    for (int i = 1; i < 5; i++) {
        result = result * i;
    }

    printf("5! = %d\n", result);

    return 0;
}
```

**What it ACTUALLY outputs:** `5! = 24`

**Your Task:**
1. **Find the bug:** What's wrong with line 6?
2. **Trace it:** Show what gets multiplied at each iteration
3. **Explain why:** Why does 24 appear instead of 120?
4. **Write the fix:** Change the loop condition only (don't change the body)
5. **Verify:** Confirm your fix produces 120

**Show your work:**
```
Buggy line: _______

What's multiplied:
  i = 1: result = 1 × 1 = ________
  i = 2: result = ________ × 2 = ________
  i = 3: result = ________ × 3 = ________
  i = 4: result = ________ × 4 = ________
  i = 5: Does this run? ________

Current result: ________
Expected result: ________
Missing multiplication: ________ × 5

The fix (change the condition):
for (int i = 1; i _______ 5; i++) {

Why this fix works:
__________________________________________________________________
```

---

## Question 3: Nested Logic Error (25 points)

**Context:** This program should determine if a year is a leap year.
- A year is a leap year if:
  - It's divisible by 4 AND
  - If it's divisible by 100, it must also be divisible by 400
- Examples:
  - 2020: Leap year (divisible by 4, not by 100)
  - 2000: Leap year (divisible by 400)
  - 1900: NOT leap year (divisible by 100 but not 400)
  - 2019: NOT leap year (not divisible by 4)

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int year = 2000;

    if (year % 4 == 0 || year % 100 != 0 || year % 400 == 0) {
        printf("Leap year\n");
    } else {
        printf("Not a leap year\n");
    }

    return 0;
}
```

**Test Cases:**
- 2000: Outputs "Leap year" ✓ (CORRECT)
- 1900: Outputs "Leap year" ✗ (WRONG - should be "Not a leap year")
- 2020: Outputs "Leap year" ✓ (CORRECT)
- 2019: Outputs "Not a leap year" ✓ (CORRECT)

**Your Task:**
1. **Find the bug:** What's wrong with the condition on line 6?
2. **Analyze:** Why does 1900 incorrectly print "Leap year"?
3. **Trace:** Test 1900 with the buggy condition
4. **Write the fix:** Rewrite the complete if condition correctly
5. **Verify:** Test your fixed condition with all 4 cases

**Show your work:**
```
Buggy condition:
if (year % 4 == 0 || year % 100 != 0 || year % 400 == 0)

Test with year = 1900:
  1900 % 4 == 0? ________
  1900 % 100 != 0? ________
  1900 % 400 == 0? ________
  With OR: At least one true? ________
  Result: Prints "Leap year" (WRONG!)

What's wrong:
__________________________________________________________________
__________________________________________________________________

The fix (complete if condition):
if (________________) {

Verify with all cases:
  2000: (divisible by 4? yes) (by 100? yes) (by 400? yes) → ________
  1900: (divisible by 4? yes) (by 100? yes) (by 400? no)  → ________
  2020: (divisible by 4? yes) (by 100? no)                → ________
  2019: (divisible by 4? no)                              → ________
```

---

## Question 4: Combined Logic and Boundary Bug (25 points)

**Context:** This program should sum all numbers from 10 to 15 that are EVEN
- Expected: 10 + 12 + 14 = 36

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int sum = 0;

    for (int i = 10; i <= 15; i++) {
        if (i % 2 = 0) {
            sum = sum + i;
        }
    }

    printf("Sum of evens: %d\n", sum);

    return 0;
}
```

**What it ACTUALLY outputs:** Code does NOT compile

**Your Task:**
1. **Find ALL bugs:** There are 2 bugs in this code. Find both!
2. **Explain each bug:** What's wrong and why?
3. **Write the fixes:** Correct both bugs
4. **Trace:** Show what the fixed code does for each iteration
5. **Verify:** Confirm the output is 36

**Show your work:**
```
Bug 1 - Line ______
What's wrong: ______________________________________________________

Bug 2 - Line ______
What's wrong: ______________________________________________________

Fixed code (show the corrected lines):
Line 6: for (int i = 10; i <= 15; i++) {
Line 7: if (________________) {

Trace the fixed code:
  i = 10: (10 % 2 == 0?) ________ → sum = ________
  i = 11: (11 % 2 == 0?) ________ → sum = ________
  i = 12: (12 % 2 == 0?) ________ → sum = ________
  i = 13: (13 % 2 == 0?) ________ → sum = ________
  i = 14: (14 % 2 == 0?) ________ → sum = ________
  i = 15: (15 % 2 == 0?) ________ → sum = ________

Final sum: ________
Expected: 36
Correct? ________
```

---

## Scoring Rubric

| Question | Points | Grading Criteria |
|----------|--------|------------------|
| **1** | 25 | Bug identified (5) + Explanation (5) + Trace (5) + Correct fix (5) + Verification (5) |
| **2** | 25 | Bug identified (5) + Trace (5) + Explanation (5) + Correct fix (5) + Verification (5) |
| **3** | 25 | Bug identified (5) + Analysis (5) + Trace (5) + Correct fix (5) + Verification (5) |
| **4** | 25 | Both bugs found (5) + Both explained (5) + Both fixed (5) + Trace (3) + Verification (2) |

---

## General Grading Notes

- **Full Credit (20-25 points/question):** All parts correct, clear explanations, complete traces
- **Good (15-19 points/question):** Most parts correct, minor gaps in explanation or tracing
- **Developing (10-14 points/question):** Some parts correct, significant gaps in reasoning
- **Beginning (5-9 points/question):** Minimal correct work shown
- **No Credit (0-4 points/question):** No work shown or completely incorrect

---

## Exam Difficulty Notes

**Why this is intermediate:**
- Uses concepts from Day 3 exercises (operators, conditions, loops, logic)
- Combines multiple concepts (e.g., question 3 requires understanding leap year logic)
- Requires careful tracing and logical thinking
- More subtle bugs than the basic exercises
- Question 4 has multiple bugs (testing comprehensive understanding)

**Skills tested:**
1. Operator usage (=, ==, %, ||, &&)
2. Loop boundaries and conditions
3. Logical thinking and reasoning
4. Careful code reading
5. Systematic tracing and verification

---

**Time Management Tips:**
- Spend 2-3 minutes reading and understanding context
- Spend 3-5 minutes finding and analyzing the bug
- Spend 2-3 minutes writing the fix
- Spend 2-3 minutes verifying (trace the fixed code)
- Don't spend too long on one question - move on and come back

Good luck! Remember: debugging is a professional skill. Take your time, think systematically, and show your work. 🐛→🔧
