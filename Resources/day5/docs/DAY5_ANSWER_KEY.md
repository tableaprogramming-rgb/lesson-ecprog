# PROG2 Day 5: Answer Key (Instructor Guide)
## Functions: Void, Value-Returning, and Parameter Passing

---

## EXERCISE SET 1: Understanding Void Functions

### Exercise 1.1: Calling a Void Function - ANSWER

**The Bug:** Line 10
```c
 1 | greet;              // ← Missing ()
```

**What's Wrong:**
Using just `greet` references the function but doesn't CALL it. To call a function, you need parentheses `()`.

**Explanation:**
- `greet` = Reference to the function itself (doesn't execute)
- `greet()` = Function call (executes the function body)

**The Fix:**
```c
 1 | int main() {
 2 |     greet();        // ← Add () to call the function
 3 |
 4 |     return 0;
 5 | }
```

**Execution Trace:**
```
main() starts
greet() is called
  → printf("Hello, World!\n") executes
  → "Hello, World!" prints
  → greet() returns to main()
main() continues
return 0
```

**Output:**
```
Hello, World!
```

**Key Lesson:** Function names alone are references. Use `()` to actually call them.

---

### Exercise 1.2: Multiple Void Function Calls - ANSWER

**This code is CORRECT!**

**Output:**
```
Top
-----
Middle
-----
Bottom
```

**Execution Trace:**
```
main() starts
printf("Top\n") → prints "Top"
printLine() called → prints "-----"
printf("Middle\n") → prints "Middle"
printLine() called → prints "-----"
printf("Bottom\n") → prints "Bottom"
return 0
```

**Modified Version (call printLine() 4 times):**
```c
 1 | int main() {
 2 |     printf("Top\n");
 3 |     printLine();
 4 |     printLine();
 5 |     printf("Middle\n");
 6 |     printLine();
 7 |     printf("Bottom\n");
 8 |     printLine();
 9 |
10 |     return 0;
11 | }
```

**Output:**
```
Top
-----
-----
Middle
-----
Bottom
-----
```

**Your Own Version (box border function):**
```c
 1 | void printBoxTop() {
 2 |     printf("+-----+\n");
 3 | }
 4 |
 5 | void printBoxMiddle() {
 6 |     printf("|     |\n");
 7 | }
 8 |
 9 | void printBoxBottom() {
10 |     printf("+-----+\n");
11 | }
12 |
13 | int main() {
14 |     printBoxTop();
15 |     printBoxMiddle();
16 |     printBoxMiddle();
17 |     printBoxMiddle();
18 |     printBoxBottom();
19 |
20 |     return 0;
21 | }
```

**Output:**
```
+-----+
|     |
|     |
|     |
+-----+
```

---

### Exercise 1.3: Void Function Execution Order - ANSWER

**Answer:** B) Hello! / Goodbye! / Hello!

**Execution Trace:**
```
main() starts
sayHello() called
  → printf("Hello!\n") executes
  → "Hello!" prints
  → returns to main()
sayGoodbye() called
  → printf("Goodbye!\n") executes
  → "Goodbye!" prints
  → returns to main()
sayHello() called
  → printf("Hello!\n") executes
  → "Hello!" prints
  → returns to main()
return 0
```

**Output:**
```
Hello!
Goodbye!
Hello!
```

**Key Points:**
- Functions are DEFINED once (lines 3-5, 7-9)
- Functions are CALLED three times (lines 12, 13, 14)
- Definition location doesn't matter (can be before or after main)
- Call order matters (determines output order)

---

## EXERCISE SET 2: Value-Returning Functions

### Exercise 2.1: Simple Return Value - ANSWER

**Function Analysis:**
- Function name: `addNumbers`
- Return type: `int`
- Parameters: `int a`, `int b` (2 parameters)
- Returns: `sum` (the result of a + b)

**Execution Trace:**
```
main() calls addNumbers(5, 3)
  a = 5, b = 3
  sum = 5 + 3 = 8
  return 8
result = 8
printf("Sum: %d\n", result) → prints "Sum: 8"
```

**Output:**
```
Sum: 8
```

**Modified Version (multiply instead of add):**
```c
 1 | int multiplyNumbers(int a, int b) {
 2 |     int product = a * b;
 3 |     return product;
 4 | }
 5 |
 6 | int main() {
 7 |     int result = multiplyNumbers(5, 3);
 8 |     printf("Product: %d\n", result);  // Prints: Product: 15
 9 |
10 |     return 0;
11 | }
```

**Modified Version (floating-point):**
```c
 1 | double addNumbers(double a, double b) {
 2 |     double sum = a + b;
 3 |     return sum;
 4 | }
 5 |
 6 | int main() {
 7 |     double result = addNumbers(5.5, 3.2);
 8 |     printf("Sum: %.1f\n", result);  // Prints: Sum: 8.7
 9 |
10 |     return 0;
11 | }
```

**Direct Return Version:**
```c
 1 | int addNumbers(int a, int b) {
 2 |     return a + b;  // Return directly without intermediate variable
 3 | }
```

---

### Exercise 2.2: Return Type Mismatch - ANSWER

**Manual Calculation:**
```
(5 + 6) / 2 = 11 / 2 = 5 (integer division)
The decimal part (.5) is lost!
```

**Why it's wrong:**
- The function divides two integers: 11 / 2
- Integer division truncates (cuts off) the decimal
- Result: 5 instead of 5.5

**Fixed Version:**
```c
 1 | double calculateAverage(int a, int b) {
 2 |     return (a + b) / 2.0;  // Divide by 2.0 (double) not 2 (int)
 3 | }
 4 |
 5 | int main() {
 6 |     double avg = calculateAverage(5, 6);
 7 |     printf("Average: %.1f\n", avg);  // Prints: Average: 5.5
 8 |
 9 |     return 0;
10 | }
```

**Why the fix works:**
- When you divide by 2.0 (a double), C promotes the result to double
- 11 / 2.0 = 5.5 (floating-point division)
- Result: 5.5 (correct!)

**Edge Cases:**
```
a = 4, b = 5:  (4 + 5) / 2.0 = 9 / 2.0 = 4.5
a = 3, b = 3:  (3 + 3) / 2.0 = 6 / 2.0 = 3.0
a = 1, b = 2:  (1 + 2) / 2.0 = 3 / 2.0 = 1.5
```

---

### Exercise 2.3: Multiple Return Statements - ANSWER

**Execution Trace - First Call:** `findMax(10, 7)`
```
Is 10 > 7? YES
Return 10
max1 = 10
```

**Execution Trace - Second Call:** `findMax(3, 8)`
```
Is 3 > 8? NO
Go to else
Return 8
max2 = 8
```

**Output:**
```
Max of 10,7: 10
Max of 3,8: 8
```

**findMax3 Function:**
```c
 1 | int findMax3(int a, int b, int c) {
 2 |     if (a > b && a > c) {
 3 |         return a;
 4 |     } else if (b > c) {
 5 |         return b;
 6 |     } else {
 7 |         return c;
 8 |     }
 9 | }
10 |
11 | // Usage:
12 | int max = findMax3(5, 10, 3);  // Returns 10
```

**findMin Function:**
```c
 1 | int findMin(int a, int b) {
 2 |     if (a < b) {
 3 |         return a;
 4 |     } else {
 5 |         return b;
 6 |     }
 7 | }
 8 |
 9 | // Usage:
10 | int min = findMin(10, 7);  // Returns 7
```

**Ternary Operator Version:**
```c
 1 | int findMax(int a, int b) {
 2 |     return (a > b) ? a : b;
 3 | }
 4 |
 5 | // Same logic, more concise!
```

---

## EXERCISE SET 3: Parameters and Arguments

### Exercise 3.1: Understanding Parameters vs Arguments - ANSWER

**Definitions:**
- **Parameter:** Variable in function definition that holds a value passed in
- **Argument:** Actual value passed when calling the function
- Parameters are placeholders, arguments are actual values

**Example:**
```
int printNumber(int num) {   ← num is a PARAMETER
    printf("Number: %d\n", num);
}

printNumber(42);             ← 42 is an ARGUMENT
```

**Execution Trace:**
```
Call: printNumber(42)
  num = 42 (parameter gets argument's value)
  printf prints: "Number: 42"

Call: printNumber(100)
  num = 100
  printf prints: "Number: 100"
```

**Output:**
```
Number: 42
Number: 100
```

**Multiple Parameters Example:**
```c
 1 | void printCoords(int x, int y, int z) {
 2 |     printf("(%d, %d, %d)\n", x, y, z);
 3 | }
 4 |
 5 | // How to call it:
 6 | printCoords(5, 10, 15);   // Prints: (5, 10, 15)
 7 | printCoords(1, 2, 3);     // Prints: (1, 2, 3)
```

**Key Points:**
- Parameter count MUST match argument count
- Parameter types MUST match argument types
- Parameter order MUST match argument order

---

### Exercise 3.2: Parameter Passing by Value - ANSWER

**Key Concept:** In C, parameters are passed **by value**, meaning:
- Function receives a COPY of the value
- Changes to the parameter don't affect the original variable
- This is called "pass-by-value"

**Execution Trace:**
```
main():
  num = 5
  Call increment(num)

increment():
  x = 5  (x is a NEW variable, copy of num)
  x = 5 + 1 = 6
  printf("Inside: x = 6")
  return to main

main():
  num is still 5 (never changed!)
  printf("After: num = 5")
```

**Output:**
```
Before: num = 5
Inside: x = 6
After: num = 5
```

**Why doesn't num change?**
- The function receives a COPY: x = 5
- Modifying x doesn't affect the original num
- When the function returns, x is discarded

**Variation - Prediction:**
```c
int a = 10;
increment(a);      // a is still 10 after this
increment(a);      // a is still 10 after this
printf("Final: %d\n", a);  // Prints: Final: 10
```

**Important Limitation:**
If you NEED to modify a variable in another function, you must either:
1. Return the new value and assign it
2. Use pointers (advanced topic)

**Alternative Approach:**
```c
int increment(int x) {
    return x + 1;  // Return the new value
}

int main() {
    int num = 5;
    num = increment(num);  // Assign the returned value
    printf("num = %d\n", num);  // Prints: num = 6

    return 0;
}
```

---

### Exercise 3.3: Multiple Parameters - ANSWER

**Function Analysis:**
```c
void printInfo(char name[20], int age) {
  //           ↑ Parameter 1      ↑ Parameter 2
```

- First parameter: `char name[20]` (string/array)
  - Pass a string argument
  - Example: "Alice", "Bob"

- Second parameter: `int age` (integer)
  - Pass an integer argument
  - Example: 20, 25

**Execution Trace - First Call:** `printInfo("Alice", 20)`
```
name = "Alice"
age = 20
printf("Name: %s\n", name);  → "Name: Alice"
printf("Age: %d\n", age);    → "Age: 20"
```

**Execution Trace - Second Call:** `printInfo("Bob", 25)`
```
name = "Bob"
age = 25
printf("Name: %s\n", name);  → "Name: Bob"
printf("Age: %d\n", age);    → "Age: 25"
```

**Output:**
```
Name: Alice
Age: 20
Name: Bob
Age: 25
```

**Why Order Matters:**
```c
printInfo(20, "Alice");  // ← ERROR! Types don't match order
```
This would cause an error because:
- First parameter expects char[] (string)
- You're giving int (20)
- Second parameter expects int
- You're giving char[] ("Alice")

**Your Own Function - Sum and Average:**
```c
 1 | void printSumAndAverage(int a, int b, int c) {
 2 |     int sum = a + b + c;
 3 |     double average = (a + b + c) / 3.0;
 4 |
 5 |     printf("Sum: %d\n", sum);
 6 |     printf("Average: %.2f\n", average);
 7 | }
 8 |
 9 | int main() {
10 |     printSumAndAverage(10, 20, 30);
11 |     // Output:
12 |     // Sum: 60
13 |     // Average: 20.00
14 |
15 |     return 0;
16 | }
```

---

## EXERCISE SET 4: Combining Concepts

### Exercise 4.1: Multiple Parameters Returning Value - ANSWER

**Function Analysis:**
```c
int rectangleArea(int length, int width) {
    return length * width;
}
```
- Parameters: length, width
- Return type: int
- Returns: area (length × width)

**Execution Trace - First Call:** `rectangleArea(5, 3)`
```
length = 5, width = 3
return 5 * 3 = 15
area1 = 15
```

**Execution Trace - Second Call:** `rectangleArea(10, 4)`
```
length = 10, width = 4
return 10 * 4 = 40
area2 = 40
```

**Output:**
```
Area 1: 15
Area 2: 40
```

**Extended Functions:**

```c
 1 | int rectanglePerimeter(int length, int width) {
 2 |     return 2 * (length + width);
 3 | }
 4 | // Example: rectanglePerimeter(5, 3) = 2 * (5 + 3) = 16
 5 |
 6 | int cubeVolume(int side) {
 7 |     return side * side * side;
 8 | }
 9 | // Example: cubeVolume(3) = 3 * 3 * 3 = 27
10 |
11 | double circleArea(double radius) {
12 |     return 3.14159 * radius * radius;
13 | }
14 | // Example: circleArea(2.0) = 3.14159 * 4 = 12.566...
```

---

### Exercise 4.2: Void Function with Parameters - ANSWER

**What This Function Does:**
1. Takes two numbers as parameters
2. Calculates their sum
3. Prints the calculation with result
4. Returns nothing (void)

**Execution Trace:**
```
printSum(3, 7):
  a = 3, b = 7
  sum = 3 + 7 = 10
  printf("3 + 7 = 10")

printSum(10, 5):
  a = 10, b = 5
  sum = 10 + 5 = 15
  printf("10 + 5 = 15")

printSum(2, 8):
  a = 2, b = 8
  sum = 2 + 8 = 10
  printf("2 + 8 = 10")
```

**Output:**
```
3 + 7 = 10
10 + 5 = 15
2 + 8 = 10
```

**Compare to Value-Returning Version:**
```c
 1 | int calculateSum(int a, int b) {
 2 |     return a + b;
 3 | }
 4 |
 5 | int main() {
 6 |     int result = calculateSum(3, 7);
 7 |     printf("3 + 7 = %d\n", result);
 8 |
 9 |     return 0;
10 | }
```

**When to use void vs value-returning:**
- **Void:** When the function's main purpose is side effects (printing, modifying)
- **Value-returning:** When you need a computed result to use elsewhere

**Similar Functions:**

```c
 1 | void printProduct(int a, int b) {
 2 |     int product = a * b;
 3 |     printf("%d * %d = %d\n", a, b, product);
 4 | }
 5 |
 6 | void printDifference(int a, int b) {
 7 |     int difference = a - b;
 8 |     printf("%d - %d = %d\n", a, b, difference);
 9 | }
10 |
11 | void compareNumbers(int a, int b) {
12 |     if (a > b) {
13 |         printf("%d is larger\n", a);
14 |     } else if (b > a) {
15 |         printf("%d is larger\n", b);
16 |     } else {
17 |         printf("%d and %d are equal\n", a, b);
18 |     }
19 | }
20 |
21 | int main() {
22 |     printProduct(4, 5);          // Output: 4 * 5 = 20
23 |     printDifference(10, 3);      // Output: 10 - 3 = 7
24 |     compareNumbers(8, 8);        // Output: 8 and 8 are equal
25 |
26 |     return 0;
27 | }
```

---

## EXERCISE SET 5: Common Function Mistakes

### Exercise 5.1: Missing Return Statement - ANSWER

**The Bug:**
```c
 1 | int getNumber() {
 2 |     int num = 42;
 3 |     // ← Missing: return num;
 4 | }
```

**What's Wrong:**
- Function declares return type `int`
- But never actually returns a value
- This causes **undefined behavior**
- Result is unpredictable

**The Problem:**
The function signature promises to return an int, but doesn't deliver. C allows this to compile (or warns), but the result is garbage.

**The Fix:**
```c
 1 | int getNumber() {
 2 |     int num = 42;
 3 |     return num;    // ← Add this line
 4 | }
```

**Execution:**
```
main() calls getNumber()
  num = 42
  return 42
result = 42
printf("Result: %d\n", result);  // Prints: Result: 42
```

**Key Lesson:** Every function with a non-void return type MUST return a value.

---

### Exercise 5.2: Void Function Returning Value - ANSWER

**The Bug:**
```c
 1 | void printNumber() {
 2 |     return 5;  // ← ERROR: Can't return value from void!
 3 | }
```

**What's Wrong:**
- Function is declared as `void` (no return value)
- But tries to return 5
- This is a compile error

**Understanding void:**
- `void` = "this function returns nothing"
- You CAN use `return;` alone (returns nothing)
- You CANNOT use `return VALUE;`

**Fix Option A (Remove return value):**
```c
 1 | void printNumber() {
 2 |     printf("Number: %d\n", 5);
 3 |     return;  // Optional: explicitly return nothing
 4 | }
```

**Fix Option B (Change to value-returning):**
```c
 1 | int printNumber() {      // ← Change return type
 2 |     return 5;            // ← Now valid
 3 | }
 4 |
 5 | int main() {
 6 |     int result = printNumber();
 7 |     printf("Result: %d\n", result);
 8 |
 9 |     return 0;
10 | }
```

**Key Lesson:** Match your return statements to your function's declared return type.

---

### Exercise 5.3: Argument/Parameter Type Mismatch - ANSWER

**Type Conversion:**
```c
void printDouble(double x) {
    printf("Double: %.2f\n", x);
}

printDouble(5);      // int 5 → converted to 5.0
printDouble(3.14);   // double 3.14 (no conversion needed)
```

**What Prints:**
```
Double: 5.00
Double: 3.14
```

**Explanation:**
- First call: `printDouble(5)`
  - Argument: 5 (int)
  - Parameter expects: double
  - C auto-converts: 5 → 5.0
  - Prints: "Double: 5.00" ✓

- Second call: `printDouble(3.14)`
  - Argument: 3.14 (double)
  - Parameter expects: double
  - No conversion needed
  - Prints: "Double: 3.14" ✓

**When Type Conversion is Problematic:**
```c
void printInt(int x) {
    printf("Int: %d\n", x);
}

printInt(3.14);  // double → int conversion
// Result: 3 (decimal part lost!)
```

**When to Worry:**
- **Safe conversions:** int → double, char → int
- **Data loss:** double → int (loses decimals), int → char (loses precision)
- **Best practice:** Always match types exactly

**Solution:**
```c
 1 | void printDouble(double x);
 2 | void printInt(int x);
 3 |
 4 | int main() {
 5 |     printDouble(5.0);    // ← Pass correct type
 6 |     printDouble(3.14);
 7 |
 8 |     printInt(5);         // ← Pass correct type
 9 |
10 |     return 0;
11 | }
```

---

## EXERCISE SET 6: Function Design Practice

### Exercise 6.1: Multiplication Table Function - ANSWER

```c
 1 | #include <stdio.h>
 2 |
 3 | void printMultiplicationTable(int n) {
 4 |     for (int i = 1; i <= 10; i++) {
 5 |         printf("%d x %d = %d\n", n, i, n * i);
 6 |     }
 7 | }
 8 |
 9 | int main() {
10 |     printMultiplicationTable(3);
11 |     printf("\n");
12 |     printMultiplicationTable(5);
13 |
14 |     return 0;
15 | }
```

**Output:**
```
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30

5 x 1 = 5
5 x 2 = 10
...
5 x 10 = 50
```

**Key Points:**
- Void function (no return)
- Takes one parameter (n)
- Uses loop to generate table
- Can be called multiple times with different values

---

### Exercise 6.2: Calculate Grade Function - ANSWER

```c
 1 | #include <stdio.h>
 2 |
 3 | char calculateGrade(int score) {
 4 |     if (score >= 90) {
 5 |         return 'A';
 6 |     } else if (score >= 80) {
 7 |         return 'B';
 8 |     } else if (score >= 70) {
 9 |         return 'C';
10 |     } else if (score >= 60) {
11 |         return 'D';
12 |     } else {
13 |         return 'F';
14 |     }
15 | }
16 |
17 | int main() {
18 |     int score1 = 95;
19 |     int score2 = 85;
20 |     int score3 = 72;
21 |     int score4 = 68;
22 |     int score5 = 50;
23 |
24 |     char grade1 = calculateGrade(score1);
25 |     printf("Score: %d, Grade: %c\n", score1, grade1);  // Grade: A
26 |
27 |     char grade2 = calculateGrade(score2);
28 |     printf("Score: %d, Grade: %c\n", score2, grade2);  // Grade: B
29 |
30 |     char grade3 = calculateGrade(score3);
31 |     printf("Score: %d, Grade: %c\n", score3, grade3);  // Grade: C
32 |
33 |     char grade4 = calculateGrade(score4);
34 |     printf("Score: %d, Grade: %c\n", score4, grade4);  // Grade: D
35 |
36 |     char grade5 = calculateGrade(score5);
37 |     printf("Score: %d, Grade: %c\n", score5, grade5);  // Grade: F
38 |
39 |     return 0;
40 | }
```

**Output:**
```
Score: 95, Grade: A
Score: 85, Grade: B
Score: 72, Grade: C
Score: 68, Grade: D
Score: 50, Grade: F
```

**Key Points:**
- Returns char type (single character)
- Uses multiple if-else statements
- Can test with boundary values (90, 80, 70, 60)

---

### Exercise 6.3: Complete Program - ANSWER

```c
 1 | #include <stdio.h>
 2 |
 3 | int add(int a, int b) {
 4 |     return a + b;
 5 | }
 6 |
 7 | int subtract(int a, int b) {
 8 |     return a - b;
 9 | }
10 |
11 | int multiply(int a, int b) {
12 |     return a * b;
13 | }
14 |
15 | double divide(double a, double b) {
16 |     if (b == 0) {
17 |         printf("Error: Cannot divide by zero!\n");
18 |         return 0;
19 |     }
20 |     return a / b;
21 | }
22 |
23 | void displayResult(char operation, int a, int b, int result) {
24 |     printf("%d %c %d = %d\n", a, operation, b, result);
25 | }
26 |
27 | void displayResultDouble(char operation, double a, double b, double result) {
28 |     printf("%.1f %c %.1f = %.2f\n", a, operation, b, result);
29 | }
30 |
31 | int main() {
32 |     // Test add
33 |     int sum = add(10, 5);
34 |     displayResult('+', 10, 5, sum);
35 |
36 |     // Test subtract
37 |     int difference = subtract(10, 5);
38 |     displayResult('-', 10, 5, difference);
39 |
40 |     // Test multiply
41 |     int product = multiply(10, 5);
42 |     displayResult('*', 10, 5, product);
43 |
44 |     // Test divide
45 |     double quotient = divide(10, 5);
46 |     displayResultDouble('/', 10.0, 5.0, quotient);
47 |
48 |     return 0;
49 | }
```

**Output:**
```
10 + 5 = 15
10 - 5 = 5
10 * 5 = 50
10.0 / 5.0 = 2.00
```

**Key Points:**
- Multiple functions working together
- Void function for displaying results
- Value-returning functions for calculations
- Proper parameter types for each operation

---

## Summary of Key Concepts

### Void Functions
✓ Return type is `void`
✓ Called for their effects (printing, modifying)
✓ Don't return a value
✓ Still use `return;` if needed to exit early

### Value-Returning Functions
✓ Return type is int, double, char, etc.
✓ Must have at least one `return VALUE;` statement
✓ Return type must match the returned value's type
✓ Can be used in expressions and assignments

### Parameters and Arguments
✓ Parameters are in the function definition
✓ Arguments are the values passed when calling
✓ Must match in number, type, and order
✓ C uses pass-by-value (function gets a copy)

### Pass-by-Value
✓ Function receives a COPY of the argument
✓ Changes to parameters don't affect originals
✓ This is C's default parameter passing method
✓ Use return values to send results back

### Function Design Tips
✓ Choose void or value-returning based on need
✓ Use parameters to make functions flexible
✓ Write pure functions (same input → same output)
✓ Keep functions focused on one task

---

Good luck with functions! They're essential to programming. 💪
