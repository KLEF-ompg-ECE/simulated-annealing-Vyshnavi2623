# Assignment 1 — Simulated Annealing: Exam Timetable Scheduling

## Observation Report

Student Name : BonBon Vyshnavi
Student ID : 2310040012
Date Submitted : 17-03-2026

---

## Before You Begin — Read the Code

Q1. What does `count_clashes()` measure? What value means a perfect timetable?

count_clashes() measures the number of exam clashes where a student has more than one exam in the same slot.
A value of 0 means a perfect timetable.

---

Q2. What does `generate_neighbor()` do? How is the new timetable different?

generate_neighbor() creates a new timetable by moving one exam to a different slot.
The new timetable differs from the current one by one exam assignment.

---

Q3. What does this line decide?

if delta < 0 or random.random() < math.exp(-delta / T)

This decides whether to accept a new solution.
Better solutions are always accepted.
Worse solutions are sometimes accepted based on probability to escape local minima.

---

## Experiment 1 — Baseline Run

| Metric                             | Your result |
| ---------------------------------- | ----------- |
| Number of iterations completed     | 1379        |
| Clashes at iteration 1             | 12          |
| Final best clashes                 | 3           |
| Did SA reach 0 clashes? (Yes / No) | No          |

---

Final Timetable

Slot 1: Geography
Slot 2: Chemistry, English
Slot 3: History, Computer Science, Economics
Slot 4: Biology, Statistics
Slot 5: Mathematics, Physics

Total clashes : 3

---

Plot Observation

The clashes decrease rapidly in early iterations.
The curve later flattens showing convergence.

---

## Experiment 2 — Effect of Cooling Rate

| cooling_rate | Final clashes | Iterations completed | Reached 0 clashes? |
| ------------ | ------------- | -------------------- | ------------------ |
| 0.80         | 8             | 40                   | No                 |
| 0.95         | 3             | 90                   | No                 |
| 0.995        | 3             | 1379                 | No                 |

---

Observation

Lower cooling rate gives faster but worse results.
Higher cooling rate gives better optimization.

---
