# Turn a Dataset into an Interactive Dashboard Using an AI Assistant

In this activity, you will take a dataset — any CSV, Excel, or JSON file with rows and columns of data — and turn it into two things: a Jupyter notebook with visualizations and written analysis, and a standalone interactive HTML report you can open and explore in any browser.

You will not write all the analysis code by hand. Instead, you will learn how to **direct an AI assistant** to explore, clean, chart, and explain your data step by step using *good prompting*. This is a powerful skill used by professional data analysts today.

This tutorial assumes you're using an AI assistant that can actually **run code and hand you back real files** — for example Claude or ChatGPT with code execution turned on, or a Cowork-style session — rather than a plain chat that can only describe code without running it. You'll know you have the right kind of tool if it can take a file you upload, run Python on it, and give you back a working file (like a `.ipynb` or `.html`) rather than just a block of text.

> **Goal:** Learn how to direct an AI assistant to explore a dataset, build real visualizations, and package findings into something interactive that anyone can open and explore — not just look at.

---

## How to Prompt Your AI Assistant Properly

AI assistants work best when you give them **very small, clear instructions**. Do *not* ask for "a full dashboard" all at once.

### Good Prompt Examples

- "Load this CSV and show me the column names, data types, and the first 5 rows."
- "Make a bar chart of average sales by region, sorted highest to lowest, with clear axis labels and a title."
- "Add a dropdown so I can filter this line chart by product category."
- "Turn this into a standalone HTML file that still works if I just double-click it and open it in a browser."

### Bad Prompt Examples

- "Analyze my data."
- "Make me a full dashboard with everything."
- "The chart is wrong" (without saying what's wrong).

---

## Debugging Tip

When something looks wrong, describe **exactly what you see**:

- "The x-axis shows 0, 1, 2, 3... instead of the actual dates."
- "The notebook throws a `KeyError` on a column name — can you check for extra spaces or different capitalization in the actual column names?"
- "The HTML file opens but the charts are blank."
- "The total in this bar chart doesn't match the number of rows in the dataset."

This is how real analysts debug problems — not "it's wrong," but a precise description of what's actually on the screen versus what should be there.

---

## What You're Really Learning

- How to explore an unfamiliar dataset before jumping to conclusions
- The difference between a notebook (a record of your process) and a report (something built for an audience)
- How interactivity — sliders, hover tooltips, zoom, rotating 3D views — lets people explore data themselves instead of just looking at one fixed picture
- How to spot a chart that's misleading, mislabeled, or just wrong
- How to communicate a *finding*, not just produce a chart
- How to communicate clearly with an AI coding assistant

> You are not just making charts — you are learning how data analysts actually work.

---

## Before You Start

Don't have a dataset handy? Use the included `sample-sales-data.csv` (with `data-dictionary.md` describing its columns) — it's a synthetic weekly retail dataset with real seasonal trends, regional differences, a marketing-spend relationship, and a few intentionally messy rows for you to clean.

1. Get your dataset as a single file the AI can read — CSV, Excel (`.xlsx`), and JSON all work well.
2. Open an AI assistant that can execute code and return real files, not just describe code in chat.
3. Upload or attach your dataset to the conversation.
4. Decide on 2–3 real questions you want the data to answer (for example, "how does this change over time" or "which category performs best"). You'll get far better results asking focused questions than asking for "a dashboard."
5. Ask for one piece at a time — explore, then clean, then chart, then add interactivity, then build the report — the same rule as any other AI-assisted project.
6. Actually open and check each file the AI hands you (the notebook and the HTML report) before asking for the next piece. Don't stack five requests on top of an file you haven't looked at yet.

---

## Step-by-Step Build Plan

Ask your AI assistant for each step **one at a time**.

The bulleted items below are not the prompts. You will need to turn them into your own clear instructions. Full example prompts are given further down.

### Step 1 – Upload and Explore

- Load the dataset and show the column names, data types, and row count.
- Show the first few rows.
- Report which columns (if any) have missing values.

### Step 2 – Clean the Data

- Handle missing values sensibly, and have the AI explain what it chose to do and why.
- Fix any columns that have the wrong data type (e.g. a date stored as plain text).
- Remove exact duplicate rows, and report how many were removed.

### Step 3 – Ask Real Questions

- Write down 2–3 specific questions you actually want answered from this data.
- Ask the AI to answer the first one directly, in words, before making any chart.

### Step 4 – Static Charts in the Notebook

- Turn each answered question into one clear chart with a title and labeled axes.
- Keep each chart focused on one idea — resist the urge to cram everything into one plot.

### Step 5 – Add Interactivity Inside the Notebook

- Add a widget (like a dropdown or slider) that lets you filter or explore a chart without editing code.
- Confirm the chart actually updates when you change the widget.

### Step 6 – Build the Standalone HTML Report *(priority)*

- Ask for a single self-contained HTML file (not dependent on Jupyter being open) that includes your key charts.
- Make sure it opens correctly just by double-clicking it in a file browser.
- Add hover tooltips so a viewer can see exact values without you explaining them.

### Step 7 – Add Advanced Interactive Elements

- Add at least one chart people can zoom and pan into.
- If your data supports it, add a 3D chart (like a 3D scatter plot) that can be rotated with the mouse.
- Add a slider or filter control that changes what the report shows.

### Step 8 – Write the Narrative

- Add a short, plain-language summary above or below each chart explaining the one main insight it shows.
- A chart without a sentence explaining what it means is only half finished.

### Step 9 – Polish and Test

- Open the HTML report in a fresh browser tab (not just the AI's preview) to confirm it really works standalone.
- Check that every chart's numbers actually match the underlying data.
- Ask someone else to look at it without you explaining anything first — if they're confused, that's useful information.

---

## AI Ethics Checkpoint

Choose three topics below. For each one, paste the prompt into your AI assistant, read the answer, and decide what you think. These are discussion prompts, not coding prompts.

1. **Bias in the data** — Could this dataset over- or under-represent certain groups or situations? How would I even check?
2. **Correlation vs. causation** — What are three ways this analysis could tempt someone to claim a cause-and-effect relationship the data doesn't actually support?
3. **Misleading charts** — What are common ways a chart (axis scaling, cherry-picked time range, missing context) can technically be accurate but still misleading?
4. **Trust but verify** — What are three numbers or claims in this report I should double-check by hand instead of trusting the AI automatically?
5. **Privacy** — If this dataset contains information about real people, what should I check or remove before sharing this report with anyone?
6. **Transparency** — If I present these findings to someone, should I tell them an AI helped build the analysis? Give both sides briefly, then give your recommendation.
7. **Accessibility** — Could someone with color blindness or a screen reader understand this report? What would make it more accessible?
8. **Overclaiming** — What's the difference between "the data shows X" and "the data is consistent with X, but doesn't prove it"? Why does that distinction matter?

---

## Example Prompts

**Exploring the data:**

> I've attached a dataset called data.csv. Load it and show me the column names, data types, number of rows, and the first 5 rows. Also tell me which columns have missing values.

**Cleaning the data:**

> Based on what you found, clean the dataset: handle missing values sensibly (tell me what you chose to do and why), fix any obviously wrong data types, and remove exact duplicate rows. Show me a before/after row count.

**Answering a question with a chart:**

> Using the cleaned data, show me total revenue by month as a line chart, with clear axis labels and a title. Then tell me in a sentence or two what the trend looks like.

**Adding interactivity inside the notebook:**

> Add an interactive dropdown using ipywidgets that lets me pick a region and updates the revenue-by-month chart to show just that region.

**Building the standalone HTML report:**

> Now build a standalone HTML report — not dependent on Jupyter — using an interactive charting library, including the charts we've built so far. Give each chart hover tooltips, and make sure at least one chart supports zoom and pan. The file should open correctly if I just double-click it in a browser.

**Adding a 3D or advanced interactive element:**

> Turn the relationship between [category, value 1, value 2] into a 3D scatter plot I can rotate and zoom with my mouse, and add a slider that filters the points by [date or category].

**Adding the narrative:**

> Add a short written summary above each chart in the HTML report explaining, in plain language, the one main insight from that chart.

---

## Try It Yourself

Once your HTML report is done, close the AI conversation and open only the report file, cold — as if you were a stranger seeing it for the first time.

Ask yourself: **without any extra explanation, could you tell what the data shows and why it matters?**

If the answer is no, that's not a failure — it tells you exactly which chart needs a better title, label, or sentence of explanation.
