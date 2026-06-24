# Week 1 Resources: Quick Start Guide

## 📁 Folder Structure

```
Resources/week1/
├── docs/                          ← Documentation & Exercises
│   ├── README.md                 ← Overview of all files
│   ├── WEEK1_EXERCISES.md        ← Student exercise worksheets
│   ├── WEEK1_ANSWER_KEY.md       ← Instructor answer guide
│   └── INSTRUCTOR_GUIDE.md       ← How to teach this material
│
├── slides/                        ← Interactive Code Tracing Slides
│   ├── deck.mdx                  ← Exercise 1.1 slide deck
│   ├── package.json              ← Project configuration
│   ├── .gitignore                ← Git ignore rules
│   ├── README.md                 ← How to run and customize slides
│   └── node_modules/             ← Dependencies (auto-installed)
│
└── QUICK_START.md                ← This file
```

---

## 🎯 What You Have

### **docs/** - For Teaching Code Reading
- Traditional worksheet-based exercises
- Students work through code traces manually
- Great for independent practice
- Print-friendly format

### **slides/** - For Interactive Visualization
- Modern presentation-style code tracing
- Animate through code step-by-step
- Use during live class teaching
- Great for demonstrations

---

## 🚀 Running the Slides

### Step 1: Open Terminal
```bash
cd /Users/ericmagto/Projects/scs/prog2/Resources/week1/slides
```

### Step 2: Start the Slides
```bash
npm start
```

**Result:** Opens at `http://localhost:3000` with live reload

### Step 3: Present to Students
- Use arrow keys to navigate
- Press `P` for fullscreen presentation mode
- Click or spacebar to go to next slide

---

## 📊 What Exercise 1.1 Slides Show

The deck walks through this C code step-by-step:

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

**Slides cover:**
1. **Full code view** - See the complete program
2. **Step 1:** Declare `age = 15`
3. **Step 2:** Evaluate condition `age >= 18` → FALSE
4. **Step 3:** Execute else block
5. **Step 4:** Print output
6. **Summary** - Review what happened
7. **Challenge** - "Try It Yourself" question for students

Each slide shows:
- 📝 Code with highlighted current line
- 📊 Variable state table
- 💬 Output section
- 📌 Explanation of what's happening

---

## ✏️ Using Both Resources Together

### Option A: In-Class Demo + Homework
1. **Class (30 min):** Run slides, walk through Exercise 1.1 together
   ```bash
   npm start
   ```
2. **Homework:** Have students complete Exercise 1.1 worksheet from `docs/WEEK1_EXERCISES.md`
3. **Compare:** Show them the slide version vs. their hand-traced version

### Option B: Homework + Review
1. **Homework (day 1):** Students do Exercise 1.1-1.3 from worksheet
2. **Review (day 2):** Show slides to verify their understanding
   ```bash
   npm start
   ```

### Option C: Flipped Classroom
1. **Before class:** Share slides with students
2. **In class:** Worksheets to reinforce understanding

---

## 🎨 Customizing the Slides

### Edit Exercise 1.1:
```bash
# Open in any text editor
open /Users/ericmagto/Projects/scs/prog2/Resources/week1/slides/deck.mdx
```

### Create new slides for Exercise 1.2:
Add new sections to `deck.mdx` following the same pattern

### Change the code:
Edit the C code blocks in triple backticks

### Change the theme:
Edit the import at top of `deck.mdx`:
```javascript
import 'code-surfer/themes/night-owl'
```

Options: `night-owl`, `prism`, `dracula`, `duotone-dark`, `duotone-light`

---

## 📚 For Students

### Viewing Slides
If students want to review slides at home:
1. Run `npm start` in slides folder
2. Or export to HTML: `npm export`
3. Share the HTML file

### Using Worksheets
From `docs/WEEK1_EXERCISES.md`:
- Print or work digitally
- **Must show traces** - not just answers
- **Explain your reasoning** - this matters for grading
- Use slides to verify after completing worksheet

---

## ⚡ Quick Commands Reference

```bash
# Start development server (run slides)
npm start

# Build for production
npm build

# Export to static HTML
npm export

# Install dependencies (if needed)
npm install
```

---

## 🔍 What Students Learn

### From Worksheets (docs/):
- How to systematically read code
- How to trace variable changes
- How to predict output
- How to identify errors

### From Slides (slides/):
- Visual representation of code execution
- Animation of variable state changes
- Real-time demonstration of control flow
- Interactive engagement during class

---

## 💡 Pro Tips

### Before Teaching
1. ✅ Test `npm start` before class
2. ✅ Have worksheet printed
3. ✅ Read the INSTRUCTOR_GUIDE.md
4. ✅ Know which navigation keys work

### During Class
1. 📺 Use presenter mode (press P)
2. ⏸️ Pause on questions
3. 💬 Ask students: "What happens next?"
4. 🎯 Use "Try It Yourself" slide for engagement

### After Class
1. 📊 Review student worksheets with answer key
2. 📝 Note common mistakes
3. 🔄 Address misconceptions in next class
4. 🚀 Repeat for Exercises 1.2-1.5

---

## 🆘 Troubleshooting

### Slides won't start?
```bash
# Make sure you're in the right directory
cd /Users/ericmagto/Projects/scs/prog2/Resources/week1/slides

# Try again
npm start
```

### Port 3000 in use?
```bash
npm start -- --port 3001
```

### Need to reinstall?
```bash
rm -rf node_modules package-lock.json
npm install
npm start
```

---

## 📋 Next Steps

1. **Test Exercise 1.1 slides:**
   ```bash
   cd /Users/ericmagto/Projects/scs/prog2/Resources/week1/slides
   npm start
   ```

2. **Create slides for Exercises 1.2-1.5** (optional)
   - Follow same pattern in `deck.mdx`
   - Add new sections with `---` separator

3. **Print worksheets** from `docs/WEEK1_EXERCISES.md`

4. **Read** `docs/INSTRUCTOR_GUIDE.md` for teaching tips

5. **Teach the class!** 🎓

---

## 📚 File Locations

| File | Purpose | Location |
|------|---------|----------|
| Slides | Demo/teach | `slides/deck.mdx` |
| Exercises | Student work | `docs/WEEK1_EXERCISES.md` |
| Answer Key | Grading reference | `docs/WEEK1_ANSWER_KEY.md` |
| Instructor Guide | Teaching tips | `docs/INSTRUCTOR_GUIDE.md` |

---

## ✨ You're All Set!

Everything is ready to teach Week 1. Choose your approach and go!

**Questions?** Check the README files in each folder.

Good luck! 🚀
