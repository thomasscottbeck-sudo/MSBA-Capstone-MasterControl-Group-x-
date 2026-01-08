# 📊 MSBA Capstone - Group Project Dashboard
**MSBA IS 6813 | Spring 2026**

[![Project Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)]()
[![Engine](https://img.shields.io/badge/Engine-Quarto%20(Polyglot)-blue?style=flat-square)]()
[![Deploy](https://img.shields.io/badge/Deploy-GitHub%20Pages-orange?style=flat-square)]()

---

## 🛠️ Functional Hub & Assignments

| **Core Tools** 🛠️ | [📋 Specs](./docs/Assignments.md) | [📊 Data Room](./data/) | [📝 Question Log](./docs/Sponsor_QA.md) | [🌐 Group Dashboard](https://thomasscottbeck-sudo.github.io/MSBA-Capstone-MasterControl-GroupProject/) | [💻 GitHub Repo](https://github.com/thomasscottbeck-sudo/MSBA-Capstone-MasterControl-GroupProject) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Assignments** 📂 | [📂 01 Problem](./notebooks/01_Business_Problem/) | [📂 02 EDA](./notebooks/02_EDA/) | [📂 03 Modeling](./notebooks/03_Modeling/) | [📂 04 Presentation](./notebooks/04_Presentation/) | 🚫 |

---

## 📅 Deadlines

| Phase | Milestone | Hard Deadline |
| :---: | :--- | :--- |
| 🟢 | **Business Problem Statement** | **Jan 28** |
| 🟡 | **EDA Group Notebook** | **Feb 18** |
| ⚪ | **Modeling Notebook** | **Mar 18** |
| ⚪ | **Practice Presentation** | **Apr 05** |
| ⚪ | **Final Sponsor Delivery** | **Apr 08/15** |
| ⚪ | **Portfolio & Peer Eval** | **Apr 19** |

---

## ⚙️ Notebook tips

### 1. Notebook Standards & The "Golden" YAML
**Primary Directive:** Copy this block **exactly** into the top of every `.qmd` file.

```yaml
---
title: 
subtitle: 
date: "Spring 2026"
format:
  html:
    theme: journal
    toc: true
    toc-depth: 3
    toc-float: true
    number-sections: false
    code-fold: true
    code-tools: true
    df-print: paged
    highlight-style: github
  pdf:
    documentclass: article
    geometry:
      - margin=1in
    toc: true
    number-sections: false
    colorlinks: true
    mainfont: "Arial"
    sansfont: "Arial"
    monofont: "Courier New"
editor: visual
---
```

### 2. Standard Setup & Parallel Processing (Copy-Paste)
**Rule:** Use these blocks to initialize your environment. They include **Dynamic Core Selection** to maximize performance on any machine without crashing it (N-1 logic).

#### 🟢 R Setup (Tidyverse + Parallel)
```r
# Load Core Packages
if (!require("pacman")) install.packages("pacman")
pacman::p_load(tidyverse, here, parallel, doParallel)

# Dynamic Parallel Processing (Detects your hardware)
# Leaves 1 core free for the OS to prevent freezing
num_cores <- parallel::detectCores(logical = FALSE)
cl <- makeCluster(num_cores - 1)
registerDoParallel(cl)

print(paste("Cluster active with", num_cores - 1, "cores."))
```

#### 🔵 Python Setup (Pandas + Multiprocessing)
```python
import pandas as pd
import numpy as np
import multiprocessing
from pyprojroot import here

# Dynamic Core Selector
# Use 'n_jobs' in Scikit-Learn models (e.g., n_jobs=n_jobs)
n_jobs = multiprocessing.cpu_count() - 1

print(f"Parallel processing enabled: {n_jobs} cores available.")
```

#### ⚡ Performance Note: Why Parallel Processing?
Standard R and Python scripts run linearly on a **single CPU core**, leaving 80-90% of your computer's power idle. By enabling parallel processing (as shown above), we distribute computations across multiple cores simultaneously.
* **Impact:** This is critical for resource-intensive tasks like Random Forest, XGBoost, or Grid Search.
* **Result:** It can reduce model training time by **4x to 8x** depending on your hardware.

### 3. Foolproof Data Loading (Polyglot Paths)
Try not to use absolute paths (e.g., `C:/Users/Thomas/...`). 

**For R (using `here`):**
```r
library(here)
# Automatically finds the project root (where .git is)
df <- read.csv(here::here("data", "application_train.csv"))
```

**For Python (using `pyprojroot`):**
```python
from pyprojroot import here
# Automatically finds the project root
path = here("data/application_train.csv")
df = pd.read_csv(path)
```

---

## 🧠 Repository Architecture & Usage Flow
*Visual map of how files, data, and code interact within this repository.*

```text
┌─────────────────┐       ┌────────────────────┐      ┌──────────────────┐
│  📂 data/       │       │  📂 notebooks/     │      │  📂 output/      │
│  (Local Only)   │──────▶│  (Code Execution)  │─────▶│  (Deliverables)  │
│  Raw .csv Files │       │  .qmd Analysis     │      │  .csv / .png     │
└─────────────────┘       └────────────────────┘      └──────────────────┘
        │                           ▲
        │                           │
        └────── (Load via 'here') ──┘
```

## 📂 Physical Directory Structure
```text
├── data/               # RAW data (Local only - Git ignored)
├── notebooks/
│   ├── 01_Business_Problem/
│   ├── 02_EDA/
│   ├── 03_Modeling/
│   ├── 04_Presentation/
│   └── individual/     # Individual "Sandboxes" for portfolio
├── output/             # Exported .csv results and .png plots
├── docs/               # Meeting notes and sponsor requirements
└── README.md           # This Hub
```

---

## 📞 Contact Information

| Team Member | Email (Personal) | Email (University) | Phone |
| :--- | :--- | :--- | :--- |
| **Thomas Beck** | thomasscottbeck@gmail.com | u0399590@utah.edu | +1 (801) 631-2080 |
| **Max Ridgeway** | [TBD] | [TBD] | +1 (801) 597-3824 |

---
> **Note:** Before starting any work session, run `git pull` to sync the latest model changes from the team.