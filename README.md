# 🐱 Mobile Game A/B Testing: Cookie Cats Retention Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Pandas%20%7C%20NumPy%20%7C%20Statsmodels-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📖 Introduction
This project analyzes the results of an A/B test performed on the popular mobile puzzle game **Cookie Cats**. The goal of the experiment was to determine the optimal placement for the first "gate" in the game—a mechanism that forces players to wait or make a purchase before progressing.

**The Experiment:**
* **Control Group (`gate_30`):** The gate is placed at **Level 30**.
* **Test Group (`gate_40`):** The gate is moved to **Level 40**.

**Objective:**
To evaluate the impact of this change on player retention, specifically **1-Day Retention** and **7-Day Retention**.

## 📂 Dataset Description
The dataset consists of game data from **90,189 players**.

| Column Name | Description |
| :--- | :--- |
| `userid` | A unique number that identifies each player. |
| `version` | The group the player was assigned to (`gate_30` or `gate_40`). |
| `sum_gamerounds` | The number of game rounds played by the player during the first 14 days after install. |
| `retention_1` | Did the player come back and play **1 day** after installing? (True/False) |
| `retention_7` | Did the player come back and play **7 days** after installing? (True/False) |

## 🛠️ Tech Stack & Prerequisites
The analysis is performed using **Python** within a Jupyter Notebook environment.

**Libraries Used:**
* `pandas` (Data manipulation)
* `numpy` (Numerical computations)
* `matplotlib` / `seaborn` (Data visualization)
* `statsmodels` (Statistical hypothesis testing)

## 🚀 How to Run
You can run this project locally or via Google Colab.

### Option 1: Local Installation
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Suannecy-young/cookie_cats_ab_testing.git](https://github.com/Suannecy-young/cookie-cats-ab-testing.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib statsmodels
    ```
3.  **Run the notebook:**
    ```bash
    jupyter notebook Cookie_Cats_AB_Test.ipynb
    ```

### Option 2: Google Colab
Click the badge below to run the notebook directly in your browser:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Suannecy-young/mobile-game-ab-testing/blob/main/Cookie_Cats_AB_Test.ipynb)

## 📊 Analysis Pipeline
1.  **Data Loading & Cleaning:** Checked for missing values and handled outliers (e.g., players with abnormally high game rounds).
2.  **Exploratory Data Analysis (EDA):** Visualized the distribution of game rounds played.
3.  **Retention Analysis:** Calculated the mean retention rates for both groups.
4.  **Hypothesis Testing:** Performed a **Z-test** (Two-sample Z-test for proportions) to determine if the difference in retention rates was statistically significant.

## 📊 Results & Conclusion

Statistical analysis (Z-test) shows that moving the gate to Level 40 negatively impacts long-term retention.

| Metric | Z-Stat | P-Value | Significance (α=0.05) |
| :--- | :--- | :--- | :--- |
| **1-Day Retention** | 1.79 | 0.074 | Not Significant |
| **7-Day Retention** | 3.16 | **0.0016** | **Significant Decline** |

**Key Takeaway:**
* **Short-term:** No significant difference in 1-day retention.
* **Long-term:** There is strong evidence (p < 0.01) that retention **drops** when the gate is moved to Level 40.

**Recommendation:**
**Keep the gate at Level 30** to maximize player retention.

---
*Author: [Xuanci Yang]*
