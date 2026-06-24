# Day 1 Exercises: Instructor Implementation Guide

## Overview

This guide helps you implement the Week 1 code-reading exercises in a way that:
- Builds a class culture of careful code analysis
- Prevents students from using AI or internet shortcuts
- Develops genuine programming understanding
- Establishes expectations for the semester

---

## Quick Implementation Strategy

### Option 1: In-Class Activity (Recommended for Week 1)

**Duration:** 50-60 minutes (one class period)

**Setup:**
1. Print Exercise Set 1 (all 5 tracing exercises)
2. Have students work individually
3. Collect work at end of class

**Execution:**
```
0-5 min:   Introduction & expectations speech
5-25 min:  Exercises 1.1-1.3 (students work, circulate to observe)
25-45 min: Exercises 1.4-1.5 (students work, circulate, help those struggling)
45-50 min: Collect work, brief discussion of common mistakes
```

**Key Points to Emphasize:**
- "No running the code first - that's cheating"
- "We want to see your trace, not just your answer"
- "If you're stuck, ask me or a classmate, not Google"

---

### Option 2: Homework Assignment

**Duration:** 30-45 minutes (home work)

**Assignment:**
- Assign Exercise Sets 1 + 3 (Tracing + Output Prediction)
- Due next class
- Hand-written preferred (harder to plagiarize)

**Submission Format:**
- Either paper or typed PDF
- Must show all work/traces
- Questions with answer blanks to fill in

**Check:**
- Look for traces and reasoning
- Don't just grade answers - grade process

---

### Option 3: Hybrid Approach (Ideal)

**Day 1 - Class Activity:**
- Do Exercise Set 1 (Tracing) in class as guided practice
- Walk through Exercise 1.1 together first
- Then let them do 1.2-1.5 individually
- Collect and review

**Day 2 - Homework:**
- Assign Exercise Sets 2, 3, and 4
- Due next class meeting
- Go over answers in class

**This gives:**
- Immediate feedback (in-class)
- Independent practice (homework)
- Building confidence progressively

---

## Getting Started: The Opening Speech

**Read this to set the tone on Day 1:**

---

### "Welcome to PROG2"

> "Over the next semester, we're going to practice one of the most important skills in programming: **reading code**.
>
> In the real world, you'll spend 80% of your time reading code—your own old code, teammates' code, library code, documentation. You'll spend maybe 20% writing new code.
>
> But here's the problem: Most people skip right to AI. They ask ChatGPT what code does, and they never actually *read* it. That's a disaster.
>
> **In this class, we read code carefully.** That means:
>
> 1. We trace through it step-by-step
> 2. We predict outputs *before* running them
> 3. We explain *why* code works or breaks
> 4. We do NOT search the internet for answers
> 5. We do NOT ask AI to explain our code
>
> If you get stuck, you ask:
> - A classmate (they can help you think)
> - Me (I can guide you to understanding)
> - Not Google, not AI
>
> Why? Because I'm teaching you to be a programmer, not a googler. When you understand code deeply, everything else gets easier.
>
> This first set of exercises is going to feel hard. That's **good**. That means you're building real understanding. Let's start."

---

## Exercise-by-Exercise Implementation Tips

### Exercise Set 1: Code Tracing (Best for Initial Practice)

**Why Start Here:**
- Concrete and visual
- Students can see their work
- Builds systematic thinking

**How to Facilitate:**
1. **Model behavior first:**
   - Do Exercise 1.1 together on whiteboard/screen
   - Say: "I read line-by-line. I check the condition. I update my trace table."
   - Make thinking visible: "What's the value of age? Is age >= 18?"

2. **Then release students:**
   - Exercise 1.2-1.3: Let them try with minimal help
   - Circulate and check traces, not answers
   - If they're wrong, ask: "What happens in iteration 2?"

3. **Red flags to watch for:**
   - Not showing traces (just guessing answers)
   - Skipping steps ("I'll just jump to the end")
   - Not understanding operators

4. **If students are struggling:**
   - Have them talk through it aloud
   - Ask Socratic questions: "What's i at this point?"
   - Don't tell them the answer

**Common Questions:**
- "Can we run the code first to check?" → "No, that's the point!"
- "Is there a shortcut?" → "Not yet - we're building understanding"
- "This is taking too long" → "Good - complexity builds deep learning"

---

### Exercise Set 2: Error Finding (Best for Understanding)

**Why Use This:**
- Develops debugging mindset
- Requires explanation (can't just google)
- Shows common mistakes clearly

**How to Facilitate:**
1. **Do one together** (Exercise 2.1):
   - Ask: "Does this code compile?"
   - Ask: "Does it do what the programmer intended?"
   - Discuss why a semicolon changes everything

2. **Have them find errors independently:**
   - Exercise 2.2-2.4 as homework or partner activity
   - Require written explanation (2-3 sentences)

3. **Class Discussion:**
   - Ask 3-4 students: "What error did you find? Why is it wrong?"
   - Discuss implications: "What if this was in production code?"

**Assessment Notes:**
- Partial credit if they find error but explanation is weak
- Full credit if reasoning is clear even if explanation is brief
- Encourage: "You found an error - that's debugging skill right there"

---

### Exercise Set 3: Output Prediction (Best for Independence Check)

**Why Use This:**
- Tests understanding without help
- Builds confidence when right
- Shows misunderstandings when wrong

**How to Facilitate:**
1. **After Exercise Sets 1-2:**
   - Assign these as independent work
   - "Predict before you run"
   - Compare predictions to actual output

2. **Learning moment if wrong:**
   - DON'T just mark it wrong
   - Ask: "Run the code. What happened differently?"
   - Ask: "Why did you think that?"
   - Help them see the reasoning break

3. **If mostly right:**
   - Celebrate! ("You're reading code correctly")
   - Push harder: Add more complex examples

---

### Exercise Set 4: Code Matching (Best for Review)

**Why Use This:**
- Quick assessment of understanding
- Different thinking skill (pattern matching)
- Good for exit tickets

**How to Facilitate:**
1. **Timing:** Use as review after Set 1-3
2. **Format:** Could be quiz or homework
3. **The "why" matters more:** 
   - Wrong answer with good reasoning = learning opportunity
   - Right answer with no reasoning = guessing (lower credit)

---

## Preventing Cheating & Shortcuts

### Rule #1: Require Traces & Explanations
- Just answers = too easy to cheat
- Traces + explanations = shows real thinking
- Format: "Show your work" sections make this clear

### Rule #2: Vary Exercises
- Different students get slightly different numbers
- Or: Rotate which exercises are homework
- This prevents copy-paste spreading

### Rule #3: Make Submission Tangible
- Prefer hand-written for in-class work
- If digital: Require handwritten traces scanned
- Timestamp: "Turn in by end of class" prevents overnight AI use

### Rule #4: Spot Check Understanding
- Ask 1-2 students: "Walk me through Exercise 1.3"
- Their explanation reveals if they understand or copied
- If they can't explain, you know to help

### Rule #5: Normalize Mistakes
- "I got this wrong - here's what I learned"
- "I misunderstood this operator"
- Show vulnerability: "I make mistakes too, and that's how I learn"

---

## Grading Framework

### What to Grade:

| Aspect | Weight | What to look for |
|--------|--------|-----------------|
| **Completeness** | 20% | All exercises attempted, all blanks filled |
| **Work Shown** | 30% | Clear traces, step-by-step work, variable tracking |
| **Explanations** | 30% | Can explain reasoning in own words, references code |
| **Correctness** | 20% | Outputs/answers match expected results |

### Grading Rubric Examples:

**Full Credit (90-100%):**
- ✅ All exercises complete
- ✅ Traces shown for all problems
- ✅ Explanations are clear and specific
- ✅ Most answers correct

**Good (75-89%):**
- ✅ Most exercises complete
- ✅ Work shown for most exercises
- ✅ Explanations present but brief
- ✅ Some answers incorrect but reasoning visible

**Developing (60-74%):**
- ⚠️ Some exercises incomplete
- ⚠️ Work shown for some exercises
- ⚠️ Explanations lacking detail
- ⚠️ Several answers incorrect

**Needs Support (<60%):**
- ❌ Many incomplete
- ❌ Little to no work shown
- ❌ No explanations
- ❌ Mostly incorrect

### Important: Don't Grade Harshly on Wrong Answers

If student shows clear thinking and work, partial credit is better than zero. You're assessing *thinking*, not just *rightness*.

Example:
- Student predicts "Sum: 6" for Exercise 1.3
- But shows trace: 1+2+3 = 6 (stopped at iteration 3)
- Give 75% - they traced correctly but missed iteration 4
- Use as teaching moment: "What's the loop condition? Does it include 4?"

---

## Discussion Points for Class

**Use these to debrief the exercises:**

### After Exercise Set 1:
- "Which exercise surprised you?"
- "Where did your trace break down?"
- "Did anyone's prediction match perfectly? How?"

### After Exercise Set 2:
- "What's trickier - a compilation error or a logic error? Why?"
- "Would this error be caught by a compiler?"
- "Why is the explanation harder than finding the error?"

### After Exercise Set 3:
- "How many of you got them all right? Good - that means you're reading code!"
- "How many got some wrong? Even better - now you know what to watch for"
- "Which code construct trips you up most?"

### Class Culture Questions:
- "How many of you wanted to google an answer?"
- "How many figured it out by tracing?"
- "What's the difference in how you feel after tracing vs googling?"

---

## If Students Struggle

### Red Flag #1: "I don't understand what the code does"
**Response:**
- "That's okay, let's trace it step-by-step"
- Read first line aloud together
- Ask: "What's the value of x now?"
- One step at a time, don't jump ahead

### Red Flag #2: "I predicted wrong"
**Response:**
- "Perfect - that's how you learn!"
- "Run the code now. What's different from your prediction?"
- "Let's trace to see where your thinking broke"
- "What will you look for next time?"

### Red Flag #3: "This is taking forever"
**Response:**
- "Yes, tracing carefully takes time"
- "That's better than running code 20 times and still not understanding"
- "Speed comes with practice - for now, accuracy is more important"

### Red Flag #4: "Can I just run it and then explain?"
**Response:**
- "No - that defeats the purpose"
- "The whole point is to *predict before you run*"
- "Once you run it, your brain is biased"
- "Trust the process - you'll get better at this"

---

## Connection to Rest of Course

**Explain to students how this matters for PROG2:**

- **Functions lesson:** "Understanding parameter passing requires tracing code"
- **Arrays lesson:** "Nested loops are easiest if you can trace them"
- **Pointers lesson:** "This is impossible if you don't read code carefully"
- **Debugging lesson:** "Debugging is just tracing code methodically"

---

## Optional Extensions

### For Advanced Students:
- "Create your own code for others to trace"
- "Find bugs in real-world C code snippets"
- "Predict output of code with nested structures (3 levels)"

### For Struggling Students:
- "Trace a program with me, then try similar one alone"
- "Use provided trace templates (fill in blanks)"
- "Start with 1-line changes to existing code"

---

## Timeline Suggestions

### Option A: Single Class Period
- Day 1: Introduce, do Exercise Set 1 together and individually
- Collect, review, discuss common mistakes next class

### Option B: Spread Across Week
- Day 1: Exercise Set 1 (tracing) in class
- Day 2: Exercise Set 2 (errors) as homework  
- Day 3: Exercise Set 3 (prediction) as homework
- Day 4: Exercise Set 4 (matching) as quiz
- Day 5: Review, discuss, move to next lesson

### Option C: Progressive Homework
- Assign all exercises as homework
- Students do 1-2 exercises per night
- Discuss answers in class next day
- Takes longer but builds habit

---

## Key Success Metrics

By end of Week 1, students should:
- ✅ Show consistent traces without prompting
- ✅ Explain their reasoning clearly
- ✅ Predict outputs correctly for simple programs
- ✅ Spot simple errors (semicolons, off-by-one)
- ✅ Understand that tracing is a tool, not busywork

---

## Final Thought

This first week sets the tone for the entire semester. If you can get students to:
1. Trust the tracing process
2. Value understanding over speed
3. Explain clearly and show work
4. See errors as learning opportunities

...then the rest of PROG2 will flow much more smoothly.

Good luck! 🚀
