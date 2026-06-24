# PROG2 Day 4: Advanced Debugging Exercises
## Mastering Bug Identification and Tracing

---

## How to Approach These Exercises

**DEBUGGING MASTERY REQUIRES:**
1. **Read carefully** - Understand what the code SHOULD do
2. **Predict mentally** - What will it ACTUALLY do?
3. **Trace step-by-step** - Follow each variable through execution
4. **Find the bug** - Identify which line and what's wrong
5. **Explain thoroughly** - Why does this cause the error?
6. **Write the fix** - Correct it properly
7. **Verify your fix** - Trace the corrected code

**TOOLS YOU NEED:**
- Pen and paper
- Your understanding of C logic
- Patience to trace line-by-line

---

## EXERCISE SET 1: Logic Operator Bugs

### Exercise 1.1: Range Check Bug

**Context:** This program should count numbers between 5 and 15 (inclusive).

**Expected Output:** Count numbers where: 5 ≤ i ≤ 15

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;

    for (int i = 1; i <= 20; i++) {
        if (i > 5 || i < 15) {      // ← BUG
            count++;
        }
    }

    printf("Numbers in range: %d\n", count);

    return 0;
}
```

**What it ACTUALLY outputs:** `Numbers in range: 19`

**Expected output:** `Numbers in range: 11` (the numbers 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15)

**Your Task:**

1. **Find the bug:** Which line has the error?

2. **Trace a few values:**
   ```
   i = 3:  (3 > 5 || 3 < 15) = ? → Counted? (Should be NO)
   i = 5:  (5 > 5 || 5 < 15) = ? → Counted? (Should be YES)
   i = 10: (10 > 5 || 10 < 15) = ? → Counted? (Should be YES)
   i = 16: (16 > 5 || 16 < 15) = ? → Counted? (Should be NO)
   ```

3. **Explain what's wrong:**

4. **Write the fix:**

5. **Verify your fix with tracing:**

---

### Exercise 1.2: Even/Odd Filter Bug

**Context:** This program should count EVEN numbers from 1 to 10.

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;

    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 1) {          // ← BUG
            count++;
        }
    }

    printf("Even numbers: %d\n", count);

    return 0;
}
```

**What it ACTUALLY outputs:** `Even numbers: 5`

**Expected output:** `Even numbers: 5` (numbers 2, 4, 6, 8, 10)

**Your Task:**

1. **Find the bug:** What does `i % 2 == 1` check for?

2. **Trace:**
   ```
   i = 2: 2 % 2 == 1? → ? → Counted?
   i = 4: 4 % 2 == 1? → ? → Counted?
   i = 1: 1 % 2 == 1? → ? → Counted?
   i = 3: 3 % 2 == 1? → ? → Counted?
   ```

3. **Explain:** Is the bug in the condition or the variable name?

4. **Write the fix:**

5. **Verify:**

---

## EXERCISE SET 2: Counter & Accumulator Bugs

### Exercise 2.1: Double Counting Bug

**Context:** Count numbers divisible by 3 in range 1-20.

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;

    for (int i = 1; i <= 20; i++) {
        if (i % 3 == 0) {
            count++;
            count++;                // ← BUG
        }
    }

    printf("Divisible by 3: %d\n", count);

    return 0;
}
```

**What it ACTUALLY outputs:** `Divisible by 3: 12`

**Expected output:** `Divisible by 3: 6` (numbers 3, 6, 9, 12, 15, 18)

**Your Task:**

1. **Find the bug:** What line and why?

2. **Count manually:** How many numbers from 1 to 20 are divisible by 3?

3. **Trace the bug:**
   ```
   When i = 3:  count++ happens how many times?
   When i = 6:  count++ happens how many times?
   ```

4. **Explain:** Why does this produce 12 instead of 6?

5. **Write the fix:**

---

### Exercise 2.2: Wrong Accumulator

**Context:** Calculate sum of multiples of 5 from 1 to 50.

**Expected:** 5 + 10 + 15 + 20 + 25 + 30 + 35 + 40 + 45 + 50 = 275

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int sum = 0;
    int count = 0;

    for (int i = 1; i <= 50; i++) {
        if (i % 5 == 0) {
            count = count + i;      // ← BUG
        }
    }

    printf("Sum of multiples: %d\n", count);

    return 0;
}
```

**What it ACTUALLY outputs:** `Sum of multiples: 275`

**Expected output:** Same, but uses the wrong variable

**Your Task:**

1. **Find the bug:** Which line?

2. **Identify the problem:** What variable should be used?

3. **Trace:**
   ```
   When i = 5:  What gets updated? (sum or count?)
   When i = 10: What gets updated?
   After loop:  sum = ?   count = ?
   ```

4. **Explain:** Why is this a logic error even if the output seems correct?

5. **Write the fix:**

6. **Why this matters:** What goes wrong if we use `printf("Sum: %d, Count: %d\n", sum, count);`?

---

## EXERCISE SET 3: Loop Control Bugs

### Exercise 3.1: Loop Increment Wrong Position

**Context:** Print numbers 1 to 5.

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int i = 1;

    while (i <= 5) {
        printf("%d ", i);
        i = i + 2;              // ← BUG
    }

    printf("\n");

    return 0;
}
```

**What it ACTUALLY outputs:** `1 3 5`

**Expected output:** `1 2 3 4 5`

**Your Task:**

1. **Find the bug:** What's the increment issue?

2. **Trace:**
   ```
   i = 1: Print 1, then i = 1 + 2 = 3
   i = 3: Print 3, then i = 3 + 2 = 5
   i = 5: Print 5, then i = 5 + 2 = 7
   i = 7: Is 7 <= 5? NO → Loop exits
   ```

3. **Explain:** Why does it skip 2 and 4?

4. **Write the fix:**

---

### Exercise 3.2: Nested Loop Off-by-One

**Context:** Print a 3×3 grid of asterisks.

**Expected Output:**
```
* * *
* * *
* * *
```

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 2; col++) {    // ← BUG
            printf("* ");
        }
        printf("\n");
    }

    return 0;
}
```

**What it ACTUALLY outputs:**
```
* *
* *
* *
```

**Your Task:**

1. **Find the bug:** Which loop has the problem?

2. **Trace outer loop:**
   ```
   row = 0: Inner loop runs with col = 0, 1 (only 2 times!)
   row = 1: Inner loop runs with col = 0, 1 (only 2 times!)
   row = 2: Inner loop runs with col = 0, 1 (only 2 times!)
   ```

3. **Count asterisks:**
   - How many should print per row? (3)
   - How many actually print? (2)

4. **Write the fix:**

---

## EXERCISE SET 4: Boundary Condition Bugs

### Exercise 4.1: Condition Direction

**Context:** Count numbers less than or equal to 10 (from 1 to 20).

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;

    for (int i = 1; i <= 20; i++) {
        if (i >= 10) {              // ← BUG
            count++;
        }
    }

    printf("Count: %d\n", count);

    return 0;
}
```

**What it ACTUALLY outputs:** `Count: 11`

**Expected output:** `Count: 10` (numbers 1 through 10)

**Your Task:**

1. **Find the bug:** What's the condition checking?

2. **List numbers that match the buggy condition:**
   - Which numbers satisfy `i >= 10`?
   - How many? (10, 11, 12, ..., 20)

3. **List expected numbers:**
   - Which numbers should be counted? (1-10)
   - How many? (10)

4. **Explain:** What operator should be used instead of `>=`?

5. **Write the fix:**

---

### Exercise 4.2: Sentinel Value Bug

**Context:** Count positive numbers in a list that terminates with 0.

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;
    int num = 1;

    while (num != 0) {              // ← BUG
        count++;
        printf("Enter number: ");
        scanf("%d", &num);
    }

    printf("Positive count: %d\n", count);

    return 0;
}
```

**What happens:** If user enters: 5, 3, 8, 0
- Outputs: `Positive count: 4`

**Expected:** Should count only positive numbers, not include 0

**Your Task:**

1. **Find the bug:** What does the condition actually check?

2. **Trace with input (5, 3, 8, 0):**
   ```
   First: num = 5, count++ → count = 1, read next
   Second: num = 3, count++ → count = 2, read next
   Third: num = 8, count++ → count = 3, read next
   Fourth: num = 0, count++ → count = 4, then check 0 != 0?
   ```

3. **Identify issue:** When does it check if the number is positive?

4. **Write the fix:** (Hint: need to move the condition check)

---

## EXERCISE SET 5: Complex Logic Bugs

### Exercise 5.1: Multi-Condition Error

**Context:** Find numbers that are even AND greater than 10 (from 1-20).

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int count = 0;

    for (int i = 1; i <= 20; i++) {
        if (i % 2 == 0 && i > 10) {
            count++;
        }
    }

    printf("Even and > 10: %d\n", count);

    return 0;
}
```

**What it outputs:** `Even and > 10: 5`

**Expected output:** `Even and > 10: 5` (numbers 12, 14, 16, 18, 20)

**BUT** - Change question: What if we want "even OR greater than 10"?

**Modified Buggy Code:**
```c
if (i % 2 == 0 || i > 10) {         // ← Should this be here?
    count++;
}
```

**Your Task:**

1. **Test both conditions with i = 12:**
   ```
   With &&: (12 % 2 == 0 && 12 > 10) = ? → Counted?
   With ||: (12 % 2 == 0 || 12 > 10) = ? → Counted?
   ```

2. **Test with i = 7:**
   ```
   With &&: (7 % 2 == 0 && 7 > 10) = ? → Counted?
   With ||: (7 % 2 == 0 || 7 > 10) = ? → Counted?
   ```

3. **List all numbers that satisfy (even OR greater than 10):**

4. **Trace && vs || carefully - which should be used for different problems?**

---

## EXERCISE SET 6: Variable Scope & State Bugs

### Exercise 6.1: Variable Not Reset

**Context:** Calculate sum for 3 separate lists (should sum each independently).

**Buggy Code:**
```c
#include <stdio.h>

int main() {
    int sum;                        // ← BUG: Not initialized

    // List 1: 1 + 2 + 3
    sum = 0;
    for (int i = 1; i <= 3; i++) {
        sum += i;
    }
    printf("List 1 sum: %d\n", sum);

    // List 2: 4 + 5 + 6
    // Missing: sum = 0;
    for (int i = 4; i <= 6; i++) {
        sum += i;
    }
    printf("List 2 sum: %d\n", sum);

    // List 3: 7 + 8 + 9
    sum = 0;
    for (int i = 7; i <= 9; i++) {
        sum += i;
    }
    printf("List 3 sum: %d\n", sum);

    return 0;
}
```

**What it outputs:**
```
List 1 sum: 6        (1+2+3=6) ✓
List 2 sum: 27       (6+4+5+6=21... wait, should be 15)
List 3 sum: 24       (7+8+9=24) ✓
```

**Your Task:**

1. **Find the bug:** Which section is missing what?

2. **Calculate what List 2 should be:**
   ```
   4 + 5 + 6 = ?
   ```

3. **Calculate what List 2 actually gets:**
   ```
   sum starts as: 6 (from List 1)
   + 4 = 10
   + 5 = 15
   + 6 = 21
   So it prints: 21
   ```

4. **Explain:** Why is the output wrong even though the code looks similar?

5. **Write the fix:**

---

## Summary of Bug Types in Day 4

### You should now be able to identify:
1. **Logic operator bugs** (|| vs &&, >, <, >=, <=, ==, !=)
2. **Counter/Accumulator bugs** (incrementing wrong variable, double counting)
3. **Off-by-one errors in loops** (< vs <=, i++ placement)
4. **Nested loop bugs** (wrong iteration count in inner/outer loops)
5. **Boundary condition errors** (reversed operators, wrong limits)
6. **State management bugs** (forgetting to reset variables)
7. **Multi-condition logic errors** (AND vs OR confusion)

### Debugging Process Checklist:
- [ ] Read the code carefully
- [ ] Understand what it SHOULD do
- [ ] Predict what it will do
- [ ] Trace through with actual values
- [ ] Find which line is wrong
- [ ] Understand WHY it's wrong
- [ ] Write the correct version
- [ ] Verify the fix works

---

## Remember:
**Debugging is a SKILL that requires PRACTICE.** The more bugs you find and fix, the better you'll recognize them. Don't rush—take time to trace carefully.

Good luck! 💪
