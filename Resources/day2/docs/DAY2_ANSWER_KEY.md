# PROG2 Day 2: Exercise Answer Key (Instructor Guide)

---

## EXERCISE SET 1: Compound Conditions - ANSWERS

### Exercise 2.1: Simple AND Condition

**Expected Output:**
```
You can drive
```

**Explanation:**
- `age = 20`
- `hasLicense = 1`
- Condition 1: `age >= 18` → TRUE (20 >= 18) ✓
- Condition 2: `hasLicense == 1` → TRUE (1 == 1) ✓
- AND result: TRUE AND TRUE = TRUE
- The if block executes
- Prints: "You can drive"

**Common Mistakes:**
- Student writes "You cannot drive" (didn't properly evaluate AND)
- Student forgets to check the second condition
- Student confuses the `==` (comparison) with `=` (assignment)

---

### Exercise 2.2: AND Condition with False Result

**Expected Output:**
```
You cannot drive
```

**Explanation:**
- `age = 16`
- `hasLicense = 1`
- Condition 1: `age >= 18` → FALSE (16 is not >= 18) ✗
- Condition 2: `hasLicense == 1` → TRUE (1 == 1) ✓
- AND result: FALSE AND TRUE = FALSE
- The else block executes
- Prints: "You cannot drive"

**Key Insight:** In AND, **both** conditions must be TRUE. If even one is FALSE, the whole AND is FALSE.

**Common Mistakes:**
- Student writes "You can drive" (didn't check first condition)
- Student doesn't understand that one FALSE makes the whole AND false

---

### Exercise 2.3: OR Condition

**Expected Output:**
```
It's the weekend!
```

**Explanation:**
- `day = 6`
- Condition 1: `day == 6` → TRUE (6 == 6) ✓
- Condition 2: `day == 7` → FALSE (6 is not == 7) ✗
- OR result: TRUE OR FALSE = TRUE
- The if block executes
- Prints: "It's the weekend!"

**Key Insight:** In OR, only **one** condition needs to be TRUE. If even one is TRUE, the whole OR is TRUE.

**Common Mistakes:**
- Student confuses AND with OR (expects both to need true)
- Student writes "It's a weekday" (didn't properly evaluate OR)

---

### Exercise 2.4: Complex AND with Multiple Variables

**Expected Output:**
```
Grade: A
```

**Explanation:**
- `score = 85`
- `attendance = 1`
- First condition: `score >= 80 && attendance == 1`
  - `score >= 80` → TRUE (85 >= 80) ✓
  - `attendance == 1` → TRUE (1 == 1) ✓
  - AND result: TRUE AND TRUE = TRUE ✓ **This branch executes**
- The program stops checking (if-else-if stops at first TRUE)
- Prints: "Grade: A"

**Key Insight:** In if-else-if chains, only the first TRUE condition executes. All others are skipped.

**Common Mistakes:**
- Student writes "Grade: B" (didn't check the AND properly)
- Student continues checking even after finding TRUE condition

---

### Exercise 2.5: OR with Multiple Conditions

**Expected Output:**
```
Passing grade
```

**Explanation:**
- `grade = 'B'` (The ASCII value of 'B' is 66)
- Check 1: `grade == 'A'` → FALSE (66 is not 65) ✗
- Check 2: `grade == 'B'` → TRUE (66 == 66) ✓ **Stop here!**
- OR result: FALSE OR TRUE = TRUE
- The if block executes
- Prints: "Passing grade"

**Key Insight:** In OR chains, only ONE condition needs to be TRUE. As soon as you find TRUE, the whole expression is TRUE.

**Common Mistakes:**
- Student doesn't understand character comparisons ('A', 'B', etc.)
- Student thinks all conditions must be checked even after finding TRUE

---

## EXERCISE SET 2: Simple While Loops - ANSWERS

### Exercise 3.1: Basic While Loop Counter

**Expected Output:**
```
Count: 1
Count: 2
Count: 3
```

**Trace:**
```
Before loop: count = 1
Check condition: count <= 3? YES

Iteration 1:
- Print: "Count: 1"
- count = count + 1 = 1 + 1 = 2
- Check condition: count <= 3? YES

Iteration 2:
- Print: "Count: 2"
- count = count + 1 = 2 + 1 = 3
- Check condition: count <= 3? YES

Iteration 3:
- Print: "Count: 3"
- count = count + 1 = 3 + 1 = 4
- Check condition: count <= 3? NO

Loop exits when: count = 4
```

**Explanation:**
- Loop runs while count <= 3 (three iterations)
- Each iteration prints count, then increments by 1
- After third iteration, count becomes 4, loop condition becomes false

**Common Mistakes:**
- Student includes the "Count: 4" (forgets the loop condition check)
- Student misses one iteration
- Student doesn't show the condition check each iteration

---

### Exercise 3.2: While Loop with Accumulation

**Expected Output:**
```
Sum: 10
```

**Trace:**
```
Initial: i = 0, sum = 0

Iteration 1:
- i + 1 = 0 + 1 = 1
- sum = sum + (i+1) = 0 + 1 = 1
- i = i + 1 = 0 + 1 = 1
- Check: i < 4? YES

Iteration 2:
- i + 1 = 1 + 1 = 2
- sum = sum + (i+1) = 1 + 2 = 3
- i = i + 1 = 1 + 1 = 2
- Check: i < 4? YES

Iteration 3:
- i + 1 = 2 + 1 = 3
- sum = sum + (i+1) = 3 + 3 = 6
- i = i + 1 = 2 + 1 = 3
- Check: i < 4? YES

Iteration 4:
- i + 1 = 3 + 1 = 4
- sum = sum + (i+1) = 6 + 4 = 10
- i = i + 1 = 3 + 1 = 4
- Check: i < 4? NO

Loop exits when: i = 4 (condition i < 4 is FALSE)

Final output: Sum: 10
```

**Explanation:**
- Loop accumulates 1 + 2 + 3 + 4 = 10
- Variable i tracks current value (0, 1, 2, 3)
- Variable sum tracks accumulated total

**Common Mistakes:**
- Student gets "Sum: 6" (stops too early)
- Student gets "Sum: 15" (includes extra iteration)
- Student doesn't track both variables

---

### Exercise 3.3: While Loop with Early Condition Change

**Expected Output:**
```
5 3 1
```

**Trace:**
```
Initial: x = 5

Iteration 1:
- Print: "5 "
- x = x - 2 = 5 - 2 = 3
- Check: x > 0? YES

Iteration 2:
- Print: "3 "
- x = x - 2 = 3 - 2 = 1
- Check: x > 0? YES

Iteration 3:
- Print: "1 "
- x = x - 2 = 1 - 2 = -1
- Check: x > 0? NO

Loop exits when: x = -1

Final output: 5 3 1
```

**Explanation:**
- Loop prints x and decrements by 2 each iteration
- Stops when x <= 0
- Output shows three values with trailing space, then newline

**Common Mistakes:**
- Student forgets to include the space in output (" ")
- Student includes extra values (like -1)
- Student miscounts loop iterations

---

## EXERCISE SET 3: Nested Conditions & Loops - ANSWERS

### Exercise 4.1: If Inside While Loop

**Expected Output:**
```
1 is odd
2 is even
3 is odd
4 is even
```

**Trace:**
```
Initial: i = 1

Iteration 1: i = 1
- i % 2 == 0? NO (1 % 2 = 1, which is not 0)
- Execute else branch
- Print: "1 is odd"
- i = i + 1 = 2

Iteration 2: i = 2
- i % 2 == 0? YES (2 % 2 = 0)
- Execute if branch
- Print: "2 is even"
- i = i + 1 = 3

Iteration 3: i = 3
- i % 2 == 0? NO (3 % 2 = 1, which is not 0)
- Execute else branch
- Print: "3 is odd"
- i = i + 1 = 4

Iteration 4: i = 4
- i % 2 == 0? YES (4 % 2 = 0)
- Execute if branch
- Print: "4 is even"
- i = i + 1 = 5

Check: i <= 4? NO (loop exits)

Final output:
1 is odd
2 is even
3 is odd
4 is even
```

**Explanation:**
- Loop runs 4 times (i = 1, 2, 3, 4)
- Each iteration checks if i is even (i % 2 == 0) or odd
- Even iterations (i=2, 4) execute if block
- Odd iterations (i=1, 3) execute else block

**Common Mistakes:**
- Student doesn't understand modulo operator (%)
- Student skips iterations
- Student forgets the loop condition check

---

### Exercise 4.2: Condition with AND Inside Loop

**Expected Output:**
```
Count: 2
```

**Trace:**
```
Initial: count = 0, i = 1

Iteration 1: i = 1
- i > 2? NO (1 is not > 2)
- i < 5? YES (1 < 5)
- AND result: NO AND YES = NO
- count stays 0
- i = 2

Iteration 2: i = 2
- i > 2? NO (2 is not > 2)
- i < 5? YES (2 < 5)
- AND result: NO AND YES = NO
- count stays 0
- i = 3

Iteration 3: i = 3
- i > 2? YES (3 > 2) ✓
- i < 5? YES (3 < 5) ✓
- AND result: YES AND YES = YES
- count = count + 1 = 0 + 1 = 1
- i = 4

Iteration 4: i = 4
- i > 2? YES (4 > 2) ✓
- i < 5? YES (4 < 5) ✓
- AND result: YES AND YES = YES
- count = count + 1 = 1 + 1 = 2
- i = 5

Iteration 5: i = 5
- i > 2? YES (5 > 2) ✓
- i < 5? NO (5 is not < 5) ✗
- AND result: YES AND NO = NO
- count stays 2
- i = 6

Loop exits: i > 5

Final output: Count: 2
```

**Explanation:**
- The condition (i > 2 AND i < 5) is satisfied when i = 3 or i = 4
- count increments exactly 2 times
- This is a common pattern: "count items in a range"

**Key Insight:** For AND to be true, **both** conditions must be true.
- i=1: first part false → AND is false
- i=2: first part false → AND is false
- i=3: both parts true → AND is true ✓
- i=4: both parts true → AND is true ✓
- i=5: second part false → AND is false

**Common Mistakes:**
- Student writes "Count: 3" (miscounts iterations)
- Student writes "Count: 4" (includes i=2 or i=5)
- Student doesn't understand that BOTH parts must be true for AND

---

## EXERCISE SET 4: Error Finding - ANSWERS

### Exercise 5.1: Wrong Loop Condition

**The Issue:**
```c
while (i < 4) {    // Condition is i < 4, NOT i <= 4
```

**What it prints:** `1 2 3 ` (three values)

**Is there an error? YES**
- The code should print 1, 2, 3, 4
- But it prints 1, 2, 3 (missing 4)
- The loop stops when i < 4 becomes false (when i = 4)

**Fix Option 1:**
```c
while (i <= 4) {   // Change < to <=
```

**Fix Option 2:**
```c
while (i < 5) {    // Change 4 to 5
```

**Teaching Note:** This is an off-by-one error, very common in loops.

---

### Exercise 5.2: Compound Condition Logic Error

**What it outputs:** `Eligible for loan`

**Is the logic correct? YES** - Actually, this code is correct!
- age = 20 (>= 18) ✓
- OR: Only one needs to be true
- First condition is true, so eligible

**Alternative scenario:** If you wanted to require BOTH conditions:
```c
if (age >= 18 && income >= 50000) {  // Change OR to AND
```

**Teaching Note:** This teaches students to read carefully before assuming errors.

---

## EXERCISE SET 5: Output Prediction - ANSWERS

### Exercise 6.1
**Output:** `X is big`
- x = 10, y = 5
- 10 > 5? YES and 10 > 8? YES
- AND result: YES AND YES = YES
- Prints "X is big"

---

### Exercise 6.2
**Output:** `Count: 6`
- Loop: count starts at 0
- Iteration 1: count = 0 + 2 = 2, check 2 < 5? YES
- Iteration 2: count = 2 + 2 = 4, check 4 < 5? YES
- Iteration 3: count = 4 + 2 = 6, check 6 < 5? NO
- Loop runs 3 times, final count = 6

---

### Exercise 6.3
**Output:** `Found 2`
- Loop runs while i <= 3 (i = 1, 2, 3)
- Only when i = 2, the if condition is true
- Prints "Found 2" once

---

### Exercise 6.4
**Output:** `Outside range`
- num = 10
- 10 > 5? YES
- OR: Only one needs true
- Condition is true, prints "Outside range"
- (The "range" refers to values NOT greater than 5 AND NOT less than 0)

---

### Exercise 6.5
**Output:** `Total: 6`
- Loop: i = 1, 2, 3
- i = 1: i > 1? NO → skip, total stays 1
- i = 2: i > 1? YES → total = 1 * 2 = 2
- i = 3: i > 1? YES → total = 2 * 3 = 6
- This calculates 2 × 3 = 6 (factorial-like pattern)

---

## Teaching Notes & Discussion Points

### What to Look For in Student Work:

1. **Compound Condition Evaluation:**
   - Do they evaluate both parts of AND/OR?
   - Do they understand that AND requires both TRUE?
   - Do they understand that OR requires only one TRUE?

2. **Loop Tracing Quality:**
   - Do they check condition before/after each iteration?
   - Do they track variable updates correctly?
   - Do they show the order of operations?

3. **Mixed Logic:**
   - Can they combine conditions with loops?
   - Do they understand precedence (loop runs, then condition checked)?
   - Do they update variables in correct order?

### Common Student Errors to Address:

1. **AND/OR Confusion:**
   - "Both must be true" (AND) vs "Only one must be true" (OR)
   - Evaluating only one part of the condition
   - Writing AND when they mean OR

2. **Loop Condition Mistakes:**
   - Off-by-one errors (< vs <=)
   - Not checking condition each iteration
   - Forgetting when loop actually stops

3. **Nested Logic Errors:**
   - Not understanding precedence
   - Skipping iterations when checking nested conditions
   - Losing track of multiple variables

### Class Discussion Ideas:

1. **Exercise 2.2 vs 2.1:**
   - "Why did changing age to 16 change the output?"
   - "What does AND require?"
   - "What if we changed it to OR?"

2. **Exercise 3.2:**
   - "Is this adding or multiplying?"
   - "What sum do we get? 1+2+3+4?"
   - "How do you track an accumulator?"

3. **Exercise 4.2:**
   - "Which values of i were included?"
   - "Why didn't i=2 or i=5 count?"
   - "When is i > 2 AND i < 5 true?"

4. **General:**
   - Praise accurate condition tracing
   - Discuss why AND/OR confusion is common
   - Show how tracing prevents bugs

---

## Grading Tips

- **Full Credit (90-100%):** All exercises complete, traces shown, explanations clear, correct answers
- **Good (75-89%):** Most exercises complete, traces shown for most, clear explanations, minor errors
- **Developing (60-74%):** Some exercises incomplete, some traces shown, explanations brief, some errors
- **Needs Support (<60%):** Many incomplete, little work shown, no explanations, multiple errors

### Award Partial Credit For:
- Correct trace even if final answer wrong
- Clear explanation of AND/OR logic even if output wrong
- Showing condition checks even if missed one iteration

---

## Reflection Questions

Ask students:
- Which was harder - AND or OR? Why?
- Did any condition evaluation surprise you?
- How is tracing a while loop different from an if statement?
- What mistake did you make the most?
