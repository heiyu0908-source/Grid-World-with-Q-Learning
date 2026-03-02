# Grid-World-with-Q-Learning
# CDS524 Assignment 1: Reinforcement Learning Game Design  
**Q-Learning in a 5×5 Grid World**


## Project Overview
This project implements a classic **Grid World** environment using **Q-learning** (a tabular reinforcement learning algorithm). The agent learns to navigate a 5×5 grid from the starting position (bottom-left) to the goal (top-right) while avoiding three fixed obstacles, maximizing cumulative reward through trial-and-error.

The implementation includes:
- Clear game design with defined state/action spaces and reward function
- Full Q-learning algorithm with ε-greedy exploration
- Visualization: training curve, static optimal path, and animated agent movement
- Performance evaluation showing convergence to near-optimal policy

This work fulfills all requirements of the CDS524 Assignment 1.

## Features
- **Environment**: 5×5 Grid World  
  - States: 25 discrete positions (0–24, row-major)  
  - Actions: 4 directions (Up, Down, Left, Right)  
  - Rewards:  
    +10 → reach goal  
    -10 → hit obstacle (stay in place)  
    -0.01 → normal step (encourages shortest path)  
- **Q-Learning**:
  - Learning rate (α): 0.1  
  - Discount factor (γ): 0.99  
  - ε-greedy exploration (starts at 1.0, decays to 0.01)  
  - 2000 training episodes  
- **Visualization** (using Matplotlib):  
  - Reward curve over episodes  
  - Static grid with learned path (gold endpoint at goal)  
  - Animated demo of agent following the optimal path (last 5 steps for clarity)

## Results
After training:
- Average reward (last 100 episodes): ≈9.83  
- Optimal test path length: **8 steps**  
- Test reward: ≈9.93 (very close to theoretical maximum 9.92)  
- Path example: [0 → 5 → 10 → 15 → 20 → 21 → 22 → 23 → 24]

The agent consistently finds the shortest path avoiding all obstacles.

## How to Run
### Requirements
- Python 3.8+
- Libraries: numpy, matplotlib

All dependencies are standard and available in Google Colab (no pip install needed).

### Option 1: Run in Google Colab (Recommended)
1. Open the notebook:  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/YOUR_COLAB_LINK_HERE)  
   *(Replace with your actual Colab link after uploading)*

2. Run all cells sequentially.  
3. In the second-to-last cell: training curve + static path plot will appear.  
4. In the last cell: run  
   ```python
   from IPython.display import HTML
   HTML(ani.to_jshtml())
