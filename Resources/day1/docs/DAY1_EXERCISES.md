# PROG2 Day 1: Code Reading Exercises
## Control Structures (Selection & Repetition)

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
- Your understanding of C fundamentals

If you don't understand something, ask your classmate or instructor—not Google.

---

## EXERCISE SET 1: Code Tracing (Output Prediction)

### Instructions
For each program below:
1. **Read the code carefully** - line by line
2. **Create a trace table** - showing variable values after each step
3. **Predict the output** - what will print?
4. **Explain your work** - show all your reasoning
5. **Then verify** - run the code and compare

---

### Exercise 1.1: Simple If-Else (Level 1)

```c
#include <stdio.h>

int main() {
    int age = 15;
    
    if (age >= 18) {
        printf("You are an adult\n");
    } else {
        printf("You are a minor\n");
    }
    
    return 0;
}
```

**Your Task:**
- What will this program output?
- Why? Explain your reasoning.

**Show your work:**
```
Variable trace:
- age = _______
- Condition check: age >= 18 → _______
- Which branch executes? _____________
- Output: ___________________________
```

---

### Exercise 1.2: Nested If-Else (Level 2)

```c
#include <stdio.h>

int main() {
    int score = 75;
    
    if (score >= 90) {
        printf("Grade: A\n");
    } else if (score >= 80) {
        printf("Grade: B\n");
    } else if (score >= 70) {
        printf("Grade: C\n");
    } else {
        printf("Grade: F\n");
    }
    
    return 0;
}
```

**Your Task:**
- What will this program output?
- Trace through each condition check

**Show your work:**
```
Variable trace:
- score = _______
- Check: score >= 90? _______
- Check: score >= 80? _______
- Check: score >= 70? _______
- Which branch executes? _____________
- Output: ___________________________
```

---

### Exercise 1.3: Simple Loop (Level 2)

```c
#include <stdio.h>

int main() {
    int i;
    int sum = 0;
    
    for (i = 1; i <= 4; i++) {
        sum = sum + i;
    }
    
    printf("Sum: %d\n", sum);
    
    return 0;
}
```

**Your Task:**
- What is the final output?
- Show the trace for each iteration

**Show your work:**
```
Variable trace:

Initial: i = _____, sum = _____

Iteration 1:
  - i value: _____
  - sum = sum + i = _____ + _____ = _____

Iteration 2:
  - i value: _____
  - sum = sum + i = _____ + _____ = _____

Iteration 3:
  - i value: _____
  - sum = sum + i = _____ + _____ = _____

Iteration 4:
  - i value: _____
  - sum = sum + i = _____ + _____ = _____

Loop ends when: i = _____ (condition i <= 4 is ______)

Final output: ___________________________
```

---

### Exercise 1.4: Loop with Conditional (Level 3)

```c
#include <stdio.h>

int main() {
    int count = 0;
    
    for (int i = 1; i <= 5; i++) {
        if (i % 2 == 0) {
            count = count + 1;
        }
    }
    
    printf("Count: %d\n", count);
    
    return 0;
}
```

**Your Task:**
- What is the final output?
- Which iterations increment count? Why?

**Show your work:**
```
Variable trace:

Initial: count = _____, i = _____

Iteration 1: i = 1, i % 2 == 0? _____ → count = _____
Iteration 2: i = 2, i % 2 == 0? _____ → count = _____
Iteration 3: i = 3, i % 2 == 0? _____ → count = _____
Iteration 4: i = 4, i % 2 == 0? _____ → count = _____
Iteration 5: i = 5, i % 2 == 0? _____ → count = _____

Final output: ___________________________
```

---

### Exercise 1.5: Nested Loop (Level 4 - Challenge)

```c
#include <stdio.h>

int main() {
    int total = 0;
    
    for (int i = 1; i <= 3; i++) {
        for (int j = 1; j <= 2; j++) {
            total = total + 1;
        }
    }
    
    printf("Total: %d\n", total);
    
    return 0;
}
```

**Your Task:**
- What is the final output?
- How many times does the inner loop execute?
- Trace through at least the first 2 outer iterations

**Show your work:**
```
Variable trace:

Initial: total = _____, i = _____, j = _____

Outer loop i = 1:
  Inner loop j = 1: total = _____
  Inner loop j = 2: total = _____
  
Outer loop i = 2:
  Inner loop j = 1: total = _____
  Inner loop j = 2: total = _____
  
Outer loop i = 3:
  Inner loop j = 1: total = _____
  Inner loop j = 2: total = _____

Final output: ___________________________
```

---

## EXERCISE SET 2: Error Finding & Explanation

### Instructions
For each program:
1. **Identify the error(s)** - What's wrong with this code?
2. **Explain WHY it's wrong** - What will go wrong when it runs?
3. **Show the fix** - How would you correct it?
4. **Test your understanding** - Run the original code to see what happens

---

### Exercise 2.1: Semicolon Error

```c
#include <stdio.h>

int main() {
    int x = 5;
    int y = 10;
    
    for (int i = 0; i < 3; i++);
    {
        x = x + y;
        printf("x = %d\n", x);
    }
    
    return 0;
}
```

**Your Task:**
- What is the error? (Hint: Look closely at the loop)
- What will this program actually do?
- How would you fix it?

**Answer:**
```
Error: _____________________________________________________________

Why it's wrong: _____________________________________________________
__________________________________________________________________

What actually happens: ______________________________________________
__________________________________________________________________

Fixed code:

[Write corrected code here]

```

---

### Exercise 2.2: Logic Error - Wrong Condition

```c
#include <stdio.h>

int main() {
    int temperature = 25;
    
    if (temperature > 30) {
        printf("Hot day\n");
    } else if (temperature > 20) {
        printf("Warm day\n");
    } else if (temperature > 10) {
        printf("Cool day\n");
    } else {
        printf("Cold day\n");
    }
    
    return 0;
}
```

**Your Task:**
- This code runs without errors, but is the logic correct?
- If temperature is 25, what will it print?
- Is that correct? Why or why not?

**Answer:**
```
Output for temp = 25: __________________________________________________

Is this correct? (Yes/No): _____

Explanation: ________________________________________________________
__________________________________________________________________

If you wanted to fix the logic, what would you change? 
(Hint: Think about what temperature = 15 should output)

__________________________________________________________________

```

---

### Exercise 2.3: Off-by-One Error

```c
#include <stdio.h>

int main() {
    int sum = 0;
    
    for (int i = 1; i < 5; i++) {
        sum = sum + i;
    }
    
    printf("Sum of 1 to 5: %d\n", sum);
    
    return 0;
}
```

**Your Task:**
- What should "Sum of 1 to 5" be? (1+2+3+4+5 = ?)
- What will this code actually output?
- Is there an error? Explain.

**Answer:**
```
Expected output (sum of 1 to 5): _____

Actual output from code: _____

Is there an error? (Yes/No): _____

Explanation: ________________________________________________________
__________________________________________________________________

How would you fix it?

__________________________________________________________________

```

---

### Exercise 2.4: Uninitialized Variable

```c
#include <stdio.h>

int main() {
    int result;
    
    if (5 > 3) {
        result = 100;
    }
    // Note: There's no else clause!
    
    printf("Result: %d\n", result);
    
    return 0;
}
```

**Your Task:**
- What is the error in this code?
- Why is this problematic even though it compiles?
- How would you fix it?

**Answer:**
```
Error: __________________________________________________________________

Why is it problematic: __________________________________________________
__________________________________________________________________

How to fix it:

[Show corrected code]

```

---

## EXERCISE SET 3: Output Prediction Chain

### Instructions
Predict the output of each program **without running it first**. Write down your prediction, then verify by running the code.

---

### Exercise 3.1

```c
#include <stdio.h>

int main() {
    int x = 10;
    int y = 20;
    
    if (x < y) {
        x = x + 5;
    }
    
    printf("x = %d, y = %d\n", x, y);
    
    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________
```

---

### Exercise 3.2

```c
#include <stdio.h>

int main() {
    for (int i = 5; i > 0; i--) {
        printf("%d ", i);
    }
    printf("\n");
    
    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________
```

---

### Exercise 3.3

```c
#include <stdio.h>

int main() {
    int count = 0;
    
    for (int i = 0; i < 4; i++) {
        count = count + 2;
    }
    
    printf("Count: %d\n", count);
    
    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________
```

---

### Exercise 3.4

```c
#include <stdio.h>

int main() {
    int result = 1;
    
    for (int i = 1; i <= 4; i++) {
        result = result * i;
    }
    
    printf("Result: %d\n", result);
    
    return 0;
}
```

**Your Prediction:**
```
Output: ___________________________

Explanation: What is this code calculating?
_________________________________________________________________
```

---

### Exercise 3.5

```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 3; i++) {
        for (int j = 1; j <= 3; j++) {
            printf("%d ", i * j);
        }
        printf("\n");
    }
    
    return 0;
}
```

**Your Prediction:**
```
Output:
[Show exact output with line breaks]


Explanation: What pattern do you see?
_________________________________________________________________
```

---

## EXERCISE SET 4: Code Matching (Bonus)

### Instructions
Match each code snippet (A-E) with its output (1-5). **Write a 2-3 sentence explanation for each match explaining why you chose that output.**

---

### Code Snippets

**Code A:**
```c
for (int i = 1; i <= 3; i++) {
    printf("%d ", i);
}
```

**Code B:**
```c
int x = 5;
if (x > 3 && x < 10) {
    printf("Yes");
}
```

**Code C:**
```c
int sum = 0;
for (int i = 1; i <= 3; i++) {
    sum = sum + i;
}
printf("%d", sum);
```

**Code D:**
```c
for (int i = 3; i >= 1; i--) {
    printf("%d ", i);
}
```

**Code E:**
```c
int x = 0;
while (x < 3) {
    x = x + 1;
}
printf("%d", x);
```

---

### Output Options

1. `6`
2. `Yes`
3. `1 2 3 `
4. `3 2 1 `
5. `3`

---

### Your Answers

| Code | Output | Explanation |
|------|--------|-------------|
| A | ___ | _____________________________________________________ |
| B | ___ | _____________________________________________________ |
| C | ___ | _____________________________________________________ |
| D | ___ | _____________________________________________________ |
| E | ___ | _____________________________________________________ |

---

## Submission Requirements

1. **Show ALL your work** - Traces, calculations, explanations
2. **Write neatly** - We should be able to read your work
3. **Explain your reasoning** - Not just the answer
4. **Compare with actual output** - Note any differences between your prediction and actual result
5. **Reflect** - If you were wrong, write why you made that mistake

---

## Grading Rubric

| Criteria | Points |
|----------|--------|
| Completeness (all exercises attempted) | 20% |
| Shows work/traces | 30% |
| Explanations are clear | 30% |
| Predictions are correct | 20% |

**Note:** You can get partial credit for incorrect predictions **if your work and reasoning are clear**. This helps us understand where your understanding breaks down.

---

## Helpful Tips

### For Code Tracing:
- Read one line at a time
- Update your trace table after each line
- Be very careful with operators (++, %, ==, etc.)
- Don't skip ahead - trace every step!

### For Nested Loops:
- Use indentation in your trace to show inner loop steps
- Count how many times inner loop runs
- Remember: inner loop completes before outer loop advances

### For Conditionals:
- Check condition carefully (>, >=, <, <=, ==, !=)
- Only ONE branch executes
- If-else-if: stops at first TRUE condition

### Common Mistakes to Avoid:
- ❌ Running code first, then trying to explain (defeats the purpose)
- ❌ Skipping steps in loops ("just jump to the end")
- ❌ Forgetting to increment/decrement loop counters
- ❌ Confusing `=` (assignment) with `==` (comparison)
- ❌ Not showing your work (just writing the answer)

---

## Questions?

If you get stuck:
1. **Re-read the code slowly**
2. **Ask a classmate** - Explain what you think is happening
3. **Ask your instructor** - We can help you debug your understanding
4. **Do NOT use AI or search online** - That defeats the purpose

Good luck! This skill will serve you well throughout the course. 🚀
