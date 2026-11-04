# Student Performance & Attendance Analysis System

[[https://img.shields.io/badge/Python-3.8%2B-blue.svg?logo=python&logoColor=white]](https://www.python.org/)
[[https://img.shields.io/badge/Flask-2.0%2B-black.svg?logo=flask&logoColor=white]](https://flask.palletsprojects.com/)
[[https://img.shields.io/badge/Pandas-Data%20Analysis-150458.svg?logo=pandas&logoColor=white]](https://pandas.pydata.org/)
[[https://img.shields.io/badge/Matplotlib-Visualization-11557c.svg]](https://matplotlib.org/)
[[https://img.shields.io/badge/License-MIT-green.svg]](LICENSE)

A responsive, lightweight web-based educational analytics application developed with **Python**, **Flask**, **Pandas**, and **Matplotlib**. The system automates student academic record management, computes aggregate marks, averages, percentages, and standardized letter grades, monitors mandatory attendance compliance (<75%), and renders interactive data visualizations.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [System Architecture](#system-architecture)
- [Directory Structure](#directory-structure)
- [Installation & Local Setup](#installation--local-setup)
- [Data Schema](#data-schema)
- [Analytical Features](#analytical-features)
- [Future Enhancements](#future-enhancements)
- [Author & Acknowledgments](#author--acknowledgments)

---

## 📖 Overview

In academic institutions, evaluating student progression and tracking daily attendance manually often leads to arithmetic discrepancies, delayed defaulter detection, and administrative overhead. 

The **Student Performance & Attendance Analysis System** resolves these challenges by providing:
1. **Automated Academic Grading** across four core engineering subjects: Python, C Programming, DBMS, and Web Development.
2. **Real-time Attendance Compliance Monitoring** with instant alerts for students below the institutional 75% attendance threshold.
3. **Zero-Configuration Dual Persistence** utilizing flat CSV and text files (`students.csv` and `students.txt`), eliminating heavy database server dependencies.
4. **Descriptive Statistical Analytics & Visual Plotting** powered by Pandas and headless Matplotlib.

---

## 🚀 Key Features

- **Automated Academic Grading Engine:**  
  - Computes Total Marks (out of 400), Subject Averages, and Percentages.  
  - Automatically maps percentages to standardized institutional letter grades:  
    `A+` (≥90%), `A` (≥80%), `B` (≥70%), `C` (≥60%), `D` (≥50%), and `F` (<50%).

- **Proactive Defaulter Detection:**  
  - Highlights students possessing cumulative attendance strictly below **75%** on an active alert roster for faculty intervention.

- **Robust Form Validation:**  
  - Enforces alphabetic names, restricts marks strictly between 0 and 100, validates attendance percentages, and blocks duplicate roll numbers.

- **Algorithmic Sorting & Searching:**  
  - **Bubble Sort:** Ranks the entire cohort in descending order based on cumulative marks.  
  - **Substring Search:** Enables real-time case-insensitive keyword filtering by student name or roll number.

- **Integrated Pandas Aggregation:**  
  - One-click statistical summary computing cohort highest marks, lowest marks, class average score, average attendance, and mean percentage.

- **Server-Side Visual Analytics (Matplotlib):**  
  - **Bar Chart:** Direct comparative plot of total marks across all students.  
  - **Line Graph:** Performance trajectory and percentage fluctuations across the cohort.  
  - **Histogram:** Frequency density distribution across five equal percentage brackets.

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Backend Framework** | Python 3, Flask | Routing, business logic, validation, and HTTP controllers |
| **Data Analytics** | Pandas, NumPy | Statistical aggregations (min, max, mean) and data transformation |
| **Data Visualization** | Matplotlib (`Agg` backend) | Server-side image rendering (Bar Chart, Line Graph, Histogram) |
| **Frontend UI** | HTML5, CSS3, JavaScript | Responsive dashboard, AJAX dynamic updates, modal popups |
| **Storage Architecture** | Flat CSV & TXT | Atomic machine-readable records (`students.csv`) & human-readable audit trail (`students.txt`) |

---

## 🏗️ System Architecture

The application adopts a lightweight **Model-View-Controller (MVC)** design pattern:
- **Model:** Dual file persistence (`data/students.csv` and `data/students.txt`) managed via Python's built-in `csv` module.
- **Controller (`app.py`):** Flask application handling HTTP routes (`/add-student`, `/edit/<roll>`, `/update-student`, `/delete/<roll>`, `/sort`, `/search`, `/pandas-analysis`, `/bar-chart`, `/line-graph`, `/histogram`).
- **View (`templates/index.html`):** Jinja2 templated frontend with responsive CSS grid cards, color-coded badges, and AJAX asynchronous triggers.

---

## 📂 Directory Structure

```text
Student Performance And Attendence Analysis/
│
├── app.py                      # Core Flask web server, route controllers & algorithms
├── data/
│   ├── students.csv            # Primary structured CSV dataset
│   └── students.txt            # Mirrored plain-text audit log
├── charts/
│   ├── bar_chart.png           # Generated comparative bar chart
│   ├── line_graph.png          # Generated percentage trajectory line graph
│   └── histogram.png           # Generated percentage distribution histogram
├── templates/
│   └── index.html              # Dynamic responsive Jinja2 HTML dashboard
└── README.md                   # Project documentation
