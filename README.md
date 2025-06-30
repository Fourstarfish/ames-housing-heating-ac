# Impact of Heating Quality & Air Conditioning on Ames House Prices

A multiple linear regression analysis of the Ames Housing Dataset to quantify how heating quality and central air conditioning affect sale prices, controlling for overall quality, living area, and basement area.  

---

## Table of Contents

- [Project Overview](#project-overview)  
- [Dataset](#dataset)  
- [Research Question](#research-question)  
- [Methods](#methods)  
- [Results](#results)  
- [Contributors](#contributors)  
- [Reproducing the Analysis](#reproducing-the-analysis)  
- [Project Structure](#project-structure)  
- [License](#license)  

---

## Project Overview

This project investigates the impact of heating quality and central air conditioning on house sale prices using the Ames Housing Dataset. Employing multiple linear regression (MLR) and Box–Cox transformations, we build an interpretable model that controls for key covariates and meets MLR assumptions through systematic diagnostic testing and remediation.

---

## Dataset

- **Source**: Ames Housing Dataset (Prevek, 2024)  
- **Records**: 2,930 residential sales in Ames, Iowa (2006–2010)  
- **Key Variables**:  
  - **SalePrice** (response)  
  - **Heating Quality** (categorical)  
  - **Central Air** (binary)  
  - **Overall Quality** (ordinal)  
  - **Above Ground Living Area** (continuous)  
  - **Total Basement Area** (continuous)  

---

## Research Question

> How do heating quality and central air conditioning affect house sale prices, after controlling for overall quality, living area, and basement area?

---

## Methods

1. **Data Cleaning & Encoding**  
   - Checked for missing values and encoded categorical predictors.  
2. **Initial Model & Diagnostics**  
   - Fitted MLR; evaluated linearity, homoscedasticity, normality, and multicollinearity (VIF).  
3. **Transformation**  
   - Applied Box–Cox analysis; selected quarter-power (λ ≈ 0.141) transformation for SalePrice.  
4. **Refined Model & Validation**  
   - Rechecked diagnostics, identified leverage/outliers, assessed ANOVA and t-tests.  
5. **Interpretation**  
   - Quantified coefficients to infer the “comfort premium” of heating and AC features.

---

## Results

- **Adjusted R²**: 0.8263  
- **Key Findings**:  
  - Central air conditioning is associated with a 0.865-unit increase in transformed sale price (p < 0.001).  
  - Poor heating quality corresponds to a −1.465-unit change versus excellent quality (p < 0.001).  
- **Assumptions**: All MLR conditions met post-transformation.

For full details, see the [Final Project Report (PDF)](Final%20Project%20Part%203.pdf).

---

## Contributors

- **Mohammad Danish Malik**  
  - Introduction, Methods, Conclusions & Limitations, Ethical Discussion, Bibliography, Appendix  
- **Yutong Han**  
  - R coding, Results Section, Poster design  

---

## Reproducing the Analysis

1. **Clone the repo**  
   ```bash
   git clone https://github.com/your-username/ames-housing-heating-ac.git
   cd ames-housing-heating-ac
   ```

2. **Install R packages**  
   ```r
   install.packages(c("tidyverse", "car", "MASS", "knitr", "rmarkdown"))
   ```

3. **Render the R Markdown report**  
   ```r
   rmarkdown::render("part3.Rmd", output_format = "html_document")
   ```

4. **View Outputs**  
   - `part3.html`: narrative report with figures and tables  
   - `Final Project Part 3.pdf`: formatted paper  

---

## Project Structure

```
├── part3.Rmd                 # R Markdown analysis
├── Final Project Part 3.pdf  # Final write-up (PDF)
├── What Makes a House Valuable...pdf  # Poster/Paper summary
├── data/                      # Raw and processed data files
├── figures/                   # Diagnostic plots and flowchart
└── README.md                  # This file
```

---

## License

This work is licensed under the MIT License. See [LICENSE](LICENSE) for details.
