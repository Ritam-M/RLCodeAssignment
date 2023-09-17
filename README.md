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

## Reinforcement Learning Algorithms

### Q-learning

Q-learning is a type of model-free, off-policy reinforcement learning algorithm. It seeks to learn the optimal action-selection policy by estimating how good a particular action is in a given state.

The Q-learning algorithm learns by updating its Q-values using the following update rule:

\[ Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma \max_{a'} Q(s', a') - Q(s, a)] \]

Where:
- \( s \) is the current state
- \( a \) is the chosen action
- \( r \) is the received reward
- \( s' \) is the new state
- \( \alpha \) is the learning rate
- \( \gamma \) is the discount factor

In essence, Q-learning uses the maximum Q-value of the new state \( s' \) to update the Q-value of the current state \( s \). 

---

### SARSA 

SARSA, which stands for **State-Action-Reward-State-Action**, is another model-free, on-policy reinforcement learning algorithm. Unlike Q-learning which is off-policy, SARSA is on-policy, meaning it takes into account the action chosen by the current policy to update its Q-values.

The SARSA algorithm uses the following update rule:

\[ Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma Q(s', a') - Q(s, a)] \]

Where:
- \( s \) is the current state
- \( a \) is the chosen action
- \( r \) is the received reward
- \( s' \) is the new state
- \( a' \) is the action chosen in the new state following the current policy
- \( \alpha \) is the learning rate
- \( \gamma \) is the discount factor

The major difference between SARSA and Q-learning is that SARSA uses the Q-value of the next state-action pair \( (s', a') \) (as per the policy) to update its Q-values, whereas Q-learning uses the maximum Q-value of the new state \( s' \), regardless of the action taken.
