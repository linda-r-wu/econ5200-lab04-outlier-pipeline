[README.md](https://github.com/user-attachments/files/32877484/README.md)
# Outlier Detection on California Housing

## Objective

I compared outlier-detection methods on California Housing data to understand how their settings and inputs affect which observations they flag.

## Methodology

- I diagnosed and fixed three bugs involving the modified Z-score calculation, the Tukey fence multiplier, and Isolation Forest's contamination setting.
- I used an `OutlierDetector` class that validates its settings and returns a summary of the results.
- I applied modified Z-score and Tukey fences to `MedInc`, and Isolation Forest to all 9 numeric columns.
- I compared the observations flagged by each method and wrote a method-selection memo.
- I built an interactive explorer to adjust settings, compare counts, and inspect flagged rows.

## Key Findings

Modified Z-score flagged **400** observations, Tukey fences flagged **681**, and Isolation Forest flagged **1,032**. All three methods agreed on **322** observations.

I recommended using modified Z-score alongside Isolation Forest: the first identifies unusually high or low income values, while the second identifies unusual combinations across columns. For a policy team allocating housing funds, I recommended reviewing flagged observations before removing them because unusual communities may still represent valid and important data.
