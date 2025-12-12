Loan Policy Optimization using Supervised Learning and Offline Reinforcement Learning

This project implements a loan approval decision system using two approaches:

Supervised deep learning classification

Offline reinforcement learning for policy optimization

The goal is to help a lending institution make approval decisions that maximize long-term financial return.
This work is part of the Shodh ML Hiring Assignment.

Project Summary

This project includes:

EDA and preprocessing

Deep learning classifier for default prediction

Offline RL environment design

RL agent training (CQL and value-based methods)

Evaluation of AUC, F1, and policy values

Comparison between supervised and RL decisions

Disagreement analysis explaining why each model behaves differently

Repository Structure

notebooks/ – Step-by-step Jupyter notebooks
models/ – Preprocessing objects, saved models, RL policies
src/ – Scripts for preprocessing, training, and evaluation
requirements.txt – Dependencies
README.md – Project documentation
.gitignore

Dataset Information

Dataset: LendingClub Accepted Loan Data (2007–2018)
Target variable conversion:

0 = Fully Paid

1 = Charged Off / Defaulted

A reduced subset may be used during experimentation.

Methodology Overview
Supervised Learning Model

A multi-layer perceptron (MLP) is trained to predict probability of default.
Metrics reported:

AUC

F1 Score

Optimal probability threshold

Offline Reinforcement Learning

Definitions:

State: applicant features

Action: 0 = deny, 1 = approve

Reward:

0 for deny

positive interest gain if loan is paid

negative principal loss if loan defaults

Algorithms used:

Conservative Q-Learning (CQL)

Value-based policy iteration

Results Summary
Supervised Model

AUC: (insert)
F1 Score: (insert)
Best Threshold: (insert)

Offline RL Agent

Estimated Policy Value: (insert)

Policy Comparison

The supervised model applies a threshold rule on predicted default probability.
The RL agent chooses actions to maximize expected financial reward.

Policy disagreements highlight key differences:

Cases where the classifier denies but RL approves due to positive expected interest

Cases where the classifier approves but RL denies due to high expected loss

This shows how RL optimizes long-term reward instead of only minimizing classification error.
