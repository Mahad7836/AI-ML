# 🎮 Adversarial Search (Games)

> **Goal:** Plan ahead in a world where other agents are planning against you.

## 1. Game Theory Basics

* **Zero-Sum Game:** Total utility is constant (usually 0). If Player A wins (+1), Player B loses (-1). One player's gain is the other's loss.
* **Perfect Information:** Both players see the entire board (e.g., Chess, Tic-Tac-Toe).
* **Players:**
    * **MAX:** Tries to maximize the score (The Agent).
    * **MIN:** Tries to minimize the score (The Opponent).

---

## 2. Minimax Algorithm

A recursive algorithm to find the optimal move by simulating the game to the end.

### The Logic
1.  Generate the game tree down to terminal states (game over).
2.  Assign utility values to terminal states (Win=1, Lose=-1, Draw=0).
3.  **Backtrack:**
    * At **MAX** nodes: Take the **maximum** value of children.
    * At **MIN** nodes: Take the **minimum** value of children.

* **Assumption:** The opponent plays optimally. If the opponent plays badly, Minimax still guarantees the best "safety net."
* **Complexity:**
    * Time: $O(b^m)$ (Exponential - impossible for full Chess).
    * Space: $O(bm)$.

---

## 3. Alpha-Beta Pruning

An optimization technique to speed up Minimax. It ignores (prunes) branches that **will not affect the final decision**.

### The Parameters
* **$\alpha$ (Alpha):** The best (highest) value **MAX** has found so far along the path.
* **$\beta$ (Beta):** The best (lowest) value **MIN** has found so far along the path.

### The Pruning Logic
* **Stop searching a branch if: $\alpha \ge \beta$**
* *Plain English Translation:* "If I (MAX) already found a move worth 10 points, and I see the opponent (MIN) has a move in a different branch that forces me down to 5 points, I stop checking that branch immediately. I will never choose it because 10 is better than 5."

### Efficiency
* It does **not** change the result of Minimax (it is still optimal).
* It drastically reduces the number of nodes visited. Ideally reduces complexity to $O(b^{m/2})$ (doubles the search depth).

---

## 4. Evaluation Functions (Heuristic Minimax)

In complex games (like Chess or Go), we cannot search to the very end of the game because the tree is too big.

* **Cutoff Test:** Stop searching at a specific depth $d$ (e.g., 4 moves ahead).
* **Eval Function:** Instead of Win/Loss, we calculate a score to estimate "Who is winning right now?"
    * *Chess Example:* $Score = w_1(Pieces) + w_2(Position) + ...$
    * (e.g., Queen = 9, Rook = 5, Pawn = 1).