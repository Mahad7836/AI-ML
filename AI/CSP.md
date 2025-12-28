# 🧩 Constraint Satisfaction Problems (CSPs)

> **Goal:** Find a state that satisfies a set of constraints.

## 1. What is a CSP?

Unlike standard search (which finds a *path*), CSPs care only about the **assignment** of values to variables.

### The Three Components
1.  **X (Variables):** The things we need to decide (e.g., Regions on a map: $WA, NT, Q, NSW, V, SA, T$).
2.  **D (Domains):** The allowed values for each variable (e.g., Colors: $\{Red, Green, Blue\}$).
3.  **C (Constraints):** Rules that limit valid assignments (e.g., $SA \neq WA$ - "Adjacent regions cannot have the same color").

### Examples
* **Map Coloring:** Assign colors so no neighbors touch.
* **N-Queens:** Place $N$ queens on a board so none attack each other.
* **Sudoku:** Fill grid so rows/cols/boxes have unique numbers.
* **Cryptarithmetic:** $SEND + MORE = MONEY$ (Letters represent digits).

---

## 2. Solving CSPs: Backtracking Search

This is the primary algorithm for CSPs. It is a form of **Depth-First Search**.

### The Logic
1.  Select an unassigned variable.
2.  Try the first value in its domain.
3.  Check constraints:
    * **If valid:** Move to the next variable (Recursive call).
    * **If invalid:** Backtrack (Undo assignment and try the next value).
4.  Repeat until solution found or all options exhausted.

---

## 3. Improving Performance (Heuristics)

Standard backtracking is slow ($O(n!)$). We use heuristics to decide *which* variable to pick and *which* value to try.

### A. Variable Ordering (Which variable to pick next?)
1.  **Minimum Remaining Values (MRV):**
    * "Fail First" heuristic.
    * Pick the variable with the **fewest** legal values left.
    * *Why?* If a variable acts as a bottleneck (only 1 option left), we should fill it now to avoid exploring useless branches.
2.  **Degree Heuristic:**
    * Pick the variable involved in the **most** constraints with other unassigned variables.
    * *Why?* It reduces the branching factor for future steps.

### B. Value Ordering (Which value to try first?)
1.  **Least Constraining Value (LCV):**
    * Pick the value that rules out the **fewest** choices for neighboring variables.
    * *Why?* We want to leave maximum flexibility for the remaining variables to find a solution.

---

## 4. Inference (Constraint Propagation)

Instead of just checking constraints *after* making a move, we can look ahead to prune bad options early.

### A. Forward Checking
* Whenever a variable $X$ is assigned, look at all its neighbors $Y$.
* Remove any value from $Y$'s domain that conflicts with $X$.
* **Fail Condition:** If any variable's domain becomes empty, backtrack immediately.

### B. Arc Consistency (AC-3)
* Stronger than Forward Checking. It propagates constraints through the entire graph, not just immediate neighbors.
* *Rule:* An arc $X \to Y$ is consistent if for **every** value in $X$, there is some valid value in $Y$.
* If we remove a value from $X$, we must re-check neighbors of $X$ to ensure they are still consistent.