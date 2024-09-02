
# A/B Testing Analysis for Precision Ad Targeting Optimization

## Project Overview

This project focuses on analyzing and evaluating A/B testing data to optimize ad targeting strategies. A/B testing is a widely used method in digital marketing and product optimization to compare different versions and determine which performs better. Specifically, this project analyzes Click-Through Rate (CTR) and Conversion Rate (CR) to provide data-driven insights that inform advertising strategies.

## Table of Contents

- [Project Overview](#project-overview)
- [Data Description](#data-description)
- [Analysis Workflow](#analysis-workflow)
- [Results](#results)
- [Visualizations](#visualizations)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Data Description

The dataset used in this project includes the following features:

- **Campaign Name**: Name of the ad campaign.
- **Date**: Date of the record.
- **Spend**: Amount spent on the campaign in dollars.
- **Number of Impressions**: The number of times the ad was displayed.
- **Reach**: The number of unique impressions received.
- **Number of Website Clicks**: The number of clicks the ad received.
- **Number of Searches**: The number of searches performed by users after clicking the ad.
- **Number of View Content**: The number of users who viewed content on the website after clicking the ad.
- **Number of Add to Cart**: The number of users who added products to the cart.
- **Number of Purchases**: The number of purchases made by users.

Two campaigns were performed and divided into:

- **Control Campaign**
- **Test Campaign**

## Analysis Workflow

1. **Data Cleaning and Preparation**:
   - Imported and cleaned the data, handling missing values and outliers.
   - Calculated key metrics: CTR (Click-Through Rate) and CR (Conversion Rate).

2. **Statistical Testing**:
   - Conducted normality and variance homogeneity tests:
     - **Control Group**: Mean CTR = 5.10%, 95% CI = [4.35%, 5.84%]
     - **Test Group**: Mean CTR = 10.25%, 95% CI = [7.82%, 12.67%]
     - **Control Group CR**: Mean = 11.60%, 95% CI = [9.17%, 14.03%]
     - **Test Group CR**: Mean = 9.31%, 95% CI = [7.74%, 10.87%]
   - Performed Welch's t-test and Mann-Whitney U test to compare CTR and CR between the control and test groups:
     - **CTR t-Statistic**: `-3.98`, **p-Value**: `0.00034`
     - **CR Mann-Whitney U Statistic**: `193.0`, **p-Value**: `0.00025`

3. **Effect Size Analysis**:
   - Calculated Cohen’s d for CTR and Cliff’s Delta for CR to quantify the practical significance of differences:
     - **CTR Cohen’s d**: `-1.02` (Large effect size)
     - **CR Cliff’s Delta**: `0.156` (Small to moderate effect size)

4. **Power Analysis**:
   - Assessed the statistical power of the tests:
     - **CTR Power**: Over 90% at an effect size of `1.02`
     - **CR Power**: Approximately 11.6% at an effect size of `0.2`, indicating a need for a larger sample size.

5. **Bootstrap Analysis**:
   - Used bootstrapping to estimate confidence intervals for CTR and CR:
     - **Control Group CTR CI**: [4.35%, 5.84%]
     - **Test Group CTR CI**: [7.82%, 12.67%]
     - **Control Group CR CI**: [9.17%, 14.03%]
     - **Test Group CR CI**: [7.74%, 10.87%]

6. **Visualization**:
   - Created histograms, box plots, and confidence interval plots to visualize the results.

## Results

- **CTR**: The test group’s mean CTR (10.25%) is significantly higher than the control group’s mean CTR (5.10%). The large effect size (Cohen’s d = `-1.02`) and non-overlapping confidence intervals further support the statistical significance of this difference.
  
- **CR**: Although the test group’s mean CR (9.31%) is slightly lower than the control group’s mean CR (11.60%), the difference is not practically significant, as indicated by a small to moderate effect size (Cliff’s Delta = `0.156`).

- **Power Analysis**: The power analysis for CTR indicates a high confidence level (>90%) in detecting the observed difference, while the low power for CR (11.6%) suggests that a larger sample size is needed to reliably detect any potential differences in CR.

## Visualizations

The repository includes the following visualizations:

- **Histograms**: Show the distribution of CTR and CR across control and test groups.
- **Box Plots**: Illustrate the spread and central tendency of CTR and CR.
- **Confidence Interval Plots**: Display the 95% confidence intervals for CTR and CR, demonstrating the precision of the estimates and supporting the findings of the statistical tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Thanks to the [Kaggle](https://www.kaggle.com) community for providing valuable datasets and resources.
- Special thanks to all contributors and the open-source community.
