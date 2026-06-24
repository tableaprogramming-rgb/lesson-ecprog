# DAY 8: Multi-Dimensional Arrays (2D Arrays) - Interactive Slides

**Course:** Computer Programming 2 (PROG2)  
**Date:** June 24, 2026  
**Topic:** 2D Arrays - Declaration, Initialization, Access, and Basic Operations

---

## Overview

This folder contains interactive Reveal.js presentations for Day 8 of the PROG2 course. Each file is a self-contained HTML presentation that can be opened directly in any modern web browser.

### Files in This Directory

| File | Content | Duration |
|------|---------|----------|
| **index.html** | Main overview of 2D arrays | 15-20 min |
| **exercise-8.1.html** | Declaration and initialization | 10 min |
| **exercise-8.2.html** | Nested loops and traversal | 10 min |
| **exercise-8.3.html** | Row and column operations | 10 min |
| **exercise-8.4.html** | Functions with 2D array parameters | 10 min |
| **exercise-8.5.html** | Searching in 2D arrays | 10 min |
| **exercise-8.6.html** | Matrix transpose | 10 min |
| **exercise-8.7.html** | Practical application (grade matrix) | 15 min |

---

## How to Use

### For Students

1. **Open in Browser:**
   - Double-click any HTML file, or
   - Right-click → "Open with" → Select your browser

2. **Navigate:**
   - **Right Arrow** or **Spacebar:** Next slide
   - **Left Arrow:** Previous slide
   - **F:** Fullscreen (recommended for classroom)
   - **ESC:** Exit fullscreen
   - **?:** Show keyboard shortcuts

3. **Recommended Order:**
   - Start with `index.html` for overview
   - Then work through `exercise-8.1.html` through `exercise-8.7.html` in order
   - Each exercise builds on previous concepts

### For Instructors

1. **Setup:**
   - Open `index.html` first
   - Use fullscreen mode (F) for classroom projection
   - Have `../docs/INSTRUCTOR_GUIDE.md` available for reference

2. **Teaching Flow:**
   - Show overview slides (index.html)
   - Follow session plan from instructor guide
   - Use exercise presentations during live coding
   - Pause on key slides to discuss with students

3. **Live Coding:**
   - Open IDE alongside presentation
   - Show code execution as you go through slides
   - Have students code along in their own IDEs

---

## Content Breakdown

### Main Presentation (index.html)

**10 Slides covering:**
1. Title and course info
2. Real-world examples (grades, game boards, images)
3. 2D array concept with visualization
4. Declaration syntax
5. Initialization methods
6. Element access
7. Nested loops for traversal
8. Functions with 2D array parameters
9. Common algorithms (sum, max, search)
10. Navigation to exercises

**Teaching Approach:** Big picture first, then drill down into exercises

### Exercise Presentations

#### Exercise 8.1: Declaration & Initialization
- Shows how to declare a 3×3 matrix
- Demonstrates array initialization with nested braces
- Step-by-step access to specific elements
- Visualizes matrix structure

#### Exercise 8.2: Nested Loops & Traversal
- Shows nested loop execution order
- Demonstrates sum calculation loop
- Visualizes inner/outer loop iteration
- Emphasizes row-major traversal

#### Exercise 8.3: Row & Column Operations
- Shows how to fix one index and vary the other
- Compares row operations vs. column operations
- Visualizes selective element access
- Key concept for understanding 2D data

#### Exercise 8.4: Functions & Parameters
- Demonstrates passing 2D arrays to functions
- Shows why column count is required
- Visualizes function call with array parameter
- Common mistake: forgetting column count

#### Exercise 8.5: Searching
- Shows linear search algorithm in 2D
- Uses flag for early exit optimization
- Visualizes position found [row][col]
- Practical application example

#### Exercise 8.6: Matrix Transpose
- Demonstrates dimension swap (3×3 → 3×3, or 2×3 → 3×2)
- Shows index swapping: transpose[j][i] = matrix[i][j]
- Visualizes before/after transpose
- Real-world application in mathematics

#### Exercise 8.7: Practical Application
- Real-world scenario: student grade matrix
- Shows multiple operations on same data
- Demonstrates averaging, finding max/min
- Formatted output example

---

## Technical Details

### Framework
- **Reveal.js 4.5.0** - Presentation framework (CDN-based)
- **Highlight.js 11.8.0** - Syntax highlighting for code
- **No build step required** - Pure HTML, works in any modern browser

### Theme
- Black theme with custom blue accents (#64B5F6)
- Optimized for classroom projection
- High contrast for readability

### Features
- Fade transitions between slides
- Code syntax highlighting
- Matrix visualization grids
- Variable state tables
- Responsive layout

### Browser Support
- Chrome ✅
- Firefox ✅
- Safari ✅
- Edge ✅
- Mobile browsers (landscape orientation recommended)

---

## Classroom Tips

### Before Class
- [ ] Test each HTML file in your browser
- [ ] Check projector compatibility
- [ ] Prepare IDE for live coding examples
- [ ] Have printed handouts ready (optional)
- [ ] Set up internet (CDN resources needed for fonts)

### During Class
- Use fullscreen mode (F key) for best classroom viewing
- Pause on complex slides to let students catch up
- Ask questions before advancing
- Live code alongside presentations
- Refer back to visuals when explaining concepts

### After Class
- Share links to these presentations with students
- Let students review at their own pace
- Consider recording your audio over slides for asynchronous learning
- Use as reference during office hours

---

## Navigation Map

```
Start Here
    ↓
index.html (Overview)
    ↓
exercise-8.1.html (Declaration)
    ↓
exercise-8.2.html (Loops)
    ↓
exercise-8.3.html (Rows/Columns)
    ↓
exercise-8.4.html (Functions)
    ↓
exercise-8.5.html (Search)
    ↓
exercise-8.6.html (Transpose)
    ↓
exercise-8.7.html (Application)
    ↓
Back to ../docs/ for exercises and answers
```

---

## Common Student Questions While Viewing

**Q: "Why do we need both [rows][cols]?"**
A: Rows organize horizontal lines of data, columns organize vertical. You need both to locate any element.

**Q: "Can I access matrix[2][5] in a 3×4 array?"**
A: No, columns are 0-3, so [5] is out of bounds. This causes an error.

**Q: "Why does the inner loop run 3 times before the outer loop advances?"**
A: That's how nested loops work - inner loop completes all iterations before outer loop increments.

**Q: "How is this different from a single long array?"**
A: Conceptually the same (linear in memory), but 2D arrays let us think in rows/columns, which matches real-world data.

---

## Presentation Settings

### Recommended Projector Setup
- **Resolution:** 1920×1080 (full HD) or higher
- **Aspect Ratio:** 16:9 (modern projectors)
- **Brightness:** High (classroom lights on)
- **Refresh Rate:** 60Hz minimum

### Font Scaling
- Code examples use small fonts (0.5em - 0.7em)
- Sit closer to screen or enlarge browser (Ctrl/Cmd + +)
- Title text should be readable from back of classroom

---

## Technical Troubleshooting

### "Slides won't load"
- Check internet connection (CDN resources needed)
- Try a different browser
- Clear browser cache (Ctrl+Shift+Delete)

### "Code looks blurry or misaligned"
- Ensure fullscreen mode (F key)
- Check projector resolution matches laptop
- Zoom in browser if needed (Ctrl + +)

### "Transitions are slow"
- This is normal fade transition
- Reduce other running applications for smoother performance
- Try disabling auto-play features

### "Arrow keys don't work"
- Ensure window focus is in presentation area (click on slide)
- Some OS/keyboard combinations may need different keys
- Use on-screen navigation buttons if available

---

## Customization

### To Edit Slides
1. Open HTML file in text editor (VS Code, Sublime Text, etc.)
2. Find the slide you want to edit (marked with `<section>`)
3. Modify the content between section tags
4. Save file
5. Refresh browser to see changes

### To Change Theme
- In the HTML file, find this line:
  ```html
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
  ```
- Replace "black" with one of: white, league, sky, beige, simple, serif, blood, night, moon
- Refresh browser to see new theme

### To Add Custom Styling
- Find the `<style>` section near the top
- Add your CSS rules
- Refresh browser to see changes

---

## Extending Content

### To Add More Exercises
1. Duplicate an existing exercise HTML file
2. Change the filename (e.g., exercise-8.8.html)
3. Update titles and content for new exercise
4. Add link to index.html navigation buttons

### To Add More Steps/Slides
1. Find the `<section>` tags for a specific slide
2. Copy the entire `<section>...</section>` block
3. Insert after the slide you want to extend
4. Modify the content for your new slide

### Template for New Exercise Section
```html
<section>
    <div class="slide-container">
        <div class="slide-header">
            <h2>Exercise #.#: [Title]</h2>
            <p>[Description]</p>
        </div>
        <div class="slide-content">
            <!-- Your content here -->
        </div>
    </div>
</section>
```

---

## Performance Notes

- These presentations are lightweight (~50-100 KB per file)
- Load quickly even on slow internet (CDN cached)
- Work well on older computers and tablets
- No plugins or Flash required

---

## Accessibility

### For Students with Visual Impairments
- High contrast black/blue color scheme
- Large text for titles
- Code formatted with monospace font
- Consider offering text versions of presentations

### For Students with Learning Differences
- Slides present same content multiple ways (visual + code)
- Step-by-step progression through examples
- Frequent pause points for discussion
- Aligned with provided written exercises

---

## Related Resources

- **Exercises & Answers:** See `../docs/` folder
- **Instructor Guide:** See `../docs/INSTRUCTOR_GUIDE.md`
- **Student Worksheets:** See `../docs/DAY8_EXERCISES.md`
- **Answer Key:** See `../docs/DAY8_ANSWER_KEY.md`

---

## Quick Reference: Keyboard Shortcuts

| Key | Action |
|-----|--------|
| Right Arrow / Space | Next slide |
| Left Arrow | Previous slide |
| F | Fullscreen |
| ESC | Exit fullscreen |
| ? | Show help |
| S | Show speaker notes (if available) |
| B | Pause presentation |
| . | Blank screen (any key to resume) |

---

## Credits

- **Framework:** Reveal.js by Hakim El Hattab
- **Syntax Highlighting:** Highlight.js
- **Course:** PROG2 - Computer Programming 2
- **Institution:** University of San Jose-Recoletos

---

**Last Updated:** June 23, 2026  
**Maintainer:** [Instructor Name]  
**License:** Educational - Free to use and modify for teaching

---

## Summary

You have everything you need for Day 8 of PROG2:
- ✅ Complete course overview (index.html)
- ✅ 7 interactive exercise presentations (exercise-8.1 through 8.7)
- ✅ Student worksheets with 7 exercises
- ✅ Complete answer key with solutions
- ✅ Detailed instructor guide with teaching plan
- ✅ Visual diagrams and examples throughout

Start with `index.html` in fullscreen mode for best classroom experience!
