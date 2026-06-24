# Day 7 Resources: Single-Dimensional Arrays - Quick Start Guide

## 📁 Folder Structure

```
Resources/day7/
├── docs/                          ← Documentation & Exercises
│   ├── README.md                 ← Overview of all files
│   ├── DAY7_EXERCISES.md         ← Student exercise worksheets
│   ├── DAY7_ANSWER_KEY.md        ← Instructor answer guide
│   └── INSTRUCTOR_GUIDE.md       ← How to teach this material
│
├── slides/                        ← Interactive Code Tracing Slides
│   ├── exercise-7.1.html         ← Array Declaration & Initialization
│   ├── exercise-7.2.html         ← Array Indexing
│   ├── exercise-7.3.html         ← Looping Through Arrays
│   ├── exercise-7.4.html         ← Array Manipulation
│   ├── exercise-7.5.html         ← Searching/Analysis
│   ├── index.html                ← Presentation hub (links to all exercises)
│   ├── README.md                 ← How to run and customize slides
│   ├── slides.md                 ← Markdown reference
│   ├── .gitignore                ← Git ignore rules
│   └── assets/                   ← (optional) Images/resources
│
└── QUICK_START.md                ← This file
```

---

## 🎯 What You Have

### **docs/** - For Teaching Code Reading
- Traditional worksheet-based exercises
- Students work through array problems manually
- Great for independent practice
- Print-friendly format

### **slides/** - For Interactive Visualization
- Modern presentation-style code tracing
- Animate through code step-by-step
- Use during live class teaching
- Great for demonstrations

---

## 📋 The 5 Exercises

| Exercise | Topic | Focus |
|----------|-------|-------|
| **7.1** | Array Declaration & Initialization | Declaring arrays, initializing with values |
| **7.2** | Array Indexing | Accessing elements by index (arr[i]) |
| **7.3** | Looping Through Arrays | Using loops to iterate through array elements |
| **7.4** | Array Manipulation | Modifying array values, building arrays dynamically |
| **7.5** | Searching/Analysis | Finding elements, calculating totals, finding min/max |

---

## 🚀 Running the Slides

### Step 1: Open Terminal
```bash
cd /Users/ericmagto/Projects/scs/prog2/Resources/day7/slides
```

### Step 2: View Slides
Option A: Direct open
```bash
open index.html
```

Option B: Serve locally (recommended)
```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Step 3: Present to Students
- Use arrow keys or spacebar to navigate
- Press `F` for fullscreen presentation mode
- Click on exercise links in `index.html` to jump to specific exercises

---

## ⌨️ Keyboard Navigation

| Key | Action |
|-----|--------|
| **Space** or **→** | Next slide |
| **←** | Previous slide |
| **F** | Fullscreen presentation mode |
| **ESC** | Exit fullscreen |
| **?** | Show all keyboard shortcuts |

---

## ✏️ Using Both Resources Together

### Option A: In-Class Demo + Homework
1. **Class (30 min):** Run slides for Exercise 7.1-7.3
2. **Homework:** Have students complete worksheet exercises
3. **Compare:** Show them slide versions vs. their hand-traced versions

### Option B: Homework + Review
1. **Homework (day 1):** Students complete exercises 7.1-7.3 from worksheet
2. **Review (day 2):** Show slides to verify their understanding

### Option C: Flipped Classroom
1. **Before class:** Share slides with students
2. **In class:** Use worksheets to reinforce understanding
3. **After class:** Review with answer key

---

## 📊 What Each Slide Set Shows

### Exercise 7.1: Declaration & Initialization
```c
int numbers[5] = {10, 20, 30, 40, 50};
```
- Slide sequence showing array declaration
- Memory layout visualization
- Variable tracking for array

### Exercise 7.2: Indexing
```c
int value = numbers[2];  // Access element at index 2
```
- Accessing specific array elements
- Index-to-value mapping
- Multiple element access examples

### Exercise 7.3: Looping
```c
for(int i = 0; i < 5; i++) {
    printf("%d\n", numbers[i]);
}
```
- Loop iteration through array
- Variable tracking (i and array values)
- Output for each iteration

### Exercise 7.4: Manipulation
```c
numbers[0] = 100;  // Change value
```
- Modifying array elements
- Building arrays with assignments
- Multiple modifications

### Exercise 7.5: Searching/Analysis
```c
// Find maximum value in array
```
- Iterating to find specific values
- Calculating sums/averages
- Min/max operations

---

## 🎨 Customizing the Slides

### Edit an Exercise:
```bash
# Open in text editor
open /Users/ericmagto/Projects/scs/prog2/Resources/day7/slides/exercise-7.1.html
```

### Create new slides:
- Copy one of the step sections
- Modify the code and explanations
- Update step numbers and variable tables

### Change the theme:
Look for the `<link>` tag in the `<head>`:
```html
<!-- Change from "black" to: white, league, sky, beige, simple, serif, blood, night, moon -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
```

---

## 📚 For Students

### Viewing Slides
1. Open `index.html` in browser
2. Click exercise links to navigate
3. Use arrow keys to step through
4. Share HTML files with students for review

### Using Worksheets
From `docs/DAY7_EXERCISES.md`:
- Print or work digitally
- Show traces/explanations
- Use slides to verify answers

---

## 💡 Pro Tips

### Before Teaching
1. ✅ Test slides (open in browser)
2. ✅ Have worksheets printed
3. ✅ Read INSTRUCTOR_GUIDE.md
4. ✅ Practice navigation keys

### During Class
1. 📺 Use fullscreen mode (Press F)
2. ⏸️ Pause on questions
3. 💬 Ask students: "What happens next?"
4. 🎯 Use Challenge slides for engagement

### After Class
1. 📊 Review student worksheets with answer key
2. 📝 Note common mistakes
3. 🔄 Address misconceptions next class
4. 🚀 Progress to next exercises

---

## 📝 Quick Instructor Checklist

**Before Class (20 minutes):**
- [ ] Read INSTRUCTOR_GUIDE.md (especially opening speech)
- [ ] Review DAY7_ANSWER_KEY.md
- [ ] Print or share DAY7_EXERCISES.md
- [ ] Test slides in browser
- [ ] Practice presentation mode (F key)

**During Class (45-50 minutes):**
- [ ] Opening speech setting expectations
- [ ] Model Exercise 7.1 on whiteboard
- [ ] Students work on 7.2-7.3 (guided)
- [ ] Students work on 7.4-7.5 (independent)
- [ ] Wrap-up with one common mistake

**After Class:**
- [ ] Grade worksheets using answer key
- [ ] Note patterns of misunderstanding
- [ ] Plan next class based on common errors

---

## 🆘 Troubleshooting

### Slides won't open?
```bash
# Make sure you're in right directory
cd /Users/ericmagto/Projects/scs/prog2/Resources/day7/slides

# Try opening directly
open index.html
```

### Port 8000 in use?
```bash
python3 -m http.server 8001
# Use port 8001 instead
```

### Slideshow navigation not working?
- Make sure file is `.html` not `.txt`
- Open in modern browser (Chrome, Firefox, Safari, Edge)
- Check JavaScript is enabled

---

## 📋 Next Steps

1. **Read the docs:**
   - Review `docs/README.md` for exercise overview
   - Read `docs/INSTRUCTOR_GUIDE.md` for teaching strategy

2. **Test the slides:**
   ```bash
   cd /Users/ericmagto/Projects/scs/prog2/Resources/day7/slides
   open index.html
   ```

3. **Review exercises:**
   - Open `docs/DAY7_EXERCISES.md`
   - Check `docs/DAY7_ANSWER_KEY.md` for answers

4. **Teach the class!** 🎓

---

## 📚 File Locations

| File | Purpose | Location |
|------|---------|----------|
| Slides Hub | Navigate all exercises | `slides/index.html` |
| Exercise 7.1 Slides | Array declaration | `slides/exercise-7.1.html` |
| Exercise 7.2 Slides | Array indexing | `slides/exercise-7.2.html` |
| Exercise 7.3 Slides | Array loops | `slides/exercise-7.3.html` |
| Exercise 7.4 Slides | Array manipulation | `slides/exercise-7.4.html` |
| Exercise 7.5 Slides | Searching/analysis | `slides/exercise-7.5.html` |
| Exercises | Student work | `docs/DAY7_EXERCISES.md` |
| Answer Key | Grading reference | `docs/DAY7_ANSWER_KEY.md` |
| Instructor Guide | Teaching tips | `docs/INSTRUCTOR_GUIDE.md` |

---

## ✨ You're All Set!

Everything is ready to teach Day 7 (Single-Dimensional Arrays).

**Questions?** Check the README files in `docs/` and `slides/` folders.

Good luck! 🚀
