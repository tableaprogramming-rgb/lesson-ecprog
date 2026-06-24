# Day 7 Instructor Guide: Single-Dimensional Arrays

**Comprehensive Teaching Strategy and Implementation Guide**

---

## Table of Contents

1. [Opening Speech](#opening-speech)
2. [Implementation Options](#implementation-options)
3. [Exercise-by-Exercise Facilitation](#exercise-by-exercise-facilitation)
4. [Common Misconceptions](#common-misconceptions)
5. [Grading Framework](#grading-framework)
6. [Strategies for Struggling Students](#strategies-for-struggling-students)
7. [Prevention and Integrity](#prevention-and-integrity)
8. [Timeline Variations](#timeline-variations)
9. [Assessment Strategy](#assessment-strategy)

---

## Opening Speech

**Read this to your class before starting:**

---

"Today we're moving from functions to arrays. Functions let us organize code and pass data around. Arrays let us organize **collections** of data.

Imagine you're building a gradebook. With functions alone, you could store one student's grade in a variable. But what if you have 30 students? Do you create 30 variables? That's impractical.

Arrays solve this. An array is like a filing cabinet with numbered drawers. All the drawers are the same size, all hold the same type of data, and we access each one by its number (called an index).

The key insight: **Arrays let us work with many items as a single unit.**

Over the next few days, we'll learn:
- How to create arrays
- How to access elements by index
- How to loop through arrays
- How to modify and search arrays

Just like with functions, the best way to understand arrays is to **read code carefully, trace execution step-by-step, and predict output before running it.**

Here's what I want from you:
1. **Slow down.** Arrays seem simple until they're not. Rushing leads to off-by-one errors.
2. **Show your work.** Traces, variable tables, step-by-step execution.
3. **Ask yourself first.** Before googling or asking me, try tracing it yourself.
4. **Mistakes are learning.** If your trace is wrong, that's where learning happens. Don't be afraid.

By the end of today, you'll understand arrays well enough to explain them to someone else. Let's go."

---

## Implementation Options

### Option A: Full In-Class (50 minutes) ⭐ **Recommended**

**Time Breakdown:**
- Opening speech & setup: 5 min
- Model 7.1 on whiteboard: 10 min
- Guided practice (7.2-7.3): 15 min
- Independent work (7.4-7.5): 15 min
- Wrap-up & common mistakes: 5 min

**Setup:**
- Print worksheets (or project on screen)
- Have slides ready on computer
- Whiteboard/board for modeling

**Flow:**
1. Give opening speech
2. Project Exercise 7.1 on screen
3. Ask students to read the code
4. Ask: "What's the first line of code? What does it do?"
5. Walk through step-by-step on whiteboard
6. Have students try 7.2 in pairs
7. Circulate and help
8. Show solution for 7.2
9. Repeat for 7.3
10. 7.4-7.5 are independent (optional in-class)
11. Collect worksheets

**Advantages:**
- Immediate feedback
- Can address misconceptions in real-time
- Keeps pace controlled
- Students see professor modeling

**Challenges:**
- Some students may fall behind
- Less time for reflection
- May not finish all exercises

---

### Option B: Homework + Review (2 days)

**Day 1 (Homework):**
- Students work through 7.1-7.3 at home
- 45-60 minutes expected
- Submit traces (on paper or digital)

**Day 2 (In Class - 30 minutes):**
- Review most common mistakes
- Show slides for each exercise
- Discuss 2-3 student questions
- Assign 7.4-7.5 for practice

**Advantages:**
- Students have time to think deeply
- Reduced class time pressure
- More self-paced learning
- Can address struggles with 1-on-1 help

**Challenges:**
- Less immediate feedback
- Harder to catch misconceptions early
- Some students may copy

---

### Option C: Flipped Classroom

**Before Class:**
- Send students slides to watch at own pace
- Optional: Pre-recorded lecture on arrays
- Students attempt 7.1-7.2 at home

**During Class (45 minutes):**
- Brief review (5 min): "What questions about arrays?"
- Hands-on labs (30 min): 
  - Students work on 7.3-7.5 in pairs
  - You circulate and help
  - Show solutions as pairs finish
- Debrief (10 min): Common errors, key takeaways

**Advantages:**
- Students learn at own pace
- Class time is interactive
- More time for hands-on practice
- Works for diverse learning speeds

**Challenges:**
- Students must watch content beforehand
- Less structured introduction
- Some may not engage with slides

---

## Exercise-by-Exercise Facilitation

### Exercise 7.1: Array Declaration & Initialization

**Key Concept:** Arrays reserve memory for multiple elements

**How to Model (Whiteboard):**

```
Step 1: int numbers[5];

        Index: 0    1    2    3    4
        Value: [?] [?] [?] [?] [?]     (? = uninitialized)

Step 2: numbers[0] = 10;

        Index: 0    1    2    3    4
        Value: [10] [?] [?] [?] [?]

Step 3: printf("First element: %d\n", numbers[0]);

        Output: First element: 10
```

**Common Student Questions:**
- **Q: What's in the other elements?**
  A: Garbage values. Could be anything. That's why we initialize.

- **Q: Do all elements have to be the same value?**
  A: No, we'll learn how to set them individually.

- **Q: What if I need more than 5 elements?**
  A: Make the array bigger: `int numbers[100]` for example.

**Facilitation Tips:**
1. Ask: "How many 'slots' does this array have?"
2. Ask: "What are the valid indices?"
3. Ask: "What's in slot 1?" (Emphasize slot 0 exists)
4. Have them draw the array themselves
5. Modify one element, ask about the others

**Watch For:**
- Students using 1-based indexing
- Confusion about array size vs. last index
- Not understanding uninitialized memory

---

### Exercise 7.2: Array Indexing

**Key Concept:** Arrays are accessed by index, indices start at 0

**How to Model (Whiteboard):**

```
Array: int values[4] = {5, 10, 15, 20};

Index:  0    1    2    3
Value: [5] [10] [15] [20]

Access values[0] → 5
Access values[2] → 15
Access values[3] → 20
```

**Common Student Questions:**
- **Q: Why does it start at 0?**
  A: Historical reason from how memory works. Just accept it.

- **Q: What happens if I access values[5]?**
  A: Undefined behavior. Could crash or give garbage. Arrays don't check bounds in C.

- **Q: Can I use a variable as an index?**
  A: Yes! `values[i]` works if i is 0, 1, 2, or 3.

**Facilitation Tips:**
1. Create a large diagram on board
2. Use index notation consistently: arr[i] not arr_i
3. Have them write out: "arr[2] means the element at index 2"
4. Make them predict the index before accessing
5. Show that accessing doesn't change the array

**Watch For:**
- Confusion between value and index
- Off-by-one errors ("shouldn't the last one be at index 4?")
- Believing that the index name matters (arr[i] vs arr[x])

---

### Exercise 7.3: Looping Through Arrays

**Key Concept:** Loops + indices = process entire arrays

**How to Model (Whiteboard):**

```c
int arr[3] = {5, 10, 15};
for(int i = 0; i < 3; i++) {
    printf("%d\n", arr[i]);
}

Trace:
i=0: 0 < 3? YES → arr[0] = 5 → print 5 → i++
i=1: 1 < 3? YES → arr[1] = 10 → print 10 → i++
i=2: 2 < 3? YES → arr[2] = 15 → print 15 → i++
i=3: 3 < 3? NO → exit loop

Output:
5
10
15
```

**Common Student Questions:**
- **Q: Why `i < 3` and not `i <= 3`?**
  A: Because indices go 0, 1, 2 (not 0, 1, 2, 3). If i = 3, arr[3] is out of bounds.

- **Q: Can I start at i = 1?**
  A: Yes, but you'd skip arr[0]. Usually you want to start at 0.

- **Q: Can I use a different variable instead of i?**
  A: Yes! `for(int j = 0; j < 3; j++)` works the same.

**Facilitation Tips:**
1. Create a loop trace table:
   ```
   i | i<3 | arr[i] | Output
   0 | T   | 5      | 5
   1 | T   | 10     | 10
   2 | T   | 15     | 15
   3 | F   | -      | (exit)
   ```
2. Ask: "What's the value of i on each iteration?"
3. Ask: "What is arr[i] on each iteration?"
4. Show what happens with `i <= 3` (error)
5. Let them code this and run it

**Watch For:**
- Using `i <= size` instead of `i < size`
- Confusion about what happens when condition becomes false
- Not understanding that i is just a number
- Thinking the loop variable name matters

---

### Exercise 7.4: Array Manipulation

**Key Concept:** Can change individual elements using loops

**How to Model (Whiteboard):**

```c
int values[3] = {1, 2, 3};
values[0] = values[0] * 10;  // 1 * 10 = 10
values[1] = values[1] + 5;   // 2 + 5 = 7
values[2] = values[0] + values[1];  // 10 + 7 = 17

Array becomes: {10, 7, 17}
```

**Common Student Questions:**
- **Q: Does changing one element affect others?**
  A: No, only that element. Each slot is independent.

- **Q: What if I don't follow the right order?**
  A: Order matters! If we did values[2] first, we'd get different result (show example).

- **Q: Can I modify elements inside a loop?**
  A: Yes, and that's very useful. See Exercise 7.4.2.

**Facilitation Tips:**
1. Show before/after diagrams
2. Emphasize that each assignment is independent
3. Show what happens if order changes
4. Demo modifying in a loop
5. Show conditional modification (if inside loop)

**Watch For:**
- Thinking that modifications cascade
- Not realizing order matters
- Confusion about what the old value is before modification

---

### Exercise 7.5: Searching & Analysis

**Key Concept:** Can iterate to find, sum, or analyze data

**How to Model (Whiteboard):**

```
Sum Example:
Array: {10, 20, 30, 40}
sum = 0
i=0: sum = 0 + 10 = 10
i=1: sum = 10 + 20 = 30
i=2: sum = 30 + 30 = 60
i=3: sum = 60 + 40 = 100

Final sum: 100
Average: 100 / 4 = 25
```

**Common Student Questions:**
- **Q: What's the point of accumulation?**
  A: We need one value (the sum), not five. Loop builds it up.

- **Q: Can I initialize sum to something other than 0?**
  A: Only if you have a reason. Starting at 0 is standard.

- **Q: What about finding min/max?**
  A: Initialize to first element, then compare all others.

**Facilitation Tips:**
1. Show accumulation pattern clearly
2. Show the trace table for sum
3. Show min/max algorithm step-by-step
4. Discuss why we start at i=1 for min/max (already used data[0])
5. Show what happens with different data

**Watch For:**
- Students not understanding accumulation
- Confusion about initialization values
- Not seeing the pattern for different problems

---

## Common Misconceptions

### Misconception 1: "Array size and last index are the same"
**What students think:**
```c
int arr[5];
arr[5] = 10;  // "size is 5, so last index is 5"
```
**Why it's wrong:** Size 5 means indices 0-4. Last index is size-1.
**How to fix:** Show diagrams consistently. Say "size N has indices 0 to N-1."

### Misconception 2: "Modifying one element affects others"
**What students think:**
```c
int a[3] = {1, 2, 3};
a[0] = 100;
// They think: a[1] and a[2] might change
```
**Why it's wrong:** Each element is independent.
**How to fix:** Show memory diagram. Each slot is separate.

### Misconception 3: "Loops must use i as the index"
**What students think:**
```c
for(int counter = 0; counter < 5; counter++) {
    arr[i] = counter;  // Error - i doesn't exist!
}
```
**Why it's wrong:** The loop variable is just a variable. Use whatever name you made.
**How to fix:** Show examples with different variable names.

### Misconception 4: "The index variable persists after the loop"
**What students think:**
```c
for(int i = 0; i < 3; i++) { }
printf("%d\n", i);  // What's i now?
```
**Why it's wrong:** Loop variable is scoped to the loop.
**How to fix:** Show that i = 3 when loop exits, but is then destroyed. Accessing it is an error.

### Misconception 5: "You can resize an array after creation"
**What students think:**
```c
int arr[5];
// Later... I need more space!
arr[10] = 5;  // This works, right?
```
**Why it's wrong:** Array size is fixed at creation. No bounds checking in C.
**How to fix:** Mention that we'll learn about dynamic arrays (malloc) later.

---

## Grading Framework

### Category 1: Correct Output (40%)
- ✅ Output matches expected exactly
- ✅ All values printed in right order
- ✅ Format matches (spaces, newlines, etc.)

### Category 2: Execution Trace (40%)
- ✅ Step-by-step trace shown
- ✅ Variable values at each step
- ✅ Shows what happens at each line
- ✅ Clear progression from start to end

### Category 3: Explanation/Reasoning (20%)
- ✅ Explanation of key operations
- ✅ Why they chose certain answers
- ✅ Shows understanding, not just copying

### Scoring:
```
Full Credit (100%):  Output ✓  Trace ✓  Explanation ✓
Good (85-90%):       Output ✓  Trace ✓  Explanation ~
OK (70-80%):         Output ✓  Trace ~  Explanation ~
Weak (50-70%):       Output ~ or Trace ~ or Explanation ✗
Failed (0-50%):      Output ✗ or No trace shown
```

### Important Rule:
**Process > Answer**

A student with wrong output but clear, careful trace deserves more credit than correct output with no work shown.

```
Example 1:
Output: WRONG
Trace: Clear, detailed, shows thinking
Explanation: Good understanding
Grade: 75-85% (shows understanding, made an error)

Example 2:
Output: CORRECT
Trace: None shown
Explanation: None
Grade: 30-40% (may have guessed or copied)
```

---

## Strategies for Struggling Students

### Student A: "I don't understand how indexing works"
**Signs:** Confusing index with value, off-by-one errors, trying to access arr[size]

**Strategy:**
1. Go back to the diagram. Draw it repeatedly.
2. Use colored markers for index (one color) and value (another color).
3. Have them count out loud: "Index 0, index 1, index 2..."
4. Have them write: arr[0]=value, arr[1]=value for small array
5. Don't move forward until this is solid.

### Student B: "I can't predict output, I need to run the code"
**Signs:** Refuses to trace, immediately compiles, doesn't think before running

**Strategy:**
1. Don't allow them to compile until after prediction.
2. Say: "I want your thought process first, then we'll verify."
3. Have them explain their prediction out loud before writing it.
4. Compare their prediction to actual output. If wrong, trace together to find the error.
5. Celebrate when they're right - reinforce that thinking works.

### Student C: "I understand loops, but not with arrays"
**Signs:** Fine with for loops alone, struggles when combining with array access

**Strategy:**
1. Separate the concerns: Loop structure vs. array access
2. Use a table showing loop variable and array access:
   ```
   i | i < 5 | arr[i]
   0 | true  | ?
   ...
   ```
3. Fill in the loop column first (they already know this)
4. Then fill in the array column
5. Then combine them in code

### Student D: "Off-by-one errors every time"
**Signs:** Consistently uses arr[size], or arr[size-1] when should use arr[0], etc.

**Strategy:**
1. Create a rule card they keep:
   ```
   Array size N → indices are 0, 1, ..., N-1
   Loop: for(i = 0; i < N; i++)
   Valid: arr[0] through arr[N-1]
   Invalid: arr[N] and above
   ```
2. Before every loop, ask: "What's the size? What's the last index?"
3. Make them write it down first
4. Then write the loop

### Student E: "I get the concept but the details trip me up"
**Signs:** Understand the big picture but miss small things (parentheses, semicolons, etc.)

**Strategy:**
1. Slow down - they're going too fast
2. Use a checklist:
   ```
   [ ] Array size matches loop condition?
   [ ] Indices correct (0 to size-1)?
   [ ] Variable names consistent?
   [ ] Output format matches expected?
   ```
3. Have them check their own work using checklist
4. Build a habit of being careful

---

## Prevention and Integrity

### How to Prevent Cheating

#### Issue 1: Students copying from each other
**Prevention:**
- Vary the exercises slightly (different numbers, different conditions)
- Have them explain their reasoning aloud
- Collect work frequently
- Spot-check by asking: "Show me where you traced this step"

#### Issue 2: Students using AI (ChatGPT, etc.)
**Prevention:**
- Emphasize: "I want YOUR thought process"
- Collect work-in-progress, not just final answer
- Ask detailed questions: "Why did you predict this output?"
- If answer is too good, ask them to explain the trace
- Compare AI patterns: AI traces are often too polished

#### Issue 3: Students running code instead of thinking
**Prevention:**
- Make prediction before code execution
- Don't allow compilation until they submit prediction
- Grade prediction separately
- Show them that thinking first improves their understanding

### The Culture You Set
The most important prevention is **making thinking visible and valued**.

If students see that you:
- Grade process over answer
- Ask them to explain their reasoning
- Celebrate correct thinking even with wrong output
- Catch and discuss errors as learning moments

Then they'll buy in. They'll want to show you they thought carefully.

---

## Timeline Variations

### Variation A: Single 50-minute session (Most Common)
See "Option A: Full In-Class" above.

### Variation B: Two 50-minute sessions
**Session 1 (50 min):**
- Opening speech: 5 min
- Explain arrays concept: 10 min
- 7.1: Declaration & Initialization: 15 min
- 7.2: Indexing: 15 min
- Preview looping: 5 min

**Session 2 (50 min):**
- Review 7.1-7.2: 10 min
- 7.3: Looping: 15 min
- 7.4: Manipulation: 15 min
- 7.5: Searching: 10 min

### Variation C: Mini-sessions throughout a week
**Day 1 (20 min):** 7.1 Declaration
**Day 2 (20 min):** 7.2 Indexing
**Day 3 (20 min):** 7.3 Looping
**Day 4 (20 min):** 7.4-7.5 Applications

### Variation D: Flipped approach (see Option C above)

---

## Assessment Strategy

### Formative Assessment (During Learning)
Use these to check understanding in-real-time:

1. **Whiteboardding:**
   - Ask students to draw array diagrams on mini-whiteboards
   - Hold them up so you can see misconceptions
   - Correct immediately

2. **Think-Pair-Share:**
   - "Think about this code silently (1 min)"
   - "Pair up and discuss (2 min)"
   - "Share with class (1 min)"
   - You hear what students are thinking

3. **One-Minute Traces:**
   - "Trace this code in 1 minute. Go!"
   - Collect (don't grade) - just read
   - See patterns of misunderstanding

4. **Exit Ticket:**
   - Last 2 minutes: "Write one thing that confused you"
   - Shows what to re-teach next time

### Summative Assessment (After Learning)
Grade the worksheets using the rubric in Grading Framework section.

### Mastery Check
After grading, categorize students:

```
✅ Mastery (85%+): Understands arrays well. Ready for next topic.
⚠️ Developing (70-84%): Getting it, needs practice. Maybe one more day.
❌ Struggling (< 70%): Significant misconceptions. Needs intervention.
```

**For Struggling:**
- Offer office hours
- Provide extra practice problems
- Pair with peer tutor
- Revisit specific concept

---

## Tips for Success

### Before Class
- [ ] Read all exercise solutions
- [ ] Think about what will confuse students
- [ ] Prepare whiteboard space
- [ ] Test any code examples you'll use
- [ ] Prepare slides/projector

### During Class
- [ ] Give opening speech (set tone)
- [ ] Model Exercise 7.1 completely
- [ ] Ask questions, don't just tell
- [ ] Circulate and listen
- [ ] Correct misconceptions immediately
- [ ] Celebrate effort and thinking
- [ ] Summarize key points at end

### After Class
- [ ] Review student work
- [ ] Note patterns of misunderstanding
- [ ] Plan reteach for next class if needed
- [ ] Provide feedback to students
- [ ] Keep this guide for next semester

---

## Troubleshooting Common Class Situations

### Situation 1: Everyone looks confused
**What to do:**
- Stop and check: "Does everyone understand what an array is?"
- Go back to the definition and diagram
- Don't move forward until basics are clear
- This is salvageable, but moving on won't help

### Situation 2: Some students finished in 5 minutes
**What to do:**
- Have challenge problems ready (Challenge 7.1-7.3 in worksheet)
- Ask them: "Can you explain this to someone else?"
- Pair them with struggling students
- Don't let them just sit - keeps them engaged

### Situation 3: Only 2 students have submitted
**What to do:**
- Check in with quiet students individually
- "Are you stuck? What's confusing?"
- Offer to model a similar problem
- Give them extension if needed
- Document who needs extra help

### Situation 4: Multiple students got answer right but trace is wrong
**What to do:**
- They might have guessed or used AI
- In next class, ask them to explain
- Highlight this pattern in class: "Getting the answer matters less than understanding"
- Reinforce tracing in all future assignments

---

## Resources for You

### If students need more practice:
- Create variations of exercises with different numbers
- Use Challenge Problems in worksheet
- Point them to online array resources (after class)

### If you need to reteach:
- Use the slides (exercise-7.1.html, etc.) as review
- Create simpler examples for struggling students
- Use the "Strategies for Struggling Students" section

### If students ask about more advanced topics:
- 2D arrays: "That's Lesson 4"
- Strings: "Strings are arrays of characters, Lesson 6"
- Dynamic arrays: "That's advanced, uses malloc()"
- Pointers: "Lesson 5"

---

## Final Words

Array teaching is about building **deep understanding**. Students who really understand arrays will find functions, pointers, and advanced topics much easier.

Don't rush. Don't let students move forward if they're confused. Spend time on this.

And remember: The student who struggles through an off-by-one error and then fixes it has learned more than the student who got it right the first time without thinking.

Good luck! You've got this! 🚀

---

**Created for PROG2: Computer Programming 2**
**Lesson 3: Single-Dimensional Arrays**
**Focus: Deep understanding through careful code reading**
