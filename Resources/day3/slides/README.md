# PROG2 Day 3: Interactive Presentations

This folder contains Reveal.js-based interactive presentations for debugging exercises.

---

## What's Included

### Fully Created Presentations ✅ (All 5 Complete)
- **index.html** - Main menu with links to all exercises
- **exercise-1.1.html** - Off-by-one error (< vs <=)
- **exercise-1.2.html** - Assignment vs comparison (= vs ==)
- **exercise-2.1.html** - AND vs OR operator (&& vs ||)
- **exercise-2.2.html** - Missing loop increment
- **exercise-3.1.html** - Logic error (backwards condition)

---

## Day 3 Presentation Structure

Unlike Day 1-2, Day 3 presentations don't show step-by-step execution.

Instead, they show:
1. **The Context** - What should the program do?
2. **The Buggy Code** - What code are we debugging?
3. **The Bug Highlighted** - Where's the error and why?
4. **The Fix** - What's the correct code?
5. **Verification** - Does the fix work?
6. **Key Lesson** - What did we learn?

---

## All Exercises Complete ✅

### Exercise 1.1: Off-by-One Error
- **Bug Type:** Loop boundary condition
- **Code:** Sum numbers 1 to 5
- **Buggy Output:** Sum: 10 (should be 15)
- **Bug:** `i < 5` should be `i <= 5`
- **Difficulty:** Easy
- **File:** `exercise-1.1.html`

### Exercise 1.2: Assignment vs Comparison
- **Bug Type:** Wrong operator (= vs ==)
- **Code:** Check if x equals 5
- **Buggy Output:** Always prints "x is 5"
- **Bug:** `if (x = 5)` should be `if (x == 5)`
- **Difficulty:** Easy
- **File:** `exercise-1.2.html`

### Exercise 2.1: AND vs OR Operator
- **Bug Type:** Wrong logical operator (&& vs ||)
- **Code:** Check if x is in range 0 < x < 10
- **Buggy Output:** "In range" for x = 15 (wrong!)
- **Bug:** `if (x > 0 || x < 10)` should be `if (x > 0 && x < 10)`
- **Difficulty:** Easy-Medium
- **File:** `exercise-2.1.html`

### Exercise 2.2: Missing Loop Increment
- **Bug Type:** Missing increment in for loop
- **Code:** Print numbers 1 to 5
- **Buggy Output:** Prints 1 forever (infinite loop)
- **Bug:** `for (int i = 1; i <= 5; )` missing `i++`
- **Difficulty:** Medium
- **File:** `exercise-2.2.html`

### Exercise 3.1: Logic Error (Backwards Condition)
- **Bug Type:** Backwards condition logic
- **Code:** Check if number is positive
- **Buggy Output:** "x is negative" for x = 10 (wrong!)
- **Bug:** `if (x < 0)` should be `if (x > 0)`
- **Difficulty:** Medium
- **File:** `exercise-3.1.html`

---

## How to Use

### View in Browser
```bash
open /Users/ericmagto/Projects/scs/prog2/Resources/day3/slides/index.html
```

### Teaching
1. Open index.html
2. Click exercise link
3. Project on screen (press F for fullscreen)
4. Walk through each slide with class
5. Pause to discuss and ask questions

### Navigation
- **Spacebar/Right Arrow**: Next slide
- **Left Arrow**: Previous slide
- **F**: Fullscreen mode
- **ESC**: Exit fullscreen
- **?**: Keyboard help

---

## Presentation Slide Order

Each debugging presentation follows this structure:

**Slide 1: Title**
- Exercise number and name
- Type of bug

**Slide 2: Context**
- What should the program do?
- Expected output

**Slide 3: Buggy Code**
- Show the buggy code
- Show actual (wrong) output
- Highlight discrepancy

**Slide 4: Bug Highlighted**
- Show the specific bug
- Explain what's wrong
- Show why it causes the error

**Slide 5: The Fix**
- Show corrected code
- Highlight what changed
- Explain the fix

**Slide 6: Verification**
- Show buggy output
- Show correct output
- Confirm fix works

**Slide 7: Key Lesson**
- Summarize learning point
- Connect to broader concepts
- Tips for avoiding this bug

---

## Design Patterns

### Color Scheme
- **Accent**: `#ffaa00` (orange) - Headers
- **Correct**: `#66ff66` (green) - Fixed code, correct output
- **Bug**: `#ff6666` (red) - Buggy code, wrong output
- **Output**: `#4CAF50` on `#001a00` - Terminal-style

### Layout
- Two-column when comparing buggy vs fixed
- Single column for full explanation
- Info boxes for context/explanation
- Output boxes for terminal output

### Styling
- Consistent with Day 1-2 presentations
- Home button (gradient purple)
- Fade transitions
- Clear visual hierarchy

---

## Creating Additional Day 3 Exercises

### Template Structure

```html
<!-- SLIDE 2: CONTEXT -->
<section>
    <h2 style="color: #ffaa00;">The Context</h2>
    <p>What should the program do?</p>
    <p>Expected output: ...</p>
</section>

<!-- SLIDE 3: BUGGY CODE -->
<section>
    <h2>The Buggy Code</h2>
    [Show code]
    Actual output: ...
    Expected: ...
</section>

<!-- SLIDE 4: BUG HIGHLIGHTED -->
<section>
    <h2>The Bug</h2>
    <div class="bug-highlight">
        🐛 What's wrong
    </div>
    <p>Explanation of why it's wrong</p>
</section>

<!-- SLIDE 5: THE FIX -->
<section>
    <h2>The Fix</h2>
    [Show corrected code]
    <div class="correct-highlight">
        ✓ What changed
    </div>
</section>

<!-- SLIDE 6: VERIFICATION -->
<section>
    Buggy output: ...
    Fixed output: ...
</section>

<!-- SLIDE 7: LESSON -->
<section>
    Key learning point and tips
</section>
```

---

## Bug Types for Future Exercises

### Easy (Good for Introduction)
- Off-by-one in loop boundaries (`<` vs `<=`)
- Wrong comparison operator (`=` vs `==`)
- Missing loop increment

### Medium (Building Skills)
- Wrong logical operator (`&&` vs `||`)
- Incorrect variable in condition
- Loop condition logic error

### Hard (Advanced Challenge)
- Subtle boundary conditions
- Complex nested logic
- Multiple bugs in one program

---

## Teaching Tips

### Effective Debugging Discussion
1. **Don't explain immediately** - Let students struggle first
2. **Ask guiding questions** - "What should happen here?"
3. **Have them trace** - Show the step-by-step breakdown
4. **Celebrate discovery** - "Good catch!" when they find it
5. **Connect to professional work** - "Real programmers do this daily"

### Preventing Student Frustration
- Start with easy bugs (confidence builder)
- Show context clearly (without context, bugs are impossible)
- Explain that bugs are normal and expected
- Pair harder exercises with support

### Making It Engaging
- Ask: "Can you spot the bug before I reveal it?"
- Challenge: "Fix this in 2 minutes"
- Compare: "What if we wanted X instead?"
- Create scenarios: "What would a user notice?"

---

## Common Bugs to Cover (Future)

1. **Off-by-one**: Loop boundaries
2. **Operators**: `<` vs `<=`, `&&` vs `||`, `=` vs `==`
3. **Variables**: Using wrong variable in condition
4. **Logic**: Condition is backwards (should be `!`)
5. **Increments**: Missing or wrong increment
6. **Initialization**: Variable starts at wrong value
7. **Nesting**: Wrong nesting level
8. **Array**: Off-by-one with array indexing

---

## File Organization

```
day3/slides/
├── index.html              ← Main menu with all 5 exercises
├── exercise-1.1.html       ← Off-by-one error in loop
├── exercise-1.2.html       ← Assignment vs comparison
├── exercise-2.1.html       ← AND vs OR operator
├── exercise-2.2.html       ← Missing loop increment
├── exercise-3.1.html       ← Logic error (backwards condition)
├── slides.md               ← Optional markdown reference
└── README.md               ← This file
```

---

## Dependencies

All resources use CDN:
- **Reveal.js** 4.5.0 (Presentation framework)
- **Highlight.js** 11.8.0 (Syntax highlighting)
- No local packages needed
- No build process required

---

## Version Info

- **Framework**: Reveal.js 4.5.0
- **Syntax Highlighter**: Highlight.js 11.8.0
- **Theme**: Black (customized)
- **Last Updated**: [Date created]

---

**Created for PROG2 Day 3: Debugging - Finding and Fixing Bugs**

Good luck with debugging! 🐛→🔧
