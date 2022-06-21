# Responsible Machine Learning - Summer 2022

* Lecture 1: Self-explainable Machine Learning Models
* Lecture 2: Post-hoc Explanation
* Lecture 3: Discrimination Testing and Remediation
* Lecture 4: Machine Learning Security
* Lecture 5: Machine Learning Model Debugging
* Lecture 6: Responsible Machine Learning Best Practices



## WIP Instructions and Rubric.
This is a pure technical writing assignment. Very little introduction, narrative, or conclusion text is necessary. You may make copious use of bullet points, charts, and tables. (But remember that all charts and tables should have descriptions!)

Your model card must include the following sections: Intended use, Training data, Evaluation data, Model details, Quantitative analysis, Ethical considerations. The focus of the model card should be your best performing remediated model. You should briey address your other models as \alternative approaches" in the Quantitative analysis section, and point to why your main model is a better choice.

## WIP Rubric:
### Structure (6 pts.)
Abid Shafiullah (abidshafi@gwu.edu) - Somendar Chaudhary (somender@gwu.edu) - Yasir Mohammad (yasir@gwu.edu)
* Model version: 1.0
* License: Apache License
* Model date: June 2022
* Clearly delineated sections for:
*   * Intended use ( 1/2 pt.)
  * Training data ( 1/2 pt.)
  * Evaluation data ( 1/2 pt.)
  * Model details ( 1/2 pt.)
  * Quantitative analysis ( 1/2 pt.)
  * Ethical considerations ( 1/2 pt.)
* Correct and informative external links (e.g., to training and evaluation data) ( 1/2 pt.)
* Correct use and introduction of abbreviations ( 1/2 pt.)
* Charts or tables:
  * Meaningful and informative use of charts or tables ( 1/2 pt.)
  * Proper description of charts or tables ( 1/2 pt.)

### Content (13 pts.)
* Intended use (2 pts.)
 * * **Primary intended uses**: To predict whether or not the annual percentage rate (APR) charged for a mortgage is 150 basis points (1.5%) or more above a survey-based estimate of similar mortgages. (High-priced mortgages are legal, but somewhat punitive to borrowers. High-priced mortgages often fall on the shoulders of minority home owners, and are one of many issues that perpetuates a massive disparity in overall wealth between different
demographic groups in the US.)
 * * **Primary intended users**: Students in GWU DNSC 6209.
 * * **Out-of-scope use cases**: Any use beyond an educational example is out-of-scope.

  * Describe the business value of your group's best remediated model
  * * ** The best remediated model is used for:
  * * ** Discrimination testing and attempt remediating of discovered discrimination using AIR (adverse impact ratio)
  * * ![image](https://user-images.githubusercontent.com/89049995/174690589-a3f65396-bfa9-491d-a7d6-d6e7c124b23c.png)

  * * ** Retrained the most accurate model above 0.8 AIR
  * * ** Best AUC: 0.7809 above 0.8 AIR (0.8116). Remediated EBM retrained with AUC: 0.7809. 
  * * ** Checked that other groups are not adversely impacted y change: Adverse impact ratio for Asian people vs. White people: 1.146. Adverse impact ratio for Black people vs. White people: 0.812. Adverse impact ratio for Females vs. Males: 0.957
This analysis shows that even with a selective cutoff of 0.17, less discriminatory models are available. The new set of features and hyperparameters leads to a ~13% increase in AIR with a ~5% decrease in AUC.
  * Describe how your group's best remediated model is designed to be used
  * Describe the intended users for your group's best remediated model
  * State whether your group's best remediated model can or cannot be used for any additional purposes
* Training data (2 pts.)
  * State the source of training data
  * * **  Home Mortgage Disclosure Act (HMDA) data in the class repository https://github.com/jphall663/GWU_rml/tree/master/assignments/data
  * State how training data was divided into training and validation data
  * * ** 70/30
  * State the number of rows in training and validation data
  *  * ** Train data rows = 112253, columns = 23; and the Validation data rows = 48085, columns = 23
  * Define the meaning of all training data columns

* Data dictionary: 

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**high_priced**| target | int | whether (1) or not (0) the annual percentage rate (APR) charged for a mortgage is 150 basis points (1.5%) or more above a survey-based estimate of similar mortgages |
| **conforming** | input | int | whether the mortgage conforms to normal standards (1), or whether the loan is different (0) |
| **debt_to_income_ratio_std** | input | int | standardized debt-to-income ratio for mortgage applicants | 
| **debt_to_income_ratio_missing** | demographic information | int | missing marker (1) for debt to income ratio std |
| **income_std** | input | int | standardized income for mortgage applicants |
| **loan_amount_std	** | input | int | standardized amount of the mortgage for applicants |
| **intro_rate_period_std	** | input | int | standardized introductory rate period for mortgage applicants |
| **loan_to_value_ratio_std** | input | int | ratio of the mortgage size to the value of the property for mortgage applicants |
| **no_intro_rate_period_std** | input | int | whether (1) or not (0) a mortgage does not include an introductory rate period |
| **property_value_std** | input | int | value of the mortgaged property |
| **term_360**| input | int | whether the mortgage is a standard 360 month mortgage (1) or a different type of mortgage (0) |
| **male**| demographic information | int | whether a person identifies as male (1) or not male (0) |
| **female**| demographic information | int | whether a person identifies as female (1) or not female (0) |
| **black**| demographic information | int | whether a person identifies as black (1) or not black (0) |
| **asian**| demographic information | int | whether a person identifies as asian (1) or not asian (0) |
| **white**| demographic information | int | whether a person identifies as white (1) or not white (0) |
| **amind**| demographic information | int | whether a person identifies as amind (1) or not amind (0) |
| **hipac**| demographic information | int | whether a person identifies as hipac (1) or not hipac (0) |
| **hispanic**| demographic information | int | whether a person identifies as hispanic (1) or not hispanic (0) |
| **non_hispanic**| demographic information | int | whether a person identifies as non_hispanic (1) or not non_hispanic (0) |
| **agegte62**| demographic information | int | 	whether a person is over the age of 62 (1) or not over the age of 62 (0) |
| **agelt62E**| demographic information | int | whether a person is below the age of 62 (1) or not below the age of 62 (0) |
| **row_id**| ID | int | unique row indentifier |















  * Define the meaning of all engineered columns
* Evaluation data (2 pts.)
  * State the source of evaluation (or test) data
  *  * ** Home Mortgage Disclosure Act (HMDA) data in the class repository https://github.com/jphall663/GWU_rml/tree/master/assignments/data
  * State the number of rows in evaluation (or test) data
  *  * ** 19830
  * State any dierences in columns between training and evaluation (or test) data
  * * ** There is no difference in the columns between training and evaluation (or test) data
* Model details (2 pts.)
  * State the columns used as inputs in your group's best remediated model
  * State the columns used as targets in your group's best remediated model
  * State the type of your group's best remediated model
  * State the software used to implement your group's best remediated model
  * State the version of the modeling software for your group's best remediated model
  * State the hyperparameters or other settings of your group's best remediated model
* Quantitative analysis (3 pts.)
  * State the metrics used to evaluate your group's best remediated model
  * State the values of the metrics for training, validation, and evaluation (or test) data evaluation (or test) metrics come from the most recent class full evaluation results, link under Assignment 1.
  * Provide at least one plot or table from each weekly assignment for a total of at least six plots, that must include the global variable importance and partial dependence of your group's best remediated model.
  * Address other alternative models considered
* Ethical considerations (2 pts.)
  * Describe potential negative impacts of using your group's best remediated model:
   * Consider math or software problems
   * Consider real-world risks: who, what, when and how?
* Describe potential uncertainties relating to the impacts of using your group's best remediated model:
  * Consider math or software problems
  * Consider real-world risks: who, what, when and how?
* Describe any unexpected or results encountered during training

### Grammar and spelling (1 pt.)
* Correct grammar and punctuation ( 1/2 pt.)
* Correct spelling ( 1/2 pt.)

