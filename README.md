# DATA 607 Week 2B: Classification Metrics

**Author:** Patricio Romero  
**Date:** September 13, 2026

## Project Overview

This project evaluates the performance of a binary classification model using the `penguin_predictions.csv` dataset. The dataset contains the predicted probability that each penguin is female, the predicted class, and the actual sex.

The purpose of the analysis is to examine how changing the probability threshold affects the model's predictions and performance. Female is treated as the positive class.

## Research Question

How do probability thresholds of 0.2, 0.5, and 0.8 affect the accuracy, precision, recall, F1 score, false positives, and false negatives of the classification model?

## Dataset

The dataset contains:

- 93 observations
- 3 original variables
- 39 female penguins
- 54 male penguins
- No missing values

The original class labels were stored as `female` and `male`. For the analysis, female was converted to 1 and male was converted to 0.

## Analysis

The analysis includes:

- Data loading and validation
- Class-distribution analysis
- Null error rate calculation
- Predictions at thresholds of 0.2, 0.5, and 0.8
- Confusion matrices
- Accuracy, precision, recall, and F1 score calculations
- A comparison table and visualization
- Interpretation of threshold tradeoffs

## Null Model

Male is the majority class, with 54 of the 93 observations. A null model that always predicts male would have an accuracy of 58.1% and an error rate of 41.9%.

## Results

| Threshold | TP | FP | TN | FN | Accuracy | Precision | Recall | F1 Score |
|:---------:|---:|---:|---:|---:|---------:|----------:|-------:|---------:|
| 0.2 | 37 | 6 | 48 | 2 | 91.4% | 86.0% | 94.9% | 90.2% |
| 0.5 | 36 | 3 | 51 | 3 | 93.5% | 92.3% | 92.3% | 92.3% |
| 0.8 | 36 | 2 | 52 | 3 | 94.6% | 94.7% | 92.3% | 93.5% |

The 0.2 threshold produced the highest recall, but it also produced the most false positives. The 0.5 threshold provided a good balance between precision and recall. Among the three thresholds tested, 0.8 produced the highest accuracy, precision, and F1 score while maintaining the same recall as the 0.5 threshold.

The best threshold still depends on the purpose of the model and the consequences of false-positive and false-negative predictions.

## Project Files

- [`week2b_classification_metrics.Rmd`](week2b_classification_metrics.Rmd): R Markdown source code and analysis
- [`week2b_classification_metrics.html`](week2b_classification_metrics.html): Complete rendered report
- [`data/penguin_predictions.csv`](data/penguin_predictions.csv): Dataset used in the analysis

## How to Reproduce the Analysis

1. Clone or download this repository.
2. Open `week2b_classification_metrics.Rmd` in RStudio.
3. Install the required R packages if necessary: `readr`, `dplyr`, `ggplot2`, `tibble`, and `knitr`.
4. Knit the R Markdown file to HTML.

The R Markdown file reads the CSV through its GitHub Raw URL, so the analysis does not depend on a private local file path.

## Video Explainer

Include this sentence and link:

Watch the Week 2B video presentation here:
https://youtu.be/xrnHd3pk5Os

## Conclusion

All three thresholds performed substantially better than the null-model accuracy of 58.1%. For this dataset, the 0.8 threshold produced the best overall results among the thresholds tested.

The results also demonstrate that accuracy alone is not sufficient for evaluating a classification model. Precision, recall, F1 score, false positives, and false negatives should also be considered when selecting a probability threshold.

## AI Use

ChatGPT was used to help interpret the assignment requirements, organize the planned approach, improve the English writing, and provide coding guidance. I ran the code, reviewed the results, and confirmed that I understood the analysis.
