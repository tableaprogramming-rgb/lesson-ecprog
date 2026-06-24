# PROG2 Week 1: Code Tracing Slides

Interactive slide presentations for visualizing code execution step-by-step using **Reveal.js**.

No build system needed — just open the HTML file in a browser!

---

## What's Inside

- `index.html` - Exercise 1.1 line-by-line code tracing presentation
- `.gitignore` - Git ignore rules
- `README.md` - This file

---

## Quick Start

### Option 1: Open Directly in Browser
```bash
# Simply open the file
open index.html

# Or drag and drop into your browser
```

Opens immediately with no installation needed! ✨

### Option 2: Serve Locally (Recommended)
```bash
# Using Python (comes pre-installed)
python3 -m http.server 8000

# Then visit http://localhost:8000
```

---

## Slide Navigation

| Key | Action |
|-----|--------|
| **Space** or **→** | Next slide |
| **←** | Previous slide |
| **F** | Fullscreen presentation mode |
| **ESC** | Exit fullscreen mode |
| **?** | Show keyboard shortcuts |

---

## What Exercise 1.1 Shows

The presentation walks through this C code **step-by-step**:

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

**Slides include:**
1. ✅ Full code view
2. ✅ Step-by-step execution (7 steps)
3. ✅ Variable state tracking (each step)
4. ✅ Condition evaluation (TRUE/FALSE)
5. ✅ Branch selection (which path taken)
6. ✅ Program output display
7. ✅ Execution summary (all steps)
8. ✅ Challenge question for students

---

## How to Use in Class

### Live Presentation:
1. Open `index.html` in browser
2. Press `F` for fullscreen presentation mode
3. Use arrow keys or spacebar to navigate
4. Pause on each slide to ask questions:
   - "What's the value of age?"
   - "Is the condition true or false?"
   - "Which branch will execute?"
5. Use "Challenge" slide for student engagement

### Student Self-Study:
1. Share the HTML file with students
2. Students can open and review at own pace
3. Slides show complete execution flow
4. Helps students verify their hand-traced answers

---

## Customizing the Slides

### Edit the Code:
1. Open `index.html` in any text editor
2. Find the `<code class="language-c">` blocks
3. Replace with your own C code

### Add New Exercises:
1. Copy one of the step sections
2. Modify the code and explanations
3. Update step numbers and variable tables

### Change the Theme:
Replace the `black` theme in the `<head>`:
```html
<!-- Change this line: -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">

<!-- To one of these: -->
<!-- white, league, sky, beige, simple, serif, blood, night, moon -->
```

---

## Creating More Exercise Slides

### Template for a new exercise:

```html
<!-- Step Template -->
<section>
    <div class="slide-section">
        <div class="step-number">Step N: [Description]</div>
        <h3>[What Happens]</h3>
        <pre><code class="language-c">[Your code with highlights]</code></pre>
        <div class="variable-table">
            <table>
                <tr>
                    <th>Variable</th>
                    <th>Type</th>
                    <th>Value</th>
                </tr>
                <tr>
                    <td>[var]</td>
                    <td>[type]</td>
                    <td>[value]</td>
                </tr>
            </table>
        </div>
        <p style="font-size: 0.8em; color: #ffaa00;">📌 [Explanation]</p>
    </div>
</section>
```

---

## Available Themes

For dark/professional presentations:
- `black` (default) - Dark with white text
- `night` - Dark with purple accents
- `moon` - Dark with blue accents

For light presentations:
- `white` - Light background
- `sky` - Light blue background
- `beige` - Warm beige background

---

## Tips for Effective Presentations

### Before Class:
✅ Test the slides (open in browser)
✅ Practice navigation
✅ Check screen brightness/contrast
✅ Have printer-friendly worksheet ready

### During Class:
📺 Use fullscreen mode (Press F)
⏸️ Pause between steps for questions
💬 Ask: "What will happen next?"
🎯 Use "Challenge" slide for engagement

### After Class:
📧 Email HTML file to students for review
📊 Have them compare with their traced answers
📝 Collect common mistakes for discussion

---

## Troubleshooting

### Slides won't display?
- Make sure file is saved as `.html` (not `.txt`)
- Open in Chrome, Firefox, Safari, or Edge
- Check browser console (F12) for errors

### Code not styled correctly?
- Make sure language is specified: `class="language-c"`
- Copy-paste code carefully (watch for line breaks)

### Want to share with students?
- Email them the `index.html` file
- Or upload to your LMS
- Or share a link if hosted online

---

## File Structure

```
slides/
├── index.html        ← Exercise 1.1 presentation
├── .gitignore        ← Git ignore rules
└── README.md         ← This file
```

That's it! No build system, no dependencies, no configuration. 🎉

---

## More Information

- **Reveal.js Docs:** https://revealjs.com/
- **Reveal.js Themes:** https://github.com/hakimel/reveal.js/tree/master/css/theme
- **HTML5 Cheatsheet:** https://htmlcheatsheet.com/

---

**Created for PROG2 Course - Week 1 Code Tracing Exercises**
