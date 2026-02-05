# 0/1 Knapsack Solver

A C++ implementation of the **0/1 Knapsack Problem** utilizing **Dynamic Programming** to find the optimal subset of items. It maximizes the total value without exceeding the maximum weight limit.

## Academic Context

This project was developed as a part of a university assignment at **CTU** (Czech Technical University in Prague).

* The core logic, including the `knapsack` function, the construction of the **Dynamic Programming table**, and the **backtracking algorithm** to reconstruct the solution, is my original implementation.
* The testing framework (including the `Item` structure, test data generation `gen_items`, and the `main` validation loop) was provided as part of the course materials to verify correctness and time complexity limits.

## Features

* **Dynamic Programming:** Solves the optimization problem by breaking it down into smaller sub-problems, storing results in a table to avoid redundant calculations.
* **Solution Reconstruction:** Unlike basic implementations that only return the maximum value, this solver backtracks through the DP table to identify exactly **which items** constitute the optimal subset.
* **0/1 Constraint:** Strictly enforces the rule that each item can be selected or not (no fractional items or multiple copies).

## Technical Details

The implementation relies on several key algorithmic concepts:

*  **Iterative DP:** Uses iterative table construction to ensure stack safety and optimal performance.
*  **State Definition:** The state `table[i][j]` represents the maximum value achievable using a subset of the first `i` items with a maximum weight capacity of `j`.
*  **Recurrence Relation:**
    * If the current item's weight is greater than the current capacity, the value is inherited from the previous row.
    * Otherwise, the algorithm decides whether to include the item by comparing the value of "skipping it" vs. "taking it".
*  **Backtracking Logic:** After filling the table, the solution is reconstructed by traversing from `table[n][max_weight]` back to `table[0][0]`. If `table[i][w] != table[i-1][w]`, the item was selected.

## Disclaimer

If you are a student currently enrolled in the same course, please be aware of your university's academic integrity policy. This code is shared for portfolio purposes only. Copying this code for your own assignment submission is considered plagiarism.
