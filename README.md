Loan Policy Optimization using Supervised Learning and Offline Reinforcement Learning

This project implements a loan approval decision-making system using two approaches:

Supervised deep learning classification

Offline reinforcement learning for policy optimization

The objective is to help a lending institution decide whether to approve or deny loan applications in a way that maximizes long-term financial returns.

This work is based on the Shodh Hiring ML Assignment.

Project Overview

The project covers:

Data preprocessing and feature selection

A deep learning model to predict the probability of default

An offline RL agent that learns an approval policy using historical outcomes

Comparison between the supervised decision threshold policy and the RL policy

Analysis of disagreements between the two policies

Repository Structure

notebooks: EDA, preprocessing, supervised model training, RL training, policy comparison
models: trained models, preprocessed data, RL policies
src: python scripts for preprocessing, training, and evaluation
requirements.txt: dependencies
.gitignore
README.md

Dataset

The dataset used is the LendingClub accepted loan data (2007–2018).
The target variable is binary:
0 = Fully Paid
1 = Charged Off or Defaulted

Methodology

Supervised Model
A multi-layer perceptron is trained to predict the probability of default.
Metrics reported include AUC, F1 score, and the optimal decision threshold.

Offline Reinforcement Learning
States are the applicant features.
Actions are: 0 = deny loan, 1 = approve loan.
Rewards were defined as:

0 for deny

(loan_amount * interest_rate) if fully paid

loan_amount if defaulted

The agent was trained using offline RL algorithms such as CQL and a basic value-based policy.

Results

Supervised Model Metrics
AUC: (add your value)
F1 Score: (add your value)
Best Threshold: (add your value)

Offline RL Agent
Estimated Policy Value: (add your value)

Policy Comparison

The supervised model follows a rule based on predicted probability of default.
The RL agent follows a rule based on expected long-term reward.

Differences between the two often occur in borderline cases:

Cases the classifier denies but RL approves because expected interest outweighs risk.

Cases the classifier approves but RL denies due to high expected loss.

Installation

Create environment:
python -m venv venv
Activate:
venv\Scripts\activate (Windows)
Install dependencies:
pip install -r requirements.txt

Running the Project

python src/preprocessing.py
python src/train_supervised.py
python src/train_rl.py
python src/evaluate.py

Author

Anmol Srivastava
