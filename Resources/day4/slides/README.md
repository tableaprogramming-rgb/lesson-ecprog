# PROG2 Day 4: Debugging Slides
## Interactive Reveal.js Presentation

---

## Overview

This folder contains an interactive Reveal.js presentation that introduces the 6 categories of debugging bugs and walks through the debugging process.

**File:** `index.html`

---

## How to Use

### View the Presentation

**Option 1: Open directly in browser**
```bash
open index.html
```

**Option 2: Run with local server**
```bash
python3 -m http.server 8000
# Then visit: http://localhost:8000/index.html
```

---

## Keyboard Navigation

- **Spacebar** or **Right Arrow**: Next slide
- **Left Arrow**: Previous slide
- **F**: Fullscreen presentation mode
- **ESC**: Exit fullscreen, show slide overview
- **?**: Show all keyboard shortcuts

---

## Presentation Structure

### 1. Title Slide
Introduction to Day 4: Advanced Debugging

### 2. Learning Objectives
What students will learn

### 3. The Debugging Process
The 6-step systematic approach:
1. READ - Understand intent
2. PREDICT - What will happen?
3. TRACE - Step through execution
4. FIND - Which line is wrong?
5. FIX - Write correct version
6. VERIFY - Confirm fix works

### 4-5. Exercise Set 1: Logic Operators
- Overview of || vs && confusion
- Exercise 1.1: Range check bug walkthrough
- Analysis and verification

### 6-8. Exercise Set 2: Counters & Accumulators
- Category overview
- Exercise 2.1: Double counting
- Exercise 2.2: Wrong variable

### 9-11. Exercise Set 3: Loop Control
- Category overview
- Exercise 3.1: Wrong increment
- Exercise 3.2: Nested loop off-by-one

### 12-14. Exercise Set 4: Boundary Conditions
- Category overview
- Exercise 4.1: Reversed operator
- Operator reference guide

### 15-16. Exercise Set 5: Complex Logic
- Category overview
- AND vs OR truth table with examples

### 17-18. Exercise Set 6: Variable State
- Category overview
- Exercise 6.1: Forgotten reset

### 19-23. Summary & Tips
- Summary table of all 6 categories
- Tips for finding bugs
- Debugging checklist
- Next steps
- Final motivation slide

---

## Key Features

✅ **Interactive walkthrough** - Follows the debugging process step-by-step

✅ **Real code examples** - Shows actual buggy code from exercises

✅ **Trace tables** - Demonstrates how to trace through code

✅ **Color-coded boxes** - Visual distinction of bugs vs fixes

✅ **Responsive design** - Works on all screen sizes

✅ **Keyboard shortcuts** - Full navigation support

✅ **Fade transitions** - Clean, professional appearance

✅ **Syntax highlighting** - Color-coded C code

---

## Customization

### Change Colors
Edit the `<style>` section:
```css
.reveal h1, .reveal h2, .reveal h3 {
    color: #64B5F6;     /* Change header color */
}
```

### Modify Transitions
In the `Reveal.initialize()` section:
```javascript
transition: 'fade',    // Options: slide, fade, convex, concave, zoom, etc.
```

### Adjust Layout
```javascript
width: '100%',
margin: 0.1,           // Space around slides
minScale: 0.2,
maxScale: 2.0
```

---

## Teaching Tips

### In the Classroom

1. **Use fullscreen mode (F)** for projection
2. **Pause on each bug example** to let students predict the output
3. **Ask questions before showing the trace:**
   - "What will i = 3 evaluate to?"
   - "Which numbers will be counted?"
   - "Is this the bug or just a trace?"
4. **Refer back to the debugging process** - emphasize each step
5. **Connect to their work** - "This is exactly what Set 1 in your exercises asks"

### Discussion Points

**After Exercise 1.1:**
- "Why is OR wrong for range checking?"
- "When would you use OR instead of AND?"

**After Exercise 2.1:**
- "What other mistakes could cause double-counting?"

**After Exercise 3.1:**
- "What other increment values might be wrong?"

**After Exercise 4.1:**
- "How do you remember the difference between < and >?"
- "Why are these errors so common?"

**After Exercise 5.1:**
- "Draw your own truth table for different conditions"

**After Exercise 6.1:**
- "Where else might forgetting to reset cause problems?"

---

## Integration with Other Materials

**Use alongside:**
- `DAY4_EXERCISES.md` - Student worksheet
- `DAY4_ANSWER_KEY.md` - Detailed solutions
- `README.md` - Overview and teaching guide

**Workflow:**
1. Present Day 4 introduction (Slides 1-3)
2. Explain the debugging process (Slide 3)
3. Work through Exercise Set 1 together (Slides 4-5)
4. Have students attempt Exercise Set 2 (slides as reference)
5. Review findings using answer key
6. Repeat for remaining sets

---

## Slide Count

**Total Slides:** 23

**Time to Present:**
- Quick walkthrough: 30-45 minutes
- With discussion: 60-90 minutes
- Interactive (with student participation): 90-120 minutes

---

## Browser Compatibility

Works in:
- Chrome/Chromium
- Firefox
- Safari
- Edge
- Any modern browser supporting HTML5 + ES6

---

## Offline Use

This presentation is **fully self-contained**:
- All libraries loaded from CDN
- No internet needed after libraries are cached
- Works offline in modern browsers

---

## Troubleshooting

**Issue:** Slides don't appear
- **Fix:** Make sure index.html is in the same folder as README.md
- **Fix:** Check browser console (F12) for errors

**Issue:** Code highlighting not working
- **Fix:** Highlight.js is loaded from CDN - check internet connection
- **Fix:** Syntax will still display even if highlighting fails

**Issue:** Keyboard navigation not working
- **Fix:** Click on a slide first, then use keyboard
- **Fix:** Try pressing ESC to reset focus

**Issue:** Fullscreen not working
- **Fix:** Some browsers require user interaction first
- **Fix:** Press F after clicking on the presentation

---

## Resources

- **Reveal.js Documentation:** https://revealjs.com/
- **Highlight.js Documentation:** https://highlightjs.org/
- **Keyboard Shortcuts:** Press ? on any slide

---

## Version Info

- **Reveal.js:** 4.5.0 (CDN)
- **Highlight.js:** 11.8.0 (CDN)
- **Created:** June 16, 2026
- **For:** PROG2 Enrichment Course, Summer Session

---

## Notes for Instructors

1. **Pacing:** Don't rush through slides. Give students time to process each bug.

2. **Engagement:** Ask students to predict before showing traces. This keeps them active.

3. **Flexibility:** You can skip sections based on student needs. Focus on categories that were problematic in the exam.

4. **Repetition:** Some students may need to see the same bug multiple times. Don't hesitate to go back.

5. **Live Coding:** Consider coding examples live to show how bugs appear in practice.

6. **Extension:** After slides, have students write bugs for each category for peers to find.

---

## Questions?

If you need:
- **More slides** for specific exercises
- **Different bug examples**
- **Additional categories**
- **Customization for your teaching style**

Refer to the DAY4_ANSWER_KEY.md for more detailed explanations you can reference.

---

Good luck with Day 4! 💪
