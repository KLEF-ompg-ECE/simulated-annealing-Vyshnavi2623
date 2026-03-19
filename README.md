# Assignment 1 — Simulated Annealing: Exam Timetable Scheduling
## Observation Report

Student Name  : BonBon Vyshnavi
Student ID    : 2310040012
Date Submitted: 17-03-2026

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
[The count_clashes() function calculates the total number of exam scheduling conflicts among students. A clash occurs when a student has two or more exams scheduled in the same time slot. The function checks each student's exam list and counts how many times the same slot appears. A value of 0 means a perfect timetable with no conflicts.]
```

Q2. What does `generate_neighbor()` do? How is the new timetable different from the current one?

```
[The generate_neighbor() function creates a slightly modified timetable from the current timetable. It randomly selects one exam and moves it to a different time slot while keeping all other exams unchanged. This produces a neighbouring solution that the Simulated Annealing algorithm can evaluate.]
```

Q3. In `run_sa()`, there is this line:
if delta < 0 or random.random() < math.exp(-delta / T):
What does this line decide? Why does SA sometimes accept a worse solution?

```
[This line decides whether the algorithm should accept the new timetable. If the new solution has fewer clashes (delta < 0), it is always accepted. If the solution is worse, it may still be accepted with a probability based on the temperature T. This helps Simulated Annealing escape local minimum solutions and explore better possibilities.]
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
| Number of iterations completed | 1379 |
| Clashes at iteration 1 | 12 |
| Final best clashes | 3 |
| Did SA reach 0 clashes? (Yes / No) | No |

Copy the printed timetable output here:

```
  Final Timetable
------------------------------------------
  Slot 1:  Geography
  Slot 2:  Chemistry, English
  Slot 3:  History, Computer Science, Economics
  Slot 4:  Biology, Statistics
  Slot 5:  Mathematics, Physics
------------------------------------------
  Total clashes : 3
```

Look at `plots/experiment_1.png` and describe what you see (2–3 sentences).  
*Where does the biggest drop in clashes happen? Does the curve flatten out?*

```
[The plot shows that the number of clashes decreases significantly during the early iterations. The largest drop happens in the initial phase when the algorithm explores many possible schedules. After some iterations the curve starts flattening, indicating that improvements become smaller. In this run the algorithm reduced clashes from 12 to 3 but did not reach a perfect timetable.]
```

---

## Experiment 2 — Effect of Cooling Rate

Instructions: In sa_timetable.py, find the # EXPERIMENT 2 block in __main__.  
Copy it three times and run with cooling_rate = 0.80, 0.95, and 0.995.  
Save plots as experiment_2a.png, experiment_2b.png, experiment_2c.png.

Results table:

| cooling_rate | Final clashes | Iterations completed | Reached 0 clashes? |
|-------------|---------------|----------------------|--------------------|
| 0.80        | 8 | 31 | No |
| 0.95        | 3 | 135 | No |
| 0.995       | 3 | 1379 | No |

Compare the three plots and describe the effect of cooling_rate:

```
[The cooling rate has a dramatic effect on algorithm performance. With cooling_rate=0.80 (fast cooling), the algorithm converges very quickly (31 iterations) but gets stuck at poor solutions (8 clashes). With cooling_rate=0.95 (moderate cooling), it reaches the same quality as the baseline (3 clashes) but in much fewer iterations (135 vs 1379). With cooling_rate=0.995 (slow cooling), it matches the baseline exactly, taking 1379 iterations. Slower cooling rates allow better exploration but take longer, while faster cooling rates converge quickly but risk getting trapped in local minima.]
```

Which cooling_rate gave the best result?

```
[cooling_rate=0.95 gave the best practical result. It achieved the same final quality (3 clashes) as the slower 0.995 rate but in 10x fewer iterations (135 vs 1379). This shows that the moderate cooling rate provides an effective balance between solution quality and computational efficiency.]
```

---

## Summary — Reflection

What was the most important thing you learned about Simulated Annealing?

```
[The most important thing I learned is that Simulated Annealing uses randomness strategically to escape local minima. By accepting worse solutions probabilistically early on (when temperature is high) and becoming more selective as temperature drops, the algorithm balances exploration and exploitation. The cooling rate is crucial: too fast and you miss better solutions, too slow and you waste iterations. This demonstrates that the right balance between exploration and convergence speed is key to optimization algorithm design.]
```

---
