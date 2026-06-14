# Adaptive Firewall Decision-Making: Reinforcement Learning vs Supervised Models Under Evolving Attacks

> **Graduating Project** — Master of Data Analytics, Intelligence and Security  
> Rennes School of Business, 2025–2026  
> **Author:** Safa Bougacha | **Supervisor:** Karim Zkik

---

## Overview

This project investigates whether a **Deep Q-Network (DQN)** reinforcement learning agent can outperform static supervised models — **Random Forest** and **Gradient Boosting** — for firewall intrusion detection, especially when network traffic patterns shift (concept drift).

The core hypothesis: RL agents, by learning from interaction rather than fixed labels, should generalise better to novel or evolving attack patterns that supervised models have never seen.

---

## Research Questions

1. Can a DQN agent match or exceed supervised model performance on known traffic distributions?
2. Does the RL agent maintain an advantage under concept drift (cross-dataset evaluation)?
3. What are the practical trade-offs between adaptability and accuracy for real-world firewall deployment?

---

## Methodology

### Datasets

| Dataset | Role | Description |
|---|---|---|
| **CIC-IDS2017** | Phase 1 — In-distribution training & evaluation | Modern labelled network intrusion dataset |
| **NSL-KDD** | Phase 2 — Cross-dataset / concept drift evaluation | Classic benchmark with different attack distributions |

> ⚠️ **Data note:** Raw datasets are not included in this repository due to size constraints. Download them from their official sources (links below) and place them under `data/raw/`.
> - [CIC-IDS2017](https://www.unb.ca/cic/datasets/ids-2017.html)
> - [NSL-KDD](https://www.unb.ca/cic/datasets/nsl.html)

### Models

- **Random Forest** — baseline supervised classifier
- **Gradient Boosting (Tuned)** — optimised supervised classifier
- **Deep Q-Network (DQN)** — RL agent framing intrusion detection as a sequential decision problem

### Evaluation

- Phase 1: standard classification metrics (accuracy, precision, recall, F1) on CIC-IDS2017
- Phase 2: same metrics on NSL-KDD to assess cross-dataset generalisation
- Feature importance analysis on supervised models

---

## Repository Structure

```
.
├── data/               # Data loading scripts (raw data excluded — see above)
├── figures/            # Generated plots and visualisations
├── models/             # Saved model weights and checkpoints (excluded from git)
├── notebooks/          # Exploratory and analysis Jupyter notebooks
├── results/            # Evaluation metrics and result summaries
├── src/                # Source code
│   ├── preprocessing/  # Data cleaning and feature engineering
│   ├── models/         # Model definitions (DQN, RF, GB)
│   ├── training/       # Training loops and scripts
│   └── evaluation/     # Metrics and evaluation utilities
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Getting Started

### Prerequisites

- Python 3.9+
- pip

### Installation

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### Running the Models

```bash
# Preprocess data (run after placing raw data in data/raw/)
python src/preprocessing/preprocess.py

# Train supervised models
python src/training/train_supervised.py

# Train DQN agent
python src/training/train_dqn.py

# Evaluate all models
python src/evaluation/evaluate.py
```

> Refer to individual notebooks in `notebooks/` for step-by-step walkthroughs.

---

## Key Results

*(Fill in your main findings here — e.g. accuracy tables, F1 scores per phase)*

| Model | Phase 1 F1 (CIC-IDS2017) | Phase 2 F1 (NSL-KDD) |
|---|---|---|
| Random Forest | — | — |
| Gradient Boosting | — | — |
| DQN Agent | — | — |

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.9+-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-RL-red)
![scikit-learn](https://img.shields.io/badge/scikit--learn-supervised-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-notebooks-yellow)

---

## Academic Context

This work was submitted in partial fulfilment of the requirements for the **Master of Data Analytics, Intelligence and Security** at Rennes School of Business.

---

## License

This repository is for academic purposes. Please cite appropriately if you build on this work.
