# PROG2 Day 3: Debugging Exercises
## Finding and Fixing Bugs

---

## Important: How to Approach These Exercises

**DEBUGGING SKILL:** Your goal is to:
1. **Read the buggy code carefully** - What should it do?
2. **Understand the expected output** - What is the context?
3. **Run the code mentally** - What will it actually do?
4. **Find the bug** - What's wrong? Why?
5. **Fix it** - How would you correct it?
6. **Verify** - Does the fixed code produce correct output?

**NO SHORTCUTS.** The only tools you need are:
- Pen and paper
- Your brain
- Your understanding of C from Day 1 & 2

If you don't understand, ask your classmate or instructor—not Google or AI.

---

## EXERCISE SET 1: Off-by-One Errors

### Instructions
For each buggy program:
1. **Read the code** - Understand what it's supposed to do
2. **Know the context** - What output should it produce?
3. **Identify the bug** - What line has the error?
4. **Explain why** - Why does that line cause the bug?
5. **Write the fix** - What should it be instead?
6. **Verify** - Trace the fixed code to confirm it works

---

### Exercise 1.1: Sum 1 to 5 (Off-by-One)

**Context:** This program should calculate the sum of numbers from 1 to 5.
- Expected: 1 + 2 + 3 + 4 + 5 = **15**

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int sum = 0;

    for (int i = 1; i < 5; i++) {
        sum = sum + i;
    }

    printf("Sum: %d\n", sum);

    return 0;
}
```

**What it ACTUALLY outputs:** `Sum: 10`

**Your Task:**
1. **Find the bug:** Which line has the error?
2. **Explain the bug:** Why does this line cause wrong output?
3. **Trace it:** Show what values get added
   ```
   i = 1: sum = 0 + 1 = ?
   i = 2: sum = ? + 2 = ?
   i = 3: sum = ? + 3 = ?
   i = 4: sum = ? + 4 = ?
   i = 5: Does i = 5 even run? Why or why not?
   ```
4. **Write the fix:** What should line 6 be?
5. **Verify:** After fixing, trace through the corrected code

**Show your work:**
```
Buggy line number: _______

What's wrong with it:
__________________________________________________________________
__________________________________________________________________

Why it causes the bug:
__________________________________________________________________
__________________________________________________________________

What values actually get added:
__________________________________________________________________

What should the line be instead:
__________________________________________________________________

Fixed code (show the corrected line):
for (int i = 1; i _______ ; i++) {
```

---

## EXERCISE SET 2: Operator Errors

### Instructions
For each buggy program, identify which operator is wrong and why.

---

### Exercise 1.2: Check if x equals 5 (Assignment vs Comparison)

**Context:** This program should check if a variable x equals 5.
- If x = 5: Print "x is 5"
- If x = 3: Print "x is not 5"

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int x = 3;

    if (x = 5) {
        printf("x is 5\n");
    } else {
        printf("x is not 5\n");
    }

    return 0;
}
```

**What it ACTUALLY outputs:** `x is 5`

**Your Task:**
1. **Find the bug:** What operator is wrong on line 6?
2. **Explain the bug:** Why does `=` instead of `==` cause this?
3. **Trace it:** What happens when you use assignment in an if statement?
4. **Write the fix:** What should line 6 be?
5. **Verify:** Show that the fixed code produces correct output

**Show your work:**
```
Buggy operator: _______

What's wrong with it:
__________________________________________________________________
__________________________________________________________________

Why it causes the bug:
__________________________________________________________________
__________________________________________________________________

What should the line be instead:
if (x _______ 5) {

Assignment vs Comparison:
= means: _______________________________________________
== means: _______________________________________________
```

---

### Exercise 2.1: Check if x is in range (AND vs OR)

**Context:** This program should check if x is between 0 and 10.
- If x = 5: Print "In range"
- If x = 15: Print "Out of range"

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int x = 15;

    if (x > 0 || x < 10) {
        printf("In range\n");
    } else {
        printf("Out of range\n");
    }

    return 0;
}
```

**What it ACTUALLY outputs:** `In range`

**Your Task:**
1. **Find the bug:** Is it `&&` or `||` on line 6?
2. **Explain the bug:** Why does OR cause wrong output here?
3. **Test with values:**
   - For x = 5: Is 5 > 0? Is 5 < 10? Should both be true?
   - For x = 15: Is 15 > 0? Is 15 < 10? Should both be true?
4. **Write the fix:** What operator should it be?
5. **Verify:** Does your fix work for both test cases?

**Show your work:**
```
Buggy operator: _______

Why OR (||) is wrong:
__________________________________________________________________
__________________________________________________________________

Test with x = 15:
15 > 0? ________
15 < 10? ________
With OR: At least one true? ________
With AND: Both true? ________

What should the line be instead:
if (x > 0 _______ x < 10) {

When to use AND vs OR:
AND (&&) = _______________________________________________
OR (||) = _______________________________________________
```

---

## EXERCISE SET 3: Loop Errors

### Exercise 2.2: Print 1 to 5 (Missing Loop Increment)

**Context:** This program should print numbers 1 through 5, one per line.
- Expected output:
  ```
  1
  2
  3
  4
  5
  ```

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; ) {
        printf("%d\n", i);
    }

    return 0;
}
```

**What it ACTUALLY outputs:** `1 1 1 1 1 ... (infinite loop)`

**Your Task:**
1. **Find the bug:** What's missing from line 4?
2. **Explain the bug:** Why does this cause an infinite loop?
3. **Trace the loop:**
   - What is i when the loop starts?
   - Does the condition i <= 5 check anything?
   - What happens to i in each iteration?
   - Will the loop ever stop?
4. **Write the fix:** What should line 4 be?
5. **Verify:** Show the corrected code produces 1 2 3 4 5

**Show your work:**
```
Buggy line number: _______

What's missing:
__________________________________________________________________

Why it causes infinite loop:
__________________________________________________________________
__________________________________________________________________

Loop parts (init; condition; increment):
for (int i = 1; i <= 5; ____________ )

The increment is: _______________________________________________

What should line 4 be:
for (int i = 1; i <= 5; ______________ ) {
```

---

## EXERCISE SET 4: Logic Errors

### Exercise 3.1: Check if positive (Backwards Condition)

**Context:** This program should check if a number is positive or negative.
- If x = 10: Print "x is positive"
- If x = -5: Print "x is negative"

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int x = 10;

    if (x < 0) {
        printf("x is positive\n");
    } else {
        printf("x is negative\n");
    }

    return 0;
}
```

**What it ACTUALLY outputs:** `x is negative`

**Your Task:**
1. **Find the bug:** What's wrong with the condition on line 6?
2. **Explain the bug:** Why is the logic backwards?
3. **Trace with x = 10:**
   - Is 10 < 0? (TRUE or FALSE?)
   - Which branch executes?
   - What gets printed?
   - Should it print that?
4. **Write the fix:** What should the condition be?
5. **Verify:** Check both positive and negative cases

**Show your work:**
```
Buggy condition: x _______ 0

What's wrong:
__________________________________________________________________
__________________________________________________________________

Test with x = 10:
10 < 0? ________
Prints: ___________________
Should print: ___________________

The fix:
if (x _______ 0) {
    printf("x is positive\n");

Comparison operators:
< means: _______________________________________
> means: _______________________________________
```

---

## Submission Requirements

1. **Show ALL your work** - Line numbers, traces, explanations
2. **Explain clearly** - Not just "it's off by one"
3. **Show tracing** - Prove why the bug happens
4. **Write the fix** - Exactly what should change
5. **Verify** - Confirm your fix works

---

## Grading Rubric

| Criteria | Points |
|----------|--------|
| Bug identified (correct line) | 20% |
| Bug explanation (why it's wrong) | 30% |
| Trace showing the bug | 30% |
| Correct fix provided | 20% |

**Note:** You get credit for clear thinking even if your initial fix isn't perfect. The goal is understanding, not guessing.

---

## Helpful Tips

### For Finding Off-by-One Errors:
- Check loop conditions: `<` vs `<=`, `>` vs `>=`
- Count loop iterations by hand
- Ask: "Does my loop include the last value?"
- Does the first value get included?

### Common Places for Off-by-One:
- Loop condition (`i < n` vs `i <= n`)
- Array indexing (arrays start at 0, not 1)
- Loop initialization (start at 0 or 1?)

### Debugging Strategy:
1. **Understand the context** - What should this code do?
2. **Trace the code** - Follow variables step by step
3. **Find where it breaks** - Where do values go wrong?
4. **Fix the root cause** - Not just the symptom

---

## Questions?

If you get stuck:
1. **Re-read the context** - What should this code do?
2. **Trace it step by step** - Don't skip ahead
3. **Count loop iterations** - How many times should it run?
4. **Ask a classmate** - Explain what you think is happening
5. **Ask your instructor** - We can guide you to find the bug

Good luck! Finding bugs is where real programming skill develops. 🐛→🔧
