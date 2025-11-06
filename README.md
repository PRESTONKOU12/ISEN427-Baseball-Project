# Bayesian Analysis of MLB Umpire Decision-Making

## Project Overview

This project applies Bayesian statistical modeling to analyze the decision-making accuracy of MLB umpires using Statcast data from Baseball Savant. By leveraging PyMC for probabilistic programming, we developed predictive models to identify key factors influencing umpire errors on ball/strike calls.

**Key Question:** What pitch characteristics, game situations, and contextual factors predict umpire decision-making errors?

## Technical Highlights

### Methodology
- **Bayesian Logistic Regression** using PyMC3/PyMC for probabilistic inference
- **Variational Inference (ADVI)** for efficient posterior approximation
- **Prior Predictive Checking** to validate model assumptions
- **Class Imbalance Handling** via random undersampling
- **Model Comparison** using F1 scores and posterior distributions

### Technologies Used
- **Python**: pandas, NumPy, Matplotlib
- **Probabilistic Programming**: PyMC, ArviZ
- **Machine Learning**: scikit-learn, imbalanced-learn
- **Data Visualization**: Matplotlib, ArviZ plotting

## Dataset

**Source:** [Baseball Savant Statcast System](https://baseballsavant.mlb.com/csv-docs)

**Features Analyzed:**
- **Pitch Characteristics**: location, type, velocity, movement (pfx_x, pfx_z)
- **Game Context**: count (balls/strikes), runners on base, score differential
- **Situational Pressure**: win expectancy change, run expectancy change
- **Player Attributes**: pitcher/batter handedness, All-Star status, strike zone dimensions

**Target Variable:** `error_in_decision` (binary: correct/incorrect call)

## Analysis Approach

### Data Preprocessing
1. **Feature Engineering**: Categorized pitch types into fastballs, changeups, off-speed, and rare pitches
2. **Encoding**: Converted categorical variables (handedness, pitch outcomes) to binary
3. **Scaling**: Applied StandardScaler/MinMaxScaler for coefficient interpretability
4. **Train-Test Split**: 80/20 split with stratification
5. **Class Balancing**: Undersampled majority class to address imbalance (umpires are correct most of the time)

## Project Structure

```
ISEN427-Baseball-Project/
│
├── README.md                 # Project documentation
├── UmpireData.md            # Statcast data dictionary
│
├── Umpire_1.csv             # Umpire 1 Statcast data
├── Umpire_2.csv             # Umpire 2 Statcast data
├── Umpire_3.csv             # Umpire 3 Statcast data
│
├── umpire1.ipynb            # Sequential model building analysis
├── umpire2.ipynb            # Situational factors analysis
└── umpire3.ipynb            # Comprehensive feature categorization
```

## Notebooks

### [umpire1.ipynb](umpire1.ipynb)

### [umpire2.ipynb](umpire2.ipynb)

### [umpire3.ipynb](umpire3.ipynb)

## Skills Demonstrated

- **Statistical Modeling**: Bayesian inference, logistic regression, hierarchical modeling
- **Machine Learning**: Feature engineering, train-test splitting, class imbalance handling, cross-validation
- **Probabilistic Programming**: PyMC model specification, ADVI optimization, posterior analysis
- **Data Wrangling**: Handling missing data, encoding categorical variables, data normalization
- **Model Validation**: Prior/posterior predictive checks, F1 scores, accuracy metrics
- **Data Visualization**: Posterior distributions, prior predictive coverage plots
- **Domain Knowledge Application**: Baseball analytics, Statcast system understanding

## Future Enhancements

1. **Hierarchical Modeling**: Build multi-level models accounting for umpire-specific effects
2. **Time Series Analysis**: Examine umpire fatigue effects over course of game/season
3. **Interaction Effects**: Model interactions between pitch location and game situation
4. **External Validation**: Test models on different seasons or umpires
5. **Automated Zone Comparison**: Compare umpire calls to MLB's automated strike zone system
6. **Causal Inference**: Use causal modeling to distinguish correlation from causation

## References

- [Baseball Savant - Statcast CSV Documentation](https://baseballsavant.mlb.com/csv-docs)
- [PyMC Documentation](https://www.pymc.io/)
- [ArviZ: Exploratory Analysis of Bayesian Models](https://arviz-devs.github.io/arviz/)

## Course Information

**Course**: ISEN 427/627 - Decision and Risk Analysis
**Institution**: Texas A&M Univeristy
**Semester**: Spring 2025

---

*This project demonstrates the application of Bayesian statistical methods to real-world sports analytics, showcasing skills in probabilistic modeling, feature engineering, and data-driven decision analysis.*
