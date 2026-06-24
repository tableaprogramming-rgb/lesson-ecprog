# PROG2 Day 3: Exam Answer Key (Instructor Guide)

---

## Question 1: Multiple Condition Bug - ANSWER

**Answer Summary:**
- Buggy line: Line 7
- Bug: Using `||` (OR) instead of `&&` (AND)
- Expected output: `Count: 10`
- Actual output: `Count: 20`

---

## Complete Answer

**Buggy Line:** Line 7
```c
if (i > 0 || i > 10) {  // ← BUG: Should be &&, not ||
```

**What's Wrong:**
The condition uses OR (||) instead of AND (&&). This means "if i is greater than 0 OR greater than 10" instead of "if i is BOTH greater than 0 AND greater than 10."

**Why It's Wrong:**
- Since we're looping from 1 to 20, ALL numbers are > 0
- So the condition is ALWAYS true
- Every number from 1 to 20 gets counted (count = 20)
- But we only want numbers that are BOTH > 0 AND > 10 (which means > 10)

**Trace:**
```
i = 5:  (5 > 0 || 5 > 10) = (TRUE || FALSE) = TRUE → counted (wrong!)
i = 15: (15 > 0 || 15 > 10) = (TRUE || TRUE) = TRUE → counted (correct)
i = 1:  (1 > 0 || 1 > 10) = (TRUE || FALSE) = TRUE → counted (wrong!)
```

**The Fix:**
```c
if (i > 0 && i > 10) {
    // Or more simply: if (i > 10) {
```

**Why the Fix Works:**
- Now both conditions must be true
- i > 0 is always true in our loop (1-20)
- But i > 10 is only true for 11, 12, 13, 14, 15, 16, 17, 18, 19, 20
- That's 10 numbers → count = 10 ✓

**Verification:**
```
i = 5:  (5 > 0 && 5 > 10) = (TRUE && FALSE) = FALSE → not counted ✓
i = 15: (15 > 0 && 15 > 10) = (TRUE && TRUE) = TRUE → counted ✓
i = 1:  (1 > 0 && 1 > 10) = (TRUE && FALSE) = FALSE → not counted ✓

Correct output: Count: 10
```

---

## Question 2: Loop Boundary with Increment - ANSWER

**Answer Summary:**
- Buggy line: Line 6
- Bug: Loop condition `i < 5` instead of `i <= 5`
- Expected output: `5! = 120`
- Actual output: `5! = 24`

---

## Complete Answer

**Buggy Line:** Line 6
```c
for (int i = 1; i < 5; i++) {  // ← BUG: Should be i <= 5
```

**What's Wrong:**
The loop condition `i < 5` stops before reaching 5. This is an off-by-one error similar to Exercise 1.1.

**Why It's Wrong:**
To calculate 5!, we need: 1 × 2 × 3 × 4 × 5 = 120

But with `i < 5`:
- i = 1: result = 1 × 1 = 1
- i = 2: result = 1 × 2 = 2
- i = 3: result = 2 × 3 = 6
- i = 4: result = 6 × 4 = 24
- i = 5: Loop stops (doesn't execute) ✗

**Trace:**
```
i = 1: result = 1 × 1 = 1
i = 2: result = 1 × 2 = 2
i = 3: result = 2 × 3 = 6
i = 4: result = 6 × 4 = 24
i = 5: Condition 5 < 5? NO → Loop exits

Final result: 24 (missing the × 5)
Expected: 120
```

**The Fix:**
```c
for (int i = 1; i <= 5; i++) {  // CHANGED: < to <=
```

**Why the Fix Works:**
- Now the loop includes i = 5
- i = 5: result = 24 × 5 = 120 ✓

**Verification:**
```
i = 1: result = 1 × 1 = 1
i = 2: result = 1 × 2 = 2
i = 3: result = 2 × 3 = 6
i = 4: result = 6 × 4 = 24
i = 5: result = 24 × 5 = 120  ← NOW INCLUDED!

Correct output: 5! = 120
```

---

## Question 3: Leap Year Logic - ANSWER

**Answer Summary:**
- Buggy line: Line 6
- Bug: Logic is incorrect for leap year rules
- Problem: 1900 should output "Not a leap year" but outputs "Leap year"

---

## Complete Answer

**The Leap Year Rule:**
A year is a leap year if:
- (Divisible by 4) AND (NOT divisible by 100 OR divisible by 400)

Simpler way to think about it:
- If divisible by 400: LEAP YEAR ✓
- Else if divisible by 100: NOT LEAP YEAR ✗
- Else if divisible by 4: LEAP YEAR ✓
- Else: NOT LEAP YEAR ✗

**Buggy Condition Analysis:**
```c
if (year % 4 == 0 || year % 100 != 0 || year % 400 == 0) {
```

This reads as: "If (divisible by 4) OR (NOT divisible by 100) OR (divisible by 400)"

**Why It's Wrong - Test with 1900:**
```
1900 % 4 == 0?     → YES (1900 ÷ 4 = 475)
1900 % 100 != 0?   → NO (1900 ÷ 100 = 19, so 1900 IS divisible by 100)
1900 % 400 == 0?   → NO (1900 ÷ 400 = 4.75, not whole)

With OR: At least one true?
  YES || NO || NO = YES → Prints "Leap year" ✗ WRONG!

Reality: 1900 is divisible by 100 but NOT by 400, so it's NOT a leap year
```

**The Fix:**
```c
if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0)) {
    printf("Leap year\n");
} else {
    printf("Not a leap year\n");
}
```

Or written differently:
```c
if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0)) {
```

**Why This Works:**
- First condition: Divisible by 400 → LEAP YEAR (catches 2000, 2400, etc.)
- Second condition: Divisible by 4 AND NOT by 100 → LEAP YEAR (catches 2020, 2024, etc.)
- Everything else: NOT LEAP YEAR

**Verification with All Cases:**
```
2000: (2000 % 400 == 0) → YES
      → Prints "Leap year" ✓ CORRECT
      (divisible by 400, always leap year)

1900: (1900 % 400 == 0) → NO
      (1900 % 4 == 0 && 1900 % 100 != 0) → (YES && NO) → NO
      → Prints "Not a leap year" ✓ CORRECT
      (divisible by 100 but not 400)

2020: (2020 % 400 == 0) → NO
      (2020 % 4 == 0 && 2020 % 100 != 0) → (YES && YES) → YES
      → Prints "Leap year" ✓ CORRECT
      (divisible by 4 but not 100)

2019: (2019 % 400 == 0) → NO
      (2019 % 4 == 0 && 2019 % 100 != 0) → (NO && YES) → NO
      → Prints "Not a leap year" ✓ CORRECT
      (not divisible by 4)
```

---

## Question 4: Combined Logic and Boundary Bug - ANSWER

**Answer Summary:**
- Bug 1: Line 7 - Using `=` (assignment) instead of `==` (comparison)
- Bug 2: Loop condition - `i <= 15` is correct, but the code won't compile due to Bug 1
- Expected output: `Sum of evens: 36`

---

## Complete Answer

**Bug 1 - Line 7:**
```c
if (i % 2 = 0) {  // ← BUG: = is assignment, should be ==
```

**What's Wrong:**
Using `=` (assignment) instead of `==` (comparison). This causes a compilation error.

**Why It's Wrong:**
- `i % 2 = 0` tries to assign 0 to the result of `i % 2`, which is invalid
- The compiler will reject this with an error like "lvalue required as left operand of assignment"

---

**Bug 2 - Line 6:**
Actually, there's no bug here! The loop `for (int i = 10; i <= 15; i++)` is correct.

Wait, let me recount... The original problem says there are 2 bugs:

**Bug 1:** Line 7 - the `=` vs `==` issue
**Bug 2:** There is actually only ONE obvious bug in this code

*Instructor Note:* This question was designed to have students find the syntax error (line 7). If they want to be thorough, they might notice that after fixing the syntax, they should verify the logic works correctly. The loop is actually fine as is.

**Alternative interpretation:** If students say the loop should be `i < 15` instead of `i <= 15`, that would be WRONG - we want to include 15, so `<= 15` is correct. 10 + 12 + 14 = 36, so we don't include 15 (it's odd anyway).

---

## The Fix:

**Corrected Code:**
```c
#include <stdio.h>

int main() {
    int sum = 0;

    for (int i = 10; i <= 15; i++) {
        if (i % 2 == 0) {   // FIXED: Changed = to ==
            sum = sum + i;
        }
    }

    printf("Sum of evens: %d\n", sum);

    return 0;
}
```

**Trace:**
```
i = 10: (10 % 2 == 0?) → YES → sum = 0 + 10 = 10
i = 11: (11 % 2 == 0?) → NO  → sum = 10
i = 12: (12 % 2 == 0?) → YES → sum = 10 + 12 = 22
i = 13: (13 % 2 == 0?) → NO  → sum = 22
i = 14: (14 % 2 == 0?) → YES → sum = 22 + 14 = 36
i = 15: (15 % 2 == 0?) → NO  → sum = 36

Final sum: 36
Expected: 36
Correct? YES ✓
```

---

## Grading Guide

### Question 1 (25 points)
- **Bug identified (5 pts):** Correctly identifies line 7 and the OR vs AND issue
- **Explanation (5 pts):** Explains why OR causes the wrong count
- **Trace (5 pts):** Shows values for i=5, i=15, i=1 and evaluates correctly
- **Correct fix (5 pts):** Changes || to && (or simplifies to `if (i > 10)`)
- **Verification (5 pts):** Shows fixed code produces 10

### Question 2 (25 points)
- **Bug identified (5 pts):** Correctly identifies line 6 and the `<` vs `<=` issue
- **Trace (5 pts):** Shows all iterations and identifies when loop stops
- **Explanation (5 pts):** Explains the off-by-one error and missing 5
- **Correct fix (5 pts):** Changes `i < 5` to `i <= 5`
- **Verification (5 pts):** Shows fixed code produces 120

### Question 3 (25 points)
- **Bug identified (5 pts):** Identifies the logical error in the condition
- **Analysis (5 pts):** Explains why 1900 is incorrectly accepted
- **Trace (5 pts):** Shows the condition evaluation for 1900
- **Correct fix (5 pts):** Provides correct leap year logic
- **Verification (5 pts):** Tests all 4 cases and shows correct output

### Question 4 (25 points)
- **Bug 1 identified (3 pts):** Finds the `=` vs `==` issue on line 7
- **Bug 1 explained (2 pts):** Explains assignment vs comparison
- **Fix (5 pts):** Correctly changes to `==`
- **Trace (10 pts):** Complete trace showing even numbers 10, 12, 14
- **Verification (5 pts):** Shows output is 36

---

## Common Student Errors & How to Score

### Question 1

**Student says:** "The bug is line 6 (the loop)"
**Score:** 2/5 for bug identification - Guide them to line 7

**Student says:** "We need AND because both conditions must be true"
**Score:** 5/5 - This is correct reasoning

**Student traces but gets values wrong:**
**Score:** Partial credit (3/5) - Check their logic even if calculation is off

---

### Question 2

**Student says:** "Change `i < 5` to `i < 6`"
**Score:** 5/5 - Both are correct fixes (equivalent)

**Student says:** "The factorial is missing 5"
**Score:** 5/5 - Shows understanding

**Student traces and gets 24 but can't explain why:**
**Score:** 3/5 for trace - Ask them to count how many iterations

---

### Question 3

**Student provides correct leap year logic but in different form:**
**Score:** 5/5 for fix - Accept any logically equivalent solution
Examples that are correct:
- `if ((year % 400 == 0) || (year % 4 == 0 && year % 100 != 0))`
- `if (year % 400 == 0 || (year % 4 == 0 && year % 100 != 0))`
- Different condition order is OK as long as logic is right

**Student tests fewer than 4 cases:**
**Score:** 3-4/5 for verification - Encourage complete testing

---

### Question 4

**Student identifies only 1 bug (the = issue):**
**Score:** Full credit on what they found

**Student says "there are 2 bugs" but can't find both:**
**Score:** 3/5 for bug finding - The = is the only clear bug

**Student correctly identifies and fixes the = issue:**
**Score:** 5/5 - The rest of the code is fine

---

## Class Discussion Points

1. **Question 1 - When to use AND vs OR:**
   - "AND means ALL conditions must be true"
   - "OR means AT LEAST ONE must be true"
   - Range checking almost always uses AND

2. **Question 2 - Off-by-One Errors:**
   - "This is the most common error in loops"
   - "Think about whether you want to include or exclude the boundary"
   - "Manual tracing always catches these"

3. **Question 3 - Complex Logic:**
   - "Leap year is tricky because it has exceptions to exceptions"
   - "Break complex conditions into parts"
   - "Always test edge cases"

4. **Question 4 - Multiple Bugs:**
   - "Some code has multiple bugs"
   - "Fix one bug at a time and test"
   - "Syntax errors prevent running, so find those first"

---

## Exam Difficulty Notes

**Why this is Intermediate:**
- Requires understanding of operators (=, ==, %, ||, &&)
- Combines multiple concepts (loops, conditions, logic)
- Question 3 needs domain knowledge (leap year rules)
- Question 4 has syntax errors (more advanced debugging)
- All require systematic tracing and verification

**Success Indicators:**
- Students who score 70%+ on this exam have solid Day 3 understanding
- Students who struggle with Q3 often have weak logical reasoning skills
- Students who miss Q1 vs Q2 tell you different things:
  - Q1 miss = confusion about logical operators
  - Q2 miss = off-by-one errors (very common, needs more practice)

---

## Remediation Suggestions

**If students struggle with:**

**OR vs AND (Question 1):**
- Have them write out truth tables
- Practice with real-world examples ("am I tired AND hungry?" vs "am I tall OR short?")
- Create more practice problems with range checking

**Loop Boundaries (Question 2):**
- More off-by-one practice (like Day 3 Exercises 1.1)
- Have them manually count iterations
- Create extra practice with different starting/ending values

**Complex Logic (Question 3):**
- Break conditions into smaller parts
- Practice writing conditions step-by-step
- Discuss domain-specific logic (leap year, age groups, etc.)

**Multiple Bugs (Question 4):**
- Have students fix one bug at a time
- Teach systematic debugging approach
- More practice with mixed bug types

---

## Post-Exam Analysis

**Good performance (80%+):**
- Students are ready for more complex debugging
- Consider advanced topics: arrays, nested loops, functions

**Average performance (60-79%):**
- Solid understanding of basics
- Need practice with complex logic
- More drill work on off-by-one errors recommended

**Below average (<60%):**
- Review Day 3 concepts
- Go back to basic exercises (1.1-3.1)
- Consider peer tutoring or office hours
- More time on systematic tracing

---

**Total Possible Points:** 100

**A (90-100):** Excellent - Mastered all debugging skills
**B (80-89):** Good - Strong understanding, minor gaps
**C (70-79):** Satisfactory - Adequate understanding, needs practice
**D (60-69):** Below Standard - Fundamental gaps
**F (<60):** Unsatisfactory - Needs significant review

Good luck with grading! Remember that debugging is challenging even for professionals. These scores show potential for growth. 🐛→🔧
