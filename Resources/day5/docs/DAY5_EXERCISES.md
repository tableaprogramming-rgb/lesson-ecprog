# PROG2 Day 5: Functions Exercises
## Void Functions, Value-Returning Functions, and Parameter Passing

---

## What are Functions?

Functions are reusable blocks of code that perform specific tasks.

**Benefits:**
- **Code Reusability:** Write once, use many times
- **Readability:** Give code meaningful names
- **Maintainability:** Easier to fix and update
- **Modularity:** Break problems into smaller pieces

---

## Function Types

### Type 1: Void Functions
- Perform a task
- No return value
- Used for actions (printing, modifying, etc.)

### Type 2: Value-Returning Functions
- Perform a calculation or process
- Return a result
- Used for computing values

### Type 3: Parameter Passing
- Pass data INTO functions
- Use parameters to customize behavior
- Different passing methods available

---

## EXERCISE SET 1: Understanding Void Functions

### Exercise 1.1: Calling a Void Function

**Context:** A void function that prints a greeting.

**Buggy Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void greet() {
 4 |     printf("Hello, World!\n");
 5 | }
 6 |
 7 | int main() {
 8 |     greet;              // ← BUG: Missing ()
 9 |
10 |     return 0;
11 | }
```

**What it ACTUALLY does:** No output (function is not called)

**Expected output:**
```
Hello, World!
```

**Your Task:**

1. **Identify the bug:** What's wrong with line 10?

2. **Explain why:** Why does this cause no output?

3. **Understand the difference:**
   - `greet` = Reference to the function (no call)
   - `greet()` = Call the function (execute it)

4. **Write the fix:**

5. **Trace the fixed code:**
   - What happens when main() runs?
   - When does greet() execute?

---

### Exercise 1.2: Multiple Void Function Calls

**Context:** Calling the same void function multiple times.

**Buggy Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void printLine() {
 4 |     printf("-----\n");
 5 | }
 6 |
 7 | int main() {
 8 |     printf("Top\n");
 9 |     printLine();
10 |     printf("Middle\n");
11 |     printLine();
12 |     printf("Bottom\n");
13 |
14 |     return 0;
15 | }
```

**This code is CORRECT!**

**Expected output:**
```
Top
-----
Middle
-----
Bottom
```

**Your Task:**

1. **Predict the output:** Trace through the code step-by-step

2. **Understand function flow:**
   - When does printLine() execute?
   - How many times is it called?
   - What happens after each call?

3. **Write a modified version:**
   - Change the code to call printLine() FOUR times instead of two
   - Keep the other printf statements

4. **Create your own version:**
   - Write a void function that prints a box border
   - Call it multiple times to create a pattern

---

### Exercise 1.3: Void Function Execution Order

**Context:** Understanding when functions execute.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void sayGoodbye() {
 4 |     printf("Goodbye!\n");
 5 | }
 6 |
 7 | void sayHello() {
 8 |     printf("Hello!\n");
 9 | }
10 |
11 | int main() {
12 |     sayHello();
13 |     sayGoodbye();
14 |     sayHello();
15 |
16 |     return 0;
17 | }
```

**Your Task:**

1. **Order the output:** What prints and in what order?
   ```
   A) Hello!
      Hello!
      Goodbye!

   B) Hello!
      Goodbye!
      Hello!

   C) Goodbye!
      Hello!
      Hello!
   ```

2. **Trace execution:**
   - Line by line, which function runs when?
   - Show the exact order

3. **Function definition vs function call:**
   - Where are the functions DEFINED?
   - Where are they CALLED?
   - Why does it matter?

---

## EXERCISE SET 2: Value-Returning Functions

### Exercise 2.1: Simple Return Value

**Context:** A function that calculates and returns a result.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | int addNumbers(int a, int b) {
 4 |     int sum = a + b;
 5 |     return sum;
 6 | }
 7 |
 8 | int main() {
 9 |     int result = addNumbers(5, 3);
10 |     printf("Sum: %d\n", result);
11 |
12 |     return 0;
13 | }
```

**Expected output:** `Sum: 8`

**Your Task:**

1. **Identify the parts:**
   - What is the function name?
   - What is the return type?
   - How many parameters does it have?
   - What gets returned?

2. **Trace the execution:**
   ```
   main() calls addNumbers(5, 3)
   a = 5, b = 3
   sum = 5 + 3 = ?
   return sum → 8
   result = 8
   printf prints: ?
   ```

3. **Modify the function:**
   - Change it to multiply instead of add
   - Change it to work with floating-point numbers
   - Call it with different values

4. **Direct return (optional):**
   - Rewrite the function to use `return a + b;` directly

---

### Exercise 2.2: Return Type Mismatch

**Context:** Understanding return types and type conversion.

**Buggy Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | int calculateAverage(int a, int b) {
 4 |     return (a + b) / 2;  // ← Integer division
 5 | }
 6 |
 7 | int main() {
 8 |     int avg = calculateAverage(5, 6);
 9 |     printf("Average: %d\n", avg);
10 |
11 |     return 0;
12 | }
```

**What it outputs:** `Average: 5`

**Why it's wrong:** Integer division loses the decimal part (5.5 becomes 5)

**Your Task:**

1. **Calculate manually:**
   - (5 + 6) / 2 = 11 / 2 = ?
   - Why is the result 5 and not 5.5?

2. **Fix the function:**
   - Change return type to `double`
   - Use `(a + b) / 2.0` or cast to double

3. **Test your fix:**
   ```c
   double avg = calculateAverage(5, 6);
   printf("Average: %.1f\n", avg);  // Print with 1 decimal place
   ```

4. **Edge case:**
   - What if a = 4, b = 5?
   - What if a = 3, b = 3?

---

### Exercise 2.3: Multiple Return Statements

**Context:** Functions with conditional returns.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | int findMax(int a, int b) {
 4 |     if (a > b) {
 5 |         return a;
 6 |     } else {
 7 |         return b;
 8 |     }
 9 | }
10 |
11 | int main() {
12 |     int max1 = findMax(10, 7);
13 |     int max2 = findMax(3, 8);
14 |
15 |     printf("Max of 10,7: %d\n", max1);
16 |     printf("Max of 3,8: %d\n", max2);
17 |
18 |     return 0;
19 | }
```

**Expected output:**
```
Max of 10,7: 10
Max of 3,8: 8
```

**Your Task:**

1. **Trace first call:**
   - findMax(10, 7)
   - Is 10 > 7? YES
   - Which return executes?
   - What gets returned?

2. **Trace second call:**
   - findMax(3, 8)
   - Is 3 > 8? NO
   - Which return executes?
   - What gets returned?

3. **Extend the function:**
   - Create findMax3 that finds max of 3 numbers
   - Create findMin that finds the minimum

4. **Use a ternary operator (optional):**
   - Rewrite using: `return (a > b) ? a : b;`

---

## EXERCISE SET 3: Parameters and Arguments

### Exercise 3.1: Understanding Parameters vs Arguments

**Context:** Parameters are in the definition, arguments are in the call.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void printNumber(int num) {    // ← num is a PARAMETER
 4 |     printf("Number: %d\n", num);
 5 | }
 6 |
 7 | int main() {
 8 |     printNumber(42);           // ← 42 is an ARGUMENT
 9 |     printNumber(100);          // ← 100 is an ARGUMENT
10 |
11 |     return 0;
12 | }
```

**Expected output:**
```
Number: 42
Number: 100
```

**Your Task:**

1. **Terminology:**
   - What is a parameter?
   - What is an argument?
   - How are they related?

2. **Trace the calls:**
   - First call: printNumber(42)
     - What value does num have?
     - What prints?
   - Second call: printNumber(100)
     - What value does num have?
     - What prints?

3. **Count and match:**
   - How many parameters in printNumber()? (1)
   - How many arguments in each call? (1)
   - Do they match? (Yes!)

4. **Multiple parameters:**
   ```c
   void printCoords(int x, int y, int z) {
       printf("(%d, %d, %d)\n", x, y, z);
   }

   // How would you call this function?
   // printCoords(?, ?, ?);
   ```

---

### Exercise 3.2: Parameter Passing by Value

**Context:** Understanding how values are passed to functions.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void increment(int x) {
 4 |     x = x + 1;
 5 |     printf("Inside: x = %d\n", x);
 6 | }
 7 |
 8 | int main() {
 9 |     int num = 5;
10 |     printf("Before: num = %d\n", num);
11 |
12 |     increment(num);
13 |
14 |     printf("After: num = %d\n", num);
15 |
16 |     return 0;
17 | }
```

**Expected output:**
```
Before: num = 5
Inside: x = 5
After: num = 5
```

**Important:** num is NOT changed by increment()

**Your Task:**

1. **Understand pass-by-value:**
   - When you call increment(num), what gets passed?
   - Does the function receive the variable itself or a COPY of its value?
   - Can the function modify the original num?

2. **Trace execution:**
   ```
   In main: num = 5
   Call increment(5)
   In increment: x = 5 (x is a NEW variable with value 5)
   x = x + 1 → x = 6
   Print "Inside: x = 6"
   Return to main
   Back in main: num is still 5 (unchanged!)
   Print "After: num = 5"
   ```

3. **Why doesn't it change?**
   - The function receives a COPY of the value
   - Changes to x don't affect num
   - This is called "pass-by-value"

4. **Predict output (variation):**
   ```c
   int a = 10;
   increment(a);
   increment(a);
   printf("Final: %d\n", a);  // Prints 10 or 12?
   ```

---

### Exercise 3.3: Multiple Parameters

**Context:** Functions with more than one parameter.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void printInfo(char name[20], int age) {
 4 |     printf("Name: %s\n", name);
 5 |     printf("Age: %d\n", age);
 6 | }
 7 |
 8 | int main() {
 9 |     printInfo("Alice", 20);
10 |     printInfo("Bob", 25);
11 |
12 |     return 0;
13 | }
```

**Expected output:**
```
Name: Alice
Age: 20
Name: Bob
Age: 25
```

**Your Task:**

1. **Parameter matching:**
   - First parameter: `char name[20]`
     - What type is it?
     - What do we pass?
   - Second parameter: `int age`
     - What type is it?
     - What do we pass?

2. **Trace first call:** `printInfo("Alice", 20)`
   - name = "Alice"
   - age = 20
   - What prints?

3. **Trace second call:** `printInfo("Bob", 25)`
   - name = "Bob"
   - age = 25
   - What prints?

4. **Order matters:**
   - What if you call: `printInfo(20, "Alice")`?
   - Why would this be an error?
   - Arguments must match parameters in type AND order

5. **Create your own:**
   - Write a function that takes 3 int parameters
   - Have it calculate and print their sum and average

---

## EXERCISE SET 4: Combining Concepts

### Exercise 4.1: Function Using Multiple Parameters and Returning a Value

**Context:** A complete function that uses parameters and returns a result.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | int rectangleArea(int length, int width) {
 4 |     return length * width;
 5 | }
 6 |
 7 | int main() {
 8 |     int area1 = rectangleArea(5, 3);
 9 |     int area2 = rectangleArea(10, 4);
10 |
11 |     printf("Area 1: %d\n", area1);
12 |     printf("Area 2: %d\n", area2);
13 |
14 |     return 0;
15 | }
```

**Expected output:**
```
Area 1: 15
Area 2: 40
```

**Your Task:**

1. **Function analysis:**
   - Parameters: length, width
   - Return type: int
   - Return value: length * width

2. **Trace first call:** `rectangleArea(5, 3)`
   - length = 5, width = 3
   - return 5 * 3 = 15
   - area1 = 15

3. **Trace second call:** `rectangleArea(10, 4)`
   - length = ?, width = ?
   - return ? * ? = ?
   - area2 = ?

4. **Extend it:**
   ```c
   // Write these functions:
   int rectanglePerimeter(int length, int width);
   int cubeVolume(int side);
   double circleArea(double radius);
   ```

---

### Exercise 4.2: Void Function That Uses Parameters

**Context:** A void function that does something with its parameters.

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void printSum(int a, int b) {
 4 |     int sum = a + b;
 5 |     printf("%d + %d = %d\n", a, b, sum);
 6 | }
 7 |
 8 | int main() {
 9 |     printSum(3, 7);
10 |     printSum(10, 5);
11 |     printSum(2, 8);
12 |
13 |     return 0;
14 | }
```

**Expected output:**
```
3 + 7 = 10
10 + 5 = 15
2 + 8 = 10
```

**Your Task:**

1. **What does this function do?**
   - Takes two numbers
   - Calculates their sum
   - Prints the result
   - Returns nothing (void)

2. **Trace each call:**
   - printSum(3, 7): prints "3 + 7 = 10"
   - printSum(10, 5): prints ?
   - printSum(2, 8): prints ?

3. **Compared to value-returning:**
   - Could you rewrite this as a value-returning function?
   - What would you return?
   - How would you print the result?

4. **Create similar functions:**
   - printProduct(int a, int b)
   - printDifference(int a, int b)
   - compareNumbers(int a, int b) - prints which is larger

---

## EXERCISE SET 5: Common Function Mistakes

### Exercise 5.1: Missing Return Statement

**Buggy Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | int getNumber() {
 4 |     int num = 42;
 5 |     // ← BUG: Missing return statement!
 6 | }
 7 |
 8 | int main() {
 9 |     int result = getNumber();
10 |     printf("Result: %d\n", result);
11 |
12 |     return 0;
13 | }
```

**Your Task:**

1. **Identify the bug:** What's missing?

2. **Predict the output:**
   - What does result contain?
   - What might print? (It's unpredictable!)

3. **Why is this wrong?**
   - Function declares return type int
   - But doesn't return anything
   - This causes undefined behavior

4. **Fix it:**
   ```c
   int getNumber() {
       int num = 42;
       return num;  // ← Add this
   }
   ```

---

### Exercise 5.2: Void Function Trying to Return a Value

**Buggy Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void printNumber() {
 4 |     return 5;  // ← BUG: Can't return value from void function!
 5 | }
 6 |
 7 | int main() {
 8 |     printNumber();
 9 |
10 |     return 0;
11 | }
```

**Your Task:**

1. **Identify the bug:** What's wrong?

2. **Understand void:**
   - void means "no return value"
   - You CAN use return; (returns nothing)
   - You CANNOT use return VALUE;

3. **Fix it (two options):**
   - Option A: Remove the return statement
   - Option B: Change to `int printNumber()` and adjust

---

### Exercise 5.3: Argument/Parameter Type Mismatch

**Code:**
```c
 1 | #include <stdio.h>
 2 |
 3 | void printDouble(double x) {
 4 |     printf("Double: %.2f\n", x);
 5 | }
 6 |
 7 | int main() {
 8 |     printDouble(5);      // ← Passing int to double parameter
 9 |     printDouble(3.14);   // ← Passing double (correct)
10 |
11 |     return 0;
12 | }
```

**Your Task:**

1. **Type conversion:**
   - First call passes int 5
   - Parameter expects double
   - What happens? (It converts 5 → 5.0)

2. **What prints?**
   ```
   Double: ?
   Double: 3.14
   ```

3. **When is this a problem?**
   - Some conversions work fine (int → double)
   - Some conversions lose data (double → int)
   - Always try to match types exactly

---

## EXERCISE SET 6: Function Design Practice

### Exercise 6.1: Design a Function

**Your Task:**

Write a void function named `printMultiplicationTable` that:
- Takes one int parameter `n`
- Prints the multiplication table for that number (1 to 10)
- Example for n=3:
  ```
  3 x 1 = 3
  3 x 2 = 6
  3 x 3 = 9
  ...
  3 x 10 = 30
  ```

**Steps:**
1. Write the function signature
2. Write the function body (use a loop)
3. Call it from main() with different values

---

### Exercise 6.2: Design a Function with Return Value

**Your Task:**

Write a function named `calculateGrade` that:
- Takes one int parameter `score` (0-100)
- Returns a char representing the grade:
  - 90-100: 'A'
  - 80-89: 'B'
  - 70-79: 'C'
  - 60-69: 'D'
  - Below 60: 'F'

**Steps:**
1. Determine the return type and parameter type
2. Write the function using if-else
3. Test with multiple scores
4. Print the result in main()

---

### Exercise 6.3: Design a Complete Program

**Your Task:**

Create a program with these functions:
- `int add(int a, int b)` - returns sum
- `int subtract(int a, int b)` - returns difference
- `int multiply(int a, int b)` - returns product
- `double divide(double a, double b)` - returns quotient
- `void displayResult(char operation, int a, int b, int result)` - prints result

In main():
1. Call each function with different values
2. Display the results using displayResult()

---

## Summary of Key Concepts

### Void Functions
- Return type: `void`
- Perform actions, don't return values
- Called for their side effects (printing, modifying, etc.)

### Value-Returning Functions
- Return type: int, double, char, etc.
- Compute and return a result
- Used in assignments and expressions

### Parameters and Arguments
- **Parameters:** Variables in function definition
- **Arguments:** Values passed when calling function
- Must match in number, type, and order

### Parameter Passing
- In C, parameters are passed **by value**
- Function receives a COPY of the value
- Changes to parameters don't affect original variables

### Function Components
1. **Return type:** What the function gives back
2. **Function name:** What you call it
3. **Parameters:** What it takes in
4. **Function body:** What it does
5. **Return statement:** What it returns (if not void)

---

## Testing Your Understanding

**Can you:**
- [ ] Write a void function?
- [ ] Write a value-returning function?
- [ ] Call a function with the correct arguments?
- [ ] Understand the difference between parameters and arguments?
- [ ] Trace through function execution?
- [ ] Know when to use void vs value-returning?
- [ ] Match function arguments to parameters?

If yes to all, you're ready for more advanced function topics!

---

Good luck with Day 5! Functions are fundamental to programming. 💪
