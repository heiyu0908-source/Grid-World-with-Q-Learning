# CDS524 Assignment 1: Reinforcement Learning Game Design  
**Q-Learning in a 5×5 Grid World**

## Project Overview
This project implements a 5×5 Grid World environment using Q-learning. The agent learns to navigate from the start (bottom-left) to the goal (top-right) while avoiding three obstacles, maximizing cumulative reward.

Key elements:
- Discrete state-action spaces
- Tabular Q-learning with ε-greedy exploration
- Visualizations: reward curve, static path, animated movement

This fulfills all CDS524 Assignment 1 requirements.

## Features
- **Environment**  
  - 25 states (0–24)  
  - 4 actions (Up, Down, Left, Right)  
  - Rewards: +10 (goal), -10 (obstacle), -0.01 (step)

- **Q-Learning**  
  - α = 0.1, γ = 0.99  
  - ε starts at 1.0, decays to 0.01  
  - 2000 training episodes

- **Visualizations** (Matplotlib)  
  - Training reward curve  
  - Static optimal path grid  
  - Animated agent movement (last 5 steps shown for clarity)

## Results
- Average reward (last 100 episodes): ≈9.83  
- Optimal path length: **8 steps**  
- Test reward: ≈9.93 (near theoretical max 9.92)  
- Example path: [0 → 5 → 10 → 15 → 20 → 21 → 22 → 23 → 24]

## How to Run
### Google Colab (Recommended)
1. Open the notebook:  
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DLEk5cScF3MAxmX_gvcwowdaqquxuZ4C?usp=sharing)

2. Run all cells.  
3. Training curve and static path appear automatically.  
4. For animation: run the last cell with  
   ```python
   from IPython.display import HTML
   HTML(ani.to_jshtml())
