# PROG2 Day 3: Answer Key (Instructor Guide)

---

## EXERCISE SET 1: Off-by-One Errors - ANSWERS

### Exercise 1.1: Sum 1 to 5 (Off-by-One) - ANSWER

**Context:** Program should sum 1+2+3+4+5 = 15

**Expected Output:** `Sum: 15`

**Actual Buggy Output:** `Sum: 10`

---

## The Bug

**Buggy Line:** Line 6
```c
for (int i = 1; i < 5; i++) {   // ← THE BUG IS HERE
```

**What's Wrong:**
The loop condition is `i < 5` (less than 5), not `i <= 5` (less than or equal to 5).

This means:
- Loop runs while i is 1, 2, 3, 4
- Loop STOPS when i becomes 5
- The number 5 never gets added to the sum!

**Why It's a Bug:**
The program is supposed to sum 1 through 5, but it only sums 1 through 4.

---

## The Trace

**What actually gets added:**

```
Iteration 1: i = 1, condition 1 < 5? YES ✓
  sum = 0 + 1 = 1

Iteration 2: i = 2, condition 2 < 5? YES ✓
  sum = 1 + 2 = 3

Iteration 3: i = 3, condition 3 < 5? YES ✓
  sum = 3 + 3 = 6

Iteration 4: i = 4, condition 4 < 5? YES ✓
  sum = 6 + 4 = 10

Check again: i = 5, condition 5 < 5? NO ✗
  Loop exits WITHOUT adding 5!

Final sum: 10 (missing the 5)
```

**Expected trace (if it were correct):**
```
Would need i = 5 to execute:
sum = 10 + 5 = 15
```

---

## The Fix

**Corrected Line 6:**
```c
for (int i = 1; i <= 5; i++) {   // ← CHANGED < to <=
```

**Why This Fixes It:**
Now the loop runs while i is less than OR equal to 5:
- i = 1: 1 <= 5? YES ✓
- i = 2: 2 <= 5? YES ✓
- i = 3: 3 <= 5? YES ✓
- i = 4: 4 <= 5? YES ✓
- i = 5: 5 <= 5? YES ✓ (now includes 5!)
- i = 6: 6 <= 5? NO ✗ (loop exits)

**Correct Output:** `Sum: 15`

---

## Complete Corrected Code

```c
#include <stdio.h>

int main() {
    int sum = 0;

    for (int i = 1; i <= 5; i++) {  // FIXED: changed < to <=
        sum = sum + i;
    }

    printf("Sum: %d\n", sum);

    return 0;
}
```

---

## Teaching Notes & Discussion Points

### What to Look For in Student Work:

1. **Did they identify the correct line?**
   - Many students might not pinpoint line 6 specifically
   - Some might say "the for loop" without being specific
   - Award points if they identify any part of the loop condition

2. **Did they understand the bug?**
   - Just saying "off by one" isn't enough
   - They should explain: "the condition excludes 5" or "loop stops too early"
   - Look for evidence they traced the loop

3. **Did they trace the code?**
   - Best students will show: i=1,2,3,4 get added, but i=5 doesn't
   - They should show the iterations and calculations
   - This proves they understand the bug, not just guessed

4. **Did they provide the correct fix?**
   - Change `<` to `<=` is the standard fix
   - Alternative acceptable fix: change `i < 5` to `i < 6` (less common but correct)
   - Award full credit for either approach

### Common Student Errors:

**Error 1: Confusion about loop boundaries**
- Student: "The loop only runs 4 times"
- Correct response: "Yes, exactly! But it should run 5 times (1,2,3,4,5)"
- Teaching moment: Loop condition determines how many iterations

**Error 2: Wrong fix provided**
- Student: "Change the loop to `for (int i = 0; i < 5; i++)`"
- Problem: This would sum 0+1+2+3+4=10 (still wrong, just different context)
- Teaching moment: You need to understand the context (1 to 5, not 0 to 4)

**Error 3: Didn't trace it**
- Student: "I think the condition should be `<=`"
- Missing: They should show WHY with a trace
- Teaching moment: Tracing proves understanding

### Class Discussion Ideas:

1. **Why is `<` vs `<=` confusing?**
   - Help students create a mental model: "<5 means stop before reaching 5"
   - "<=5 means include 5"

2. **Off-by-one is common in real programming**
   - Experienced programmers still make these mistakes!
   - Version 1.0 of many software has off-by-one bugs
   - This is a professional skill to practice

3. **Why does the context matter?**
   - Without knowing "sum 1 to 5", you might think i=0 to 4 is correct
   - Always read the problem statement first!

4. **How would you catch this bug?**
   - Test with small numbers
   - Trace the code on paper first
   - Use an IDE debugger (set breakpoints)

---

## Grading Example

### Example Student Answer 1: Full Credit (90-100%)
```
Buggy line number: Line 6

What's wrong with it:
The loop condition is i < 5, which stops the loop before i reaches 5.
Since we need to sum 1 through 5, we need to include the 5.

Why it causes the bug:
When i = 5, the condition 5 < 5 is FALSE, so the loop exits.
The number 5 never gets added to the sum.

What values actually get added:
i=1: sum=1
i=2: sum=3
i=3: sum=6
i=4: sum=10
i=5: LOOP STOPS, 5 is not added

What should the line be instead:
for (int i = 1; i <= 5; i++) {
```
**Grade: 95%** - Clear explanation, complete trace, correct fix

---

### Example Student Answer 2: Good Work (75-89%)
```
Buggy line number: Line 6 (the for loop)

What's wrong with it:
The < should be <=

Why it causes the bug:
The loop stops when i is 5 instead of adding it

What values actually get added:
1, 2, 3, 4

What should the line be instead:
i <= 5
```
**Grade: 80%** - Correct bug and fix, but minimal explanation/trace

---

### Example Student Answer 3: Developing (60-74%)
```
Buggy line number: the loop

What's wrong with it:
It's off by one

Why it causes the bug:
?

What values actually get added:
1+2+3+4 = 10 (not 5)

What should the line be instead:
i < 6
```
**Grade: 65%** - Found the bug and a valid fix, but explanation is weak. No trace shown.

---

## Common Question: Is `i < 6` also acceptable?

**YES!** Both fixes are correct:
- `i <= 5` (more common, easier to read)
- `i < 6` (mathematically equivalent)

If a student provides `i < 6`, award full credit with a note:
"Good fix! Both `i <= 5` and `i < 6` work. The `<=` version is more common because it's clearer."

---

## How to Use This Answer Key

**In Class:**
1. Collect student work
2. Use this key to grade quickly
3. Identify common misconceptions
4. Address them in discussion

**For Review:**
1. Show the buggy code on projector
2. Ask: "What's wrong with this?"
3. Guide students to find the bug
4. Show the trace together
5. Show the fix
6. Confirm correct output

**For Further Learning:**
1. Ask: "What if we wanted to sum 0 to 5?"
2. Ask: "What if we wanted to sum 1 to 10?"
3. Ask: "How would you catch this bug while coding?"

---

## Why This Bug Matters

Off-by-one errors are:
- **Common** - Experienced programmers make these frequently
- **Hard to spot** - Code looks right, but output is wrong
- **Teachable** - Easy to understand once you see it
- **Preventable** - Good tracing skill catches them early

Students who master this skill will:
- Write more reliable code
- Debug faster
- Build confidence in their programming

---

## EXERCISE SET 2: Operator Errors - ANSWERS

### Exercise 1.2: Check if x equals 5 (Assignment vs Comparison) - ANSWER

**Context:** Program should check if x equals 5

**Expected Output (when x=3):** `x is not 5`

**Actual Buggy Output:** `x is 5`

---

## The Bug

**Buggy Line:** Line 6
```c
if (x = 5) {   // ← THE BUG: = instead of ==
```

**What's Wrong:**
The condition uses `=` (assignment) instead of `==` (comparison).

This means:
- `x = 5` ASSIGNS the value 5 to x (changes x)
- It doesn't check if x equals 5
- The result of assignment (5) is treated as TRUE (any non-zero value is true)

**Why It's a Bug:**
- x starts at 3
- But `x = 5` changes x TO 5
- Then the if statement treats 5 as TRUE
- So it always prints "x is 5" (wrong!)

---

## The Trace

**What actually happens:**
```
x starts as: 3
Evaluate: if (x = 5)
  This ASSIGNS 5 to x (x is now 5)
  The expression evaluates to 5 (the assigned value)
  5 is non-zero, so it's TRUE
  The if block executes
  Prints: "x is 5"
```

**What SHOULD happen:**
```
x is: 3
Evaluate: if (x == 5)
  This COMPARES x with 5
  3 == 5? FALSE
  The else block executes
  Prints: "x is not 5"
```

---

## The Fix

**Corrected Line 6:**
```c
if (x == 5) {   // ← CHANGED = to ==
```

**Why This Fixes It:**
Now we use `==` (comparison) instead of `=` (assignment):
- `x == 5` checks: "Is x equal to 5?"
- It doesn't change x
- x is still 3
- 3 == 5? FALSE
- The else block executes
- Prints: "x is not 5" ✓

---

## Complete Corrected Code

```c
#include <stdio.h>

int main() {
    int x = 3;

    if (x == 5) {   // FIXED: changed = to ==
        printf("x is 5\n");
    } else {
        printf("x is not 5\n");
    }

    return 0;
}
```

---

## Teaching Notes

### Key Distinction:
- **`=`** - Assignment operator (stores a value in a variable)
- **`==`** - Comparison operator (checks if two values are equal)

### Common Student Confusion:
- Many beginners mix these up
- The compiler won't catch this error (valid C syntax)
- But the logic is wrong
- This is a classic example of "the code runs, but gives wrong answer"

---

### Exercise 2.1: Check if x is in range (AND vs OR) - ANSWER

**Context:** Program should check if x is between 0 and 10

**Expected Output (when x=15):** `Out of range`

**Actual Buggy Output:** `In range`

---

## The Bug

**Buggy Line:** Line 6
```c
if (x > 0 || x < 10) {   // ← THE BUG: || should be &&
```

**What's Wrong:**
The condition uses `||` (OR) instead of `&&` (AND).

**For range checking:**
- We need BOTH conditions to be true: x > 0 AND x < 10
- Using OR means: at least ONE condition is true
- This accepts values outside the range

**Why It's a Bug:**
With x = 15:
- Is 15 > 0? YES ✓
- Is 15 < 10? NO ✗
- With OR: At least one TRUE? YES (so it executes the if block)
- Incorrectly prints "In range" (WRONG!)

---

## The Trace

**What actually happens (x = 15):**
```
Check: if (15 > 0 || 15 < 10)
  First part: 15 > 0? TRUE ✓
  Second part: 15 < 10? FALSE ✗
  OR operator: At least one TRUE? YES
  Condition is TRUE
  Prints: "In range" (WRONG! 15 is not in range 0-10)
```

**What SHOULD happen:**
```
Check: if (15 > 0 && 15 < 10)
  First part: 15 > 0? TRUE ✓
  Second part: 15 < 10? FALSE ✗
  AND operator: BOTH TRUE? NO
  Condition is FALSE
  Goes to else block
  Prints: "Out of range" (CORRECT!)
```

---

## The Fix

**Corrected Line 6:**
```c
if (x > 0 && x < 10) {   // ← CHANGED || to &&
```

**Why This Fixes It:**
Now we use `&&` (AND) instead of `||` (OR):
- BOTH conditions must be true
- For x in range 0-10: x > 0 AND x < 10
- For x = 5: 5 > 0? YES, 5 < 10? YES → Both true → In range ✓
- For x = 15: 15 > 0? YES, 15 < 10? NO → Not both true → Out of range ✓

---

## Complete Corrected Code

```c
#include <stdio.h>

int main() {
    int x = 15;

    if (x > 0 && x < 10) {   // FIXED: changed || to &&
        printf("In range\n");
    } else {
        printf("Out of range\n");
    }

    return 0;
}
```

---

## Teaching Notes

### AND vs OR:
- **`&&` (AND)** - BOTH conditions must be true
- **`||` (OR)** - At least ONE condition is true

### When to use each:
- Use AND for range checks: "x > 0 AND x < 10"
- Use OR for exclusions: "x < 0 OR x > 10"
- Use AND for multiple requirements
- Use OR for alternatives

---

## EXERCISE SET 3: Loop Errors - ANSWERS

### Exercise 2.2: Print 1 to 5 (Missing Loop Increment) - ANSWER

**Context:** Program should print numbers 1 through 5

**Expected Output:**
```
1
2
3
4
5
```

**Actual Buggy Output:**
```
1
1
1
1
1
... (infinite loop)
```

---

## The Bug

**Buggy Line:** Line 4
```c
for (int i = 1; i <= 5; ) {   // ← THE BUG: Missing i++
```

**What's Wrong:**
The loop has no increment in the third part of the for statement.

Standard for loop structure: `for (init; condition; increment)`
- **init:** `int i = 1` ✓ (present)
- **condition:** `i <= 5` ✓ (present)
- **increment:** (MISSING!) ✗

**Why It's a Bug:**
Without the increment:
- i starts at 1
- Condition 1 <= 5? TRUE, so loop body executes
- i is NOT incremented
- Loop again: i is STILL 1
- Condition 1 <= 5? TRUE, so loop body executes again
- This repeats forever (infinite loop)

---

## The Trace

**What actually happens:**
```
Initialize: i = 1
Iteration 1: Check i <= 5? (1 <= 5? YES) → Print 1 → No increment
Iteration 2: Check i <= 5? (1 <= 5? YES) → Print 1 → No increment
Iteration 3: Check i <= 5? (1 <= 5? YES) → Print 1 → No increment
... (continues forever, i never changes)
```

**What SHOULD happen:**
```
Initialize: i = 1
Iteration 1: Check i <= 5? (1 <= 5? YES) → Print 1 → i++ (i becomes 2)
Iteration 2: Check i <= 5? (2 <= 5? YES) → Print 2 → i++ (i becomes 3)
Iteration 3: Check i <= 5? (3 <= 5? YES) → Print 3 → i++ (i becomes 4)
Iteration 4: Check i <= 5? (4 <= 5? YES) → Print 4 → i++ (i becomes 5)
Iteration 5: Check i <= 5? (5 <= 5? YES) → Print 5 → i++ (i becomes 6)
Check again: i <= 5? (6 <= 5? NO) → Loop exits
```

---

## The Fix

**Corrected Line 4:**
```c
for (int i = 1; i <= 5; i++) {   // ← ADDED i++
```

**Why This Fixes It:**
The `i++` in the third part increments i after each iteration:
- Loop body executes
- i is incremented
- Condition is checked again with new value
- Eventually i becomes 6, condition is false, loop exits

---

## Complete Corrected Code

```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {   // FIXED: added i++
        printf("%d\n", i);
    }

    return 0;
}
```

---

## Teaching Notes

### For Loop Structure:
Every for loop has three critical parts:
1. **Initialization**: `int i = 1` (starting value)
2. **Condition**: `i <= 5` (keep looping while true)
3. **Increment**: `i++` (change value each iteration)

### If increment is missing:
- The loop variable never changes
- The condition stays true forever
- The loop becomes infinite

### Common mistakes:
- Forgetting the increment entirely
- Putting increment in wrong place
- Off-by-one in the condition combined with wrong increment

---

## EXERCISE SET 4: Logic Errors - ANSWERS

### Exercise 3.1: Check if positive (Backwards Condition) - ANSWER

**Context:** Program should determine if a number is positive or negative

**Expected Output (when x=10):** `x is positive`

**Actual Buggy Output:** `x is negative`

---

## The Bug

**Buggy Line:** Line 6
```c
if (x < 0) {   // ← THE BUG: Backwards logic
    printf("x is positive\n");
```

**What's Wrong:**
The condition checks `x < 0` (x is less than 0, i.e., negative).
But when this is TRUE, it prints "x is positive" (which is backwards).

**Why It's a Bug:**
The logic is inverted:
- If x < 0 is true (x is negative), we print "positive" (wrong!)
- If x < 0 is false (x is positive), we print "negative" (also wrong!)

---

## The Trace

**What actually happens (x = 10):**
```
Check: if (10 < 0)
  Is 10 less than 0? NO (FALSE)
  Goes to else block
  Prints: "x is negative"
  But 10 IS positive! (WRONG!)
```

**What SHOULD happen:**
```
Check: if (10 > 0)
  Is 10 greater than 0? YES (TRUE)
  Executes if block
  Prints: "x is positive"
  Correct!
```

---

## The Fix

**Corrected Line 6:**
```c
if (x > 0) {   // ← CHANGED < to >
    printf("x is positive\n");
```

**Why This Fixes It:**
Now we check if x > 0 (x is greater than 0):
- If x = 10: 10 > 0? YES → Prints "x is positive" ✓
- If x = -5: -5 > 0? NO → Prints "x is negative" ✓

---

## Complete Corrected Code

```c
#include <stdio.h>

int main() {
    int x = 10;

    if (x > 0) {   // FIXED: changed < to >
        printf("x is positive\n");
    } else {
        printf("x is negative\n");
    }

    return 0;
}
```

---

## Teaching Notes

### What is a Logic Error?
A logic error is when:
- The code is syntactically correct (no compiler errors)
- The code runs without crashing
- But the logic is backwards or wrong
- The output is incorrect

### Why they're tricky:
- The code "looks right"
- The compiler won't catch them
- You only find them by testing and tracing

### How to catch them:
1. Test with sample inputs
2. Check that output matches expected behavior
3. Trace the code step by step
4. Look for backwards conditions or inverted logic

### Common backwards conditions:
- Using `<` when you need `>`
- Using `&&` when you need `||`
- Checking the opposite of what you mean
- Swapping the if and else blocks

---

## Notes for Future Day 3 Exercises

As you create more Day 3 exercises, consider varying:
1. **Bug types**: off-by-one, wrong operator, missing increment, wrong variable, etc.
2. **Difficulty**: Start easy (like this), progress to harder
3. **Contexts**: Sums, counts, patterns, arrays, nested loops
4. **Subtlety**: Obvious bugs → subtle bugs

This exercise is a good foundation. Next exercises can be harder!
