## ⚾ MLB Performance Analytics and Strategic Modeling

This project analyzes historical Major League Baseball (MLB) team and player data to identify the statistical factors that drive team success and individual All-Star selection. The findings provide actionable insights for MLB organizations regarding team structure, recruitment strategies, and resource allocation.

---

### 🚀 Objectives

The primary goal was to develop predictive models and use clustering techniques to answer key strategic questions:

* Which team statistics have the strongest correlation with wins and losses?
* What impact do statistics like batting averages, home runs, or pitches have on a team's overall performance?
* Which player qualities are most important for winning games (i.e., becoming an All-Star)?

---

### ⚙️ Methodology and Models

The analysis employed three distinct data mining techniques: **K-means Clustering**, a **Multiple Linear Regression Model**, and a **Decision Tree Model**.

#### 1. Data Preparation and Feature Engineering

* **Source:** Kaggle MLB dataset, originally including 12 distinct datasets and over 60 fields in one area.
* **Cleaning:** Eliminated numerous **null values**, **duplicate entries**, and **data inconsistencies**.
* **Filtering:** Focused only on data from each team, excluding management and recruiting data. Removed any data that happened before the All-Star game was started.
* **Feature Engineering:** Created the **Win Percentage** field by taking the amount of wins a team had and dividing them by the total games and multiplying by 100.
* **Data Merging:** Used spss to merge tables for clustering and predictive models. For the Decision Tree, an outer join was used to merge the batters table with the all-star table, where null values for non-All-Stars were turned to '0' using a filler node.

#### 2. K-means Clustering

* **Goal:** Determine the most important attributes for increasing team win percentage.
* **Attributes Used:** Number of All-Star players, Win Percentage, Runs per season, and Strikeouts per season.
* **Key Finding:** The **number of All-Star players** was the most important attribute to a team's win percentage.
    * Teams with one All-Star had the lowest win percentage, while teams with 5 All-Stars had the highest win percentage.
    * Worse performing teams had significantly less runs and strikeouts than higher performing teams.
    * The top teams had good performance in **both pitching or hitting**, while mid-tier teams were either good at one or the other.

#### 3. Multiple Linear Regression Model

* **Goal:** Predict a team's Win-Loss Percentage (W-L%) using several key factors.
* **Predictors Used:** Runs Scored (**R**), Home Runs (**HR**), Runs Allowed (**RA**), Earned Run Average (**ERA**), and Strikeouts by Pitchers (**SOA**).
* **Key Finding (Predictor Importance):**
    * **Most Important:** **Runs (R)** had the greatest impact on win percentage.
    * **Least Important:** Strikeouts by Pitchers (**SOA**) had the least impact on the expected win percentage.
* **Strategic Insight:** HR didn’t have as big of an impact on win percentage as previously thought; teams might find it more important to focus on **getting on base** instead of trying to hit home runs.

**Visual Support: Regression Model Predictor Importance**
<img width="1030" height="504" alt="Regression1" src="https://github.com/user-attachments/assets/b161a653-801d-426f-bb2d-03ca08ae3661" />
<img width="1030" height="516" alt="Regression2" src="https://github.com/user-attachments/assets/2cabfe42-1e1d-47e9-8797-a4f05cb7d4d9" />
<img width="900" height="401" alt="PredictorImportance" src="https://github.com/user-attachments/assets/d441ec0d-e752-4a9c-9314-ddecefbb9a87" />



#### 4. Decision Tree Model

* **Goal:** Predict which batters would become All-Stars based on their season stats.
* **Key Predictors Identified (in order of importance):** Hits (**H**), Home Runs (**HR**), and Runs (**R**).
* **Example Decision Rules:**
    * If a player has **fewer than 140.5 hits**, the model immediately predicts they will not be an All-Star.
    * Players with more than 140.5 hits and fewer than 18.5 home runs are also predicted to not be All-Stars.
* **Model Observation:** The model was better at predicting if a player was **not** an All-Star compared to predicting if he was an All-Star. This is believed to be because historically there has been a very small amount of All-Stars compared to the total player population.


---

### 📈 Key Visualizations

The following charts directly support the core findings of the analysis:

**All-Stars vs. Win Percentage Over Time**
This graph visualizes the finding that the amount of All-Stars a team has directly correlates to their win percentage.

<img width="700" height="465" alt="AllStarWinOverTime" src="https://github.com/user-attachments/assets/f3f69496-189f-4021-8764-fe63eb1c6fd1" />


**Win/Loss to Homeruns Scatter Plot**
Illustrates the correlation between home runs and victories, showing how it varies depending on how many home runs the sides score.

<img width="700" height="370" alt="WinLossScatterPlot" src="https://github.com/user-attachments/assets/8f1c267e-6f1a-4ecd-9da1-adc3fd5780b1" />


---

### 📚 Full Project Report

The complete analysis, including detailed data preparation steps, all four K-means clusters, and supplementary visualizations (e.g., Hits to Runs line chart), can be found in the comprehensive project report: **Business Understanding - MLB Analytics.pdf**.
