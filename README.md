# 📊 MSBA Capstone - Group Project Dashboard
**MSBA IS 6813 | Spring 2026**

[![Project Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)]()
[![Engine](https://img.shields.io/badge/Engine-Quarto%20(Polyglot)-blue?style=flat-square)]()
[![Deploy](https://img.shields.io/badge/Deploy-GitHub%20Pages-orange?style=flat-square)]()

---

## 🛠️ Functional Hub & Assignments

| **Core Tools** 🛠️ | [📋 Specs](./docs/Assignments.md) | [📊 Data Room](./data/) | [📝 Question Log](./docs/Sponsor_QA.md) | [🌐 Group Dashboard](https://thomasscottbeck-sudo.github.io/MSBA-Capstone-MasterControl-GroupProject/) |
| :--- | :---: | :---: | :---: | :---: |
| **Assignments** 📂 | [📂 01 Problem](./notebooks/01_Business_Problem/) | [📂 02 EDA](./notebooks/02_EDA/) | [📂 03 Modeling](./notebooks/03_Modeling/) | [📂 04 Presentation](./notebooks/04_Presentation/) |

---

## 📅 Mission Milestones (Hard Deadlines)

| Phase | Milestone | Hard Deadline |
| :---: | :--- | :--- |
| 🟢 | **Business Problem Statement** | **Jan 28** |
| 🟡 | **EDA Group Notebook** | **Feb 18** |
| ⚪ | **Modeling Notebook** | **Mar 18** |
| ⚪ | **Practice Presentation** | **Apr 05** |
| ⚪ | **Final Sponsor Delivery** | **Apr 08/15** |
| ⚪ | **Portfolio & Peer Eval** | **Apr 19** |

---

## ⚙️ Developer Tooling & Automation

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

### 2. Foolproof Data Loading (The "Here" Rule)
**Strict Rule:** Never use absolute paths. Use `here::here()` to detect the project root automatically.

```r
library(here)
# This automatically finds the project root (where .git is)
# Then looks inside the "data" folder for your file
df <- read.csv(here::here("data", "your_filename.csv"))
```

### 3. Efficiency Shortcuts
* **Track Changes:** View the real-time [Audit Trail](../../commits/main).
* **Task Management:** Track progress via [Milestones](../../milestones).

---

## 🧠 Repository Architecture & Usage Flow
*Visual map of how files, data, and code interact within this repository.*

![Repository Architecture](https://mermaid.ink/img/pako:eNqVkltv2jAUhf8K8nkgVfNQCJdKpQpV2zq0T6s8OHECrg028kOroP57nSRQ0qY8WPg437fPd_wGcyFZhGCes-y9oB6yTAsqL2sWsyj7xPMY6Q2LFZ_l2Xy5fMdiucAzFiuWc8F9cR2_8y2La75YvONJjH8_cM23PI35Zg5_FmQJ45KxSDEr-A3mZpX-X33d_N5O1dM25aJqM0Cj1Qp0tloBna5WQKfbCjB0WoGW1x_Q8-cKeL5cAb3AV0AvDBSQ6wcK6E2_AnrTq4DeDCqgN4MKGLpBBQzdoAKGblABQzeogKEbVMDQDSpg6AYVMHSDChgGgwoYBoMKGAaDChgGgwr4w2DQj69e_4C-N6iA3vcqoPf9Cuj9oAJ6P6iA3g8qoPeDCuj9oAJ6P6iA3g8q4NugAn4YVMBwW6GA4bZCAcNthQKG2woFDLcVCji63bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAm7dsAJu3bACbt2wAr4bVsBwW6GA4bZCAcNthQKG2woFDLcVCvjL45a6Ww-1S26p2_VQu9hSdy9D7c2WunMZaie21O3KUDu2pW7XQ-3ElrpdGWrHttTteqid2FK3K0Pt2Ja6XQ-1E1vqdmWoHdtSt-uhdmJL3a4MtWNb6nY91E5sqduVoXZsS92uh9qJLXW7MtSObanb9VA7saVuV4basS11ux5qJ7bU7cpQO7albtf7_18c7d_O618c7U-u8i-O9m_v9S-O9idX-RdH-7f3-hdH-5Or_Iuj_dt7_Yuj_clV_sXR_u29_sXR_uQq_-Jo__Ze_-Jof3KVf3G0f3uvf3G0P7nKvzjW2n9T10v-3lJ3L0NtaEvduQy1oS115zLUhrbUnctQG9pSdy5DbWhL3bkMtaEtdX8Z6l4Q-P0gCKI4S-I4XgaBCIMgXkRhshz4P14QhH4Qx-EiTpI49P1FGCfhIvD9JAz9xcI_d0_Qk2gZxEEcROH8-5skWcRxFAbhIsyTKBwcv-v1H-1Wc_k)

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
> **Lead Architect Note:** Before starting any work session, run `git pull` to sync the latest model changes from the team.