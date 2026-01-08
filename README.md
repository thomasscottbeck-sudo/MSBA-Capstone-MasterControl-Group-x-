# 🏢 MasterControl Capstone: Command Center
**MSBA IS 6813 | Spring 2026**

---

## 🛠️ Functional Hub
| [📋 Deliverable Specs](./docs/) | [📊 Data Room](./data/) | [📝 Question Log](./docs/Sponsor_QA.md) | [🌐 Live Dashboard](https://thomasscottbeck-sudo.github.io/MSBA-Capstone-MasterControl-Group-x/) |
| :---: | :---: | :---: | :---: |

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
*Standardized configs to ensure code runs on all machines instantly.*

### 1. Notebook Standards & The "Golden" YAML
**Primary Directive:** Quarto (`.qmd`) is the required notebook format for this project. Unlike standard `.Rmd` or `.ipynb` files, `.qmd` provides a unified engine that supports both R and Python seamlessly. 

The YAML header below is configured to be **polyglot-friendly**. It ensures that whether the notebook uses the `knitr` engine (R) or the `jupyter` engine (Python), the HTML and PDF outputs remain identical in professional formatting and functionality.

Copy this into the top of every `.qmd` file:

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

### 2. Branding & Palette
[TBD but this is a nice place to standardize a project palette with hex codes etc]

### 3. Efficiency Shortcuts
* **Track Changes:** View the real-time [Audit Trail](../../commits/main) of model edits.
* **Task Management:** Assign work and track progress via [Milestones](../../milestones).
* **Reproducibility:** Always use `here::here()` for data paths.

---

## 📂 System Architecture
```text
├── data/               # RAW data (Local only - Git ignored)
├── notebooks/
│   ├── final/          # Shared Group Deliverables (.qmd)
│   └── individual/     # Individual "Sandboxes" for end-of-term portfolio
├── output/             # Exported .csv results and .png plots
├── docs/               # Meeting notes and sponsor requirements
└── README.md           # This Hub
```

---
> **Lead Architect Note:** Before starting any work session, run `git pull` to sync the latest model changes from the team.

---
> **Lead Architect Note:** Before starting any work session, run `git pull` to sync the latest model changes from the team.
