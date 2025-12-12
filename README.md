Loan Policy Optimization using Supervised Learning and Offline Reinforcement Learning

This project builds a loan approval decision system using two approaches:

A supervised deep learning classifier that predicts the probability of default.

An offline reinforcement learning agent that learns a loan approval policy aimed at maximizing financial return.

The assignment is based on the LendingClub dataset and follows the requirements of the Shodh ML Hiring Task.

Project Summary

The workflow includes:

Exploratory data analysis and preprocessing

Building a deep learning model for classification

Designing an offline RL environment from static loan data

Training policy models using offline RL algorithms

Evaluating the supervised model (AUC, F1, threshold)

Estimating policy value for the RL agent

Comparing the supervised decision rule with the learned RL policy

Highlighting cases where the two disagree and analyzing the reasons

Repository Structure

notebooks/ Jupyter notebooks for each step
models/ Saved preprocessing objects, model weights, RL policies
src/ Python scripts for preprocessing, training, and evaluation
requirements.txt Package dependencies
README.md Project description
.gitignore

Dataset Information

The dataset used is the LendingClub accepted loan data (2007–2018).
The target variable is converted into a binary outcome:
0 for Fully Paid
1 for Charged Off or Defaulted

A subset may be used during experimentation for faster iteration.

Methodology Overview

Supervised Learning Model
An MLP classifier predicts the probability that an applicant will default.
Metrics include AUC, F1 score, and an optimized decision threshold to convert probabilities into actions.

Offline Reinforcement Learning
The RL setup defines:
State: applicant features
Action: 0 for deny, 1 for approve
Reward:

0 if the loan is denied

positive interest earnings if the loan is paid

negative principal loss if the loan defaults

Algorithms like Conservative Q-Learning (CQL) and value-based policies were used to train an offline agent.

Results Summary

Supervised Model
AUC: (insert)
F1 Score: (insert)
Best threshold: (insert)

Offline RL Agent
Estimated policy value: (insert)

Policy Comparison

The supervised model follows a threshold rule based on predicted default probability.
The RL agent chooses actions to maximize long-term expected reward.

Differences between the two policies usually occur in borderline risk cases.
Examples include:

Instances where the classifier denies a loan but RL approves due to expected interest outweighing risk.

Cases where RL denies a loan the classifier approves because expected loss is high.

Installation and Setup

Create environment:
python -m venv venv

Activate:
venv\Scripts\activate (Windows)
source venv/bin/activate (Linux/Mac)

Install dependencies:
pip install -r requirements.txt

Running the Project

Preprocessing:
python src/preprocessing.py

Train supervised model:
python src/train_supervised.py

Train RL agent:
python src/train_rl.py

Evaluate and compare:
python src/evaluate.py
