# PROG2 Day 5: Functions Slides
## Interactive Reveal.js Presentation

---

## Overview

This folder contains an interactive Reveal.js presentation that introduces functions in C, covering void functions, value-returning functions, and parameter passing.

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
Introduction to Day 5: Functions in C

### 2. Learning Objectives
What students will learn about functions

### 3. What are Functions?
Definition and benefits of using functions

### 4. Three Types of Functions
Overview comparing void, value-returning, and parameterized functions

### 5-6. Void Functions
- Concept and basic examples
- Trace table showing function call execution
- When to use void functions

### 7-8. Value-Returning Functions
- Concept of returning results
- Trace table showing how return values replace function calls
- Type matching

### 9. Parameters vs Arguments
Clear distinction between terminology

### 10-11. Parameter Passing and Pass-by-Value
- How parameters work (copies, not references)
- Multiple parameter handling
- Parameter order importance

### 12-14. Exercise Walkthroughs
- Exercise 1.1: Missing function call parentheses
- Exercise 2.1: Missing return statement
- Exercise 3.2: Type mismatch in division

### 15-17. Common Function Mistakes
- Forgetting void for functions with no return
- Returning from void functions
- Wrong number or type of arguments

### 18. Function Signature Reference
Breaking down function declaration syntax

### 19. Function Design Checklist
Seven steps for properly designing functions

### 20. Function Types Summary
Comparison table of all function types

### 21. Key Takeaways
Main concepts students must remember

### 22. Debugging Functions Checklist
Step-by-step debugging checklist for function problems

### 23. Final Motivation
Congratulations and next steps

---

## Key Features

✅ **Interactive walkthrough** - Follows function concepts step-by-step

✅ **Real code examples** - Shows actual function examples with bugs and fixes

✅ **Trace tables** - Demonstrates how to trace through function calls

✅ **Color-coded boxes** - Visual distinction of concepts, correct code, and mistakes

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
2. **Pause on each concept** to let students ask questions
3. **Ask questions before showing solutions:**
   - "What will this function return?"
   - "What happens when we call this function?"
   - "Is this correct or is there a bug?"
4. **Refer back to concepts** - emphasize parameter passing and pass-by-value
5. **Connect to exercises** - "This is exactly what Exercise 2.1 asks about"

### Discussion Points

**After Void Functions slides:**
- "When would you use a void function instead of a value-returning function?"
- "Why do we need the () to call a function?"

**After Value-Returning Functions slides:**
- "What happens if you forget the return statement?"
- "Can you return any type of value?"

**After Parameter Passing slides:**
- "Why is pass-by-value important to understand?"
- "What would happen if parameters were changed inside the function?"

**After Exercise Walkthroughs:**
- "Have you seen these bugs before?"
- "How would you trace through this function with pen and paper?"

**After Common Mistakes:**
- "Which of these mistakes have you made?"
- "How did you find and fix the error?"

---

## Integration with Other Materials

**Use alongside:**
- `DAY5_EXERCISES.md` - Student worksheet
- `DAY5_ANSWER_KEY.md` - Detailed solutions
- `README.md` - Overview and teaching guide

**Workflow:**
1. Present Day 5 introduction (Slides 1-4)
2. Explain void functions (Slides 5-6)
3. Explain value-returning functions (Slides 7-8)
4. Explain parameters and pass-by-value (Slides 9-11)
5. Work through exercise examples together (Slides 12-14)
6. Review common mistakes (Slides 15-17)
7. Have students work on Day 5 exercises
8. Review findings using answer key
9. Use debugging checklist (Slide 22) for problem-solving

---

## Slide Count

**Total Slides:** 23

**Time to Present:**
- Quick walkthrough: 40-50 minutes
- With discussion: 75-90 minutes
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

1. **Pacing:** Don't rush through slides. Give students time to understand each function concept.

2. **Engagement:** Ask students to predict the output before showing traces. This keeps them active.

3. **Flexibility:** You can adjust which slides to emphasize based on student needs. Focus on areas where students struggle.

4. **Repetition:** Some students may need to see the same function example multiple times. Don't hesitate to go back.

5. **Live Coding:** Consider coding examples live to show how functions appear in practice.

6. **Extension:** After slides, have students write their own functions for peers to trace and critique.

7. **Connection to Debugging:** Use the debugging checklist (Slide 22) when reviewing function problems with students.

---

## Questions?

If you need:
- **More slides** for specific exercises
- **Different function examples**
- **Additional walkthroughs**
- **Customization for your teaching style**

Refer to the DAY5_ANSWER_KEY.md for more detailed explanations you can reference.

---

Good luck with Day 5! 💪
