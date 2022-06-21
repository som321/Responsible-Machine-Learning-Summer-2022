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
  * State how training data was divided into training and validation data
  * State the number of rows in training and validation data
  * Define the meaning of all training data columns

* Data dictionary: 

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**ID**| ID | int | unique row indentifier |
| **LIMIT_BAL** | input | float | amount of previously awarded credit |
| **SEX** | demographic information | int | 1 = male; 2 = female
| **RACE** | demographic information | int | 1 = hispanic; 2 = black; 3 = white; 4 = asian |
| **EDUCATION** | demographic information | int | 1 = graduate school; 2 = university; 3 = high school; 4 = others |
| **MARRIAGE** | demographic information | int | 1 = married; 2 = single; 3 = others |
| **AGE** | demographic information | int | age in years |
| **PAY_0, PAY_2 - PAY_6** | inputs | int | history of past payment; PAY_0 = the repayment status in September, 2005; PAY_2 = the repayment status in August, 2005; ...; PAY_6 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; ...; 8 = payment delay for eight months; 9 = payment delay for nine months and above |
| **BILL_AMT1 - BILL_AMT6** | inputs | float | amount of bill statement; BILL_AMNT1 = amount of bill statement in September, 2005; BILL_AMT2 = amount of bill statement in August, 2005; ...; BILL_AMT6 = amount of bill statement in April, 2005 |
| **PAY_AMT1 - PAY_AMT6** | inputs | float | amount of previous payment; PAY_AMT1 = amount paid in September, 2005; PAY_AMT2 = amount paid in August, 2005; ...; PAY_AMT6 = amount paid in April, 2005 |
| **DELINQ_NEXT**| target | int | whether a customer's next payment is delinquent (late), 1 = late; 0 = on-time |
  * Define the meaning of all engineered columns
* Evaluation data (2 pts.)
  * State the source of evaluation (or test) data
  * State the number of rows in evaluation (or test) data
  * State any dierences in columns between training and evaluation (or test) data
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

