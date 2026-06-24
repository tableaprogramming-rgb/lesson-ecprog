# PROG2 Day 2: Code Reading Exercises
## Control Structures - Stepping Up (Compound Conditions & Repetition)

---

## Important: How to Approach These Exercises

**READ THE CODE CAREFULLY.** Your goal is to:
1. Understand what each line does
2. Trace through the execution step-by-step
3. Track how variables change
4. Predict the output **before** running the code
5. Explain your reasoning

**NO INTERNET. NO AI.** The only tool you need is:
- Pen and paper
- Your brain
- Your understanding of C fundamentals and Day 1 concepts

If you don't understand something, ask your classmate or instructor—not Google.

**Note:** Day 2 builds on Day 1. Make sure you're comfortable with simple if-else and basic loops before starting!

---

## EXERCISE SET 1: Compound Conditions (AND / OR Operators)

### Instructions
For each program below:
1. **Read the code carefully** - line by line
2. **Evaluate the condition** - check both parts if AND/OR is used
3. **Predict the output** - what will print?
4. **Explain your work** - show how you evaluated the condition
5. **Then verify** - run the code and compare

---

### Exercise 2.1: Simple AND Condition (Level 1)

```c
#include <stdio.h>

int main() {
    int age = 20;
    int hasLicense = 1;  // 1 = true, 0 = false

    if (age >= 18 && hasLicense == 1) {
        printf("You can drive\n");
    } else {
        printf("You cannot drive\n");
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- Trace through both conditions (age >= 18 AND hasLicense == 1)

**Show your work:**
```
Variable trace:
- age = _______
- hasLicense = _______
- Condition 1: age >= 18? _______
- Condition 2: hasLicense == 1? _______
- AND result: _______ AND _______ = _______
- Which branch executes? _____________
- Output: ___________________________
```

---

### Exercise 2.2: AND Condition with False Result (Level 2)

```c
#include <stdio.h>

int main() {
    int age = 16;
    int hasLicense = 1;

    if (age >= 18 && hasLicense == 1) {
        printf("You can drive\n");
    } else {
        printf("You cannot drive\n");
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- Why is the output different from Exercise 2.1?

**Show your work:**
```
Variable trace:
- age = _______
- hasLicense = _______
- Condition 1: age >= 18? _______
- Condition 2: hasLicense == 1? _______
- AND result: _______ AND _______ = _______
- Which branch executes? _____________
- Output: ___________________________

Explanation: Why does the AND result in false?
__________________________________________________________
```

---

### Exercise 2.3: OR Condition (Level 2)

```c
#include <stdio.h>

int main() {
    int day = 6;  // 1=Mon, 2=Tue, ..., 6=Sat, 7=Sun

    if (day == 6 || day == 7) {
        printf("It's the weekend!\n");
    } else {
        printf("It's a weekday\n");
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- Why does OR work differently than AND?

**Show your work:**
```
Variable trace:
- day = _______
- Condition 1: day == 6? _______
- Condition 2: day == 7? _______
- OR result: _______ OR _______ = _______
- Which branch executes? _____________
- Output: ___________________________

Explanation: How does OR differ from AND?
__________________________________________________________
```

---

### Exercise 2.4: Complex AND with Multiple Variables (Level 3)

```c
#include <stdio.h>

int main() {
    int score = 85;
    int attendance = 1;  // 1 = perfect, 0 = missing classes

    if (score >= 80 && attendance == 1) {
        printf("Grade: A\n");
    } else if (score >= 80) {
        printf("Grade: B\n");
    } else {
        printf("Grade: C\n");
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- Trace through each condition check in order

**Show your work:**
```
Variable trace:
- score = _______
- attendance = _______

First condition: score >= 80 && attendance == 1
- score >= 80? _______
- attendance == 1? _______
- AND result: _______
- Does this branch execute? _______

Output: ___________________________

Why did we stop checking after the first condition?
__________________________________________________________
```

---

### Exercise 2.5: OR with Multiple Conditions (Level 3 - Challenge)

```c
#include <stdio.h>

int main() {
    int grade = 'B';  // 'A'=65, 'B'=66, 'C'=67, etc.

    if (grade == 'A' || grade == 'B' || grade == 'C') {
        printf("Passing grade\n");
    } else {
        printf("Failing grade\n");
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- How many conditions need to be true for the if block to execute?

**Show your work:**
```
Variable trace:
- grade = _______

Condition checks (stop at first TRUE):
- Condition 1: grade == 'A'? _______
- Condition 2: grade == 'B'? _______
- Condition 3: grade == 'C'? _______

OR result: Does ANY condition need to be true? _______
Which branch executes? _____________
Output: ___________________________
```

---

## EXERCISE SET 2: Simple While Loops

### Instructions
For each program below:
1. **Read the code carefully** - identify loop condition
2. **Create iteration trace** - show each loop iteration
3. **Predict the output** - what will print?
4. **Explain your work** - show variable changes each iteration
5. **Then verify** - run the code and compare

---

### Exercise 3.1: Basic While Loop Counter (Level 2)

```c
#include <stdio.h>

int main() {
    int count = 1;

    while (count <= 3) {
        printf("Count: %d\n", count);
        count = count + 1;
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- How many times does the loop run?

**Show your work:**
```
Variable trace:

Before loop: count = _______

Check condition: count <= 3? _______

Iteration 1:
- Print: _____________________________
- count = ____________________________
- Check condition: count <= 3? _______

Iteration 2:
- Print: _____________________________
- count = ____________________________
- Check condition: count <= 3? _______

Iteration 3:
- Print: _____________________________
- count = ____________________________
- Check condition: count <= 3? _______

Check condition again: count <= 3? _______
Loop exits when: count = _______

Final output:
___________________________
___________________________
___________________________
```

---

### Exercise 3.2: While Loop with Accumulation (Level 2)

```c
#include <stdio.h>

int main() {
    int i = 0;
    int sum = 0;

    while (i < 4) {
        sum = sum + (i + 1);
        i = i + 1;
    }

    printf("Sum: %d\n", sum);

    return 0;
}
```

**Your Task:**
- What is the final sum?
- Show how sum changes each iteration

**Show your work:**
```
Variable trace:

Initial: i = _______, sum = _______

Iteration 1:
- i + 1 = _______
- sum = sum + (i+1) = _______ + _______ = _______
- i = i + 1 = _______
- Check: i < 4? _______

Iteration 2:
- i + 1 = _______
- sum = sum + (i+1) = _______ + _______ = _______
- i = i + 1 = _______
- Check: i < 4? _______

Iteration 3:
- i + 1 = _______
- sum = sum + (i+1) = _______ + _______ = _______
- i = i + 1 = _______
- Check: i < 4? _______

Iteration 4:
- i + 1 = _______
- sum = sum + (i+1) = _______ + _______ = _______
- i = i + 1 = _______
- Check: i < 4? _______

Loop exits when: i = _______ (condition i < 4 is ______)

Final output: ___________________________
```

---

### Exercise 3.3: While Loop with Early Condition Change (Level 3)

```c
#include <stdio.h>

int main() {
    int x = 5;

    while (x > 0) {
        printf("%d ", x);
        x = x - 2;
    }
    printf("\n");

    return 0;
}
```

**Your Task:**
- What will this program output?
- Track how x changes each iteration

**Show your work:**
```
Variable trace:

Initial: x = _______

Iteration 1:
- Print: _______
- x = x - 2 = _______ - 2 = _______
- Check: x > 0? _______

Iteration 2:
- Print: _______
- x = x - 2 = _______ - 2 = _______
- Check: x > 0? _______

Iteration 3:
- Print: _______
- x = x - 2 = _______ - 2 = _______
- Check: x > 0? _______

Loop exits when: x = _______

Final output (with all prints):
___________________________
```

---

## EXERCISE SET 3: Nested Conditions & Loops

### Instructions
For each program below:
1. **Read carefully** - understand both the condition and loop
2. **Trace execution** - show condition checks and loop iterations
3. **Predict output** - what will print?
4. **Explain** - how condition and loop interact
5. **Verify** - run and compare

---

### Exercise 4.1: If Inside While Loop (Level 3)

```c
#include <stdio.h>

int main() {
    int i = 1;

    while (i <= 4) {
        if (i % 2 == 0) {
            printf("%d is even\n", i);
        } else {
            printf("%d is odd\n", i);
        }
        i = i + 1;
    }

    return 0;
}
```

**Your Task:**
- What will this program output?
- Which iterations print "is even" vs "is odd"?

**Show your work:**
```
Variable trace:

Initial: i = _______

Iteration 1: i = 1
- i % 2 == 0? _______
- Which branch? _____________
- Print: _____________________________
- i = _______

Iteration 2: i = 2
- i % 2 == 0? _______
- Which branch? _____________
- Print: _____________________________
- i = _______

Iteration 3: i = 3
- i % 2 == 0? _______
- Which branch? _____________
- Print: _____________________________
- i = _______

Iteration 4: i = 4
- i % 2 == 0? _______
- Which branch? _____________
- Print: _____________________________
- i = _______

Check: i <= 4? _______ (loop exits)

Final output:
___________________________
___________________________
___________________________
___________________________
```

---

### Exercise 4.2: Condition with AND Inside Loop (Level 3 - Challenge)

```c
#include <stdio.h>

int main() {
    int count = 0;
    int i = 1;

    while (i <= 5) {
        if (i > 2 && i < 5) {
            count = count + 1;
        }
        i = i + 1;
    }

    printf("Count: %d\n", count);

    return 0;
}
```

**Your Task:**
- What is the final count?
- Which iterations satisfy (i > 2 AND i < 5)?

**Show your work:**
```
Variable trace:

Initial: count = _______, i = _______

Iteration 1: i = 1
- i > 2? _______ AND i < 5? _______
- AND result = _______
- count = _______

Iteration 2: i = 2
- i > 2? _______ AND i < 5? _______
- AND result = _______
- count = _______

Iteration 3: i = 3
- i > 2? _______ AND i < 5? _______
- AND result = _______
- count = _______
- increment: count = _______

Iteration 4: i = 4
- i > 2? _______ AND i < 5? _______
- AND result = _______
- count = _______
- increment: count = _______

Iteration 5: i = 5
- i > 2? _______ AND i < 5? _______
- AND result = _______
- count = _______

Loop exits: i = _______

Final output: ___________________________

Explanation: Which values of i satisfied the AND condition?
__________________________________________________________
```

---

## EXERCISE SET 4: Error Finding

### Instructions
For each program:
1. **Find the logical error** - What's the logic mistake?
2. **Explain the problem** - What will go wrong?
3. **Show the fix** - How would you correct it?
4. **Test understanding** - Trace to verify your fix works

---

### Exercise 5.1: Wrong Loop Condition

```c
#include <stdio.h>

int main() {
    int i = 1;

    while (i < 4) {
        printf("%d ", i);
        i++;
    }
    printf("\n");

    return 0;
}
```

**Task:** Is there an error? The code is meant to print 1, 2, 3, 4. Does it?

**Answer:**
```
What does it print? _______________________________

Is this correct? (Yes/No): _______

Explanation: ____________________________________________________________

How would you fix it? ____________________________________________________
```

---

### Exercise 5.2: Compound Condition Logic Error

```c
#include <stdio.h>

int main() {
    int age = 20;
    int income = 25000;

    if (age >= 18 || income >= 50000) {
        printf("Eligible for loan\n");
    } else {
        printf("Not eligible\n");
    }

    return 0;
}
```

**Task:** Should this person be eligible? Check the logic.

**Answer:**
```
What does it output? _______________________________

Is the logic correct? (Yes/No): _______

Explanation: ____________________________________________________________

If you wanted to require BOTH conditions, what would you change?
__________________________________________________________________
```

---

## EXERCISE SET 5: Output Prediction Chain

### Instructions
Predict the output **without running first**. Write your prediction, then verify.

---

### Exercise 6.1

```c
#include <stdio.h>

int main() {
    int x = 10;
    int y = 5;

    if (x > y && x > 8) {
        printf("X is big\n");
    } else {
        printf("X is small\n");
    }

    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________
```

---

### Exercise 6.2

```c
#include <stdio.h>

int main() {
    int count = 0;

    while (count < 5) {
        count = count + 2;
    }

    printf("Count: %d\n", count);

    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________

Explain: How many times did the loop run?
__________________________________________________________________
```

---

### Exercise 6.3

```c
#include <stdio.h>

int main() {
    int i = 1;

    while (i <= 3) {
        if (i == 2) {
            printf("Found 2\n");
        }
        i++;
    }

    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________
```

---

### Exercise 6.4

```c
#include <stdio.h>

int main() {
    int num = 10;

    if (num > 5 || num < 0) {
        printf("Outside range\n");
    } else {
        printf("Inside range\n");
    }

    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________

Explain: What does "Outside range" mean here?
__________________________________________________________________
```

---

### Exercise 6.5

```c
#include <stdio.h>

int main() {
    int total = 1;
    int i = 1;

    while (i <= 3) {
        if (i > 1) {
            total = total * i;
        }
        i++;
    }

    printf("Total: %d\n", total);

    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________

Explanation: What calculation is this doing?
__________________________________________________________________
```

---

## Submission Requirements

1. **Show ALL your work** - Traces, condition checks, explanations
2. **Write neatly** - We should be able to read your work
3. **Explain your reasoning** - Not just the answer
4. **Compare with actual output** - Note any differences
5. **Reflect** - If wrong, explain why you made that mistake

---

## Grading Rubric

| Criteria | Points |
|----------|--------|
| Completeness (all exercises attempted) | 20% |
| Shows work/traces | 30% |
| Explanations are clear | 30% |
| Predictions are correct | 20% |

**Note:** Partial credit for incorrect predictions if your work and reasoning are clear.

---

## Helpful Tips

### For Compound Conditions:
- Evaluate BOTH parts of AND/OR
- AND: Both must be TRUE
- OR: Only ONE needs to be TRUE
- Use parentheses in your work: (part1) AND (part2)

### For While Loops:
- Check condition BEFORE each iteration
- Update variables inside loop carefully
- Count loop iterations by hand
- Use indentation to show iterations

### For Mixed Conditions + Loops:
- First check loop condition
- Then check if condition inside
- Update variables in correct order

### Common Mistakes to Avoid:
- ❌ Forgetting to evaluate both parts of AND/OR
- ❌ Not checking loop condition each iteration
- ❌ Confusing AND (&&) with OR (||)
- ❌ Losing track of variable values
- ❌ Running code first, then predicting

---

## Questions?

If you get stuck:
1. **Re-read the code slowly**
2. **Ask a classmate** - Explain what you think is happening
3. **Ask your instructor** - We can help you debug your understanding
4. **Do NOT use AI or search online** - That defeats the purpose

**Day 2 builds on Day 1.** If you find yourself struggling, review Day 1 concepts first. You've got this! 💪
