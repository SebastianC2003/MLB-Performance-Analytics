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

The analysis employed three distinct data mining techniques: K-means Clustering, Multiple Linear Regression, and a Decision Tree.

#### 1. Data Preparation and Feature Engineering

* **Source:** Kaggle MLB dataset, originally including 12 distinct datasets and over 60 fields in one area.
* **Cleaning:** Eliminated numerous null values, duplicate entries, and data inconsistencies.
* **Filtering:** Focused only on data from each team, excluding management and recruiting data.
* **Feature Engineering:** Created the **Win Percentage** field by dividing wins by total games and multiplying by 100.
* **Data Merging:** Used SPSS to merge tables for clustering and predictive models. For the Decision Tree, an outer join was used to merge batters with the all-star table, where null values for non-All-Stars were turned to '0'.

#### 2. K-means Clustering

* **Goal:** Determine the most important attributes for increasing team win percentage.
* **Attributes Used:** Number of All-Star players, Win Percentage, Runs per season, and Strikeouts per season.
* **Key Finding:** The **number of All-Star players** was the most important attribute for a team's win percentage.
    * Teams with one All-Star had the lowest win percentage, while teams with 5 All-Stars had the highest win percentage.
    * Worse performing teams had significantly less runs and strikeouts than higher performing teams.

#### 3. Multiple Linear Regression Model

* **Goal:** Predict a team's Win-Loss Percentage (W-L%).
* **Predictors Used:** Runs Scored (**R**), Home Runs (**HR**), Runs Allowed (**RA**), Earned Run Average (**ERA**), and Strikeouts by Pitchers (**SOA**).
* **Key Finding (Predictor Importance):**
    * **Most Important:** **Runs (R)** had the greatest impact on win percentage.
    * **Least Important:** Strikeouts by Pitchers (**SOA**) had the least impact on the expected win percentage.
* **Strategic Insight:** HR did not have as large an impact on win percentage as initially thought; teams might find it more important to focus on **getting on base** instead of trying to hit home runs.

#### 4. Decision Tree Model

* **Goal:** Predict which batters would become All-Stars based on their season stats.
* **Key Predictors Identified (in order of importance):** Hits (**H**), Home Runs (**HR**), and Runs (**R**).
* **Example Decision Rules:**
    * If a player has **fewer than 140.5 hits**, the model immediately predicts they will not be an All-Star.
    * Players with more than 140.5 hits and fewer than 18.5 home runs are also predicted to not be All-Stars.
* **Model Observation:** The model was better at predicting if a player was **not** an All-Star, likely because there has been a very little amount of All-Stars compared to the total player population.

---

### 📈 Visualizations

Key findings were supported by the following visualizations:

* **Win/Loss to Homeruns:** A scatter plot illustrating the correlation between home runs and victories, showing how the ratio varies.
* **Hits to Runs:** A line chart contrasting a team's hits and runs, making it clear there are more runs than hits.
* **All-Stars vs. Win Percentage:** A graph visualizing the finding that the amount of All-Stars a team has directly correlates to their win percentage.
* **Predictor Importance Charts:** Visualizing the relative impact of variables for the Regression and Decision Tree models.

---
