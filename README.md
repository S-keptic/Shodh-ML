Supervised Learning + Offline Reinforcement Learning

This project explores how to improve loan approval decisions using:

🔵 A deep learning classifier (predicts probability of default)

🟢 An offline reinforcement learning agent (learns an approval policy that maximizes financial return)

Built as part of the Shodh ML Hiring Assignment.

📘 Overview

The project includes:

📊 Exploratory data analysis

🧹 Preprocessing and feature engineering

🤖 Deep learning classification model

🎮 Offline reinforcement learning environment & agent

📈 AUC, F1, threshold optimization

🏆 Policy value estimation

⚔️ Comparison of supervised vs RL policies

🔍 Disagreement analysis with explanations

The goal is not only prediction, but policy optimization.

📂 Repository Structure
notebooks/        Step-by-step Jupyter notebooks
models/           Saved ML models, RL policies, preprocessing
src/              Training, preprocessing, evaluation scripts
requirements.txt  Dependencies
README.md         Project documentation
.gitignore

📊 Dataset

Dataset: LendingClub Accepted Loans (2007–2018)

Target variable (binary):

0 → Fully Paid

1 → Default or Charged Off

A reduced sample may be used for faster experimentation.

🧠 Methodology
🔵 Supervised Learning (Deep Learning Classifier)

Model: Multi-Layer Perceptron
Output: probability of default

Metrics:

AUC

F1 Score

Best decision threshold

🟢 Offline RL Agent

State → processed applicant features
Action → approve (1) or deny (0)

Reward design:

Deny → 0

Approve + fully paid → +interest earned

Approve + default → –loan amount

Algorithms used:

CQL (Conservative Q-Learning)

Value-based policy estimation

RL learns a policy that maximizes expected financial return, not classification accuracy.

📈 Results Summary
Supervised Model

AUC: (insert)
F1 Score: (insert)
Best Threshold: (insert)

RL Agent

Estimated Policy Value: (insert)

⚔️ Policy Comparison

The supervised model uses a threshold rule:
approve if predicted default probability < threshold.

The RL agent approves only when it expects positive reward.

Common disagreements:

Classifier denies but RL approves → expected profit outweighs risk

Classifier approves but RL denies → expected loss too high

RL acts more like a profit-maximizing decision system.
