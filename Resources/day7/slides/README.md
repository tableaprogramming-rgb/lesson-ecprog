# Day 7: Single-Dimensional Arrays - Interactive Slide Presentations

Interactive slide presentations for visualizing array code execution step-by-step using **Reveal.js**.

No build system needed — just open the HTML files in a browser!

---

## What's Inside

- `index.html` - Main hub with links to all exercises
- `exercise-7.1.html` - Array Declaration & Initialization
- `exercise-7.2.html` - Array Indexing
- `exercise-7.3.html` - Looping Through Arrays
- `exercise-7.4.html` - Array Manipulation
- `exercise-7.5.html` - Searching & Analysis
- `slides.md` - Markdown reference (optional)
- `.gitignore` - Git ignore rules
- `README.md` - This file

---

## Quick Start

### Option 1: Open Directly in Browser
```bash
# Open the main hub
open index.html

# Or open a specific exercise
open exercise-7.1.html
```

Opens immediately with no installation needed! ✨

### Option 2: Serve Locally (Recommended)
```bash
# Using Python (comes pre-installed)
python3 -m http.server 8000

# Then visit http://localhost:8000
```

---

## Navigation

| Key | Action |
|-----|--------|
| **Space** or **→** | Next slide |
| **←** | Previous slide |
| **F** | Fullscreen presentation mode |
| **ESC** | Exit fullscreen mode |
| **?** | Show keyboard shortcuts |

---

## The 5 Exercises

### Exercise 7.1: Array Declaration & Initialization
```c
int numbers[5] = {10, 20, 30, 40, 50};
```
- Shows array declaration syntax
- Memory layout visualization
- Variable tracking as array is initialized

**Slides:** 
1. Title slide
2. Code overview
3. Include library
4. Enter main()
5. Array declaration
6. Array initialization
7. Access first element (index 0)
8. Access last element (index 4)
9. Return from main() + output summary

---

### Exercise 7.2: Array Indexing
```c
int value = numbers[2];  // Access element at index 2
```
- Accessing specific array elements
- Index-to-value mapping
- Demonstrating that index refers to position

**Slides:**
1. Title slide
2. Array diagram
3. Access first element explanation
4. Access middle element explanation
5. Access last element explanation
6. Trace complete execution
7. Output summary
8. Challenge question

---

### Exercise 7.3: Looping Through Arrays
```c
for(int i = 0; i < 5; i++) {
    printf("%d\n", numbers[i]);
}
```
- Loop iteration through array
- Variable tracking (i and array values)
- Output for each iteration

**Slides:**
1. Title slide
2. Array diagram
3. Loop initialization (i = 0)
4. Loop iteration 1 (i = 0)
5. Loop iteration 2 (i = 1)
6. Loop iteration 3 (i = 2)
7. Loop iteration 4 (i = 3)
8. Loop iteration 5 (i = 4)
9. Loop exit (i = 5, condition false)
10. Output summary
11. Challenge question

---

### Exercise 7.4: Array Manipulation
```c
numbers[0] = 100;  // Change value
```
- Modifying array elements
- Building arrays with assignments
- Multiple modifications

**Slides:**
1. Title slide
2. Initial array state
3. First modification explanation
4. After first modification
5. Second modification explanation
6. After second modification
7. Third modification explanation
8. Final array state
9. Output summary
10. Challenge question

---

### Exercise 7.5: Searching & Analysis
```c
// Find maximum value and sum all elements
```
- Iterating to find specific values
- Calculating sums/totals
- Min/max operations

**Slides:**
1. Title slide
2. Array diagram
3. Initialize min/max
4. Iteration 1 (compare values)
5. Iteration 2 (update if needed)
6. Iteration 3 (compare values)
7. Iteration 4 (update if needed)
8. Iteration 5 (compare values)
9. Final min/max values
10. Output summary
11. Challenge question

---

## How to Use in Class

### Live Presentation:
1. Open `index.html` in browser
2. Press `F` for fullscreen presentation mode
3. Use arrow keys or spacebar to navigate
4. Pause on each slide to ask questions:
   - "What's the value of arr[i]?"
   - "What happens when i becomes 5?"
   - "Which branch will execute?"
5. Use "Challenge" slides for student engagement

### Student Self-Study:
1. Share the HTML files with students
2. Students can open and review at own pace
3. Slides show complete execution flow
4. Helps students verify their hand-traced answers

### Flipped Classroom:
1. Send students exercise-7.1.html before class
2. Students watch slides at own pace
3. In class, work through 7.2-7.5 together
4. Use slides as reference/review

---

## Customizing the Slides

### Edit an Exercise:
1. Open the exercise HTML in any text editor
2. Find the sections (look for `<section>` tags)
3. Modify the code or explanations
4. Save and refresh browser

### Add New Slides:
1. Copy one of the step sections
2. Modify the code and explanations
3. Update step numbers and variable tables
4. Save and test

### Change the Theme:
Replace the `black` theme in the `<head>`:
```html
<!-- Change from "black" to one of these: -->
<!-- white, league, sky, beige, simple, serif, blood, night, moon -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
```

---

## Customizing Variable Tables

Each step shows a variable table. To modify:

```html
<!-- Find the variable table section -->
<table style="font-size: 0.8em;">
    <tr>
        <th>Variable</th>
        <th>Type</th>
        <th>Value</th>
    </tr>
    <tr>
        <td>numbers</td>
        <td>int[5]</td>
        <td>[10, 20, 30, 40, 50]</td>
    </tr>
    <!-- Add more rows as needed -->
</table>
```

---

## Available Themes

### Dark (Professional)
- `black` (default) - Dark with white text
- `night` - Dark with purple accents
- `moon` - Dark with blue accents
- `blood` - Dark with red accents

### Light (Print-friendly)
- `white` - Light background
- `sky` - Light blue background
- `beige` - Warm beige background
- `league` - Medium gray

### Try them all and pick what works best for you!

---

## Tips for Effective Presentations

### Before Class:
✅ Test the slides (open in browser)
✅ Practice navigation (arrow keys, spacebar)
✅ Check screen brightness/contrast
✅ Have printed worksheets ready
✅ Have answer key printed for reference

### During Class:
📺 Use fullscreen mode (Press F)
⏸️ Pause between steps for student questions
💬 Ask: "What will happen next?"
🎯 Use "Challenge" slides for engagement
📊 Show variable table for each step

### After Class:
📧 Email HTML files to students for review
📊 Have them compare with their traced answers
📝 Collect common mistakes for next class discussion
🔄 Use slides as reference during marking

---

## Troubleshooting

### Slides won't display?
- Make sure file is saved as `.html` (not `.txt`)
- Open in Chrome, Firefox, Safari, or Edge
- Check browser console (F12) for errors
- Try refreshing the page

### Code not styled correctly?
- Make sure language is specified: `class="language-c"`
- Check that code is in proper `<pre><code>` blocks
- Copy-paste code carefully (watch for line breaks)

### Want to share with students?
- Email them the HTML file
- Or upload to your LMS
- Or share a link if hosted online
- Or use `python3 -m http.server` for local sharing

### Port 8000 in use?
```bash
python3 -m http.server 8001
# Use port 8001 instead
```

---

## File Structure

```
slides/
├── index.html                ← Start here (hub)
├── exercise-7.1.html         ← Declaration & Initialization
├── exercise-7.2.html         ← Indexing
├── exercise-7.3.html         ← Looping
├── exercise-7.4.html         ← Manipulation
├── exercise-7.5.html         ← Searching & Analysis
├── slides.md                  ← Markdown reference
├── .gitignore                ← Git ignore rules
└── README.md                 ← This file
```

That's it! No build system, no dependencies, no configuration. 🎉

---

## Framework Information

**Presentation Framework:** Reveal.js 4.5.0
- Home: https://revealjs.com/
- Themes: https://github.com/hakimel/reveal.js/tree/master/css/theme
- Docs: https://revealjs.com/

**Syntax Highlighting:** Highlight.js 11.8.0
- Home: https://highlightjs.org/
- C Support: Built-in

---

## Quick Reference

| Task | How |
|------|-----|
| Open index | `open index.html` |
| Open exercise | `open exercise-7.1.html` |
| Serve locally | `python3 -m http.server 8000` |
| Fullscreen | Press `F` during presentation |
| Next slide | Press `→` or `Space` |
| Previous slide | Press `←` |
| Show shortcuts | Press `?` |

---

**Created for PROG2: Computer Programming 2**
**Lesson 3: Single-Dimensional Arrays**
**Interactive code tracing presentations using Reveal.js**
