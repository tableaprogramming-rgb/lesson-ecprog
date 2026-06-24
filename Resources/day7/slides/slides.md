# Day 7: Single-Dimensional Arrays - Markdown Reference

This file serves as a markdown reference for all exercise presentations.

---

## Exercise 7.1: Array Declaration & Initialization

**Code:**
```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};

    printf("First: %d\n", numbers[0]);
    printf("Last: %d\n", numbers[4]);

    return 0;
}
```

**Key Concepts:**
- `int numbers[5]` declares an array of 5 integers
- `= {10, 20, 30, 40, 50}` initializes each element
- Array indices: 0, 1, 2, 3, 4 (not 1-5!)
- Index 0 = first element, Index 4 = last element

**Output:**
```
First: 10
Last: 50
```

---

## Exercise 7.2: Array Indexing

**Code:**
```c
#include <stdio.h>

int main() {
    int scores[5] = {85, 90, 78, 92, 88};

    int first = scores[0];
    int middle = scores[2];
    int last = scores[4];

    printf("%d %d %d\n", first, middle, last);

    return 0;
}
```

**Key Concepts:**
- `scores[0]` accesses first element (85)
- `scores[2]` accesses third element (78)
- `scores[4]` accesses last element (88)
- Index = position - 1 (position 3 = index 2)

**Output:**
```
85 78 88
```

---

## Exercise 7.3: Looping Through Arrays

**Code:**
```c
#include <stdio.h>

int main() {
    int arr[3] = {5, 10, 15};

    for(int i = 0; i < 3; i++) {
        printf("%d\n", arr[i]);
    }

    return 0;
}
```

**Key Concepts:**
- Loop variable `i` is used as the index
- `i < 3` means indices 0, 1, 2 (don't use i <= 3)
- Each iteration accesses one element
- `arr[0]` → prints 5
- `arr[1]` → prints 10
- `arr[2]` → prints 15

**Loop Trace:**
```
i=0: 0 < 3? YES → arr[0]=5 → print 5 → i++
i=1: 1 < 3? YES → arr[1]=10 → print 10 → i++
i=2: 2 < 3? YES → arr[2]=15 → print 15 → i++
i=3: 3 < 3? NO → exit loop
```

**Output:**
```
5
10
15
```

---

## Exercise 7.4: Array Manipulation

**Code:**
```c
#include <stdio.h>

int main() {
    int values[3] = {1, 2, 3};

    values[0] = values[0] * 10;
    values[1] = values[1] + 5;
    values[2] = values[0] + values[1];

    printf("%d %d %d\n", values[0], values[1], values[2]);

    return 0;
}
```

**Key Concepts:**
- `values[i] = new_value` modifies that element
- Order matters - operations happen in sequence
- Later operations use updated values
- Each element is independent

**Trace:**
```
Initial:     [1]   [2]   [3]
Step 1:      [10]  [2]   [3]    (1 * 10 = 10)
Step 2:      [10]  [7]   [3]    (2 + 5 = 7)
Step 3:      [10]  [7]   [17]   (10 + 7 = 17)
```

**Output:**
```
10 7 17
```

---

## Exercise 7.5: Searching & Analysis

**Code:**
```c
#include <stdio.h>

int main() {
    int data[5] = {15, 8, 23, 5, 19};
    int min = data[0];
    int max = data[0];

    for(int i = 1; i < 5; i++) {
        if(data[i] < min) {
            min = data[i];
        }
        if(data[i] > max) {
            max = data[i];
        }
    }

    printf("Min: %d\n", min);
    printf("Max: %d\n", max);

    return 0;
}
```

**Key Concepts:**
- Initialize min and max to first element (data[0])
- Start loop at `i = 1` (skip first, already used)
- Compare each element with current min/max
- Update if smaller or larger
- Final answer after all comparisons

**Algorithm Trace:**
```
Initial: min=15, max=15

i=1: data[1]=8
     8 < 15? YES → min=8
     8 > 15? NO

i=2: data[2]=23
     23 < 8? NO
     23 > 15? YES → max=23

i=3: data[3]=5
     5 < 8? YES → min=5
     5 > 23? NO

i=4: data[4]=19
     19 < 5? NO
     19 > 23? NO

Final: min=5, max=23
```

**Output:**
```
Min: 5
Max: 23
```

---

## Summary: Array Operations

| Operation | Example | Purpose |
|-----------|---------|---------|
| **Declaration** | `int arr[5]` | Create array |
| **Initialization** | `= {1,2,3,4,5}` | Set initial values |
| **Access** | `arr[0]` | Get element at index |
| **Modify** | `arr[0] = 10` | Change element value |
| **Loop** | `for(i=0; i<5; i++)` | Process all elements |
| **Search** | `if(arr[i] < min)` | Find specific values |

---

## Common Index Mistakes

### Mistake 1: Forgetting 0-based indexing
```c
int arr[3] = {1, 2, 3};
arr[3] = 5;  // WRONG! Index 3 doesn't exist
// Valid indices: 0, 1, 2
```

### Mistake 2: Wrong loop condition
```c
for(int i = 0; i <= 3; i++)  // WRONG for arr[3]!
    printf("%d\n", arr[i]);  // Would access arr[3] (out of bounds)

// Correct:
for(int i = 0; i < 3; i++)   // Accesses arr[0], arr[1], arr[2]
```

### Mistake 3: Loop variable scope
```c
for(int i = 0; i < 5; i++) { }
printf("%i\n", i);  // ERROR - i doesn't exist here
```

---

## Key Points to Remember

1. **Array size is fixed** - Declare it once, can't change it
2. **Indices start at 0** - Array[size] has indices 0 to size-1
3. **Loops are your friend** - Use loops to process all elements
4. **Independent elements** - Changing one doesn't affect others
5. **Bounds checking is YOUR job** - C doesn't check array bounds!

---

This reference can be used alongside the interactive presentations for studying and review.
