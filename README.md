# F1 Race Prediction: Winner-Optimized Model
### DATA 602 - Final Project

# 🏎️ [View Full Interactive Analysis (HTML)](./analysis.html)

## Project Overview
Formula 1 (F1), often termed the pinnacle of engineering, is the world’s leading motorsport. Since its debut in 1950, F1 has drawn millions of fans through its dramatic Grand Prix events. With over 826 million global followers, F1 is a prime example of big data and real-time analytics in action.

**The Goal:**
This project moves beyond simple podium prediction. We developed a machine learning pipeline to predict the exact finishing order of a Grand Prix. By treating the problem as a regression task (predicting the *time gap to the winner*), our model distinguishes between a close 2nd place and a distant runner-up, providing granular insights for race strategy and performance analysis.

## Key Results (2025 Season Validation)
Our "Winner-Optimized" model significantly outperformed statistical baselines on unseen data from the 2025 season.

| Metric | Performance | Description |
| :--- | :--- | :--- |
| **Winner Accuracy** | **75%** | Correctly predicted the P1 finisher in over 2/3rds of races. |
| **NDCG@10** | **High** | Strong ability to rank the top 10 points-scorers correctly. |
| **Top Features** | **Qualifying Gap** | `position_quali`, `con_form_all` and `grid` were the strongest predictors. |

## Group Members
1. **Ravichandra Parvatham**
2. **Shreeya Dasa Lakshminath**
3. **Hemanth Thulasiraman**

---

## Methodology

### 1. Data Source
[Formula 1 Race Data (Kaggle)](https://www.kaggle.com/datasets/jtrotman/formula-1-race-data)
* **Source:** Ergast API
* **Scope:** Historical race data, qualifying times, driver standings, and constructor results.
* **Filter:** We utilized data from the **Modern Era (2004–Present)** to ensure regulation consistency and car reliability.

### 2. Feature Engineering
We engineered **14 custom features** to capture the nuance of racing, split into five categories:

* **Raw Speed:** `gap_to_pole_pct`, `gap_to_ahead_ms`, `quali_vs_field_pct`, `is_pole`.
* **Team Context:** `con_form_all` (Team Momentum), `tm_gap_ms` (Performance vs. Teammate), `con_circuit`.
* **Driver Skill:** `race_craft` (Avg. positions gained/lost), `drv_form_all`, `drv_season`, `drv_pos_5`.
* **Track History:** `drv_circuit`.
* **Positioning:** `grid`, `position_quali`.

### 3. Model Architecture
We benchmarked three algorithms to find the optimal balance between accuracy and ranking quality:
1.  **Xtreme Gradient Boosting Regressor (Champion Model):** Best performance for winner prediction.
2.  **Gradient Boosting Regressor:** Similar to XGBoost.
3.  **Random Forest:** High in NDCG@10 prediction.

### 4. Evaluation Strategy
Instead of simple accuracy, we used **NDCG@k (Normalized Discounted Cumulative Gain)**. This metric rewards the model heavily for getting the top positions (P1, P2, P3) correct, while being more forgiving of errors at the back of the grid.

---

## Visualizations & Analysis

The project includes detailed analysis modules:
* **EDA Plots**: Popular teams, reliability over the years, correlation of qualifying position and race winner, etc.
* **Feature Importance:** Quantifying whether "Car Performance" outweighs "Driver Skill."
* **Error Audit:** Identifying "The Disappointments" (Predicted Podium -> Low Finish) and "Surprise Performances" (Predicted Low -> Podium).
* **Reliability Analysis:** Historical trends of accidents and mechanical failures.

*(Refer to the Jupyter Notebook for interactive plots)*

---

## How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/ravi1-7/F1-DATA602-project.git](https://github.com/ravi1-7/F1-DATA602-project.git)
    ```
2.  **Install dependencies:**
    ```bash
    uv pip install -r requirements.txt
    ```
3.  **Download Data:**
    Download the dataset from Kaggle: [Ergast API Formula 1 Race Data](https://www.kaggle.com/datasets/jtrotman/formula-1-race-data)
4.  **Run the Notebook:**
    Open `F1_Project.ipynb` in Jupyter or Google Colab.
    * *Note:* The notebook automatically reads from a local `./data` folder. Ensure that is the path for all the data you have downloaded.

---