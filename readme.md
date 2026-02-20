# 📝 FAQ Chatbot - Easy Editing Guide for Non-Coders

## Table of Contents

1. [Overview](#overview)
2. [Before You Start](#before-you-start)
3. [Finding the Questions Section](#finding-the-questions-section)
4. [How to Edit an Existing Question](#how-to-edit-an-existing-question)
5. [How to Edit an Answer](#how-to-edit-an-answer)
6. [How to Add a New Question](#how-to-add-a-new-question)
7. [Formatting Your Answers](#formatting-your-answers)
8. [Common Mistakes to Avoid](#common-mistakes-to-avoid)
9. [Testing Your Changes](#testing-your-changes)
10. [Troubleshooting](#troubleshooting)

---

## Overview

Your chatbot stores all questions and answers in a single file. Think of it like a digital filing cabinet where each question is in its own folder. You can:

- ✅ Edit existing questions
- ✅ Change answers
- ✅ Add alternative ways to ask the same question
- ✅ Add completely new questions
- ✅ Change which category a question belongs to

**You don't need coding knowledge!** Just follow these step-by-step instructions carefully.

---

## Before You Start

### What You'll Need:

1. A text editor (recommended options):
   - **Notepad++** (Windows) - [Free Download](https://notepad-plus-plus.org/)
   - **Sublime Text** (Mac/Windows) - [Free Download](https://www.sublimetext.com/)
   - **VS Code** (Mac/Windows) - [Free Download](https://code.visualstudio.com/)

   ⚠️ **DO NOT use Microsoft Word or Google Docs** - they add hidden formatting that breaks code!

2. I've created a landing page in Kajabi called "FAQ Chatbot." If you open it in edit mode, you'll find the chatbot along with the full code. Kindly copy the entire code, save it locally, and name the file `chatbot.html`

3. A backup copy (always make a copy before editing!)

### Making a Backup:

1. Right-click on `chatbot.html`
2. Click "Copy"
3. Click "Paste" in the same folder
4. You'll now have `chatbot - Copy.html` as a backup
5. If something goes wrong, you can always go back to this backup

---

## Finding the Questions Section

### Step 1: Open Your File

1. Right-click on `chatbot.html`
2. Choose "Open With" → Select your text editor (Notepad++, Sublime Text, or VS Code)
3. **Don't double-click!** That opens it in a web browser, not for editing

### Step 2: Find the Questions

1. Press `Ctrl+F` (Windows) or `Cmd+F` (Mac) to open the Find box
2. Type: `const faqData`
3. Click "Find" or press Enter
4. This will jump you to where all questions start

You'll see something like this:

```javascript
const faqData = [
    {
        id: 1,
        category: "training",
        question: "What weight loads should I start with?",
```

**This is where all your questions live!**

---

## How to Edit an Existing Question

### Example: Let's change Question #2

**BEFORE:**

```javascript
{
    id: 2,
    category: "nutrition",
    question: "How many calories should I eat?",
    variations: [
        "How much should I be eating each day?",
        "What's the right amount of food for my body and goals?"
    ],
```

**Let's say you want to change the main question to "How do I calculate my daily calories?"**

### Steps:

1. **Find the question** you want to edit (use Ctrl+F to search for text)

2. **Change only the text inside the quotes** after `question:`

   ```javascript
   question: "How do I calculate my daily calories?",
   ```

3. **Keep the comma at the end!** Very important - don't delete it

### ✅ DO:

- Change text inside the `"quotes"`
- Keep the comma `,` at the end of the line
- Keep the structure the same

### ❌ DON'T:

- Delete the word `question:`
- Delete the quotes `""`
- Delete the comma at the end
- Change anything else on that line

---

## How to Edit an Answer

Answers are longer and have special formatting. Here's how to edit them safely:

### Example: Question #2's Answer

**The answer starts after** `answer:` **and looks like this:**

```javascript
answer: `I don't recommend guessing your calories. To calculate a smart starting point, go here:

<a href="https://example.com" target="_blank">Calculate Your Calories</a>

This will give you a personalized estimate.`;
```

### Important Things to Know:

1. **Answers use backticks** `` ` `` (the key above Tab), NOT regular quotes
2. The answer starts with: `` answer: ` ``
3. The answer ends with: `` `} ``
4. Everything in between is the answer text

### Steps to Edit an Answer:

1. **Find the answer** you want to edit
2. **Look for the backtick** `` ` `` after `answer:`
3. **Edit the text between the backticks**
4. **Don't delete the starting or ending backtick!**

### Example Edit:

**BEFORE:**

```javascript
answer: `This will give you a personalized estimate.`;
```

**AFTER:**

```javascript
answer: `This will give you a customized calorie target based on your goals.`;
```

---

## How to Add a New Question

This is like adding a new folder to your filing cabinet.

### Step 1: Find Where to Add It

1. Scroll to the **end of all questions**
2. Look for the **last question** (currently Question #52)
3. Find where it ends - look for `}` followed by nothing else

**You'll see something like:**

```javascript
            ... (end of question 52's answer)
            `
            }
        ];
```

### Step 2: Add a Comma

**Change the closing `}` to `},` - add a comma!**

```javascript
            ... (end of question 52's answer)
            `
            }  ← Add a comma here to make it: },
        ];
```

**After adding comma:**

```javascript
            ... (end of question 52's answer)
            `
            },  ← Comma added!
        ];
```

### Step 3: Copy This Template

**Copy this exact template** and paste it BEFORE the `];` line:

```javascript
            {
                id: 53,
                category: "training",
                question: "Your new question here?",
                variations: [
                    "Alternative way to ask?",
                    "Another way to phrase it?"
                ],
                keywords: ["keyword1", "keyword2", "keyword3", "keyword4"],
                answer: `Your answer goes here.

You can use multiple paragraphs.

**Use two asterisks for bold text**

• Use bullet points like this
• And like this

<a href="https://yourlink.com" target="_blank">Add links like this</a>

That's it!`
            }
```

### Step 4: Fill in Your Information

**Replace each part:**

1. **id:** Change `53` to the next number (if last question is 52, use 53)

2. **category:** Choose ONE of these (keep the quotes):
   - `"training"`
   - `"nutrition"`
   - `"recovery"`
   - `"equipment"`
   - `"progress"`

3. **question:** Your main question (keep in quotes)

4. **variations:** Alternative ways people might ask (2-5 variations work best)

5. **keywords:** Important words that should trigger this answer (5-10 keywords)

6. **answer:** Your full answer (between the backticks)

### Example of a Complete New Question:

```javascript
            {
                id: 53,
                category: "nutrition",
                question: "How often should I eat protein?",
                variations: [
                    "How frequently should I consume protein throughout the day?",
                    "Should I eat protein at every meal?",
                    "What's the best protein timing?"
                ],
                keywords: ["protein", "timing", "frequency", "often", "meals", "how often", "eating"],
                answer: `You should aim to include protein at every meal and snack for optimal results.

**Here's why:**
• Keeps blood sugar stable
• Supports muscle maintenance
• Reduces cravings
• Improves satiety

**Practical approach:**
Aim for 20-30 grams of protein per meal, 3-4 times per day.

For more details, visit the <a href="https://www.hollyperkins.com/nutrition" target="_blank">Nutrition Project</a>.`
            }
```

---

## Formatting Your Answers

You can make your answers look professional with simple formatting:

### Bold Text

```
**This will be bold**
```

Shows as: **This will be bold**

### Bullet Points

```
• First point
• Second point
• Third point
```

### Paragraphs

Just leave a blank line between paragraphs:

```
First paragraph.

Second paragraph.
```

### Links

```
<a href="https://yourwebsite.com" target="_blank">Click Here</a>
```

### Headings (bold and larger)

```
**Main Topic:**
Regular text follows here.
```

---

## Common Mistakes to Avoid

### ❌ Mistake #1: Deleting Commas

**Wrong:**

```javascript
question: "My question?"
variations: [
```

**Right:**

```javascript
question: "My question?",  ← Need comma here!
variations: [
```

**Rule:** Almost every line needs a comma at the end, except:

- The last item in variations `]`
- The last item in keywords `]`
- The very last `}` before `];`

---

### ❌ Mistake #2: Breaking the Quotes

**Wrong:**

```javascript
question: "What's the best approach?",
```

The apostrophe in "What's" might cause issues.

**Right:**

```javascript
question: "What is the best approach?",
```

Or use a backslash before the apostrophe:

```javascript
question: "What\'s the best approach?",
```

---

### ❌ Mistake #3: Using Wrong Quote Types

**Wrong:** Using regular quotes for answer

```javascript
answer: "This is my answer";
```

**Right:** Using backticks for answer

```javascript
answer: `This is my answer`;
```

**Remember:**

- Questions, keywords, variations = regular quotes `"`
- Answers = backticks `` ` ``

---

### ❌ Mistake #4: Forgetting to Add Comma When Adding New Question

When adding a new question, the previous question MUST end with `},` not just `}`

**Wrong:**

```javascript
            ... previous question answer ...
            `
            }      ← Missing comma!
            {
                id: 53,
```

**Right:**

```javascript
            ... previous question answer ...
            `
            },     ← Has comma!
            {
                id: 53,
```

---

## Testing Your Changes

### Step 1: Save Your File

1. Press `Ctrl+S` (Windows) or `Cmd+S` (Mac)
2. Make sure it saves as `.html` file, not `.txt`

### Step 2: Open in Browser

1. Copy the entire code you just saved and replace the existing code on the FAQ Chatbot page with it. Then click Save.
2. Click Preview to view the updated version.
3. The chatbot should load.

### Step 3: Test Your Changes

**If you edited a question:**

1. Try typing that question in the chatbot
2. See if the answer appears
3. Try the variations you added

**If you added a new question:**

1. Click on the category you assigned it to
2. Look for your question in the list
3. Click it and see if the answer shows up correctly

---

## Quick Reference Checklist

When adding or editing questions, check these:

✅ **Commas:**

- [ ] Every line except the last few has a comma
- [ ] Added comma to previous question when adding new one

✅ **Quotes:**

- [ ] Regular quotes `"` for question, variations, keywords, category
- [ ] Backticks `` ` `` for answer
- [ ] All quotes properly closed

✅ **Structure:**

- [ ] ID number is unique and sequential
- [ ] Category matches one of the 5 options exactly
- [ ] At least 2 variations provided
- [ ] At least 5 keywords provided

✅ **Testing:**

- [ ] File saved
- [ ] Opens without errors
- [ ] Question appears in correct category
- [ ] Answer displays properly
- [ ] Links work (if you added any)

---

## Troubleshooting

### Problem: Chatbot won't load, blank page

**Solution:**

1. Open the file in your text editor
2. Press `Ctrl+F` and search for `const faqData`
3. Carefully check every question has:
   - Opening `{` and closing `}`
   - Commas after each section
   - Matching quotes
4. If you can't find the issue, restore your backup

---

### Problem: New question doesn't appear

**Check:**

1. Did you add a comma after the previous question's `}`?
2. Is the ID number unique (not used by another question)?
3. Is the category name spelled exactly right?
4. Did you save the file?

---

### Problem: Answer looks wrong (no bold, no bullets)

**Check:**

1. Did you use backticks `` ` `` not regular quotes `"`?
2. Did you use `**text**` for bold?
3. Did you use `•` for bullets?

---

### Problem: A quote broke my question

**If your question has an apostrophe (like "What's"), do this:**

**Wrong:**

```javascript
question: "What's the best way?",
```

**Right (Option 1):** Remove apostrophe

```javascript
question: "What is the best way?",
```

**Right (Option 2):** Add backslash before apostrophe

```javascript
question: "What\'s the best way?",
```

---

## Summary

**To Edit a Question:**

1. Find it with `Ctrl+F`
2. Change text inside `"quotes"`
3. Keep commas
4. Save and test

**To Edit an Answer:**

1. Find it after `answer: `backtick``
2. Edit text between backticks
3. Use formatting codes
4. Save and test

**To Add a Question:**

1. Go to end of questions
2. Add comma to previous `}`
3. Copy template
4. Fill in your info
5. Save and test

---

## Quick Tips for Success

💡 **Always make a backup first**
💡 **Change only one thing at a time**
💡 **Test after each change**
💡 **Don't delete commas**
💡 **Use the right quotes for each part**
💡 **Keep the structure identical to existing questions**

---

**You've got this!** Take it slow, follow the steps, and don't be afraid to use your backup if needed. The chatbot is very forgiving - if something breaks, just restore and try again.

The more you practice, the easier it gets! 🎉