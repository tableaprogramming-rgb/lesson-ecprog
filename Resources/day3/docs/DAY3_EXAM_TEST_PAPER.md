# PROG2 Day 3: Debugging Exam

**Exam Date:** ________________
**Student Name:** ________________
**Time Limit:** 60 minutes
**Total Points:** 100

---

## EXAM INSTRUCTIONS

**Rules:**
1. You may use pen and paper for tracing
2. You may NOT use a compiler or IDE
3. You may NOT ask for help from others
4. Show ALL your work - line numbers, traces, and explanations

**Answer Format:**
- Write your answers on separate answer sheets
- Label each answer clearly (Question 1, Question 2, etc.)
- Show all traces and work for full credit

**Scoring:**
- Each question: 25 points
- Total: 100 points

---

## QUESTION 1: Multiple Condition Bug (25 points)

**Context:** This program should count how many numbers between 1 and 20 are positive AND greater than 10.
- Expected output: `Count: 10` (numbers 11-20)
- Actual output: `Count: 20`

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

**Your Task:**
1. Find the bug (what line(s) have the error?)
2. Explain why this causes the wrong output
3. Trace with 3 test values: i = 5, i = 15, i = 1
4. Write the corrected if condition
5. Verify the fix produces `Count: 10`

---

## QUESTION 2: Loop Boundary with Increment (25 points)

**Context:** This program should calculate the factorial of 5 (5! = 120)
- Expected output: `5! = 120`
- Actual output: `5! = 24`

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

**Your Task:**
1. Find the bug (what's wrong with the loop condition?)
2. Trace what gets multiplied at each iteration
3. Explain why 24 appears instead of 120
4. Write the corrected loop condition
5. Verify your fix produces 120

---

## QUESTION 3: Nested Logic Error (25 points)

**Context:** This program determines if a year is a leap year.
- A leap year is divisible by 4 AND (NOT divisible by 100 OR divisible by 400)

**Test Cases:**
- 2000 → "Leap year" ✓ (correct)
- 1900 → "Leap year" ✗ (WRONG - should be "Not a leap year")
- 2020 → "Leap year" ✓ (correct)
- 2019 → "Not a leap year" ✓ (correct)

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

**Your Task:**
1. Find the bug in the condition (line 6)
2. Analyze why year 1900 incorrectly prints "Leap year"
3. Trace 1900 through the buggy condition
4. Write the corrected if condition
5. Verify your fix with all 4 test cases

---

## QUESTION 4: Combined Logic and Boundary Bug (25 points)

**Context:** This program should sum all EVEN numbers from 10 to 15
- Expected output: `Sum of evens: 36` (10 + 12 + 14 = 36)
- Actual output: Code does NOT compile

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

**Your Task:**
1. Find ALL bugs (there are 2 bugs!)
2. Explain what's wrong with each bug
3. Write the corrected lines
4. Trace through each iteration of the fixed code
5. Verify your fix produces 36

---

## ANSWER SHEET TEMPLATE

Use separate paper for your answers. Format each answer like this:

```
QUESTION 1:

Bug location: _________________

Explanation: _________________
_______________________________

Test traces: ...

The fix: ...

Verification: ...
```

---

**END OF EXAM**

**Time Management Tips:**
- Question 1: ~15 minutes
- Question 2: ~12 minutes
- Question 3: ~15 minutes
- Question 4: ~15 minutes
- Review: ~3 minutes

Good luck! 🐛→🔧
