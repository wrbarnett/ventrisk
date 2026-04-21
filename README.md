<img width="256" height="256" alt="image" src="https://github.com/user-attachments/assets/df92c755-a254-4926-9fba-da4205473047" />

<img width="512" height="256" alt="image" src="https://github.com/user-attachments/assets/e404ea0a-e1d7-4392-925f-4472dd368726" />


# 🧬 VentRisk

**Combinatorial Risk Estimation for Ventilator-Associated Events**

---

## Overview

**VentRisk** is a Streamlit-based clinical decision support tool that estimates the probability of ventilator-associated events (VAE) using a Naive Bayes classification model.

The application allows users to select patient characteristics and clinical factors via dropdown menus and returns a predicted risk based on learned patterns from training data.

This tool is designed for:

* Risk stratification
* Clinical pathway exploration
* Educational and research applications

---

## Foundational Study

**VentRisk** is based on the modeling approach described in:

Barnett WR, Bassett J, Jaenke C, Holtzapple Z, Boyinepally K, Back W, Maqsood A, Safi F, Assaly R. Detection of ventilator-associated events among adults: comparing a naïve Bayes classifier and logistic regression. *Translation: The University of Toledo Journal of Medical Sciences.* Published online October 30, 2024. doi:10.46570/utjms.2469-6706

This application extends that work by translating the Naive Bayes framework into an interactive tool for real-time risk estimation and combinatorial feature profiling.

---

## Key Features

* **Interactive Risk Prediction**

  * Select feature values and instantly compute predicted risk

* **Combinatorial Modeling**

  * Evaluates risk across all possible feature combinations

* **Naive Bayes Framework**

  * Transparent, interpretable probabilistic model

* **Full Risk Table Export**

  * Generate and download all combinations with predicted risk

* **Clinically Interpretable Output**

  * Class prediction + probability estimates

---

## Model Description

VentRisk uses a **Categorical Naive Bayes classifier** trained on structured clinical data.

### Predictors

* `ltac`
* `dm`
* `chf`
* `cad`
* `lung`
* `opsite`
* `timecat2`

### Outcome

* `status` (binary: 0 / 1)

### Output

* Predicted class
* Probability of event (`status = 1`)

---

## Methodology

* Categorical encoding aligned between training and inference
* Probability estimation using Naive Bayes likelihoods
* Risk defined as:

[
P(\text{status} = 1 \mid \text{features})
]

* Optional evaluation includes:

  * ROC curve
  * AUC with bootstrap confidence intervals
  * Sensitivity, specificity, PPV, NPV (Wilson CIs)

---

## Output Interpretation

* Risk values represent **model-estimated probability**, not causation
* Higher values indicate greater likelihood of VAE under modeled conditions
* Use in conjunction with clinical judgment

---

## Limitations

* Assumes conditional independence of predictors (Naive Bayes assumption)
* Performance depends on training data quality and representativeness
* Some feature combinations may not exist in real clinical settings
* Not intended for direct clinical decision-making without validation

---

## Future Enhancements

* Risk band visualization (low / moderate / high)
* Model comparison (logistic regression, ensemble methods)
* Integration with EHR-derived datasets
* Calibration analysis

---

## Author

Developed as part of ongoing work in:

* Clinical data science
* Quality improvement
* Predictive modeling in critical care

---

## License

For academic and research use. Extend as appropriate for deployment or commercialization.

---
