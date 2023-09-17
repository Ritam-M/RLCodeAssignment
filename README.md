# RLCodeAssignment

This Repository consists of the implemetations of Q-learning and SARSA algorithms for a gridworld environment.
The gridworld environment is defined as follows:

### Gridworld Environment

---

#### Overview:
- The environment is modeled as a **16x16 grid**.
- The state space comprises of 256 distinct states representing each cell in the grid.
- At each state, the agent has **4 potential actions**: 
    - Move **up**
    - Move **down**
    - Move **left**
    - Move **right**

#### Special Points:
- The **top-left corner** (position `(0, 0)`) of the grid offers a **reward of +25** upon reaching.
- Certain grid positions are designated as **trap points** which carry a negative reward:
    - Position `(5, 2)` with a reward of **-5**
    - Position `(7, 14)` with a reward of **-5**
    - Position `(10, 3)` with a reward of **-5**

#### Transition Dynamics:
- The agent receives a **reward of -1** for each move, except when landing on the top-left corner or a trap point.
- If an action would result in the agent leaving the grid, the agent remains in its current position.

---
