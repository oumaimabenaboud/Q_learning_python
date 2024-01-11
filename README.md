# Q-Learning for Pathfinding in a 2D Environment

This notebook implements the Q-learning algorithm to find the optimal path in a 2D grid environment. The goal of the algorithm is to guide an agent from a random starting location to a predefined goal while avoiding obstacles. The Q-learning process involves updating a Q-matrix that represents the learned values of taking actions in different states to achieve the highest cumulative reward.

## Description

### Environment
- The environment is represented as a 10x10 grid.
- Actions: Up, Right, Down, Left (coded as 0, 1, 2, 3).
- The goal is located at position (9, 9).
- Obstacles are present at specific locations with a negative reward of -10.

### Q-matrix
- A 3D NumPy array (`q_values`) is used to represent the Q-matrix, where each element Q(s, a) corresponds to the learned value of taking action 'a' in state 's'.
- Q-values are initialized to 0 for all state-action pairs.

### Reward Matrix
- A 2D NumPy array (`rewards`) represents the rewards for each state.
- The goal has a reward of 10 to encourage the agent to reach it.
- Other state rewards are inversely proportional to their distance from the goal.
- Obstacles have a negative reward of -10.

### Q-Learning Process
1. The agent explores the environment through episodes, starting from a random initial state.
2. At each state, the agent chooses an action based on an epsilon-greedy strategy.
3. Q-values are updated based on the received reward and the maximum Q-value in the next state.
4. Exploration continues for a set number of episodes (1000 in this case).

### Functions
- `is_terminal_state`: Checks if a given state is a terminal state (goal).
- `get_random_starting_location`: Returns a random non-terminal starting location.
- `choose_next_action`: Chooses the next action based on an epsilon-greedy strategy.
- `get_next_state`: Determines the next state based on the chosen action.
- `shortest_path`: Finds the optimal path from a given initial state to the goal.

### Learning Episodes
- The notebook runs 1000 episodes of Q-learning to train the agent.

### Parameters
- Epsilon (exploration-exploitation trade-off): 0.9
- Discount factor (gamma): 0.7

## Usage
1. Run the notebook to train the Q-learning agent.
2. After training, explore the optimal paths from different starting locations using the `shortest_path` function.

Feel free to experiment with the environment, rewards, and parameters to observe their impact on the learning process and optimal paths.
