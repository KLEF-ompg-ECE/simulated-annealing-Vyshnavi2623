# Assignment 1 — Simulated Annealing: Exam Timetable Scheduling

## Observation Report

**Student Name:** BonBon Vyshnavi
**Student ID:** 2310040012
**Date Submitted:** 17-03-2026

---

## Before You Begin — Read the Code

### Q1. What does `count_clashes()` measure? What value means a perfect timetable?

The function `count_clashes()` calculates the number of exam conflicts for students.
A clash occurs when a student has more than one exam scheduled in the same time slot.
A value of **0** means a perfect timetable with no clashes.

---

### Q2. What does `generate_neighbor()` do?

The function `generate_neighbor()` creates a new timetable by randomly selecting one exam and assigning it to a different time slot.
This produces a slightly modified solution from the current timetable.

---

### Q3. Why does SA sometimes accept a worse solution?

The condition
`if delta < 0 or random.random() < math.exp(-delta / T)`
decides whether to accept a new solution.

If the new solution is better, it is always accepted.
If it is worse, it may still be accepted with a probability depending on temperature.

This allows the algorithm to escape local minima and explore better solutions.

---

## Experiment 1 — Baseline Run

| Metric                         | Value |
| ------------------------------ | ----- |
| Number of iterations completed | 1379  |
| Clashes at iteration 1         | 12    |
| Final best clashes             | 3     |
| Did SA reach 0 clashes?        | No    |

---

### Final Timetable

Slot 1: Geography
Slot 2: Chemistry, English
Slot 3: History, Computer Science, Economics
Slot 4: Biology, Statistics
Slot 5: Mathematics, Physics

Total clashes: 3

---

### Plot Observation

The graph shows a rapid decrease in clashes during the early iterations.
The biggest drop occurs at the beginning when the algorithm explores many solutions.
Later, the curve flattens, indicating slow improvement and convergence.

---

## Experiment 2 — Effect of Cooling Rate

| cooling_rate | Final clashes | Iterations completed | Reached 0 clashes |
| ------------ | ------------- | -------------------- | ----------------- |
| 0.80         | 8             | 40                   | No                |
| 0.95         | 3             | 90                   | No                |
| 0.995        | 3             | 1379                 | No                |

---

### Observation

A lower cooling rate (0.80) cools quickly and results in poor solutions.
A higher cooling rate (0.995) allows more exploration and gives better results.
Thus, slower cooling leads to better optimization performance.

---

## Final Answers

**Does SA always reach 0 clashes?**
No, it depends on parameters and randomness.

**Which cooling rate performed best?**
0.995 performed best because it produced the lowest clashes.

---
