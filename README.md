Portfolio Optimization via Deep Reinforcement Learning
This project implements and compares two deep reinforcement learning approaches—Deep Q-Learning (DQL) and Actor-Critic (PPO variant)—to solve the portfolio optimization problem over both stable and volatile stock universes. The goal is to dynamically rebalance a portfolio to maximize risk-adjusted returns while respecting realistic trading constraints.

📊 Project Overview
Traditional portfolio optimization techniques struggle under market non-stationarity and discrete trading constraints. We address these challenges by framing portfolio rebalancing as a Markov Decision Process (MDP) and employing reinforcement learning agents that adapt to changing market regimes.

This repository contains:

Implementation of DQL agents trained on stable and volatile stock sets.

PPO-based Actor-Critic models for continuous rebalancing strategies.

Evaluation metrics including ROI and Sharpe Ratio on out-of-sample test data (2023).

Jupyter Notebooks for both training and evaluation.

🧠 Algorithms Compared
Deep Q-Learning (DQL)
State: 16-dimensional vector (portfolio weights + moving average ratios + volatilities)

Actions: 151 discrete rebalancing moves (1–5% shifts between assets)

Rewards: Multi-step log returns penalized by drawdown and rolling volatility

Stabilization Techniques: Target networks, Double DQN, ensemble Q-nets, replay buffers

Actor-Critic (PPO)
State: Normalized portfolio weight vector

Actions: Softmax over discrete allocations bounded to sum-to-one

Policy Optimization: PPO with clipping and entropy regularization

Architecture: Shared encoder with separate actor and critic heads

📉 Datasets
Stable Stocks (2014–2023): AAPL, MSFT, GOOGL, SBUX, TSLA

Volatile Stocks (2017–2023): GME, AMC, SPCE, NVAX, NOK

Data sourced from Yahoo Finance.

Train/Validation Split: 80/20

Test Period: 2023

📈 Results Summary
Dataset	Baseline ROI	DQL ROI	PPO ROI	Best Sharpe
Stable	59.4%	70.6%	83.1%	DQL: 2.30
Volatile	–37.4%	+17.1%	–20.4%	DQL: 1.23

💡 DQL excels under high volatility due to discrete constraints and drawdown penalties. PPO outperforms on smooth, trending markets due to continuous actions and entropy-driven exploration.

🛠️ Tools & Frameworks
Python 3.x

NumPy, Pandas, Matplotlib

PyTorch

OpenAI Gym (custom MDP)

Jupyter Notebooks

🧪 How to Run
Clone this repo:

bash
Copy
Edit
git clone https://github.com/yourusername/rl-portfolio-optimization.git
cd rl-portfolio-optimization
Open any of the notebooks in Jupyter Lab:

bash
Copy
Edit
jupyter lab StableQ.ipynb
Run the cells sequentially. All training and evaluation are self-contained.

📄 Reference
Please cite or refer to our project paper for further implementation details and theoretical background:

Portfolio Optimization: A Comparison of Deep Q-Learning and Actor-Critic Methods
Krishang Karir, Suharsh Sandhu, Bassam Syed, Aditya Manickam Arumugam, Asif Ihtemadul Haque
Western University, 2024