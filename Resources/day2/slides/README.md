# PROG2 Day 2: Interactive Presentations

This folder contains Reveal.js-based interactive presentations for stepping through code execution.

---

## What's Included

### Fully Created Presentations ✅
- **index.html** - Main menu with links to all exercises
- **exercise-2.1.html** - Simple AND condition (complete example)
- **exercise-3.1.html** - Basic while loop counter (complete example)

### Template Pattern 📋
The remaining presentations follow the same structure as 2.1 and 3.1:
- Title slide
- Full code overview
- Step-by-step execution slides
- Variable state tracking
- Output display
- Key takeaway slide

---

## Complete Exercise List

### Exercise Set 1: Compound Conditions (AND/OR)
- [x] Exercise 2.1: Simple AND (DONE - full presentation)
- [ ] Exercise 2.2: AND with False Result
- [ ] Exercise 2.3: Simple OR
- [ ] Exercise 2.4: Complex AND
- [ ] Exercise 2.5: Multiple OR conditions

**Code Pattern Example (2.2):**
```c
int age = 16;
int hasLicense = 1;

if (age >= 18 && hasLicense == 1) {
    printf("You can drive\n");
} else {
    printf("You cannot drive\n");
}
```
**Expected Output:** `You cannot drive`
**Key Point:** One part of AND is FALSE → whole condition FALSE

---

### Exercise Set 2: While Loops
- [x] Exercise 3.1: Basic Counter Loop (DONE - full presentation)
- [ ] Exercise 3.2: Accumulation Loop
- [ ] Exercise 3.3: Decrement Loop

**Code Pattern Example (3.2):**
```c
int i = 0;
int sum = 0;

while (i < 4) {
    sum = sum + (i + 1);
    i = i + 1;
}

printf("Sum: %d\n", sum);
```
**Expected Output:** `Sum: 10` (1+2+3+4)
**Key Point:** Track multiple variables in loop

---

### Exercise Set 3: Mixed Logic (Conditions in Loops)
- [ ] Exercise 4.1: If-else Inside While Loop
- [ ] Exercise 4.2: AND Condition Inside While Loop

**Code Pattern Example (4.1):**
```c
int i = 1;

while (i <= 4) {
    if (i % 2 == 0) {
        printf("%d is even\n", i);
    } else {
        printf("%d is odd\n", i);
    }
    i = i + 1;
}
```
**Expected Output:**
```
1 is odd
2 is even
3 is odd
4 is even
```
**Key Point:** Condition checked each iteration

---

## How to Use

### View in Browser
1. Open `index.html` in a web browser
2. Click on exercise links to view presentations
3. Use arrow keys or spacebar to navigate slides
4. Press `F` for fullscreen mode
5. Press `?` to see keyboard shortcuts

### Teaching
- Use fullscreen mode (F) for projecting
- Pause on each step to ask questions
- Let students predict before advancing slides
- Compare with worksheet answers

---

## Creating Additional Presentations

### Quick Template

Copy this structure for new presentations:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PROG2 Day 2 - Exercise X.X [TITLE]</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/reveal.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.8.0/styles/monokai.min.css">
    <!-- [Copy styling from exercise-2.1.html] -->
</head>
<body>
    <a href="index.html" class="back-button">← Back to Menu</a>

    <div class="reveal">
        <div class="slides">
            <!-- SLIDE 1: Title -->
            <section>
                <h1>Exercise X.X</h1>
                <h3>[EXERCISE TITLE]</h3>
                <p style="margin-top: 40px;">Learning: [KEY CONCEPT]</p>
            </section>

            <!-- SLIDE 2: Full Code Overview -->
            <section>
                <h2 style="color: #ffaa00;">The Code</h2>
                <pre style="width: 50%;"><code class="language-c">
[FULL C CODE HERE]
                </code></pre>
            </section>

            <!-- SLIDES 3+: Step-by-Step Execution -->
            <!-- Use structure from 2.1 or 3.1 as template -->

            <!-- FINAL SLIDE: Key Takeaway -->
            <section>
                <h2 style="color: #ffaa00;">Key Takeaway</h2>
                <p>[MAIN LEARNING POINT]</p>
            </section>
        </div>
    </div>

    <!-- [Copy scripts from exercise-2.1.html] -->
</body>
</html>
```

---

## Styling Guide

### Color Scheme
- **Accent**: `#ffaa00` (orange) - Titles, highlights
- **Highlight**: `#ffdd00` (bright yellow) - Important values
- **True**: `#00ff00` (green) - Condition TRUE
- **False**: `#ff8888` (red) - Condition FALSE
- **Output**: `#00ff00` on `#001a00` - Terminal-style

### Layout Pattern

**Three-Section Layout:**

```
┌─────────────────────────────────────┐
│         SLIDE HEADER                │
│   (Title + Description)             │
├─────────────────────────────────────┤
│   CODE (50%)     │   VARIABLES (50%)│
│  - Full code     │  - Current state │
│  - Comment marks │  - Condition val │
│    execution     │  - Result        │
├─────────────────────────────────────┤
│         OUTPUT SECTION              │
│    (Console output display)         │
└─────────────────────────────────────┘
```

---

## Presentation Sections

### Standard Slide Components

**1. Title Slide**
- Exercise number and title
- Learning focus
- Key concept teaser

**2. Full Code Slide**
- Complete code centered
- Sets context for steps
- What question to answer

**3. Step Slides (3-N)**
- One logical step per slide
- Three-section layout (header/content/output)
- Progress indication
- Variable state updates

**4. Final Slide**
- Complete output
- Key takeaway
- Learning reinforcement

---

## Tips for Creating Steps

### For Compound Condition Exercises
- Show both parts separately
- Use `<div class="condition-eval">` for each part
- Show AND/OR combination
- Highlight result with `<div class="and-result">`

### For While Loop Exercises
- Check condition BEFORE showing body execution
- Show variable update clearly
- Indicate "go back to condition check"
- Count iterations explicitly

### For Mixed Logic Exercises
- Show loop check first
- Then show condition inside
- Then show action
- Then show variable updates
- Then "loop back"

---

## File Organization

```
slides/
├── index.html                  ← Main menu
├── exercise-2.1.html          ← Simple AND (complete)
├── exercise-2.2.html          ← To be created
├── exercise-2.3.html          ← To be created
├── exercise-2.4.html          ← To be created
├── exercise-2.5.html          ← To be created
├── exercise-3.1.html          ← Basic while (complete)
├── exercise-3.2.html          ← To be created
├── exercise-3.3.html          ← To be created
├── exercise-4.1.html          ← To be created
├── exercise-4.2.html          ← To be created
├── slides.md                   ← Optional markdown reference
└── README.md                   ← This file
```

---

## Navigation

### From Menu
- Click any exercise link to jump to that presentation
- Back button returns to menu

### Within Presentation
- **Spacebar/Right Arrow**: Next slide
- **Left Arrow**: Previous slide
- **Up/Down Arrows**: Jump to different slides
- **F**: Fullscreen mode
- **ESC**: Exit fullscreen
- **?**: Keyboard help

---

## Customization

### Change Theme
Replace the theme link in `<head>`:
```html
<!-- Options: white, league, sky, beige, simple, serif, blood, night, moon -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
```

### Change Transition
In the Reveal.initialize section:
```javascript
transition: 'fade',  // Options: fade, slide, convex, concave, zoom, none
```

### Adjust Font Sizes
Modify the font-size in `<style>`:
- `.code-column pre`: Code font size
- `.variables-section`: Variables font size
- `.output-box`: Output font size

---

## Dependencies

All resources loaded from CDN:
- **Reveal.js** 4.5.0 (Presentation framework)
- **Highlight.js** 11.8.0 (Syntax highlighting)
- No local npm packages needed
- No build process required

---

## Questions?

- **"How do I create a new presentation?"** → Copy the template section above
- **"How do I change colors?"** → Update the hex codes in `<style>`
- **"Can I use this for other exercises?"** → Yes! Follow the same pattern
- **"How do I add more steps?"** → Copy a step slide and modify

---

## Version Info

- **Framework**: Reveal.js 4.5.0
- **Syntax Highlighter**: Highlight.js 11.8.0
- **Theme**: Black (customized)
- **Last Updated**: [Date created]

---

**Created for PROG2 Day 2: Control Structures - Stepping Up**

Good luck! 🚀
