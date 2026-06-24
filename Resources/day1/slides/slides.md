# Exercise 1.1: Code Tracing

### Line-by-Line Execution

PROG2 - Week 1

---

## Learning Objective

- Trace program execution line by line
- Track variable values as they change
- Understand control flow (if-else)
- Predict program output

---

## Step 1: Include Library

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

📌 The `#include` directive loads the Standard I/O library, giving us access to `printf()`

---

## Step 2: Enter main() Function

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

🎬 **Program Starts Here**

Execution begins at the `main()` function.

| Variable | Value |
|----------|-------|
| (none yet) | — |

---

## Step 3: Declare Variable 'age'

```c
#include <stdio.h>

int main() {
    int age = 15;           // ← WE ARE HERE

    if (age >= 18) {
        printf("You are an adult\n");
    } else {
        printf("You are a minor\n");
    }

    return 0;
}
```

📝 **Create & Initialize Variable**

We create an integer variable named `age` and assign it the value `15`.

| Variable | Type | Value |
|----------|------|-------|
| **age** | int | **15** |

---

## Step 4: Evaluate Condition

```c
#include <stdio.h>

int main() {
    int age = 15;

    if (age >= 18) {        // ← WE ARE HERE
        printf("You are an adult\n");
    } else {
        printf("You are a minor\n");
    }

    return 0;
}
```

❓ **Check the Condition**

We check: `age >= 18`

Is 15 ≥ 18?

**15 >= 18** → **FALSE ✗**

| Variable | Value |
|----------|-------|
| age | 15 |

---

## Step 5: Condition is FALSE

```c
#include <stdio.h>

int main() {
    int age = 15;

    if (age >= 18) {
        printf("You are an adult\n");
    } else {
        printf("You are a minor\n");  // ← WE EXECUTE THIS
    }

    return 0;
}
```

🔀 **Execute ELSE Block**

Because the condition was FALSE, we skip the `if` block and execute the `else` block.

**If block (skipped):**
```c
printf("You are an adult\n");
```

**Else block (executed):**
```c
printf("You are a minor\n");
```

---

## Step 6: Execute printf()

```c
#include <stdio.h>

int main() {
    int age = 15;

    if (age >= 18) {
        printf("You are an adult\n");
    } else {
        printf("You are a minor\n");   // ← WE ARE HERE
    }

    return 0;
}
```

📤 **Print to Console**

The `printf()` function outputs text to the screen.

**Console Output:**
```
You are a minor
```

---

## Step 7: Return from main()

```c
#include <stdio.h>

int main() {
    int age = 15;

    if (age >= 18) {
        printf("You are an adult\n");
    } else {
        printf("You are a minor\n");
    }

    return 0;               // ← WE ARE HERE
}
```

✅ **Program Complete**

We return 0 to indicate the program executed successfully.

**Final Output:**
```
You are a minor
```

---

## Execution Summary

| Line | Statement | Action |
|------|-----------|--------|
| 1 | `#include <stdio.h>` | Load I/O library |
| 3 | `int main() {` | Start program |
| 4 | `int age = 15;` | Create age = 15 |
| 6 | `if (age >= 18)` | Test: 15≥18? **NO** |
| 9 | `printf("...minor\n");` | Print output |
| 12 | `return 0;` | Exit program |

---

## Challenge: Predict the Output

What would happen if we changed line 4?

```c
int age = 25;  // Changed from 15 to 25
```

---

**Questions:**

- Is the condition `25 >= 18` TRUE or FALSE?
- Which block executes: `if` or `else`?
- What would the output be?

---

## Key Concepts to Remember

- **Variables:** Named storage for data (like age = 15)
- **Conditions:** Evaluate to TRUE or FALSE
- **If-Else:** Execute ONE path based on condition result
- **Control Flow:** Line-by-line execution affected by conditions
- **Tracing:** Follow code execution to predict output
