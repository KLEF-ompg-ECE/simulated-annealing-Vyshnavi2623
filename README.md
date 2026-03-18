# Assignment 1 — Simulated Annealing: Exam Timetable Scheduling
## Observation Report

Student Name  : _____________________
Student ID    : _____________________
Date Submitted: _____________________

---

## How to Submit

1. Run each experiment following the instructions below
2. Fill in every answer box — do not leave placeholders
3. Make sure the plots/ folder contains all required images
4. Commit this README and the plots/ folder to your GitHub repo

---

## Before You Begin — Read the Code

Open sa_timetable.py and read through it. Then answer these questions.

Q1. What does `count_clashes()` measure? What value means a perfect timetable?

```
YOUR ANSWER
```

Q2. What does `generate_neighbor()` do? How is the new timetable different from the current one?

```
YOUR ANSWER
```

Q3. In `run_sa()`, there is this line:
if delta < 0 or random.random() < math.exp(-delta / T):
What does this line decide? Why does SA sometimes accept a worse solution?

```
YOUR ANSWER
```

---

## Experiment 1 — Baseline Run

Instructions: Run the program without changing anything.
```
python sa_timetable.py
```

Fill in this table:

| Metric | Your result |
|--------|-------------|
| Number of iterations completed | |
| Clashes at iteration 1 | |
| Final best clashes | |
| Did SA reach 0 clashes? (Yes / No) | |

Copy the printed timetable output here:

```
PASTE OUTPUT
```

Look at `plots/experiment_1.png` and describe what you see (2–3 sentences).  
*Where does the biggest drop in clashes happen? Does the curve flatten out?*

```
YOUR OBSERVATION
```

---

## Experiment 2 — Effect of Cooling Rate

Instructions: In sa_timetable.py, find the # EXPERIMENT 2 block in __main__.  
Copy it three times and run with cooling_rate = 0.80, 0.95, and 0.995.  
Save plots as experiment_2a.png, experiment_2b.png, experiment_2c.png.

Results table:

| cooling_rate | Final clashes | Iterations completed | Reached 0 clashes? |
|-------------|---------------|----------------------|--------------------|
| 0.80        | | | |
| 0.95        | | | |
| 0.995       | | | |

Compare the three plots and describe the effect of cooling_rate:

```
YOUR OBSERVATION
```

Which cooling_rate gave the best result?

```
YOUR ANSWER
```

---

## Summary — Reflection

What was the most important thing you learned about Simulated Annealing?

```
YOUR REFLECTION
```

---
