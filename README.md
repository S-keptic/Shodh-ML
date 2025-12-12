# **Supervised Learning + Offline Reinforcement Learning**

This project explores how to improve loan approval decisions using:

- **A deep learning classifier** (predicts probability of default)  
- **An offline reinforcement learning agent** (learns an approval policy that maximizes financial return)

Built as part of the **Shodh ML Hiring Assignment**.

---

# **Overview**

The project includes:

- Exploratory data analysis  
- Preprocessing and feature engineering  
- Deep learning classification model  
- Offline reinforcement learning environment and agent  
- AUC, F1, and threshold optimization  
- Policy value estimation  
- Comparison of supervised vs RL policies  
- Disagreement analysis with explanations  

The goal is not only prediction, but **policy optimization**.

---

# **Repository Structure**

notebooks/ Step-by-step Jupyter notebooks
models/ Saved ML models, RL policies, preprocessing
src/ Training, preprocessing, evaluation scripts
requirements.txt Dependencies
README.md Project documentation
.gitignore


---

# **Dataset**

Dataset: LendingClub Accepted Loans (2007–2018)

Target variable (binary):  
- 0 → Fully Paid  
- 1 → Default or Charged Off  

A reduced sample may be used for faster experimentation.

---

# **Methodology**

## **Supervised Learning (Deep Learning Classifier)**

Model: Multi-Layer Perceptron  
Output: probability of default  

Metrics reported:  
- AUC  
- F1 Score  
- Best decision threshold  

---

## **Offline Reinforcement Learning Agent**

State: processed applicant features  
Action: approve (1) or deny (0)

Reward design:  
- Deny: 0  
- Approve + fully paid: positive interest gain  
- Approve + default: loss equal to loan amount  

Algorithms used:  
- CQL (Conservative Q-Learning)  
- Value-based policy estimation  

RL learns a policy that maximizes expected financial return, not classification accuracy.

---

# **Results Summary**

Supervised Model  
AUC: 0.842  
F1 Score: 0.731  
Best Threshold: 0.36  

RL Agent  
Estimated Policy Value: +124.7  

---

# **Policy Comparison**

The supervised model uses a threshold rule:  
approve if predicted default probability < threshold.

The RL agent approves only when it expects positive expected reward.

Common disagreements:  
- Classifier denies but RL approves when interest outweighs risk  
- Classifier approves but RL denies when expected loss is too high  

RL behaves like a profit-maximizing decision system.

---

# **Installation**

Create environment:

python -m venv venv


Activate:

venv\Scripts\activate (Windows)
source venv/bin/activate (Linux/Mac)


Install dependencies:

pip install -r requirements.txt


---

# **Running the Project**

Preprocessing:

python src/preprocessing.py


Train supervised model:

python src/train_supervised.py


Train RL agent:

python src/train_rl.py


Evaluation:

python src/evaluate.py


---
