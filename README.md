# A-B-Testing-Analysis-Cookie-Cats-Mobile-Game

## Project Purpose

This project aims to analyze the results of an **A/B test** conducted in the mobile game **Cookie Cats** and determine whether changing the gate level affects player behavior.

In the experiment:

- **gate_30** → control group
- **gate_40** → test group

The main objective is to evaluate whether moving the gate from level 30 to level 40 creates a **statistically significant difference** in:

- total game rounds played
- 1-day retention
- 7-day retention

This project also demonstrates how A/B testing can support **data-driven product decisions**.

---

## 🔗 Dataset Link

You can access the dataset here:

[Cookie Cats Dataset on Kaggle](https://www.kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats)

---

## About the Dataset

The dataset belongs to an A/B test from the mobile puzzle game **Cookie Cats**.  
Players were randomly assigned to one of two game versions, and the impact of the gate position on user engagement was measured.

### Variables

| Column | Description |
|--------|-------------|
| `userid` | Unique player ID |
| `version` | Assigned game version (`gate_30` or `gate_40`) |
| `sum_gamerounds` | Total number of game rounds played by the user |
| `retention_1` | Whether the user returned 1 day after installation |
| `retention_7` | Whether the user returned 7 days after installation |

### Dataset Summary

- **Number of observations:** 90,189
- **Number of variables:** 5
- **Missing values:** None

This makes the dataset suitable for statistical comparison between the control and test groups.

---

## Project Objectives

In this project, I aimed to:

- understand the logic of A/B testing on a real dataset
- perform exploratory data analysis (EDA)
- compare control and test groups
- build and interpret statistical hypotheses
- check normality and variance assumptions
- apply parametric / non-parametric testing logic
- perform **proportions z-test** for retention metrics
- calculate confidence intervals
- make a final business recommendation based on statistical evidence

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Statsmodels

---

## Exploratory Data Analysis

During the EDA process, I examined:

- dataset structure
- missing values
- group distribution
- average and median game rounds
- retention rates
- outliers
- skewness of the game rounds variable

### Key EDA Insights

- The two experiment groups are almost evenly distributed.
- There are no missing values in the dataset.
- `sum_gamerounds` is highly right-skewed.
- There are many extreme outliers in the number of game rounds played.
- Retention rates appear slightly higher for `gate_30`, especially in `retention_7`.

---

## Hypothesis Testing

### Main Hypothesis

**H0:** There is no statistically significant difference between `gate_30` and `gate_40` in terms of player behavior.  
**H1:** There is a statistically significant difference between `gate_30` and `gate_40` in terms of player behavior.

---

## Assumption Checks

Before selecting the appropriate statistical test, I checked the assumptions required for parametric testing.

### Tests Applied

- **Shapiro-Wilk Test** → for normality
- **Levene Test** → for variance homogeneity

### Results

- Normality assumption was **not satisfied**
- Variance homogeneity assumption was **satisfied**

Because the distribution was not normal, I used the **Mann-Whitney U test** instead of an independent samples t-test.

---

## A/B Testing Results

### 1. Total Game Rounds (`sum_gamerounds`)

- **Test used:** Mann-Whitney U Test
- **Result:** No statistically significant difference

Although `gate_30` had a slightly higher average number of game rounds, the difference was not statistically meaningful.

### 2. 1-Day Retention (`retention_1`)

- **Test used:** Proportions Z-Test
- **Result:** No statistically significant difference

This suggests that changing the gate position did not create a meaningful short-term retention effect.

### 3. 7-Day Retention (`retention_7`)

- **Test used:** Proportions Z-Test
- **Result:** Statistically significant difference found

The `gate_30` group showed higher 7-day retention than `gate_40`.

This indicates that keeping the gate at level 30 supports better long-term player retention.

---

## Confidence Intervals

Confidence intervals were calculated for average game rounds in both groups.

The intervals overlapped, which supports the finding that the difference in total game rounds is **not statistically significant**.

---

## Final Conclusion

The A/B test analysis showed that:

- moving the gate from level 30 to level 40 does **not** significantly change the total number of game rounds played
- it does **not** significantly affect 1-day retention
- but it **does** significantly affect 7-day retention

The results suggest that the **gate_30** version performs better in terms of long-term player retention.

### Final Recommendation

From a product and business perspective, keeping the gate at **level 30** appears to be the better decision.

---

## Business Interpretation

This project shows that not every product change improves user behavior.

Although moving the gate to level 40 might seem like a small game design adjustment, the analysis suggests that it may reduce long-term player engagement.

For game companies, even small design changes should be tested carefully, because they can affect retention and overall user loyalty.

---

## Limitations

This analysis is limited to the variables available in the dataset.

The dataset does not include potentially important factors such as:

- player age or demographics
- session duration
- in-game purchases
- player progression details
- engagement by level or device type

Therefore, the results should be interpreted within the scope of the available data.

---

## What I Learned

With this project, I practiced:

- the full A/B testing workflow
- EDA for experimental datasets
- statistical assumption checking
- non-parametric testing
- proportion testing
- confidence interval interpretation
- turning statistical findings into business recommendations

---
## Author

**Sueda Kazan**  
Data Science | Machine Learning | CRM Analytics | A/B Testing 

🔗 GitHub: https://github.com/suedakzn  
🔗 Kaggle: https://www.kaggle.com/suedakazan  
🔗 LinkedIn: https://www.linkedin.com/in/sueda-kazan/

Bu proje hakkında detaylı anlatımın yer aldığı Medium yazıma buradan ulaşabilirsiniz:
🔗 [Medium yazısını okumak için tıklayın](https://medium.com/@suedakzn/a-b-testing-analizi-cookie-cats-veri-seti-ile-oyuncu-davranışı-üzerine-17b31f76831d)

---

## Project Structure

```bash
ab-testing-cookie-cats/
│
├── a-b-testing-on-mobile-game-retention-cookie-cats.ipynb
├── cookie_cats.csv
└── README.md


