# 🔍 Search Algorithms

> **Goal:** Find a sequence of actions that reaches the goal state.

## 1. Problem Solving Basics

To solve a problem using search, we need to define the **State Space**:

1.  **Initial State:** Where we start.
2.  **Actions:** What we can do (e.g., move left, move right).
3.  **Transition Model:** What happens after an action (Result).
4.  **Goal Test:** Have we arrived?
5.  **Path Cost:** The numerical cost (e.g., distance, time) of the path.

---

## 2. Uninformed Search (Blind Search)

These algorithms have **no information** about how close they are to the goal. They just explore systematically.

### A. Breadth-First Search (BFS)
* **Strategy:** Explore all neighbors at the current depth before moving deeper. "Shallowest nodes first."
* **Data Structure:** **Queue** (FIFO - First In, First Out).
* **Properties:**
    * *Complete?* **Yes** (If a goal exists, it finds it).
    * *Optimal?* **Yes** (Only if all step costs are equal, e.g., 1).
    * *Space Complexity:* High (Keeps all nodes in memory).

### B. Depth-First Search (DFS)
* **Strategy:** Explore as deep as possible along each branch before backtracking.
* **Data Structure:** **Stack** (LIFO - Last In, First Out).
* **Properties:**
    * *Complete?* **No** (Can get stuck in infinite loops in cyclic graphs).
    * *Optimal?* **No** (Might find a long path before a short one).
    * *Space Complexity:* Low (Only stores the current path).

### C. Uniform Cost Search (UCS)
* **Strategy:** Expand the node with the **lowest path cost** ($g(n)$) so far.
* **Data Structure:** **Priority Queue**.
* **Properties:**
    * *Complete?* **Yes**.
    * *Optimal?* **Yes** (Guaranteed to find the cheapest path).
    * *Note:* It behaves exactly like BFS if all step costs are equal.

### ⚡ Comparison Table

| Algorithm | Complete? | Optimal? | Time Complexity | Space Complexity |
| :--- | :--- | :--- | :--- | :--- |
| **BFS** | Yes | Yes (if cost=1) | High ($b^d$) | High ($b^d$) |
| **DFS** | No | No | High ($b^m$) | Low ($bm$) |
| **UCS** | Yes | Yes | High | High |

*(b = branching factor, d = depth of solution, m = max depth)*

---

## 3. Local Search

These algorithms don't care about the *path* to the goal, only the **final state** (e.g., N-Queens, Optimization).

### Hill Climbing ("Greedy Local Search")
* **Strategy:** Like climbing Everest in thick fog. Look at neighbors, move to the one with the **highest value** (steepest ascent). Stop when no neighbor is higher.
* **Loop:**
    1.  Check current state.
    2.  If neighbor > current, move there.
    3.  Else, stop.

### Problems with Hill Climbing
1.  **Local Maxima:** A peak that is higher than neighbors but lower than the true highest peak (Global Maximum). The agent gets stuck here.
2.  **Plateaus:** A flat area where all neighbors have the same value. The agent wanders aimlessly.
3.  **Ridges:** A sequence of local maxima that is difficult for the greedy agent to navigate.