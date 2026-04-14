# Rally Predict

An interactive Shiny application that predicts badminton rally outcomes for 
Chou Tien-Chen and simulates optimal shot placements, powered by a logistic 
regression model.

🔗 **[Live App](https://stat-468.shinyapps.io/RallyPredict/)**  
📄 **[Full Report](https://keerthingit.github.io/Rally-Predict/)**

---

## Overview

Publicly available spatio-temporal datasets of badminton matches are scarce 
and in-depth analysis of badminton matches and players is limited. This project 
examines how a combination of rally characteristics: shot type, rally length, 
shuttle position, and player/opponent positions, influence rally outcomes for 
Chou Tien-Chen, the player with the most recorded matches in the ShuttleSet dataset.

> **How are the outcomes of a rally in CHOU's badminton matches affected by the 
> opponent, shot type, relative positions of the player, shuttle, and opponent, 
> as well as rally length?**

---
## App

Users select an opponent, rally length, shot type, and drag sliders to position 
CHOU and the opponent on the court. The app returns a predicted win probability 
from the logistic regression model.

![Winning Shuttle Landing Positions](https://keerthingit.github.io/Rally-Predict/05-visualize_files/figure-html/figure-33,%20echo-%20false,%20message-%20false,%20warning-%20false-2.png)
![Losing Shuttle Landing Positions](https://keerthingit.github.io/Rally-Predict/05-visualize_files/figure-html/figure-33,%20echo-%20false,%20message-%20false,%20warning-%20false-3.png)

---

## Key Findings

- **Shot type** and **shuttle position relative to player/opponent** were the 
  strongest predictors of rally outcome
- **Fronthand shots** scored points 50% of the time vs 15% for backhand shots
- The final model retained: `shot_type`, `chou_shuttle_paral`, `opponent`, 
  and `rally_length`

![Rally Length by Outcome](https://keerthingit.github.io/Rally-Predict/05-visualize_files/figure-html/figure-1,%20echo-%20false,%20message-%20false,%20warning-%20false-2.png)
![Shot Type Success](https://keerthingit.github.io/Rally-Predict/05-visualize_files/figure-html/figure-2,%20echo-%20false,%20message-%20false,%20warning-%20false-1.png)

---
## Data

- **Dataset:** [ShuttleSet](https://github.com/wywyWang/CoachAI-Projects/tree/main/ShuttleSet) — 
  human-annotated stroke-by-stroke badminton match data
- **Scope:** 11 men's singles matches played by Chou Tien-Chen between 2018–2019
- **Final dataset:** ~400 final rally shot data points

---

## Limitations

- Limited to 11 matches (~400 data points)
- Data quality issues required removing rallies with missing or mismatched data
- Shuttle position uses a mean value as a stand-in since it is the result of 
  the shot, not an input
- Model accuracy will improve as larger computer-vision badminton datasets 
  become available

---

