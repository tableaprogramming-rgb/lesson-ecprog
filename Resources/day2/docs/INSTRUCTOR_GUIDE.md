# Day 2 Exercises: Instructor Implementation Guide

## Overview

This guide helps you implement the Day 2 code-reading exercises in a way that:
- Builds on Day 1 skills (tracing fundamentals)
- Introduces compound logic (AND/OR operators)
- Develops while loop understanding
- Prevents shortcuts with AI or internet
- Establishes expectations for prerequisite mastery

---

## Quick Implementation Strategy

### Option 1: In-Class Activity (Recommended for Day 2)

**Duration:** 60 minutes (one class period)

**Setup:**
1. Have whiteboard/screen ready for modeling
2. Print Exercise Sets 1-2 (Compound Conditions + While Loops)
3. Have students work individually or in pairs

**Execution:**
```
0-5 min:   Brief review of Day 1 AND introduction to Day 2
5-20 min:  Exercise Set 1 (Compound Conditions 2.1-2.3) - students work
20-30 min: Exercise Set 2 (While Loops 3.1-3.2) - circulate and observe
30-50 min: Exercise Set 3 (Mixed 4.1-4.2) - guided with some help
50-60 min: Collect work, discuss common mistakes
```

**Key Points to Emphasize:**
- "Day 2 builds on Day 1 - use your tracing skills"
- "AND means BOTH must be true; OR means only ONE"
- "Check the loop condition before EACH iteration"
- "If stuck, trace one more step"

---

### Option 2: Homework Assignment

**Duration:** 45-60 minutes (homework)

**Assignment:**
- Assign Exercise Sets 1 + 2 (Conditions + Simple Loops)
- Due next class
- Hand-written preferred

**Check:**
- Look for condition evaluation traces
- Verify loop iteration counts
- Grade reasoning, not just answers

---

### Option 3: Hybrid Approach (Ideal)

**Day 2 - Class Activity:**
- Do Exercise Set 1 (Compound Conditions) in class
- Walk through Exercise 2.1 together first
- Then let them do 2.2-2.5 individually
- Collect and review

**Day 3 - Homework:**
- Assign Exercise Sets 2, 3, 4, and 5
- Due next class meeting
- Go over answers in class

**Benefits:**
- Immediate feedback on compound conditions
- Independent practice on loops
- Build confidence progressively

---

## Key Concepts to Emphasize

### Concept 1: AND (&&) vs OR (||)

**The Critical Distinction:**

| Operator | Truth Table | When True |
|----------|-------------|-----------|
| AND (&&) | T AND T = T<br/>T AND F = F<br/>F AND T = F<br/>F AND F = F | Only when BOTH are true |
| OR (\\|\|) | T OR T = T<br/>T OR F = T<br/>F OR T = T<br/>F OR F = F | When AT LEAST ONE is true |

**Teaching Analogy:**
- AND: "You need money AND a ticket to enter the movie"
  - Missing either one = you're out
- OR: "You have a car OR a bike to get to school"
  - Having either one = you're fine

---

### Concept 2: While Loop Mechanics

**Three Parts of a While Loop:**
```
while (CONDITION) {         // Check condition FIRST
    // Body executes        // Only if condition is TRUE
    UPDATE_VARIABLE;        // Usually increment/decrement
}
```

**Execution Order:**
1. Check condition
2. If TRUE: execute body
3. Go back to step 1
4. If FALSE: exit loop

**Common Confusion:**
- "Does the loop check the condition before or after?"
  - Answer: BEFORE each iteration

---

## Exercise-by-Exercise Implementation Tips

### Exercise Set 1: Compound Conditions (Best for Introducing AND/OR)

**Why Start Here:**
- Single if-else structure (familiar from Day 1)
- Focus is on evaluating the condition
- No loop complexity

**How to Facilitate:**

1. **Model Exercise 2.1 on board:**
   ```
   age = 20, hasLicense = 1

   Check: age >= 18?  → 20 >= 18? → YES ✓
   Check: hasLicense == 1? → 1 == 1? → YES ✓
   AND result: YES AND YES → YES ✓

   Execute if block: "You can drive"
   ```

2. **Emphasize the step-by-step approach:**
   - "First check the first part"
   - "Then check the second part"
   - "Then combine with AND or OR"

3. **Red flags to watch for:**
   - Only checking one part of condition
   - Confusing AND with OR
   - Not showing work
   - Using wrong comparison operator

4. **If students struggle:**
   - Have them write out both parts separately
   - Ask: "Is part 1 true? Yes or no?"
   - Ask: "Is part 2 true? Yes or no?"
   - Ask: "For AND, do BOTH need to be true?"

**Common Questions:**
- "Can I skip checking one part?" → "No, you must check both for AND"
- "Does the order matter?" → "No, 1 AND 2 = 2 AND 1"
- "What if one is true and one is false?" → "Then AND is false"

---

### Exercise Set 2: Simple While Loops (Best for Loop Foundation)

**Why Use This:**
- Single while loop (no nested conditions yet)
- Clear iteration pattern
- Easy to trace manually

**How to Facilitate:**

1. **Model Exercise 3.1 on board:**
   ```
   count = 1

   Before iteration 1:
     Check: count <= 3? → 1 <= 3? → YES
     Print: "Count: 1"
     count = 1 + 1 = 2

   Before iteration 2:
     Check: count <= 3? → 2 <= 3? → YES
     Print: "Count: 2"
     count = 2 + 1 = 3

   Before iteration 3:
     Check: count <= 3? → 3 <= 3? → YES
     Print: "Count: 3"
     count = 3 + 1 = 4

   Before iteration 4:
     Check: count <= 3? → 4 <= 3? → NO
     Loop exits
   ```

2. **Emphasize the condition check:**
   - "The condition is checked BEFORE each iteration"
   - "If true, we do the body"
   - "If false, we exit"

3. **Red flags:**
   - Not checking condition each iteration
   - Forgetting to update variable inside loop
   - Off-by-one errors (< vs <=)
   - Losing track of variable value

4. **If students struggle:**
   - Have them write condition check for each iteration
   - Use numbers on fingers to count iterations
   - Say values aloud: "count is 1... count is 2..."

**Common Questions:**
- "How many times does it loop?" → "Check the condition each time"
- "When does it stop?" → "When the condition becomes false"
- "Should I count the last check?" → "Yes, always count every condition check"

---

### Exercise Set 3: Nested Conditions & Loops (Mixed Logic)

**Why Use This:**
- Combines loop + condition
- More realistic programming
- Tests deeper understanding

**How to Facilitate:**

1. **Do Exercise 4.1 together:**
   - First: Show the loop structure
   - Then: Show the if-else inside
   - Finally: Trace one iteration together

2. **Guide through the pattern:**
   - "Each iteration, we check the condition"
   - "If true, do this; if false, do that"
   - "Then move to next iteration"

3. **Red flags:**
   - Not understanding modulo (%)
   - Skipping condition checks
   - Assuming all iterations the same
   - Wrong branch selection

4. **If students struggle:**
   - Do first iteration together
   - Then let them try second alone
   - Compare: "Did iteration 2 work the same as iteration 1?"

---

## Preventing Common Errors

### Error Type 1: AND/OR Confusion

**Prevention:**
- Explicitly teach the truth tables
- Use real-world examples
- Have them write both parts separately
- Use different colors for AND vs OR

**If You See This Error:**
- Ask: "For AND, do both need to be true?"
- Ask: "For OR, does only one need to be true?"
- Have them fill out truth table together

---

### Error Type 2: Off-by-One Loop Errors

**Prevention:**
- Have students write the condition check for EACH iteration
- Use tallies to count iterations
- Explicitly show when loop stops

**If You See This Error:**
- Ask: "Check: does the condition become false?"
- Ask: "What's the value when the condition fails?"
- Trace one iteration past where they think it stops

---

### Error Type 3: Nested Logic Mistakes

**Prevention:**
- Always show condition checks INSIDE the loop body
- Use indentation clearly
- Mark which branch executes with arrows

**If You See This Error:**
- Ask: "Which part of the loop are we in?"
- Ask: "Did we just update the variable?"
- Have them check the condition for current iteration

---

## Grading Framework

### What to Grade:

| Aspect | Weight | What to look for |
|--------|--------|-----------------|
| **Completeness** | 20% | All exercises attempted, all conditions evaluated |
| **Condition Work** | 25% | Both parts of AND/OR shown, evaluation clear |
| **Loop Tracing** | 25% | Condition checked each iteration, variables updated |
| **Explanations** | 20% | Clear reasoning, references to AND/OR/loop logic |
| **Correctness** | 10% | Outputs/answers match expected results |

### Grading Rubric Examples:

**Full Credit (90-100%):**
- ✅ All exercises complete
- ✅ Both parts of conditions evaluated clearly
- ✅ Loop condition checked each iteration
- ✅ Clear explanations of AND/OR logic
- ✅ Mostly correct answers

**Good (75-89%):**
- ✅ Most exercises complete
- ✅ Condition work shown for most
- ✅ Loop tracing present
- ✅ Explanations mostly clear
- ✅ Some answers incorrect but reasoning visible

**Developing (60-74%):**
- ⚠️ Some exercises incomplete
- ⚠️ Condition work incomplete or unclear
- ⚠️ Some loop iterations missing
- ⚠️ Brief explanations
- ⚠️ Several answers incorrect

**Needs Support (<60%):**
- ❌ Many incomplete
- ❌ Conditions not evaluated properly
- ❌ Loop tracing absent or very wrong
- ❌ No explanations
- ❌ Mostly incorrect

### Award Partial Credit For:
- Correct loop count even if output formatting wrong
- Correct AND/OR evaluation even if final answer unclear
- Clear explanation of why condition is true/false

---

## Discussion Points for Class

### After Exercise Set 1 (Compound Conditions):
- "Which was harder - AND or OR? Why?"
- "Can you have AND with three parts? Why would that work?"
- "If one part of AND is false, why is the whole thing false?"

### After Exercise Set 2 (While Loops):
- "How did you know when to stop the loop?"
- "What's different about while vs if statement?"
- "What happens if you forget to update the variable?"

### After Exercise Set 3 (Mixed):
- "When you combine loop + condition, what executes first?"
- "Can each iteration have a different result?"
- "Why is tracing important for nested logic?"

### Class Culture:
- "Who had to trace a few times before getting it right? That's normal!"
- "Who found AND/OR confusing? Let's clarify it."
- "What was your 'aha!' moment in these exercises?"

---

## If Students Struggle

### Red Flag #1: "I don't understand AND/OR"
**Response:**
- "Let's use a real example"
- "To watch a movie: age >= 13 AND have money"
  - If you're 14 and have $10 → can watch
  - If you're 14 but have $0 → can't watch
  - If you're 10 and have $10 → can't watch
- "Both must be true for AND"

### Red Flag #2: "I'm getting the loop count wrong"
**Response:**
- "Let's count on our fingers each time we check the condition"
- "Write the condition check BEFORE you think the answer"
- "Count how many times you wrote 'YES' to the condition"

### Red Flag #3: "My output is wrong but I don't know why"
**Response:**
- "Let's trace one iteration at a time"
- "After this iteration, what's the variable value?"
- "Does the condition check make sense now?"

### Red Flag #4: "Can I just guess the AND/OR result?"
**Response:**
- "No - the whole point is to evaluate both parts"
- "Guessing doesn't help you learn"
- "Take 30 seconds to check each part"

---

## Connection to Rest of Course

**Explain to students how this matters for PROG2:**

- **Functions lesson:** "Parameter passing requires understanding conditions"
- **Arrays lesson:** "Nested loops use AND/OR to control iterations"
- **Pointers lesson:** "This is impossible if you don't understand conditions"
- **All future lessons:** "Complex programs need careful condition evaluation"

---

## Optional Extensions

### For Advanced Students:
- "Create a while loop with AND condition in the loop"
- "Write a loop that counts items matching multiple conditions"
- "Find a pattern in outputs of different AND/OR combinations"

### For Struggling Students:
- "Trace a program together, then do similar one alone"
- "Use provided truth tables for AND/OR"
- "Start with simple while loops, add conditions later"

---

## Timeline Suggestions

### Option A: One Day
- Day 2: Introduce, do Exercise Set 1 in class
- Day 3: Do Exercise Set 2-3 in class
- Collect, review, discuss

### Option B: Spread Across Time
- Day 2: Exercise Set 1 in class
- Day 3: Exercise Set 2 as homework
- Day 4: Exercise Set 3 as homework
- Day 5: Exercise Sets 4-5 as quiz
- Day 6: Review and discussion

### Option C: Progressive Practice
- Assign some exercises daily
- Discuss answers next day
- Build skills gradually
- Takes longer but stronger foundation

---

## Key Success Metrics

By end of Day 2, students should:
- ✅ Evaluate AND/OR conditions correctly
- ✅ Understand when AND requires both true
- ✅ Understand when OR needs only one true
- ✅ Trace while loops with correct iteration count
- ✅ Show condition checks before each iteration
- ✅ Explain their reasoning clearly
- ✅ Spot simple loop/condition errors

---

## Final Thought

Day 2 is critical because:
1. **AND/OR is fundamental** - Used in almost all real code
2. **While loops are essential** - Found in every program
3. **The combination is powerful** - Students need both to progress

If you can get students to:
1. Confidently evaluate compound conditions
2. Carefully trace while loops
3. Combine the two without confusion
4. Explain their reasoning clearly

...then loops, arrays, and pointers will be much easier.

Good luck with Day 2! 🚀
