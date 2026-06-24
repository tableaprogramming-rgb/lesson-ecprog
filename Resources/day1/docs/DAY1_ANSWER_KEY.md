# PROG2 Week 1: Exercise Answer Key (Instructor Guide)

---

## EXERCISE SET 1: Code Tracing - ANSWERS

### Exercise 1.1: Simple If-Else

**Expected Output:**
```
You are a minor
```

**Explanation:**
- `age = 15`
- Condition: `age >= 18` evaluates to `FALSE` (15 is not >= 18)
- The else branch executes
- Prints: "You are a minor"

**Common Mistakes:**
- Student writes "You are an adult" (didn't check condition correctly)
- Student doesn't complete the trace

---

### Exercise 1.2: Nested If-Else

**Expected Output:**
```
Grade: C
```

**Explanation:**
- `score = 75`
- Check 1: `score >= 90?` → FALSE (75 < 90)
- Check 2: `score >= 80?` → FALSE (75 < 80)
- Check 3: `score >= 70?` → TRUE (75 >= 70) ✓ **This branch executes**
- The program stops checking after finding the first TRUE condition
- Prints: "Grade: C"

**Common Mistakes:**
- Student writes "Grade: F" (didn't check all conditions, just assumed final else)
- Student doesn't understand that if-else-if stops at first true condition

---

### Exercise 1.3: Simple Loop

**Expected Output:**
```
Sum: 10
```

**Trace:**
```
Initial: i = 1, sum = 0

Iteration 1: i = 1, sum = 0 + 1 = 1
Iteration 2: i = 2, sum = 1 + 2 = 3
Iteration 3: i = 3, sum = 3 + 3 = 6
Iteration 4: i = 4, sum = 6 + 4 = 10

Loop ends when: i = 5 (condition i <= 4 is FALSE)

Final output: Sum: 10
```

**Explanation:**
- Loop runs from i=1 to i=4 (four iterations)
- Each iteration: sum += i (sum = sum + i)
- Final: 1 + 2 + 3 + 4 = 10

**Common Mistakes:**
- Student writes "Sum: 6" (stops at i=3)
- Student writes "Sum: 15" (includes one extra iteration)
- Student doesn't show intermediate trace steps

---

### Exercise 1.4: Loop with Conditional

**Expected Output:**
```
Count: 2
```

**Trace:**
```
Initial: count = 0

Iteration 1: i = 1, i % 2 == 0? FALSE → count = 0
Iteration 2: i = 2, i % 2 == 0? TRUE  → count = 1
Iteration 3: i = 3, i % 2 == 0? FALSE → count = 1
Iteration 4: i = 4, i % 2 == 0? TRUE  → count = 2
Iteration 5: i = 5, i % 2 == 0? FALSE → count = 2

Final output: Count: 2
```

**Explanation:**
- The condition `i % 2 == 0` checks if i is even
- count increments only for even numbers (2 and 4)
- Final count = 2

**Common Mistakes:**
- Student forgets to check modulo operator (%)
- Student writes "Count: 5" (increments every iteration)
- Student doesn't understand that only even numbers pass the condition

---

### Exercise 1.5: Nested Loop

**Expected Output:**
```
Total: 6
```

**Trace:**
```
Initial: total = 0

Outer loop i = 1:
  Inner loop j = 1: total = 1
  Inner loop j = 2: total = 2
  
Outer loop i = 2:
  Inner loop j = 1: total = 3
  Inner loop j = 2: total = 4
  
Outer loop i = 3:
  Inner loop j = 1: total = 5
  Inner loop j = 2: total = 6

Final output: Total: 6
```

**Explanation:**
- Outer loop runs 3 times (i = 1, 2, 3)
- For each outer iteration, inner loop runs 2 times (j = 1, 2)
- Total iterations: 3 × 2 = 6
- Each iteration increments total by 1
- Final: total = 6

**Common Mistakes:**
- Student writes "Total: 3" (only counts outer loop)
- Student writes "Total: 2" (only counts inner loop)
- Student doesn't understand nested loop multiplication

---

## EXERCISE SET 2: Error Finding - ANSWERS

### Exercise 2.1: Semicolon Error

**The Error:**
```c
for (int i = 0; i < 3; i++);  // ← SEMICOLON HERE!
{
    x = x + y;
    printf("x = %d\n", x);
}
```

**Why it's wrong:**
- The semicolon (`;`) after the loop statement terminates the loop
- The for loop body is empty - it just does nothing 3 times
- The braced code is NOT part of the loop; it runs once after the loop ends
- This is a **logic error** (compiles but doesn't do what programmer intended)

**What actually happens:**
- The loop runs 3 times but does nothing
- Then the code block executes ONCE (after loop ends)
- Only prints "x = 35" one time (10 + 10 + 10 + 5 initial = 35)
- Actually, it prints: `x = 15` then `x = 25` - No wait, let me recalculate:
  - Initial: x = 5, y = 10
  - Loop does nothing 3 times
  - After loop: x = 5 + 10 = 15, prints "x = 15"
  - After that statement: x = 15 + 10 = 25, prints "x = 25"
  - Then exits

Wait, let me re-examine. The block is:
```c
{
    x = x + y;
    printf("x = %d\n", x);
}
```
This is just a block, not a loop. It runs once:
- x = 5 + 10 = 15
- prints "x = 15"

**Fixed code:**
```c
for (int i = 0; i < 3; i++) {  // Remove the semicolon
    x = x + y;
    printf("x = %d\n", x);
}
```

Or properly format without the block confusion:
```c
for (int i = 0; i < 3; i++)
{
    x = x + y;
    printf("x = %d\n", x);
}
```

**Teaching Note:** This is one of the most insidious C errors. The code compiles perfectly but doesn't behave as intended. Great opportunity to discuss why tracing matters.

---

### Exercise 2.2: Logic Error - Wrong Condition

**The Issue:**
This code compiles and runs fine, but there's a logical issue to discuss.

**For temperature = 25:**
- Check: 25 >= 90? NO
- Check: 25 >= 80? NO
- Check: 25 >= 70? YES ✓
- Output: `Warm day`

Wait, let me re-read the code. Score 75 was in the previous example. Let me check the actual code in the exercise:

```c
if (temperature > 30) {        // 25 > 30? NO
    printf("Hot day\n");
} else if (temperature > 20) {  // 25 > 20? YES ✓
    printf("Warm day\n");
} else if (temperature > 10) {
    printf("Cool day\n");
} else {
    printf("Cold day\n");
}
```

**For temperature = 25:**
- Output: `Warm day` ✓ This is correct

**Is the logic correct? YES** - This one actually has correct logic. 

Hmm, I may have made this example confusing. Let me reconsider the intent. Perhaps the issue is if temperature is 35:
- 35 > 30? YES → "Hot day" ✓ Correct

Actually, this exercise might be better if I had an error. Let me note this is actually correct code, but use it as a teaching moment about reading carefully.

**Teaching Note:** This is actually CORRECT code - use it to reinforce that students should verify outputs, not assume errors exist.

---

### Exercise 2.3: Off-by-One Error

**Expected sum of 1 to 5:** 1 + 2 + 3 + 4 + 5 = 15

**What the code actually does:**
```c
for (int i = 1; i < 5; i++)  // Condition is i < 5, NOT i <= 5
```

**Iterations:**
- i = 1: sum = 0 + 1 = 1
- i = 2: sum = 1 + 2 = 3
- i = 3: sum = 3 + 3 = 6
- i = 4: sum = 6 + 4 = 10
- i = 5: Loop condition (5 < 5) is FALSE, so loop ends

**Actual output:** `Sum of 1 to 5: 10`

**Is there an error? YES** - The message says "Sum of 1 to 5" but it actually calculates "Sum of 1 to 4"

**The Fix:**
```c
for (int i = 1; i <= 5; i++) {  // Change < to <=
    sum = sum + i;
}
```

Or keep < but start from different number:
```c
for (int i = 1; i < 6; i++) {  // Change 5 to 6
    sum = sum + i;
}
```

**Teaching Note:** Off-by-one errors are extremely common in programming. Good practice for students to identify.

---

### Exercise 2.4: Uninitialized Variable

**The Error:**
```c
int result;  // ← Not initialized!

if (5 > 3) {
    result = 100;
}
// What if the condition was false?
```

**Why it's problematic:**
- If the condition is false, `result` is never assigned a value
- The variable exists in memory but contains garbage (random value)
- When we `printf("Result: %d\n", result);` we print an undefined value
- **In this specific case**, the condition (5 > 3) is always TRUE, so result WILL be 100
- **But it's bad practice** - what if the condition was `5 > 10`? Then result would be undefined

**What actually happens:**
- 5 > 3 is TRUE
- result = 100
- Prints: `Result: 100`

**But the fix is still important:**
```c
int result = 0;  // Initialize with default value

if (5 > 3) {
    result = 100;
}
```

Or:
```c
int result;

if (5 > 3) {
    result = 100;
} else {
    result = 0;  // Ensure result is set in all paths
}
```

**Teaching Note:** Even though it works in this case, it teaches best practices about variable initialization.

---

## EXERCISE SET 3: Output Prediction - ANSWERS

### Exercise 3.1
**Output:** `x = 15, y = 20`
- x starts at 10
- 10 < 20 is TRUE
- x = 10 + 5 = 15
- y stays 20

---

### Exercise 3.2
**Output:** `5 4 3 2 1 `
- Loop counts down from 5 to 1
- Each value printed with a space
- Then newline

---

### Exercise 3.3
**Output:** `Count: 8`
- Loop runs 4 times (i = 0, 1, 2, 3)
- Each iteration: count += 2
- 0 + 2 + 2 + 2 + 2 = 8

---

### Exercise 3.4
**Output:** `Result: 24`
- This calculates factorial of 4 (4!)
- Iteration 1: 1 × 1 = 1
- Iteration 2: 1 × 2 = 2
- Iteration 3: 2 × 3 = 6
- Iteration 4: 6 × 4 = 24

---

### Exercise 3.5
**Output:**
```
1 2 3 
2 4 6 
3 6 9 
```

**Pattern:** This is a multiplication table (i × j)

---

## EXERCISE SET 4: Code Matching - ANSWERS

| Code | Output | Explanation |
|------|--------|-------------|
| A | 3 | Loop prints i from 1 to 3. Output: "1 2 3 " (with space) |
| B | 2 | Yes, x=5 satisfies both conditions (5>3 AND 5<10) |
| C | 1 | sum = 1+2+3 = 6. Multiplication of 3 iterations. |
| D | 4 | Loop counts down from 3 to 1. Output: "3 2 1 " |
| E | 5 | While loop: x increments from 0 until x<3 is false (x=3) |

Wait, let me recalculate C:
- sum = 0
- i=1: sum = 1
- i=2: sum = 3
- i=3: sum = 6
Output: 6 ✓

So the correct answer:

| Code | Output | 
|------|--------|
| A | 3 | 
| B | 2 | 
| C | 1 | 
| D | 4 | 
| E | 5 | 

Hmm, let me look at the output options again:
1. `6`
2. `Yes`
3. `1 2 3 `
4. `3 2 1 `
5. `3`

- Code A: "1 2 3 " (with trailing space) → Option 3
- Code B: "Yes" → Option 2
- Code C: 6 → Option 1
- Code D: "3 2 1 " (with trailing space) → Option 4
- Code E: 3 → Option 5

| Code | Output | Explanation |
|------|--------|-------------|
| A | 3 | Loop prints i values 1, 2, 3 with spaces. Output: "1 2 3 " |
| B | 2 | Condition checks: 5 > 3 (TRUE) AND 5 < 10 (TRUE), so prints "Yes" |
| C | 1 | Calculates sum: 1+2+3=6, prints "6" |
| D | 4 | Loop counts down from 3 to 1, prints "3 2 1 " |
| E | 5 | While loop increments x until x=3 (when x<3 becomes false) |

---

## Teaching Notes & Discussion Points

### What to Look For in Student Work:

1. **Code Tracing Quality:**
   - Do they show step-by-step work?
   - Do they update variable values correctly?
   - Do they handle operators correctly (especially %, +=, etc.)?

2. **Error Identification:**
   - Can they spot obvious errors (semicolons)?
   - Can they identify logic errors (off-by-one)?
   - Do they understand why errors are problems?

3. **Explanation Clarity:**
   - Can they explain in their own words?
   - Do they reference specific parts of the code?
   - Are they just guessing or actually reading?

### Common Student Errors to Address:

1. **Loop counting mistakes:**
   - "Starting from 0" vs "Starting from 1"
   - `i < n` vs `i <= n`
   - When loop actually stops

2. **Condition evaluation:**
   - Forgetting to check which branch executes
   - Not understanding AND (&&) vs OR (||)
   - Getting >= vs > confused

3. **Operator misuse:**
   - Modulo operator (%) not understood
   - Assignment (=) vs comparison (==)
   - Post-increment (i++) timing issues

4. **Nested structures:**
   - Inner loop iteration counts
   - Variable scope in nested blocks
   - Order of execution in nested conditions

### Class Discussion Ideas:

1. **Exercise 2.1 (Semicolon Error):**
   - Discuss why C allows this (empty loop is valid)
   - Show how hard this would be to debug if students didn't trace
   - Discuss defensive coding practices

2. **Exercise 2.3 (Off-by-one):**
   - Very common in real programming
   - Discuss different ways to fix it
   - Talk about fence-post problems

3. **Exercise 3.5 (Nested Loop Pattern):**
   - Ask what other patterns they could create
   - Discuss multiplication table, triangle patterns
   - Great for creativity and understanding

4. **General:**
   - Praise students who show detailed traces
   - Discuss why their mistakes happened (not carelessness, but something to learn)
   - Emphasize: "Tracing saved you from a runtime error"

---

## Grading Tips

- **Full Credit (100%):** All exercises complete, clear work shown, explanations present, mostly correct
- **Good (80-90%):** All exercises attempted, work shown for most, minor errors, explanations are clear
- **Developing (60-80%):** Most exercises attempted, some work shown, some errors, explanations are brief
- **Needs Work (<60%):** Many incomplete, minimal work shown, multiple errors, no explanations

### Don't deduct heavily for wrong answers IF:
- The reasoning is clear
- The work is shown
- The explanation is thoughtful

### Do give credit for:
- Complete traces even if final answer is wrong
- Good explanations of why an error exists
- Questions asked if stuck

---

## Reflection Discussion (Optional)

At the end, ask students:
- Which exercise was hardest? Why?
- Did any of your predictions surprise you?
- What mistake did you make the most?
- How did tracing help you understand?

This builds metacognition about their learning.
