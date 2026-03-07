# Fortnite Player Skill Modeling

## Overview

This project investigates whether player behavior in Fortnite can be mathematically modeled and used to derive an interpretable **Skill Index**.

Instead of focusing purely on prediction, the project emphasizes:

- behavioral structure
- interpretable modeling
- statistical reasoning

The analysis combines:

1. behavioral feature engineering  
2. dimensionality reduction (PCA)  
3. player archetype discovery  
4. skill index construction  
5. cross-mode skill generalization  

---

# Dataset

The dataset contains player statistics across multiple Fortnite game modes.

Available modes:

- Solo
- Duos
- Trios
- Squads
- Limited Time Modes

For each mode we have:

- score
- win count
- KD ratio
- matches played
- eliminations
- time played

After filtering:

Solo matches ≥ 50

the final dataset contains **1433 players**.

---

# Behavioral Feature Engineering

Raw counts were converted into behavioral metrics:

Solo_kpm = Solo kills / Solo matches
Solo_mpm = Solo minutesPlayed / Solo matches
Solo_wr = Solo wins / Solo matches

These transformations isolate **gameplay tendencies rather than activity level**.

---

# Latent Structure of Gameplay

Principal Component Analysis reveals that player behavior is mostly two-dimensional.

## PCA Explained Variance

<img width="565" height="455" alt="image" src="https://github.com/user-attachments/assets/9b509e45-7b4e-45b8-9fec-b65a39be817b" />

PC1 explains about **67% of variance** and represents **combat efficiency**.

PC2 captures **survival-oriented gameplay**.

---

# Player Archetypes

Clustering in PCA space identifies distinct behavioral groups.

<img width="609" height="547" alt="image" src="https://github.com/user-attachments/assets/ad384a99-aba6-41c0-b147-1aa2f4b3128f" />

Three archetypes emerge:

1. Low-impact players  
2. Combat-dominant players  
3. Survival-oriented players  

Combat-dominant players achieve the highest win rates.

---

# Skill Index

The first principal component is used as a **Skill Index**:

SkillIndex = PC1


Relationship with win rate:

<img width="565" height="455" alt="image" src="https://github.com/user-attachments/assets/c89c42ff-bbb4-4d32-b9f9-65eafaf28ea3" />

Regression results show:

R² ≈ 0.87


indicating that combat efficiency strongly explains Solo success.

---

# Cross-Mode Skill Transfer

We evaluate whether Solo skill transfers to team modes.

| Mode | R² |
|-----|----|
| Duos | 0.36 |
| Trios | 0.14 |
| Squads | 0.58 |

Interpretation:

- individual skill still matters
- but team dynamics influence outcomes

---

# Key Insights

1. Fortnite gameplay has a clear latent behavioral structure.
2. Combat efficiency is the main driver of Solo success.
3. Players form distinct behavioral archetypes.
4. A PCA-derived Skill Index summarizes player ability.
5. Skill partially transfers to team modes but is moderated by team dynamics.

---

# Project Structure

01_solo_eda.ipynb
02_solo_pca.ipynb
03_solo_clustering.ipynb
04_solo_skill_index.ipynb
05_cross_mode_analysis.ipynb
06_project_summary.ipynb


---

# Tools

Python  
Pandas  
NumPy  
Scikit-learn  
Matplotlib  
Seaborn

---

# Author

Data Analytics Portfolio Project
